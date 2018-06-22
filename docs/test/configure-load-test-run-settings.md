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
ms.openlocfilehash: 7aa35b072429caffc8f499f4f1bd570dcd32265b
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36282879"
---
# <a name="configure-load-test-run-settings"></a>Yük testi çalıştırma ayarlarını yapılandırma

*Çalışma ayarları* bir yük testi çalışma biçimini etkileyen özellikler kümesidir. Çalıştırma ayarlarını kategoriye göre düzenlenir **özellikleri** penceresi.

Yük testi çalıştırma ayarları, ancak tek Çalıştır etkin olabilir, birden fazla çalışma ayarı olabilir. Diğer çalışma ayarları sonraki test için kullanmak için alternatif bir ayar seçmek için hızlı bir şekilde çalışır sağlar.

Kullanarak bir yük testi oluşturduğunuzda, ilk çalıştırma ayarı oluşturulur **Yeni Yük Testi Sihirbazı**.

![Yük testi çalıştırma ayarları](../test/media/loadtestrunsettings.png)

## <a name="tasks"></a>Görevler

|Görevler|İlişkili Konular|
|-----------|-----------------------|
|**Yük testine daha fazla çalıştırma ayarları ekleyin:** çalıştırdığınızda oluşturduğunuz çalışma ayarı yanı sıra **Yeni Yük Testi Sihirbazı**, daha fazla çalıştırma ayarları, yük testi için test farklı altında çalıştırabilmeniz için ekleyebilirsiniz koşulları.|-   [Nasıl yapılır: bir yük testine ek çalışma ayarları ekleme](../test/how-to-add-additional-run-settings-to-a-load-test.md)|
|**Yük testi ile kullanmak istediğiniz ayarı etkin belirtin:** Yük Testi Düzenleyicisini kullanarak yük testinizle kullanmak istediğiniz çalışma ayarını seçebilirsiniz. Etkin çalışma ayarı "[etkin]" soneki ile tanımlanır.|-   [Nasıl yapılır: etkin çalışma ayarı için bir yük testi seçin](../test/how-to-select-the-active-run-setting-for-a-load-test.md)|
|**Düzenleme çalışması özelliklerini ayarlama:** çalıştırma düzenleyebilirsiniz ayarı özellikleri günlüğe kaydetme seçeneklerini gibi şeyler için (daha aşağıda, test, Isınma Süresi, en fazla hata sayısı uzunluğu belirleme bakın), örnekleme hızı, bağlantı bildirilen ayrıntıları Modeli (yalnızca Web performans testleri), sonuç depolama türü, doğrulama düzeyi ve SQL izleme. Çalışma ayarları yük testlerini amaçlarını yansıtmalıdır.|-   [Yük testi çalıştırma ayarları özellikleri](../test/load-test-run-settings-properties.md)<br />-   [Çalışma ayarı özelliklerini değiştirme](../test/load-test-run-settings-properties.md#LoadTestRunSettingsHowToChange)|
|**Yük testi çalışma ayarlarında test yineleme sayısını belirtin:** tüm Web performansı ve birim testleri tüm yük testleri senaryolarında yapılandırarak çalıştıran sayısı belirtebilirsiniz **Test Yinelemeleri** özellik.|-   [Nasıl yapılır: bir çalışma ayarında test yineleme sayısını belirtin](../test/how-to-specify-the-number-of-test-iterations-in-a-load-test.md)|
|**Bir yük testi çalışma ayarı için örnekleme hızını belirtin:** sık yapılandırarak Topla performans sayacı verilerini test yük nasıl belirtebilirsiniz **örnek hızı** özelliği.|-   [Nasıl yapılır: örnek hızı belirtme](../test/how-to-specify-the-sample-rate-for-a-load-test.md)|
|**Zamanlama Ayrıntıları Depolama seçeneği belirtin:** nasıl yapılandırarak kaydedilmiş yük testi ayrıntılarını istediğinizi belirtebilirsiniz **zamanlama ayrıntıları depolama** özelliği.|-   [Nasıl yapılır: zamanlama ayrıntıları depolama özelliğini belirtme](../test/how-to-specify-the-timing-details-storage-property-for-a-load-test.md)|
|**Test kaynak Bekletme dönemi belirtin:** testi hızlandırma > Düzeltme > döngüsü ayarlayarak belirli bir süre boyunca test kaynakları koruyarak yeniden sınayın **kaynaklar saklama süresi** özelliği.|-   [Yük testi hızlandırmak için gereken kaynakları korumak](/vsts/test/load-test/getting-started-with-performance-testing?view=vsts)|
|**Bağlam parametreleri kullanın:** bir dize Parametreleştirme için bağlam parametreleri kullanabilirsiniz. Örneğin, yük testlerini parametreli bir Web sunucusu kullanan bir Web performans testi içeriyorsa, farklı bir sunucuya eşlemeleri çalıştırma ayarları için bir bağlam parametresi ekleyebilirsiniz.|-   [Nasıl yapılır: bir çalışma ayarına bağlam parametreleri ekleme](../test/how-to-add-context-parameters-to-a-load-test-run-setting.md)|
|**Test günlüğü özelliklerini yapılandırma:** veri ayarlarını yükleme testi ile ilişkili günlük sıklıkta yazılan yapılandırabilirsiniz. Günlük birçok gigabayt haline çünkü büyük veya karmaşık yük testi çalıştırırken bu önemli olabilir.<br /><br /> Hata ayıklama ve uygulamanızı analiz etmenize yardımcı olmak yük testi başarısız olduğunda otomatik olarak kaydedilecek günlük dosyası da yapılandırabilirsiniz.|-   [Yük testi günlük ayarlarını değiştirme](../test/modify-load-test-logging-settings.md)|