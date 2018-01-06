---
title: "Düşük bant genişliği veya güvenilmeyen ağ ortamları yükleyin | Microsoft Docs"
description: "Visual Studio yükleyicisi güvenilir olmayan bir ağ koşullarında nasıl çalıştığını açıklar ve yüklemeye başlamadan önce yükleme dosyalarını indirmek açıklanmaktadır."
ms.date: 08/30/2017
ms.reviewer: tims
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 44DB1998-68CD-4560-870A-EE5B993DCF6E
author: timsneath
ms.author: tglee
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 1d7b9b7084b91ace1f76d4d411f117df41cfd257
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="install-visual-studio-2017-on-low-bandwidth-or-unreliable-network-environments"></a>Visual Studio 2017 düşük bant genişliği veya güvenilmeyen ağ ortamları yükleyin

Visual Studio web yükleyicisi denemenizi öneririz&mdash;bulabilirsiniz, iyi bir deneyim çoğu durumlarda düşünüyoruz.

 > [!div class="button"]
 > [Visual Studio 2017 İndir](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocsOL)
<br/>

Ancak, Internet bağlantınız kullanılabilir veya güvenilir olmayan ise, çevrimdışı bir yüklemeyi tamamlamak için gereken dosyaları yerel önbelleği oluşturmak için komut satırını kullanabilirsiniz. İşte nasıl.

> [!NOTE]
> İnternet'ten dağıtımına bir ağ güvenlik duvarı istemci iş istasyonları, Visual Studio 2017 gerçekleştirmek istediği bkz Kurumsal yönetici olması durumunda bizim [Visual Studio 2017 bir ağ yüklemesi oluşturmak](../install/create-a-network-installation-of-visual-studio.md) ve [Çevrimdışı bir ortamda Visual Studio'yu yükleme için özel hususlar](../install/install-visual-studio-in-offline-environment.md) sayfaları.

## <a name="step-1---download-the-visual-studio-bootstrapper"></a>1. adım - Visual Studio önyükleyici indirin

Seçilen, Visual Studio sürümü için Visual Studio önyükleyici yükleyerek başlatın.

Kurulum&mdash;veya daha özel bir önyükleyici dosya&mdash;eşleşmiyor veya aşağıdakilerden birini benzer.

| Sürüm                    | Dosya                                                                    |
|----------------------------|-------------------------------------------------------------------------|
| Visual Studio Community    | [vs_community.exe](https://aka.ms/vs/15/release/vs_community.exe)       |
| Visual Studio Professional | [vs_professional.exe](https://aka.ms/vs/15/release/vs_professional.exe) |
| Visual Studio Enterprise   | [vs_enterprise.exe](https://aka.ms/vs/15/release/vs_enterprise.exe)     |

## <a name="step-2---create-a-local-install-cache"></a>2. adım - yerel yükleme önbelleği oluşturma

Bu adımı tamamlamak için bir Internet bağlantısına sahip olmalıdır. Yerel bir düzen oluşturmak için bir komut istemi açın ve aşağıdaki örnekleri komutlarından birini kullanın: Burada örneklerde, Visual Studio; Community sürümü kullandığınız varsayılmaktadır komut sürümünüz için uygun şekilde ayarlayın.

- .NET web ve .NET masaüstü geliştirme için çalıştırın:

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US```

- .NET Masaüstü ve Office geliştirme için çalıştırın:

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.Office --includeOptional --lang en-US```

- C++ Masaüstü geliştirmesi için çalıştırın:

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.NativeDesktop --includeRecommended --lang en-US```

- Tüm özelliklerle eksiksiz bir yerel düzen oluşturmak için (Bu bir uzun sürmesi&mdash;sahibiz _çok_ özelliklerinin!) çalıştırın:

   ```vs_community.exe --layout c:\vs2017layout --lang en-US```

İngilizce dışındaki bir dilde yüklemek istiyorsanız, değiştirme `en-US` bu sayfanın altındaki listeden bir ayara. Bu [bileşenleri ve iş yüklerini kullanılabilir listesini](workload-and-component-ids.md) yükleme önbelleğiniz gerekirse daha fazla özelleştirmek için.

> [!IMPORTANT]
> Tam bir Visual Studio 2017 düzeni en az 35 GB disk alanı gerektirir ve indirmek için biraz zaman alabilir. Bkz: [Visual Studio 2017 yüklemek için komut satırı parametreleri kullanın](use-command-line-parameters-to-install-visual-studio.md) yüklemek istediğiniz bileşenleri ile yalnızca bir düzen oluşturma hakkında bilgi için.

## <a name="step-3---install-visual-studio-from-the-local-cache"></a>3. adım - yerel önbellek Visual Studio yükleme

> [!TIP]
> Yerel Yükleme önbellekten çalıştırdığınızda, Kurulum bu dosyaların her biri yerel sürümlerini kullanır. Ancak önbellekte değil bileşenleri yüklemesi sırasında seçerseniz, size internet'ten indir girişimi.

İndirdiğiniz dosyaları yalnızca yüklediğinizden emin olun için Düzen önbelleği oluşturmak için kullanılan aynı komut satırı seçeneklerini kullanın. Örneğin, aşağıdaki komutla bir düzen önbellek oluşturduysanız:

```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US```

Yükleme çalıştırmak için bu komutu kullanın:

```c:\vs2017layout\vs_community.exe --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional```

  > [!NOTE]
  > İmza geçersiz olduğunu belirten bir hata alırsanız, güncelleştirilmiş sertifikaları yüklemeniz gerekir. Çevrimdışı önbelleğiniz Sertifikalar klasörünü açın. Her sertifika dosyasını çift tıklatın ve Sertifika Yöneticisi sihirbazda seçeneğini tıklatın. İçin bir parola istenirse, boş bırakın.

## <a name="list-of-language-locales"></a>Dil yerel ayarları listesi

| **Dil yerel ayar** | **Dil** |
| ----------------------- | --------------- |
| cs-CZ | Çekçe |
| de-DE | Almanca |
| en-US | İngilizce |
| es-ES | İspanyolca |
| fr-FR | Fransızca |
| it-IT | İtalyanca |
| ja-JP | Japonca |
| ko-KR | Kore Dili |
| PL-PL | Lehçe |
| pt-BR | Portekizce - Brezilya |
| RU-RU | Rusça |
| tr-TR | Türkçe |
| zh-CN | Çince - Basitleştirilmiş |
| zh-TW | Geleneksel Çince- |

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:
* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun.
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio).  (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.
* [Visual Studio'yu yükleyin](install-visual-studio.md)
* [Visual Studio Yönetici Kılavuzu](visual-studio-administrator-guide.md)
* [Komut satırı parametrelerini kullanarak Visual Studio'yu yükleme](use-command-line-parameters-to-install-visual-studio.md)
