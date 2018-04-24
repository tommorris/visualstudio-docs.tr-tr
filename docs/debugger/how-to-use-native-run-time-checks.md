---
title: 'Nasıl yapılır: yerel çalışma zamanı denetimlerini kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- c.runtime.errorchecks
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- /RTC compiler option [C++], /O compiler option
- run-time checks, native
- stack, pointer corruption
- stack pointers, corruption
- /O compiler option, /RTC option
- run-time errors, error checks
- O compiler option, /RTC option
- debugger, runtime errors
- variables [debugger], loss of data
- runtime_checks pragma
- variables [debugger], catching dependencies on uninitialized local variables
- run-time errors, debugging
- debugger, native run-time checks
- optimized build option
- RTC compiler option, /O compiler option
- native run-time checks
- run-time checks
- debugging arrays
- stack pointers
- arrays [Visual Studio], debugging
ms.assetid: dc7b2f1e-5ff6-42e0-89b3-dc9dead83ee1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 6d47b39086f0363bd0bc610ec047213142fb7fec
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-use-native-run-time-checks"></a>Nasıl Yapılır: Yerel Çalışma Zamanı Denetimlerini Kullanma
Visual C++'da yerel kullanabilirsiniz [runtime_checks](/cpp/preprocessor/runtime-checks) ortak çalışma zamanı hataları gibi yakalamak için:  
  
-   İşaretçi Bozulması yığın.  
  
-   Aşırı çalıştırmaları yerel dizi.  
  
-   Yığın bozulması.  
  
-   Başlatılmayan yerel değişkenlerde bağımlılıkları.  
  
-   Daha kısa bir değişkene atamada veri kaybı.  
  
 Kullanırsanız **eş yordamlarla/RTC** bir en iyi duruma getirilmiş ile (**/O**) oluşturmak, bir derleyici hatası sonuçları. Kullanırsanız, bir `runtime_checks` pragma pragma en iyi duruma getirilmiş bir yapı içinde hiçbir etkisi.  
  
 Çalışma zamanı denetimleri etkin olan bir program hata ayıklarken varsayılan program durdurmanız ve bir çalışma zamanı hatası oluştuğunda hata ayıklayıcıya gönder eylemdir. Çalışma zamanı onay için bu varsayılan davranışı değiştirebilirsiniz. Daha fazla bilgi için bkz: [yönetme özel durumları hata ayıklayıcısı ile](../debugger/managing-exceptions-with-the-debugger.md).  
  
 Hata ayıklama derlemesi yerel çalışma zamanı denetimlerini etkinleştirme ve nasıl yerel çalışma zamanı onay davranışını değiştirmek aşağıdaki yordamları açıklanmaktadır.  
  
 Bu bölümdeki diğer konular hakkında bilgi sağlar:  
  
-   [C çalışma zamanı kitaplığı ile çalışma zamanı özelleştirme denetler](../debugger/native-run-time-checks-customization.md)  
  
-   [C çalışma zamanı kitaplığını kullanmadan çalışma zamanı kullanarak denetler](../debugger/using-run-time-checks-without-the-c-run-time-library.md)  
  
### <a name="to-enable-native-run-time-checks-in-a-debug-build"></a>Hata ayıklama derlemesi yerel çalışma zamanı denetimlerini etkinleştirmek için  
  
-   Kullanım **eş yordamlarla/RTC** seçeneği ve C çalışma zamanı kitaplığı hata ayıklama sürümü ile bağlantı (/ örneğin MDd).  
  
### <a name="to-modify-native-run-time-check-behavior"></a>Yerel çalışma zamanı onay davranışını değiştirmek için  
  
-   Kullanım `runtime_checks` pragması.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio’da hata ayıklama](../debugger/index.md)  
 [Hata ayıklayıcı özelliği turu](../debugger/debugger-feature-tour.md)   
 [runtime_checks](/cpp/preprocessor/runtime-checks)   
 [Çalışma Zamanı Hata Denetimi](/cpp/c-runtime-library/run-time-error-checking)