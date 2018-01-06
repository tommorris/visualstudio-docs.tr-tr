---
title: IDebugEngineProgram2::WatchForThreadStep | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngineProgram2::WatchForThreadStep
helpviewer_keywords: IDebugEngineProgram2::WatchForThreadStep
ms.assetid: b70922a3-1313-409a-b3b7-50c7cd13e394
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3ca2e5eff223a22a3359f6fc4a391d2102f31b67
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugengineprogram2watchforthreadstep"></a>IDebugEngineProgram2::WatchForThreadStep
İzleyen yürütme için (veya yürütme için izlemeyi durdurur) verilen iş parçacığı üzerinde gerçekleşmesi için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT WatchForThreadStep(   
   IDebugProgram2* pOriginatingProgram,  
   DWORD           dwTid,  
   BOOL            fWatch,  
   DWORD           dwFrame  
);  
```  
  
```csharp  
int WatchForThreadStep(   
   IDebugProgram2 pOriginatingProgram,  
   uint           dwTid,  
   int            fWatch,  
   uint           dwFrame  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pOriginatingProgram`  
 [in] Bir [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) adım adım program temsil eden nesne.  
  
 `dwTid`  
 [in] İzlemek için iş parçacığı tanımlayıcısını belirtir.  
  
 `fWatch`  
 [in] Sıfır olmayan (`TRUE`) anlamına gelir başlangıç tarafından tanımlanan iş parçacığı üzerine yürütülmek izlerken `dwTid`; Aksi halde, sıfır (`FALSE`) anlamına gelir Durdur üzerinde yürütme için izlemeyi `dwTid`.  
  
 `dwFrame`  
 [in] Adım türünü denetleyen bir çerçeve dizinini belirtir. Bu olduğunda değeri sıfır (0) "adımla" adım türüdür ve iş parçacığı tarafından tanımlanan her program durması gerektiğini `dwTid` yürütür. Zaman `dwFrame` sıfır, değil "Atla" ve yalnızca iş parçacığı tarafından tanıtılan program durması gerektiğini adım türüdür `dwTid` dizinini, eşit ya da daha yığında çerçevesinde çalıştıran `dwFrame`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Ne zaman oturum hata ayıklama Yöneticisi'ni (SDM) adımları tarafından tanımlanan bir program `pOriginatingProgram` parametresi bildirir iliştirilmiş tüm diğer programları bu yöntemini çağırarak.  
  
 Bu yöntem, yalnızca aynı iş parçacığı atlama için geçerlidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)