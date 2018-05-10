---
title: Visual Studio 2017 yükleme konumlarını değiştirme
description: Farklı sürücülere indirme önbelleği, paylaşılan bileşenler, SDK'lar ve Araçlar konumunu değiştirerek sistem sürücüsündeki yükleme ayak izini azaltmak öğrenin.
ms.date: 05/07/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- change installation locations for Visual Studio
- move installation files to different drives
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0460e61fea7e617e497a46c55f8af811ba2e24fe
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="change-the-installation-locations-in-visual-studio-2017"></a>Visual Studio 2017 yükleme konumlarda değiştirme

**15.7 yeni**: indirme önbelleği, paylaşılan bileşenler, SDK'lar ve Araçlar farklı sürücülerine taşıyarak, sistem sürücüsünde yükleme kaplama alanı azaltabilir.

İşte nasıl.

1. Visual Studio yüklediğinizde seçin **yükleme seçenekleri** sekmesi.

  ![Visual Studio 2017 - yükleme konumunu değiştirmek](media/installation-options-by-location.png "yükleme konumunu değiştirme")

  > [!IMPORTANT]
  > Yüklemeyi duraklatmak ve daha sonra devam, Visual Studio kaldığı yerden seçer. Diğer bir deyişle, hangi yüklenmesini ve yüklü kalır ve önceki sayısını başlamıyor yükleme ilerleme durumunu uygular.

2. İçinde **Visual Studio** bölümünde, varsayılanı kabul edin. Bu, çekirdek ürüne yükler ve Visual Studio'nun bu sürümü için belirli dosyaları içerir.

 > [!IMPORTANT]
 > Sistem sürücünüz neden öneririz, sistem sürücüsünde varsayılan konumu kabul katı hal sürücüsü (SSD), burada ın ise: Visual Studio ile geliştirirken, okuma ve disk g/ç etkinliğini artıran çok sayıda dosya, için yazma.  Hızlı sürücünüzü yükü işlemek üzere seçmek en iyisidir.

2. İçinde **İndirebilmeleri** bölümünde, indirme önbellek tutun ve ardından işaretleyin veya işaretini kaldırın isteyip istemediğinize karar **Koru indirme önbellek** uygun şekilde. <br><br>Karşıdan yükleme önbelleğine tutma karar verirseniz konum yalnızca geçici olarak kullanılır. De, bu eylem etkilemez ya da önceki yüklemelerden dosyaları silin. (Tüm yükleme paketleri temizlemek için önceki yüklemelerini ayrı olarak değiştirmeniz gerekir.)

3. İçinde **İndirebilmeleri** bölümünde, yükleme dosyalarını ve bildirimleri depolamak istediğiniz sürücüyü belirtin. <br><br>Örneğin, **C++ ile masaüstü geliştirme** iş yükü, geçici olarak gerekli boyutudur 1.58 GB yüklemesi tamamlandıktan hemen sonra serbest sistem sürücüsünde.

 > [!NOTE]
 > Dosyaları geçici bir klasöre sistem sürücüsündeki ilk indirilir ve Visual Studio doğrular ve ardından bunları indirme önbellek klasörüne taşır daha sonra silinir. Başka bir sürücüye yükleme önbelleğiniz devam etmeyi seçerseniz, Visual Studio hala sistem sürücüsündeki yükleme önbelleğin boyutunu eşdeğer olan disk alanı gerekiyor.
 > [!IMPORTANT]
 > Konumun ilk yüklemenizle birlikte ayarlanır ve yükleyici UI daha sonra değiştirilemez. Bunun yerine, şunları yapmalısınız [komut satırı parametrelerini kullanmak](use-command-line-parameters-to-install-visual-studio.md) indirme önbellek taşımak için

4. İçinde **paylaşılan bileşenleri, SDK'lar ve Araçlar** bölümünde, yan yana Visual Studio yüklemeleri tarafından paylaşılan dosyaları depolamak istediğiniz sürücüyü belirtin. SDK'lar ve Visual Studio yükleyicisi olanak sağlayan araçlar da bu dizinde depolanan yükleme konumunu değiştirin.

 > [!NOTE]
 > Bazı araçlar vardır ve burada olabilir farklı kuralları vardır SDK'ları yüklenir. Başka bir konum seçin olsa bile bu araçlar ve SDK'ları hala sistem sürücünüzde yüklenir.)

## <a name="get-support"></a>Destek alma

Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) Yardım sayfası. De bize yükleme yardımcı olmak için başvurabilirsiniz [canlı sohbet](https://www.visualstudio.com/vs/support/#talktous) (yalnızca İngilizce); daha fazla bilgi için bkz: ["Bize başvurun" sayfasında Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:

* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunlarını izlemek ve yanıtlar bulmak [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/).
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio). (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.

* [Visual Studio 2017 yükleyin](install-visual-studio.md)
* [Visual Studio 2017 güncelleştir](update-visual-studio.md)
* [Visual Studio 2027 değiştirme](update-visual-studio.md)
* [Visual Studio 2017 kaldırma](uninstall-visual-studio.md)
