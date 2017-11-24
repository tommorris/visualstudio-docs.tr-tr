---
title: "Devre dışı bırakmak veya paket önbellek taşıma | Microsoft Docs"
description: "Devre dışı bırakma, etkinleştirme veya paket önbelleği Visual Studio dağıtımları için taşıyın."
ms.date: 04/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cache
- nocache
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 2429993A-3F0E-41C5-9562-FEA6AE994440
author: heaths
ms.author: heaths
manager: ghogen
ms.openlocfilehash: f279a97cc91aa2ed3fa2efe5df21aaa90ddc5271
ms.sourcegitcommit: eb954434c34b4df6fd2264266381b23ce9e6204a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2017
---
# <a name="disable-or-move-the-package-cache"></a>Devre dışı bırakmak veya paket önbellek taşıma

Visual Studio veya ilgili diğer ürünleri Internet bağlantısı sahip olduğu durumlarda onarma gerekebileceği paket önbellek yüklü paketler için kaynak sağlar. Bazı sürücüler veya sistem ups, ancak değil isteyebilirsiniz bu paketleri geçici tutun.
Yükleyici, bunları kaydetmek veya disk alanı kurtarmak istiyorsanız, devre dışı bırakmak veya paket önbellek taşımak, gerektiğinde indirir.

## <a name="disable-the-package-cache"></a>Paket önbelleğini devre dışı

Yüklediğinizde, değiştirme veya Visual Studio veya diğer ürünleri yeni Yükleyici ile onarma önce Yükleyici ile başlayabilirsiniz `--nocache` geçiş için yükleyici.

```
"%ProgramFiles(x86)%\Microsoft Visual Studio\Installer\vs_installer.exe" --nocache
```

Herhangi bir ürün üzerinde yaptığınız herhangi bir işlem bu ürünün mevcut herhangi bir paket kaldırır ve onlar yüklendikten sonra herhangi bir paket kaydetme önlenmiş olur. Değiştirme veya Visual Studio onarın ve paketleri gereklidir, bunlar otomatik olarak yüklenir ve olması onlar yüklendikten sonra kaldırılır.

Önbelleğin yeniden etkinleştirmek istiyorsanız, geçirmek `--cache` yerine. Tüm paketler geri yüklemeniz gerekiyorsa ağ bağlantınızı kesmeden önce Visual Studio onarmanız gerekir böylece, yalnızca gerekli olan paketler önbelleğe alınır.

```
"%ProgramFiles(x86)%\Microsoft Visual Studio\Installer\vs_installer.exe" repair --passive --norestart --cache
```

Ayrıca ayarlayabilirsiniz `KeepDownloadedPayloads` [kayıt defteri ilke](set-defaults-for-enterprise-deployments.md) yüklediğinizde, değiştirme veya Visual Studio'yu onarmak önce önbelleği devre dışı bırakmak için.

## <a name="move-the-package-cache"></a>Paket önbellek taşıma

Yaygın olarak kullanılan sistem yapılandırması, bir SSD daha büyük bir sabit disk (veya daha fazla) yüklü Windows geliştirme için kaynak kodu, program ikili dosyaları ve daha fazlası gibi olmalıdır ' dir. Çevrimdışı Çalış istiyorsanız, bunun yerine paket önbellek taşıyabilirsiniz.

Ayarlarsanız şu anda yalnızca bunu yapabilirsiniz `CachePath` [kayıt defteri ilke](set-defaults-for-enterprise-deployments.md) yüklediğinizde, değiştirme veya Visual Studio'yu onarmak önce.

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:
* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun.
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio).  (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı).

## <a name="see-also"></a>Ayrıca bkz.

 * [Visual Studio yükleme](install-visual-studio.md)
 * [Kuruluş dağıtımları için Varsayılanlarını Ayarla](set-defaults-for-enterprise-deployments.md)
 * [Visual Studio'yu yüklemek için komut satırı parametreleri kullanma](use-command-line-parameters-to-install-visual-studio.md)
