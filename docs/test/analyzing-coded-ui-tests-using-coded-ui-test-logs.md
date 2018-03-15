---
title: "Kodlanmış UI testleri kodlanmış UI Test günlüklerini kullanarak analiz etme | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-devops-test
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 00c68941b86435f726833d60452518946832aadd
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="analyzing-coded-ui-tests-using-coded-ui-test-logs"></a>Kodlanmış UI Test Günlüklerini Kullanarak Kodlanmış UI Testlerini Çözümleme

Kodlanmış UI test günlüklerini filtresi ve kayıt kodlanmış UI testi hakkında önemli bilgiler çalıştırır.

 **Gereksinimler**

- Visual Studio Enterprise

## <a name="why-should-i-do-this"></a>Neden bunu yapmam gerekir?

Günlükleri sorunları hızla hata ayıklama için izin veren bir biçimde sunulur.

## <a name="how-do-i-do-this"></a>Bunu nasıl yaparım?

### <a name="step-1-enable-logging"></a>1. adım: günlük kaydını etkinleştir

Senaryonuza bağlı olarak, günlüğü etkinleştirmek için aşağıdaki yöntemlerden birini kullanın.

- .NET Framework sürüm 4 test projesinde mevcut herhangi bir App.config dosyası ile hedef

    - Açık **QTAgent32_40.exe.config** dosya.

         Varsayılan olarak, bu dosya bulunan  **\<drvie >: \Program dosyaları (x86) \Microsoft Visual Studio 12.0\Common7\IDE**.

         Değer EqtTraceLevel için istediğiniz günlük düzeyine değiştirin.

         Dosyayı kaydedin.

- Hedef .NET Framework sürüm 4.5 test projesinde mevcut herhangi bir App.config dosyası ile

    - Açık **QTAgent32.exe.config** dosya.

         Varsayılan olarak, bu dosya bulunan  **\<drvie >: \Program dosyaları (x86) \Microsoft Visual Studio 12.0\Common7\IDE**.

         İstediğiniz günlük düzeyine EqtTraceLevel değerini değiştirin.

         Dosyayı kaydedin.

- App.config dosyasını test projesinde var

    - Projede App.config dosyasını açın.

         Yapılandırma düğümü altında aşağıdaki kodu ekleyin:

         `<system.diagnostics>     <switches>       <add name="EqtTraceLevel" value="4" />     </switches>  </system.diagnostics>`

- Test kodundan günlük kaydını etkinleştir

    - <xref:Microsoft.VisualStudio.TestTools.UITesting.PlaybackSettings.LoggerOverrideState%2A> = HtmlLoggerState.AllActionSnapshot;

### <a name="step-2-run-your-coded-ui-test-and-view-the-log"></a>2. adım: kodlanmış UI testi çalıştırın ve günlüğünü görüntüleme

 Değişiklikler ile kodlanmış bir UI testi çalıştırdığınızda **QTAgent32.exe.config** dosya Gezgini Test sonuçlarında bağlantı bir çıktı görmeniz yerinde. Yalnızca test, aynı zamanda için izleme düzeyi için "ayrıntılı." olarak ayarlandığında başarılı testler başarısız olduğunda günlük dosyaları oluşturulur

1.  Üzerinde **TEST** menüsünde seçin **Windows** ve ardından **Test Gezgini**.

2.  Üzerinde **yapı** menüsünde seçin **yapı çözümü**.

3.  Test Gezgini içinde çalıştırmak, kendi kısayol menüsünü açın ve ardından istediğiniz kodlanmış UI testi seçin **seçin Testleri Çalıştır**.

     Otomatikleştirilmiş testleri çalıştırın ve geçirilen veya başarısız olmadığını gösterir.

    > [!TIP]
    >  Test Gezgini'nden görüntülemek için **Test menü**, işaret **Windows** ve ardından **Test Gezgini**.

4.  Seçin **çıkış** Test Gezgini sonuçlarında bağlantı.

     ![Test Gezgini çıkış bağlantıyı](../test/media/cuit_htmlactionlog1.png "CUIT_HTMLActionLog1")

     Bu eylem günlüğü için bir bağlantı içerir test için çıktı görüntüler.

     ![Sonuçları ve kodlanmış UI testi çıkış bağlantılarından](../test/media/cuit_htmlactionlog2.png "CUIT_HTMLActionLog2")

5.  Seçin *UITestActionLog.html* bağlantı.

     Günlük, web tarayıcınızda görüntülenir.

     ![Kodlanmış UI testi günlük dosyası](../test/media/cuit_htmlactionlog3.png "CUIT_HTMLActionLog3")

## <a name="q--a"></a>Soru - Yanıt

### <a name="q-what-happened-to-the-enablehtmllogger-key"></a>S: EnableHtmlLogger anahtarına ne?

Visual Studio'nun önceki sürümleri vardı iki daha fazla yapılandırma ayarı kodlanmış UI Test Html Günlükçü etkinleştirmek için:

```xml
<add key="EnableHtmlLogger" value="true"/>

<add key="EnableSnapshotInfo" value="true"/>
```

Bu ayarların her ikisi de Visual Studio 2012 itibaren kullanım dışı bırakıldı. EqtTraceLevel HtmlLogger etkinleştirmek için değiştirilmesi gereken tek bir ayardır.

## <a name="see-also"></a>Ayrıca bkz.

- [Kodunuzu Test Etmek için UI Otomasyonunu Kullanma](../test/use-ui-automation-to-test-your-code.md)
- [Nasıl yapılır: Microsoft Visual Studio'dan testler çalıştırma](http://msdn.microsoft.com/Library/1a1207a9-2a33-4a1e-a1e3-ddf0181b1046)
