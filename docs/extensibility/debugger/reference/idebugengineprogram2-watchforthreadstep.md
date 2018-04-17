---
title: IDebugEngineProgram2::WatchForThreadStep | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngineProgram2::WatchForThreadStep
helpviewer_keywords:
- IDebugEngineProgram2::WatchForThreadStep
ms.assetid: b70922a3-1313-409a-b3b7-50c7cd13e394
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3f7c897c4c5b8488766f72723f3e85909281abbf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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