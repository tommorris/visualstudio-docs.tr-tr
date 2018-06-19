---
title: IDebugEngineProgram2::WatchForExpressionEvaluationOnThread | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
helpviewer_keywords:
- IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
ms.assetid: 01d05e77-8cac-4d1b-b19f-25756767ed27
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a3f89502beeb1e8165450c7c07f3f55f83dd39e1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31112342"
---
# <a name="idebugengineprogram2watchforexpressionevaluationonthread"></a>IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
İfade değerlendirme programı durdurulmuş olsa bile verilen iş parçacığı üzerinde gerçekleşmesi için izin verir (veya izin vermez).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT WatchForExpressionEvaluationOnThread(   
   IDebugProgram2*       pOriginatingProgram,  
   DWORD                 dwTid,  
   DWORD                 dwEvalFlags,  
   IDebugEventCallback2* pExprCallback,  
   BOOL                  fWatch  
);  
```  
  
```csharp  
int WatchForExpressionEvaluationOnThread(   
   IDebugProgram2       pOriginatingProgram,  
   uint                  dwTid,  
   uint                  dwEvalFlags,  
   IDebugEventCallback2 pExprCallback,  
   int                   fWatch  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pOriginatingProgram`  
 [in] Bir [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) bir ifade değerlendirme programı temsil eden nesne.  
  
 `dwTid`  
 [in] İş parçacığı tanımlayıcısını belirtir.  
  
 `dwEvalFlags`  
 [in] Bayraklarını bileşimini [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) değerlendirme nasıl gerçekleştirilmesi belirtin numaralandırması.  
  
 `pExprCallback`  
 [in] Bir [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) ifadesi değerlendirmesi sırasında oluşan hata ayıklama olayları göndermek için kullanılan nesne.  
  
 `fWatch`  
 [in] Sıfır değilse (`TRUE`), tarafından tanımlanan iş parçacığı üzerinde ifade değerlendirme verir `dwTid`; Aksi halde, sıfır (`FALSE`) ifade değerlendirme o iş parçacığı üzerinde izin vermez.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Oturum hata ayıklama Yöneticisi'ni (SDM) tarafından tanımlanan bir program sorduğunda `pOriginatingProgram` parametresi, bir ifade değerlendirmek için bu yöntemi çağırmadan eklenen tüm diğer programları bildirir.  
  
 İfade değerlendirme bir programda neden olabilir. başka bir programda, İşlev değerlendirmesi veya değerlendirme herhangi biri nedeniyle çalıştırmak için kod `IDispatch` özellikleri. Bu nedenle, bu yöntem çalıştırmak ve iş parçacığı bu programda durdurulabilir olsa bile tamamlamak ifade değerlendirme sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)