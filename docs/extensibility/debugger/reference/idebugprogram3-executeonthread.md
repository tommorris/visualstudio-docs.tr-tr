---
title: IDebugProgram3::ExecuteOnThread | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugProgram3::ExecuteOnThread
ms.assetid: 2f5211e3-7a3f-47bf-9595-dfc8b4895d0d
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 649b16c1b57b2f66772c2117b776e6b79ad862be
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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