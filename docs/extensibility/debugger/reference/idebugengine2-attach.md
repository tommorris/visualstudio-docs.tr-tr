---
title: IDebugEngine2::Attach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngine2::Attach
helpviewer_keywords: IDebugEngine2::Attach
ms.assetid: 173dcbda-5019-4c5e-bca9-a071838b5739
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7c31e4c8367c1ceba5a4692438e8c1f1503f4f63
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugengine2attach"></a>IDebugEngine2::Attach
Hata ayıklama altyapısı (DE), bir program veya programlar ekler. Gizle çalışan işlem içi olarak SDM olduğunda (SDM) oturum hata ayıklama Yöneticisi tarafından çağrılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Attach(   
   IDebugProgram2**      pProgram,  
   IDebugProgramNode2**  rgpProgramNodes,  
   DWORD                 celtPrograms,  
   IDebugEventCallback2* pCallback,  
   ATTACH_REASON         dwReason  
);  
```  
  
```csharp  
int Attach(   
   IDebugProgram2[]     pProgram,  
   IDebugProgramNode2[] rgpProgramNodes,  
   uint                 celtPrograms,  
   IDebugEventCallback2 pCallback,  
   Enum_ATTACH_REASON   dwReason  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pProgram`  
 [in] Bir dizi [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) eklenmiş programları temsil eden nesne. Bu, bağlantı noktası programlardır.  
  
 `rgpProgramNodes`  
 [in] Bir dizi [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) program düğümler, her program için bir tane temsil eden nesne. Bu dizi program düğümler aynı programları olarak temsil eden `pProgram`. Program düğümleri DE eklemek için program bulabilmeniz verilir.  
  
 `celtPrograms`  
 [in] Programları ve/veya program düğümlerin sayısı `pProgram` ve `rgpProgramNodes` dizileri.  
  
 `pCallback`  
 [in] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) SDM için hata ayıklama olayları göndermek için kullanılan nesne.  
  
 `dwReason`  
 [in] Arasında bir değer [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md) bu programlar ekleme nedenini belirtir numaralandırması. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir program için aşağıdaki gibi ekleme üç nedeni vardır:  
  
-   `ATTACH_REASON_LAUNCH`Kullanıcı içerdiği işlemini başlattı çünkü DE programa ekleme gösterir.  
  
-   `ATTACH_REASON_USER`Kullanıcı bir program (veya program içeren işlem) eklemek için DE açıkça istedi gösterir.  
  
-   `ATTACH_REASON_AUTO`belirli bir işlemde diğer programları zaten hata ayıklama için DE belirli bir programa ekleme gösterir. Bu da adlandırılır otomatik ekleyin.  
  
 Bu yöntem çağrıldığında, sırayla bu olayları göndermek DE gerekir:  
  
1.  [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md) (Bu zaten hata ayıklama altyapısı belirli bir örneği için gönderildiğini değil)  
  
2.  [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)  
  
3.  [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)  
  
 Ekleme nedeni ise, ayrıca, `ATTACH_REASON_LAUNCH`, DE göndermek gereken [IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md) olay.  
  
 Bir kez DE alır [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) ayıklanacak, programın karşılık gelen bunu sorgulanan herhangi özel kullanıcı arabirimi için nesne.  
  
 Tarafından verilen dizide bir program düğümün yöntemleri çağrılmadan önce `pProgram` veya `rgpProgramNodes`, kimliğe bürünme, gerekirse etkinleştirilmelidir üzerinde `IDebugProgram2` program düğümünü temsil eden arabirim. Normalde, ancak, bu adım gerekli değildir. Daha fazla bilgi için bkz: [güvenlik sorunları](../../../extensibility/debugger/security-issues.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md)   
 [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)   
 [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)   
 [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)   
 [IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md)