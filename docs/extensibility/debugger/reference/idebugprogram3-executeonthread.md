---
title: IDebugProgram3::ExecuteOnThread | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugProgram3::ExecuteOnThread
ms.assetid: 2f5211e3-7a3f-47bf-9595-dfc8b4895d0d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8aff643014da16ed9644573a77cb8444836d713d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprogram3executeonthread"></a>IDebugProgram3::ExecuteOnThread
Hata ayıklayıcı programı yürütür. İş parçacığı, hangi iş parçacığı üzerinde kullanıcı programı yürütürken görüntüleyen hata ayıklayıcı bilgi vermek için döndürülür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT ExecuteOnThread(  
   [in] IDebugThread2* pThread)  
```  
  
```csharp  
int ExecuteOnThread(  
   IDebugThread2 pThread  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pThread`  
 [in] Bir [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir hata ayıklayıcısı durdurma sonra yürütmeye devam edebilir üç farklı yolu vardır:  
  
-   Yürütün: herhangi bir önceki adımı iptal edin ve kadar sonraki kesme ve benzeri çalıştırın.  
  
-   Adım: herhangi bir eski adımı iptal edin ve yeni adımı tamamlayana kadar çalıştırın.  
  
-   Devam Et: yeniden çalıştırın ve herhangi bir eski adımın etkin bırakın.  
  
 İş parçacığı geçirilen `ExecuteOnThread` , iptal etmek için adım karar verirken yararlıdır. Yürütme çalışan iş parçacığı, bilmiyorsanız tüm adımları iptal eder. İş parçacığı bilgiyle yalnızca etkin iş parçacığı üzerinde Adım iptal gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yürütme](../../../extensibility/debugger/reference/idebugprogram2-execute.md)   
 [IDebugProgram3](../../../extensibility/debugger/reference/idebugprogram3.md)