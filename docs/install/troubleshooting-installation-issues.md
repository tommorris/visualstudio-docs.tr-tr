---
title: Yükleme sorunlarını giderme | Microsoft Docs
description: Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemesi veya yükseltmesi başarısız olursa, bu sayfayı yardımcı olabilir.
ms.date: 11/21/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 556EDD3F-E365-43EE-B3DD-03AA4353F75B
author: tglee
ms.author: tglee
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5d947bef4f27308c9c45169c813dc564ab2ab6e2
ms.sourcegitcommit: 064f8678f4a918e1dce60285090a9803d37dc34b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/30/2018
---
# <a name="troubleshooting-visual-studio-2017-installation-and-upgrade-issues"></a>Visual Studio 2017 yükleme ve yükseltme sorunlarını giderme

## <a name="symptoms"></a>Belirtiler
Veya Visual Studio 2017 güncelleştirmesini çalıştığınızda işlemi başarısız olur.

## <a name="workaround"></a>Geçici Çözüm
Bu sorunu çözmek için şu adımları izleyin.

### <a name="step-1---check-whether-this-problem-is-a-known-issue"></a>1. adım - bu sorunun bilinen bir sorun olup olmadığını denetleyin
Düzeltmeye çalışan Microsoft Visual Studio yükleyicisi bilinen bazı sorunlar vardır. Geçici bir çözüm için sorunu olup olmadığını görmek için kontrol [bizim sürüm notları bilinen sorunlar bölümüne](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes#known-issues).

### <a name="step-2---check-with-the-developer-community"></a>2. adım - denetimi ile Geliştirici topluluğu
Hata iletisiyle Search'te [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/spaces/8/index.html). Diğer topluluk üyeleri sorununuzu çözüme belgelenen.

### <a name="step-3---delete-the-visual-studio-installer-directory-to-fix-upgrade-problems"></a>3. adım - yükseltme sorunlarını düzeltmek için Visual Studio yükleyicisi dizini silin
Visual Studio yükleyicisi önyükleyici Visual Studio yükleyicisi kalan yükler en az bir hafif yürütülebilir ' dir. Visual Studio Installer dosyalarını silerek ve önyükleyici yeniden çalıştırma bazı güncelleştirme hataları düzeltebilir.

>[!NOTE]
Aşağıdaki eylemleri gerçekleştirerek, Visual Studio Installer dosyalarını yeniden yükler ve yükleme meta verileri sıfırlar.

1. Visual Studio Yükleyicisi’ni kapatın.
2. Visual Studio yükleyicisi dizini silin. Genellikle, dizindir `C:\Program Files (x86)\Microsoft Visual Studio\Installer`.
3. Visual Studio yükleyicisi önyükleyici çalıştırın. İzleyen bir dosya adına sahip yüklemeleri klasörünüzdeki önyükleyici bulabilirsiniz bir `vs_[Visual Studio edition]__*.exe` düzeni. Bu uygulama bulamazsanız, giderek önyükleyici indirebilirsiniz [Visual Studio indirmeleri](https://www.visualstudio.com/downloads/) sayfa ve tıklayarak **karşıdan** Visual Studio sürümünüz için. Yükleme meta verileriniz sıfırlamak için yürütülebilir dosyayı çalıştırmak.
4. Yükleme veya Visual Studio güncelleştirmeyi yeniden deneyin. Yükleyici başarısız olmaya devam ederse sonraki adıma geçin.

### <a name="step-4---report-a-problem"></a>4. adım - bir sorunu bildirin
Bozuk dosyaları, ilişkili olanlar gibi bazı durumlarda, bir olay temelinde aranması sorunlarla karşılaşabilirsiniz:

1. Kurulum günlüklerini toplayın. Bkz: [Visual Studio yükleme günlüklerini alma](#how-to-get-the-visual-studio-installation-logs) Ayrıntılar için.
2. Visual Studio Yükleyicisi'ni açın ve ardından **bir sorun bildirmek** Visual Studio geri bildirim Aracı'nı açın.
![Geri bildirim Aracı'nı açmak için geri bildirim sağlayın düğmesini sekmesi](media/report-a-problem.png)
3. Sorun raporu bir başlık verin ve ilgili ayrıntıları sağlayın. ' I tıklatın **sonraki** gitmek için **ekleri** bölümünde ve ardından oluşturulan günlük dosyasını ekleyin (genellikle, en dosyasıdır `%TEMP%\vslogs.zip`).
4. Tıklatın **sonraki** sorun raporu gözden geçirin ve ardından **gönderme**.

### <a name="step-5---run-installcleanupexe-to-remove-installation-files"></a>Adım 5 - Çalıştır InstallCleanup.exe yükleme dosyalarını kaldırmak için
Son çare olarak, şunları yapabilirsiniz [Visual Studio kaldırmak](remove-visual-studio.md) tüm yükleme dosyalarını ve ürün bilgileri kaldırmak için.

1. ' Ndaki yönergeleri izleyin [kaldırmak Visual Studio](remove-visual-studio.md).
2. Açıklanan önyükleyici yeniden [adım 3 - yükseltme sorunlarını düzeltmek için Visual Studio yükleyicisi dizin silme](#step-3---delete-the-visual-studio-installer-directory-to-fix-upgrade-problems).
3. Yükleme veya Visual Studio güncelleştirmeyi yeniden deneyin.

### <a name="step-6---contact-us-optional"></a>6. adım - (isteğe bağlı) bizimle iletişime geçin
Diğer adımların hiçbiri başarılı bir şekilde yüklemeye izin verirseniz, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

## <a name="how-to-troubleshoot-an-offline-installer"></a>Çevrimdışı bir yükleyici ile ilgili sorunları giderme
Burada, yardımcı olabilecek bir yerel düzeni yüklerken bilinen sorunlar ve bazı geçici çözümler tablosu verilmiştir.

| Sorun       | Öğe                   | Çözüm |
| ----------- | ---------------------- | -------- |
| Kullanıcılar, dosyalarına erişimi yoktur. | izinleri (ACL) | Böylece bunlar diğer kullanıcılara Okuma erişimi verin (ACL) izinleri ayarla emin olun *önce* çevrimdışı yükleme paylaşın. |
| Yeni iş yükleri, bileşenleri ve diller yüklenemedi.  | `--layout`  | Kısmi düzeninden yüklediğinizde ve iş yükleri, bileşenleri ya da yüklenemedi dilleri daha önce bu kısmi düzende seçin internet erişimi olduğundan emin olun. |

## <a name="how-to-get-the-visual-studio-installation-logs"></a>Visual Studio yükleme günlüklerini alma
Kurulum günlükleri, çoğu yükleme sorunlarını gidermek için gereklidir. Ne zaman gönderdiğiniz bir sorun kullanarak [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) Visual Studio Yükleyicisi'nde, bu günlükler otomatik olarak raporunuza eklenir.

Microsoft Support başvurursanız, bu kurulum günlüklerini kullanarak sağlamanız gerekebilir [Microsoft Visual Studio ve .NET Framework günlük toplama aracı](https://aka.ms/vscollect). Günlük koleksiyonu aracı Visual Studio .NET Framework, Windows SDK ve SQL Server dahil olmak üzere 2017, yüklü tüm bileşenleri Kurulum günlüklerini toplar. Ayrıca, bilgisayar bilgilerini, Windows Installer stok ve Visual Studio yükleyicisi, Windows Installer ve sistem geri yükleme için Windows olay günlüğü bilgileri de toplar.

Günlükleri toplamak için:

1. [Aracı indirmek](https://aka.ms/vscollect).
2. Bir yönetici komut istemi açın.
3. Çalıştırma `Collect.exe` aracı kaydettiğiniz dizininden.
4. Elde edilen Bul `vslogs.zip` dosyasını, `%TEMP%` dizin, örneğin, `C:\Users\YourName\AppData\Local\Temp\vslogs.zip`.

> [!NOTE]
> Aracı yüklemesi başarısız altında çalıştırıldığı aynı kullanıcı hesabı altında çalıştırılması gerekir. Farklı bir kullanıcı hesabından aracı çalıştırıyorsanız `–user:<name>` seçeneği altında başarısız bir yüklemeyi çalıştırıldığı kullanıcı hesabı belirtin. Çalıştırma `Collect.exe -?` ek seçenekleri ve kullanım bilgileri için bir yönetici komut isteminden.

## <a name="more-support-options"></a>Daha fazla destek seçenekleri

Diğer adımların hiçbiri başarılı bir şekilde yüklemeye izin verirseniz, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer seçenekler şunlardır:
* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun.
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio).  (Bu gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.
* [Visual Studio Yönetici Kılavuzu](visual-studio-administrator-guide.md)
* [Visual Studio örneklerini algılamaya ve yönetmeye yönelik araçlar](tools-for-managing-visual-studio-instances.md)
* [Remove Visual Studio 2017](remove-visual-studio.md)
