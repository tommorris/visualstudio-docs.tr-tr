---
title: Visual Studio Yük testi çalıştırma ayarlarını yapılandırma
ms.date: 10/03/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, configuring run settings
ms.assetid: 0c86918b-cd63-4468-8f49-6d547a1276dc
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 70998285b5f1702be45cc1a5d31a976fa8c48ce8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="configure-load-test-run-settings"></a>Yük testi çalıştırma ayarlarını yapılandırma

*Çalışma ayarları* bir yük testi çalışma biçimini etkileyen özellikler kümesidir. Çalıştırma Ayarları Özellikleri penceresinde kategoriler halinde düzenlenir.

Yük testi çalıştırma ayarları, ancak tek Çalıştır etkin olabilir, birden fazla çalışma ayarı olabilir. Diğer çalışma ayarları sonraki test için kullanmak için alternatif bir ayar seçmek için hızlı bir şekilde çalışır sağlar.

Kullanarak bir yük testi oluşturduğunuzda, ilk çalıştırma ayarı oluşturulur **Yeni Yük Testi Sihirbazı**.

![Yük testi çalıştırma ayarları](../test/media/loadtestrunsettings.png)

## <a name="tasks"></a>Görevler

|Görevler|İlişkili Konular|
|-----------|-----------------------|
|**Yük testine daha fazla çalıştırma ayarları ekleyin:** Yeni Yük Testi Sihirbazı'nı çalıştırdığınızda, oluşturduğunuz çalışma ayarına ek olarak, daha fazla çalıştırma ayarlarını, yük testi farklı koşullar altında test çalıştırabilmeniz için ekleyebilirsiniz.|-   [Nasıl yapılır: bir yük testine ek çalışma ayarları ekleme](../test/how-to-add-additional-run-settings-to-a-load-test.md)|
|**Yük testi ile kullanmak istediğiniz ayarı etkin belirtin:** Yük Testi Düzenleyicisini kullanarak yük testinizle kullanmak istediğiniz çalışma ayarını seçebilirsiniz. Etkin çalışma ayarı "[etkin]" soneki ile tanımlanır.|-   [Nasıl yapılır: yük testi için etkin çalışma ayarını seçin](../test/how-to-select-the-active-run-setting-for-a-load-test.md)|
|**Düzenleme çalışması özelliklerini ayarlama:** çalıştırma düzenleyebilirsiniz ayarı özellikleri günlüğe kaydetme seçeneklerini gibi şeyler için (daha aşağıda, test, Isınma Süresi, en fazla hata sayısı uzunluğu belirleme bakın), örnekleme hızı, bağlantı bildirilen ayrıntıları Modeli (yalnızca Web performans testleri), sonuç depolama türü, doğrulama düzeyi ve SQL izleme. Çalışma ayarları yük testlerini amaçlarını yansıtmalıdır.|-   [Yük testi çalıştırma ayarları özellikleri](../test/load-test-run-settings-properties.md)<br />-   [Çalışma ayarı özelliklerini değiştirme](../test/load-test-run-settings-properties.md#LoadTestRunSettingsHowToChange)|
|**Yük testi çalışma ayarlarında test yineleme sayısını belirtin:** tüm Web performansı ve birim testleri tüm yük testleri senaryolarında yapılandırarak çalıştıran sayısı belirtebilirsiniz **Test Yinelemeleri** özellik.|-   [Nasıl yapılır: bir çalışma ayarında Test yineleme sayısını belirtin](../test/how-to-specify-the-number-of-test-iterations-in-a-load-test.md)|
|**Bir yük testi çalışma ayarı için örnekleme hızını belirtin:** sık yapılandırarak Topla performans sayacı verilerini test yük nasıl belirtebilirsiniz **örnek hızı** özelliği.|-   [Nasıl yapılır: örnek hızı belirtme](../test/how-to-specify-the-sample-rate-for-a-load-test.md)|
|**Zamanlama Ayrıntıları Depolama seçeneği belirtin:** nasıl yapılandırarak kaydedilmiş yük testi ayrıntılarını istediğinizi belirtebilirsiniz **zamanlama ayrıntıları depolama** özelliği.|-   [Nasıl yapılır: zamanlama ayrıntıları depolama özelliğini belirtme](../test/how-to-specify-the-timing-details-storage-property-for-a-load-test.md)|
|**Test kaynak Bekletme dönemi belirtin:** testi hızlandırma > Düzeltme > döngüsü ayarlayarak belirli bir süre boyunca test kaynakları koruyarak yeniden sınayın **kaynaklar saklama süresi** özelliği.|-   [Yük testi hızlandırmak için gereken kaynakları korumak](https://www.visualstudio.com/docs/test/performance-testing/getting-started/getting-started-with-performance-testing#retain-resources)|
|**Bağlam parametreleri kullanın:** bir dize Parametreleştirme için bağlam parametreleri kullanabilirsiniz. Örneğin, yük testlerini parametreli bir Web sunucusu kullanan bir Web performans testleri içeriyorsa, farklı bir sunucuya eşlemeleri çalıştırma ayarları için bir bağlam parametresi ekleyebilirsiniz.|-   [Nasıl yapılır: bir çalışma ayarına bağlam parametreleri ekleme](../test/how-to-add-context-parameters-to-a-load-test-run-setting.md)|
|**Test günlüğü özelliklerini yapılandırma:** ne sıklıkta veriler yazılır yapılandırabilirsiniz testi çalıştırma ayarlarını yükü ile ilişkili günlük için. Günlük birçok gigabayt haline çünkü büyük veya karmaşık yük testi çalıştırırken bu önemli olabilir.<br /><br /> Hata ayıklama ve uygulamanızı analiz etmenize yardımcı olmak yük testi başarısız olduğunda otomatik olarak kaydedilecek günlük dosyası da yapılandırabilirsiniz.|-   [Yük testi günlük oluşturma ayarlarını değiştirme](../test/modify-load-test-logging-settings.md)|