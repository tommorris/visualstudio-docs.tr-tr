---
title: Visual Studio'da kodlanmış UI Test günlüklerini kullanarak kodlanmış UI testlerini çözümleme
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: e2301e1c0cf2a90f701e74445d22810e67785999
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36233921"
---
# <a name="analyzing-coded-ui-tests-using-coded-ui-test-logs"></a>Kodlanmış UI test günlüklerini kodlanmış UI çözümleme testleri kullanma

Kodlanmış UI test günlüklerini filtresi ve kayıt kodlanmış UI testi hakkında önemli bilgiler çalıştırır. Günlükleri sorunları hızla hata ayıklama için izin veren bir biçimde sunulur.

## <a name="step-1-enable-logging"></a>1. adım: günlük kaydını etkinleştir

Senaryonuza bağlı olarak, günlüğü etkinleştirmek için aşağıdaki yöntemlerden birini kullanın:

- Hedef .NET Framework sürüm 4 hiçbir *App.config* test projesinde mevcut dosya:

   1. Açık *QTAgent32_40.exe.config* dosya. Varsayılan olarak, bu dosya bulunan *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE*.

   2. Değer EqtTraceLevel için istediğiniz günlük düzeyine değiştirin.

   3. Dosyayı kaydedin.

- Hedef .NET Framework sürüm 4.5 hiçbir *App.config* test projesinde mevcut dosya:

   1. Açık *QTAgent32.exe.config* dosya. Varsayılan olarak, bu dosya bulunan *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE*.

   2. İstediğiniz günlük düzeyine EqtTraceLevel değerini değiştirin.

   3. Dosyayı kaydedin.

- *App.config* dosyasıdır test projesinde var:

    - Açık *App.config* dosya projede ve yapılandırma düğümü altında aşağıdaki kodu ekleyin:

      ```xml
      <system.diagnostics>
        <switches>
          <add name="EqtTraceLevel" value="4" />
        </switches>
      </system.diagnostics>`
      ```

- Test kodundan günlük kaydını etkinleştir:

   <xref:Microsoft.VisualStudio.TestTools.UITesting.PlaybackSettings.LoggerOverrideState%2A> = HtmlLoggerState.AllActionSnapshot;

## <a name="step-2-run-your-coded-ui-test-and-view-the-log"></a>2. adım: kodlanmış UI testi çalıştırın ve günlüğünü görüntüleme

Değişiklikler ile kodlanmış bir UI testi çalıştırdığınızda *QTAgent32.exe.config* dosyayı yerinde bağlamak bir çıktı görmeniz **Test Gezgini** sonuçları. Yalnızca test, aynı zamanda için izleme düzeyi için "ayrıntılı." olarak ayarlandığında başarılı testler başarısız olduğunda günlük dosyaları oluşturulur

1.  Üzerinde **Test** menüsünde seçin **Windows** ve ardından **Test Gezgini**.

2.  Üzerinde **yapı** menüsünde seçin **yapı çözümü**.

3.  İçinde **Test Gezgini**, çalıştırmak, kendi kısayol menüsünü açın ve ardından istediğiniz kodlanmış UI testi seçin **seçin Testleri Çalıştır**.

     Otomatikleştirilmiş testleri çalıştırın ve geçirilen veya başarısız olmadığını gösterir.

    > [!TIP]
    > Görüntülemek için **Test Gezgini**, seçin **Test** > **Windows**ve ardından **Test Gezgini**.

4.  Seçin **çıkış** bağlamak **Test Gezgini** sonuçları.

     ![Çıktı bağlantıyı Test Gezgini](../test/media/cuit_htmlactionlog1.png)

     Bu eylem günlüğü için bir bağlantı içerir test için çıktı görüntüler.

     ![Sonuçları ve çıktı bağlantılarından kodlanmış UI testi](../test/media/cuit_htmlactionlog2.png)

5.  Seçin *UITestActionLog.html* bağlantı.

     Günlük, web tarayıcınızda görüntülenir.

     ![Kodlanmış UI testi günlük dosyası](../test/media/cuit_htmlactionlog3.png)

## <a name="see-also"></a>Ayrıca bkz.

- [UI otomasyonunu kullanarak kodunuzu test etme](../test/use-ui-automation-to-test-your-code.md)
- [Nasıl yapılır: Microsoft Visual Studio'dan testler çalıştırma](http://msdn.microsoft.com/Library/1a1207a9-2a33-4a1e-a1e3-ddf0181b1046)