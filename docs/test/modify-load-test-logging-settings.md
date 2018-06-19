---
title: Yük testi Visual Studio'da günlük ayarları
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, logging, modifying
ms.assetid: 9649226a-857d-41ef-8ec7-047b6e498033
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: ffd20812ec37e324dc919ea5943cf30a5329321b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31968200"
---
# <a name="modify-load-test-logging-settings"></a>Yük testi günlük oluşturma ayarlarını değiştirme

Yük testi sonucu Tamamlanan yük testi için performans sayacı örneklerinin ve oturum açma düzenli olarak test altında bilgisayarlardan toplanan hata bilgileri içerir. Çok sayıda performans sayacı örneklerinin bir yük testi süresince toplanabilir. Toplanan performans veri miktarını uzunluğuna Çalıştır, örnekleme aralığı, test bilgisayar sayısını ve toplamak için sayacı sayısı bağlıdır. Büyük yük testi için toplanan performans veri miktarı kolayca birkaç gigabayt olabilir; Bu nedenle, ne sıklıkta değiştirmeyi düşünebilirsiniz verileri günlüğe kaydedilir. Bkz: [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md).

*Test denetleyicisi* test çalışırken tüm toplanan yük testi örnek verileri bir veritabanı günlüğünde biriktirir. Test tamamlandığında zamanlama ayrıntıları ve hata ayrıntıları gibi ek veriler veritabanına yüklenir.

|Görev|İlgili Konular|
|----------|-----------------------|
|**Yük testi sırasında günlükleri sık sık kaydetmeyi nasıl belirtin:** test günlüklerine yük testlerini çalıştırdığınızda kaydedilmesini istediğiniz sıklıkta belirtebilirsiniz.|-   [Nasıl yapılır: Test günlüklerinin hangi sıklıkla kaydedileceğini belirtin](../test/how-to-specify-how-frequently-test-logs-are-saved.md)|
|**Bir yük testi başarısız olursa günlükleri kaydetmek:** bir yük testi başarısız olduğunda test günlüğü kaydetmek isteyip istemediğinizi belirtebilirsiniz.|-   [Nasıl yapılır: Test başarısızlıklarının Test günlüklerine kaydedilip kaydedilmediği belirleme](../test/how-to-specify-if-test-failures-are-saved-to-test-logs.md)|
|**Günlük dosyası için maksimum dosya boyutunu ayarlayın:** günlük dosyası için kullanmak istediğiniz maksimum dosya boyutunu belirtmek için test denetleyicisi hizmeti ile ilişkili XML yapılandırma dosyasını düzenleyebilirsiniz.|[Nasıl yapılır: günlük dosyası en büyük boyutu belirtin](../test/how-to-specify-the-maximum-size-for-the-log-file.md)|

## <a name="related-tasks"></a>İlgili görevleri

İlgili özellik **zamanlama ayrıntıları** depolama. Daha fazla bilgi için bkz: [nasıl yapılır: yapılandırma toplama tam sanal kullanıcı etkinlik grafiğini etkinleştirmek için ayrıntıları](../test/how-to-configure-load-tests-to-collect-full-details.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi çalıştırma ayarlarını yapılandırma](../test/configure-load-test-run-settings.md)