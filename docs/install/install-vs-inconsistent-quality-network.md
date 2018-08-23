---
title: Düşük bant genişliği veya güvenilir olmayan ağ ortamlarında yükleme | Microsoft Docs
description: Visual Studio yükleyicisi ağınızın güvenilir değil veya düşük bant genişliğine sahip olan ve dosyaları yükleme komut satırında kullanmak için nasıl kullanılacağını öğrenin.
ms.date: 01/17/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- installing Visual Studio
- no internet connection
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4517984b5da3c6d8e650ec4148c085c2a42aa392
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634426"
---
# <a name="install-visual-studio-2017-on-low-bandwidth-or-unreliable-network-environments"></a>Visual Studio 2017, düşük bant genişliği veya güvenilir olmayan ağ ortamlarında yükleme

Visual Studio web yükleyicisini denemenizi öneririz&mdash;bulabilirsiniz, iyi bir deneyim için çoğu durumda düşünüyoruz.

 > [!div class="button"]
 > [Visual Studio 2017 İndir](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)
<br/>

Bununla birlikte, internet bağlantınız kullanılamıyor veya güvenilir değilse, bir çevrimdışı yüklemeyi tamamlamak için gereken dosyaları yerel önbelleği oluşturmak için komut satırını kullanabilirsiniz. İşte nasıl.

> [!NOTE]
> Visual Studio 2017'in bir dağıtım için bir ağ güvenlik duvarı istemci iş istasyonları, internet'ten gerçekleştirmek isterse bkz Kurumsal Yönetici olduğunuz bizim [Visual Studio 2017'in bir ağ yüklemesini oluşturma](../install/create-a-network-installation-of-visual-studio.md) ve [Visual Studio'yu çevrimdışı yükleme için gerekli sertifikaları yükleme](../install/install-certificates-for-visual-studio-offline.md) sayfaları.

## <a name="step-1---download-the-visual-studio-bootstrapper"></a>1. adım - Visual Studio önyükleyicisini yükleyin

Seçtiğiniz Visual Studio sürümünüz için Visual Studio önyükleyicisi indirerek başlayın.

Kurulum dosyanızı&mdash;ya da daha belirgin olması için bir önyükleyici dosya&mdash;ile eşleşir veya şunlardan birini benzer.

