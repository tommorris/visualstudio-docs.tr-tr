---
title: 'Hata: işlevi hesaplama &#39;işlevi&#39; zaman aşımına uğradı ve güvenli bir şekilde durdurulmasına gerek | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.error.unsafe_func_eval_abort
ms.technology: vs-ide-debug
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1c230c27c8d1c8dcc01910fa598fb8a97b314845
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="error-evaluating-the-function-39function39-timed-out-and-needed-to-be-aborted-in-an-unsafe-way"></a>Hata: işlevi hesaplama &#39;işlevi&#39; zaman aşımına uğradı ve güvenli bir şekilde durdurulmasına gerekli

Tam ileti metni: 'function' işlevi değerlendirme zaman aşımına uğradı ve güvenli bir şekilde durdurulmasına gerekli. Bu hedef işlem bozulmuş olabilir. 

.NET nesneleri durumunu incelemek daha kolay hale getirmek için ek kod (genellikle özelliği alıcı yöntemlere ve ToString işlevleri) çalıştırmak için hata ayıklaması işlemi otomatik olarak hata ayıklayıcı zorlar. Çoğu tüm senaryolarda, bu işlevler hızlı bir şekilde tamamlamak ve çok daha kolay hata ayıklama yapın. Ancak, hata ayıklayıcı uygulama korumalı alanda çalıştırmaz. Sonuç olarak, bir özellik alıcısına veya askıda tabloya yerel işlev çağrıları ToString yöntemini kurtarılamayabilir uzun zaman aşımı için yol açabilir. Bu hata iletisiyle karşılaşırsanız, bu durum oluştu.
 
Bu sorun sık karşılaşılan bir nedeni bir özellik hata ayıklayıcı değerlendirirken, onu yalnızca yürütmek için Denetlenmekte olan iş parçacığı olanak sağlamasıdır. Bu nedenle özelliği içinde hata ayıklaması uygulamayı çalıştırmak için başka bir iş parçacığı üzerinde bekliyorsa ve .NET çalışma zamanı kesme mümkün olmayan bir şekilde bekleyen varsa, bu sorun gerçekleşir.
 
## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için
 
Bu sorun için üç olası çözümleri vardır.
 
### <a name="solution-1-prevent-the-debugger-from-calling-the-getter-property-or-tostring-method"></a>Çözüm #1: alıcı özellik veya ToString yöntemini çağırma hata ayıklayıcı engelle
 
Hata ayıklayıcı ulaşmaya çalıştık işlevin adını hata iletisi size bildirir. Bu işlev değiştirebilir, özellik alıcısı veya ToString yöntemini çağırma hata ayıklayıcı engelleyebilir. Aşağıdakilerden birini deneyin:
 
* Başka türde bir özellik alıcısı yanı sıra kodu yöntemini değiştirin veya ToString yöntemini ve sorun kaybolur.
    -veya-
* (ToString için) DebuggerDisplay özniteliği türüne tanımlayın ve ToString dışında bir şey değerlendirmek hata ayıklayıcı olabilir.
    -veya-
* (Özellik alıcısı için) PUT `[System.Diagnostics.DebuggerBrowsable(DebuggerBrowsableState.Never)]` özelliği özniteliği. Bu özellik API Uyumluluk nedenleriyle kalmak için gereken bir yöntem varsa yararlı olabilir, ancak gerçekten bir yöntemi olması gerekir.
 
### <a name="solution-2-have-the-target-code-ask-the-debugger-to-abort-the-evaluation"></a>Çözüm #2: Değerlendirme iptal etmek için hata ayıklayıcı isteyin hedef koda sahip
 
Hata ayıklayıcı ulaşmaya çalıştık işlevin adını hata iletisi size bildirir. Özellik alıcısı veya ToString yöntemini bazen düzgün çalışması başarısız burada sorunu, özellikle durumlarda kod kodu çalıştırmak için başka bir iş parçacığı gerekir, ardından uygulama işlevi çağırabilirsiniz `System.Diagnostics.Debugger.NotifyOfCrossThreadDependency` işlevi iptal etmek için hata ayıklayıcı istemek için Değerlendirme. Bu çözüm, bu işlevler açıkça değerlendirmek hala mümkündür, ancak NotifyOfCrossThreadDependency çağrısı yapıldığında çalışmayı durdurur varsayılan davranıştır.
 
### <a name="solution-3-disable-all-implicit-evaluation"></a>Çözüm #3: tüm örtük değerlendirme devre dışı bırak
 
Önceki çözümler sorunu düzeltin yok, Git *Araçları* > *seçenekleri*ve ayarı işaretini *hata ayıklama*  >   *Genel* > *özellik değerlendirmesi ve diğer dolaylı işlev çağrılarını etkinleştirme*. Bu, çoğu dolaylı İşlev değerlendirmesi devre dışı bırakır ve sorun gidermeniz gerekir.



  
