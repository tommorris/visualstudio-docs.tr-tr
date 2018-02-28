---
title: IDebugEngineProgram2::WatchForExpressionEvaluationOnThread | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
helpviewer_keywords:
- IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
ms.assetid: 01d05e77-8cac-4d1b-b19f-25756767ed27
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e40af42d1dd639b80ffac3e2f3cf9c4501782b45
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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