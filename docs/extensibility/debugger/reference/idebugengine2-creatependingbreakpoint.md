---
title: IDebugEngine2::CreatePendingBreakpoint | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngine2::CreatePendingBreakpoint
helpviewer_keywords:
- IDebugEngine2::CreatePendingBreakpoint
ms.assetid: 92e85b90-a931-48d9-89a7-a6edcb83ae5a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6a0813e077d8bdc2ba024dc932a6cb571b1b2fed
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31107783"
---
# <a name="idebugengine2creatependingbreakpoint"></a>IDebugEngine2::CreatePendingBreakpoint
Bekleyen bir kesme noktası hata ayıklama altyapısı (DE) oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT CreatePendingBreakpoint(   
   IDebugBreakpointRequest2*  pBPRequest,  
   IDebugPendingBreakpoint2** ppPendingBP  
);  
```  
  
```csharp  
int CreatePendingBreakpoint(   
   IDebugBreakpointRequest2     pBPRequest,  
   out IDebugPendingBreakpoint2 ppPendingBP  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pBPRequest`  
 [in] Bir [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md) oluşturmak için bekleyen kesme noktası tanımlayan nesne.  
  
 `ppPendingBP`  
 [out] Döndürür bir [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) bekleyen kesme noktası temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Genellikle döndürür `E_FAIL` varsa `pBPRequest` parametresi IF DE tarafından desteklenen herhangi bir dil eşleşmiyor `pBPRequest` parametresi geçersiz veya eksik.  
  
## <a name="remarks"></a>Açıklamalar  
 Bekleyen bir kesme noktası aslında bir kesme noktası kodu bağlamak için gerekli tüm bilgileri bir koleksiyonudur. Bu yöntemin döndürdüğü bekleyen kesme noktası kadar kod bağlı [bağlamak](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) yöntemi çağrılır.  
  
 Her kesme noktası bekleyen kullanıcı kümeleri oturum hata ayıklama Yöneticisi'ni (SDM) her ekli DE bu yöntemi çağırır. Kesme noktası o Gizle çalışan programlar için geçerli olduğunu doğrulamak için DE en fazla olur.  
  
 Kullanıcı bir kod satırında bir kesme noktası ayarlar, bu koduna karşılık gelen belgesinde en yakın satır kesme bağlamak DE ücretsizdir. Bu kullanıcının çok satırlı deyiminin ilk satırında bir kesme noktası belirleyerek, ancak (burada tüm kod hata ayıklama bilgilerini öznitelik) son satırında bağlamak mümkün kılar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte basit bir için bu yöntemi uygulaması gösterilmektedir `CProgram` nesnesi. DE'ın uyarlamasını `IDebugEngine2::CreatePendingBreakpoint` sonra bu uygulaması her bir program yönteminde, tüm çağrıları iletmek.  
  
```  
HRESULT CProgram::CreatePendingBreakpoint(IDebugBreakpointRequest2* pBPRequest, IDebugPendingBreakpoint2** ppPendingBP)     
{    
  
   // Create and initialize the CPendingBreakpoint object.  
   CComObject<CPendingBreakpoint> *pPending;    
   CComObject<CPendingBreakpoint>::CreateInstance(&pPending);    
   pPending->Initialize(pBPRequest, m_pInterp, m_pCallback, m_pEngine);    
   return pPending->QueryInterface(ppPendingBP);    
}    
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [Bağlama](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)   
 [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)   
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)