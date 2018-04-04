---
title: Visual Studio yükleme için komut satırı parametresi örnekleri | Microsoft Docs
ms.custom: ''
ms.date: 05/06/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 837F31AA-F121-46e9-9996-F8BCE768E579
author: tglee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ddb6afe950c2563f7ded04efbdd2b441a8c72e30
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/03/2018
---
# <a name="command-line-parameter-examples-for-visual-studio-2017-installation"></a>Visual Studio 2017 yükleme için komut satırı parametresi örnekleri
Göstermek için nasıl [Visual Studio'yu yüklemek için komut satırı parametrelerini kullanmak](use-command-line-parameters-to-install-visual-studio.md), gereksinimlerinize göre özelleştirebileceğiniz bazı örnekleri aşağıda bulabilirsiniz.

Her örnekte `vs_enterprise.exe`, `vs_professional.exe` ve `vs_community.exe` indirme işlemi başlatan bir küçük (yaklaşık 1 MB) dosyadır Visual Studio önyükleyici ilgili sürümünü temsil eder. Farklı bir sürümünü kullanıyorsanız, uygun önyükleyici adını değiştirin.

> [!NOTE]
> Tüm komutlar, yönetimsel ayrıcalık ve işlemin yükseltilmiş isteminden başlamamışsa istemi görüntülenen bir kullanıcı hesabı denetimi gerektirir.

> [!NOTE]
>  Kullanabileceğiniz `^` birden fazla satır tek bir komut birleştirmek için komut satırının sonunda karakter. Alternatif olarak, yalnızca bu satırları birlikte tek bir satır üzerine yerleştirebilirsiniz. PowerShell'de backtick eşdeğerdir (`` ` ``) karakter.

* Visual Studio, en az bir örneğini hiçbir etkileşimli istemleri ancak görüntülenen ilerleme yükleyin:
```
vs_enterprise.exe --installPath C:\minVS ^
   --add Microsoft.VisualStudio.Workload.CoreEditor ^
   --passive --norestart
```

* Hiçbir etkileşimli istemleri ancak görüntülenen ilerleme komut satırını kullanarak bir Visual Studio örneği güncelleştirin:
```
vs_enterprise.exe --update --quiet --wait
vs_enterprise.exe update --wait --passive --norestart --installPath "C:\installPathVS"
```

> [!NOTE]
> Her iki komutları gereklidir. İlk komut, Visual Studio yükleyicisi güncelleştirir. İkinci komut, Visual Studio örneğini güncelleştirir. Bir kullanıcı hesabı denetimi iletişim önlemek için komut istemini yönetici olarak çalıştırın.

* Visual Studio'nun Masaüstü örneği sessiz bir şekilde, yalnızca ürün yüklendiğinde döndürme Fransızca Dil Paketi ile yükleyin.
```
vs_enterprise.exe --installPath C:\desktopVS ^
   --addProductLang fr-FR ^
   --add Microsoft.VisualStudio.Workload.ManagedDesktop ^
   --includeRecommended --quiet --wait
```

> [!NOTE]
>  `--wait` Parametresi, bir toplu iş dosyası kullanmak için tasarlanmıştır. Yükleme tamamlanana kadar bir toplu iş dosyasında sonraki komutu yürütme devam etmez. `%ERRORLEVEL%` Açıklandığı gibi ortam değişkeni komutu döndürülen değerini içerecek [Visual Studio'yu yüklemek için komut satırı parametrelerini kullanmak](use-command-line-parameters-to-install-visual-studio.md) sayfası.

* Visual Studio çekirdek Düzenleyicisi'ni (en az Visual Studio yapılandırması) indirin. Yalnızca İngilizce dil paketi şunları içerir:

```cmd
vs_community.exe --layout C:\VS2017
   --lang en-US ^
   --add Microsoft.VisualStudio.Workload.CoreEditor
```

* Önerilen tüm bileşenleri ve GitHub uzantısı ile birlikte .NET web iş yüklerini ve .NET Masaüstü indirin. Yalnızca İngilizce dil paketi şunları içerir:
```
vs_community.exe --layout C:\VS2017 ^
   --lang en-US ^
   --add Microsoft.VisualStudio.Workload.NetWeb ^
   --add Microsoft.VisualStudio.Workload.ManagedDesktop ^
   --add Component.GitHub.VisualStudio ^
   --includeRecommended
```

* Tüm iş yükleri ve Visual Studio 2017 Enterprise Edition'da kullanılabilir bileşenleri etkileşimli bir yükleme başlatın:
```
vs_enterprise.exe --all --includeRecommended --includeOptional
```

* Visual Studio 2017 Professional ikinci, adlandırılmış bir örneği zaten Node.js geliştirme desteği yüklü Visual Studio 2017 Community edition ile bir makineye yükleyin:
```
vs_professional.exe --installPath C:\VSforNode ^
   --add Microsoft.VisualStudio.Workload.Node --includeRecommended --nickname VSforNode
```

* Profil oluşturma araçları bileşeni varsayılan olarak yüklenen Visual Studio örnekten kaldırın:
```
vs_enterprise.exe modify ^
   --installPath "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise" ^
   --remove Microsoft.VisualStudio.Component.DiagnosticTools ^
   --passive
```

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:
* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun.
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio).  (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.

 * [Visual Studio Yönetici Kılavuzu](visual-studio-administrator-guide.md)
 * [Komut satırı parametrelerini kullanarak Visual Studio'yu yükleme](use-command-line-parameters-to-install-visual-studio.md)
 * [Visual Studio 2017 çevrimdışı yüklemesini oluşturma](create-an-offline-installation-of-visual-studio.md)
