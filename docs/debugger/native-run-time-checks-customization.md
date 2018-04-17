---
title: Yerel çalışma zamanı denetler özelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.crt
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- runtime_checks pragma
- debugger, native run-time checks
- /RTC compiler option [C++], native run-time checks
- customizing CRT error checking
- native run-time checks, customizing
ms.assetid: 76a365fe-6439-49db-8603-34058b78e5a8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 2c0318a5a711fd99338fb3d4e812cb3b07c449fc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="native-run-time-checks-customization"></a>Yerel Çalışma Zamanı Denetimlerini Özelleştirme
İle derleme zaman **eş yordamlarla/RTC** (çalışma zamanı denetimleri) veya `runtime_checks` pragma, C çalışma zamanı kitaplığı, yerel çalışma zamanı denetimleri sağlar. Bazı durumlarda, çalışma zamanı denetimi özelleştirmek isteyebilirsiniz:  
  
-   Bir dosya veya varsayılan dışındaki hedef çalışma zamanı onay iletileri yönlendirmek için.  
  
-   Hedef çalışma zamanı için bir çıktı belirtmek için üçüncü taraf hata ayıklayıcı altında iletilerini denetleyin.  
  
-   C çalışma zamanı kitaplığı yayın sürümü ile derlenen bir programdan rapor çalıştırma onay iletileri için. Kitaplık yayın sürümleri kullanmayın `_CrtDbgReportW` rapor çalışma zamanı hataları. Bunun yerine, görüntüledikleri bir **Assert** her bir çalışma zamanı hata iletişim kutusu.  
  
 Çalışma zamanı hata denetimi özelleştirmek için şunları yapabilirsiniz:  
  
-   Bir çalışma zamanı hata raporlama işlevi yazma. Daha fazla bilgi için bkz: [nasıl yapılır: bir çalışma zamanı hata raporlama işlevi yazma](../debugger/how-to-write-a-run-time-error-reporting-function.md).  
  
-   Hata iletisi hedef özelleştirin.  
  
-   Sorgu çalıştırma hakkında bilgi için hataları denetleyin.  
  
## <a name="customize-the-error-message-destination"></a>Hata iletisi hedef özelleştirme  
 Kullanırsanız `_CrtDbgReportW` hatalarını raporlamak için kullanabileceğiniz `_CrtSetReportMode` hata iletileri hedefini belirlemek için.  
  
 Özel raporlama işlevi kullanıyorsanız `_RTC_SetErrorType` bir hata raporu türü ile ilişkilendirmek için.  
  
## <a name="query-for-information-about-run-time-checks"></a>Çalışma zamanı denetimleri hakkında bilgi için sorgu  
 `_RTC_NumErrors` çalışma zamanı hata denetimleri tarafından algılanan hata türlerinin sayısını döndürür. Her hata kısa bir açıklamasını almak için 0'dan dönüş değerini döngüye girer `_RTC_NumErrors`, yineleme değerine geçirme `_RTC_GetErrDesc` her döngüde. Daha fazla bilgi için bkz: [_RTC_NumErrors](/cpp/c-runtime-library/reference/rtc-numerrors) ve [_RTC_GetErrDesc](/cpp/c-runtime-library/reference/rtc-geterrdesc).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: yerel çalışma zamanı denetimlerini kullanma](../debugger/how-to-use-native-run-time-checks.md)   
 [runtime_checks](/cpp/preprocessor/runtime-checks)   
 [_CrtDbgReport, _CrtDbgReportW](/cpp/c-runtime-library/reference/crtdbgreport-crtdbgreportw)