| Sürüm                    | Dosya                                                                    |
|----------------------------|-------------------------------------------------------------------------|
| Visual Studio Community    | [vs_community.exe](https://aka.ms/vs/15/release/vs_community.exe)       |
| Visual Studio Professional | [vs_professional.exe](https://aka.ms/vs/15/release/vs_professional.exe) |
| Visual Studio Enterprise   | [vs_enterprise.exe](https://aka.ms/vs/15/release/vs_enterprise.exe)     |

## <a name="step-2---create-a-local-install-cache"></a>2. adım - yerel yükleme önbelleği oluşturma

Bu adımı tamamlamak için bir internet bağlantısı olması gerekir. Yerel bir düzen oluşturmak için bir komut istemi açın ve aşağıdaki örneklerde komutlardan birini kullanın. Buradaki örnekler Visual Studio Community sürümünü kullandığınız varsayılır; komut sürümünüz için uygun şekilde ayarlayın.

- .NET web ve .NET masaüstü geliştirme için çalıştırın:

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US```

- .NET Masaüstü ve Office geliştirme için çalıştırın:

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.Office --includeOptional --lang en-US```

- C++ Masaüstü geliştirmesi için çalıştırın:

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.NativeDesktop --includeRecommended --lang en-US```

- Tüm özellikleri ile tam olarak yerel bir düzen oluşturmak için (Bu uzun sürer&mdash;sahibiz _çok_ özelliklerinin!) çalıştırın:

   ```vs_community.exe --layout c:\vs2017layout --lang en-US```

İngilizce dışında bir dil yüklemek isterseniz değiştirme `en-US` bu sayfanın alt kısmındaki listesinden bir yerel ayar için. Bunu kullanın [kullanılabilir iş yükleri ve bileşenlerin listesini](workload-and-component-ids.md) yükleme önbelleğiniz gerektiği şekilde daha fazla özelleştirmek için.

> [!IMPORTANT]
> Visual Studio 2017 Düzen tamamlanamadı, en az 35 GB disk alanı gerektirir ve indirmek için biraz zaman alabilir. Bkz: [Visual Studio 2017'yi yüklemek için komut satırı parametreleri kullanmak](use-command-line-parameters-to-install-visual-studio.md) yüklemek istediğiniz bileşenleri ile yalnızca bir düzen oluşturma konusunda bilgi için.

## <a name="step-3---install-visual-studio-from-the-local-cache"></a>Adım 3 - yerel önbellekten Visual Studio yükleme

> [!TIP]
> Yerel Yükleme önbellekten çalıştırdığınızda, Kurulum bu dosyaların her biri yerel sürümünü kullanır. Ancak önbellekte olmayan bileşenleri yüklemesi sırasında seçerseniz, bunları internet'ten indir denediğimiz.

Yalnızca indirdiğiniz dosyaları yüklemek emin olmak için Düzen önbelleği oluşturmak için kullanılan aynı komut satırı seçeneklerini kullanın. Örneğin, aşağıdaki komutla bir düzen önbelleği oluşturduysanız:

```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US```

Yüklemesini çalıştırmak için bu komutu kullanın:

```c:\vs2017layout\vs_community.exe --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional```

> [!NOTE]
> İmza geçersiz olduğunu belirten bir hata alırsanız, güncelleştirilmiş bir sertifika yüklemeniz gerekir. Çevrimdışı önbelleğinize sertifikaları klasörünü açın. Her sertifika dosyasını çift tıklayın ve Sertifika Yöneticisi sihirbazda'ye tıklayın. İçin bir parola istenirse, boş bırakın.

## <a name="list-of-language-locales"></a>Dil yerel ayarlar listesi

| **Dil yerel ayar** | **Dil** |
| ----------------------- | --------------- |
| cs-CZ | Çekçe |
| de-DE | Almanca |
| en-US | İngilizce |
| es-ES | İspanyolca |
| fr-FR | Fransızca |
| İt-IT | İtalyanca |
| ja-JP | Japonca |
| ko-KR | Kore Dili |
| pl-PL | Lehçe |
| pt-BR | Portekizce - Brezilya |
| ru-RU | Rusça |
| tr-TR | Türkçe |
| zh-CN | Çince - Basitleştirilmiş |
| zh-TW | Çince - Geleneksel |

## <a name="get-support"></a>Destek alın

Bazı durumlarda sorunlar. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme, Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı (yalnızca İngilizce) yükleme Yardımı için canlı sohbet göre bize başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfasını](https://visualstudio.microsoft.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:

* Ürün sorunları bize bildirebilirsiniz [sorun bildir](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem de Visual Studio yükleyicisi Visual Studio IDE içinde görünen bir araç.
* Üzerinde bir ürün önerisi bizimle paylaşabilirsiniz [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunları izlemek ve sorularınıza cevap bulun [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/).
* ABD ve diğer Visual Studio geliştiricilere ile görüşebilirsiniz [Gitter Topluluğu'nda Visual Studio konuşma](https://gitter.im/Microsoft/VisualStudio). (Bu seçenek gerektirir bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.

* [Visual Studio'yu yükleyin](install-visual-studio.md)
* [Visual Studio Yönetici Kılavuzu](visual-studio-administrator-guide.md)
* [Komut satırı parametrelerini kullanarak Visual Studio'yu yükleme](use-command-line-parameters-to-install-visual-studio.md)
* [Visual Studio 2017 iş yükü ve Bileşen kimlikleri](workload-and-component-ids.md)
