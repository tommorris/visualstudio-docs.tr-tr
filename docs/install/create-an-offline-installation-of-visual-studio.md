---
title: Visual Studio çevrimdışı yüklemesini oluşturma
description: Visual Studio çevrimdışı nasıl yükleneceğini öğrenin.
ms.custom: ''
ms.date: 01/17/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- offline installation [Visual Studio]
- offline install [Visual Studio]
- layout [Visual Studio]
ms.assetid: f8625d5e-f6ea-4db0-83c0-619b77fab3cf
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1ef917b4e8aa5cde8d95c036523bb525799cc19e
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36279969"
---
# <a name="create-an-offline-installation-of-visual-studio-2017"></a>Visual Studio 2017 çevrimdışı yüklemesini oluşturma

Biz de çok çeşitli ağ ve makine koşullar içinde çalışmak için Visual Studio 2017 yükleyici tasarlanmıştır.

- Yeni iş yükü tabanlı modeli gerekir indirmek şimdiye kadar küçüktür, Visual Studio'nun önceki sürümleri ile anlamına gelir: en az 300 MB olarak en küçük yükleme;
- Bir genel "ISO" veya zip dosyası ile karşılaştırıldığında, biz yalnızca makine için gereksinim duyduğunuz paketlerini yükleyin. Örneğin, bunları gerekmiyorsa, biz 64-bit dosyalar yüklemeyin;
- Yükleme işlemi sırasında şu üç farklı indirme teknolojileri (WebClient, BITS ve WinINet) yazılımıyla; virüsten koruma ve proxy girişim en aza indirmek için deneyin
- Biz bunları sizin için bir yerel sunucudan alabilmek için Visual Studio'yu yüklemek için gereken dosyaları genel teslim ağ üzerinde dağıtılır.

Denemenizi öneririz [Visual Studio web yükleyicisi](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)&mdash;bulabilirsiniz, iyi bir deneyim düşünüyoruz.

 > [!div class="button"]
 > [Visual Studio 2017 İndir](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

Internet bağlantınız kullanılabilir veya güvenilir olmayan, bkz: olduğundan çevrimdışı yüklemek istiyorsanız, [yükleme Visual Studio 2017 düşük bant genişliği veya güvenilmeyen ağ ortamları](../install/install-vs-inconsistent-quality-network.md). Çevrimdışı bir yüklemeyi tamamlamak için gereken dosyaları yerel önbelleği oluşturmak için komut satırını kullanabilirsiniz. Bu işlem önceki sürümler için ISO dosyaları değiştirir.

> [!NOTE]
> İnternet'ten dağıtımına bir ağ güvenlik duvarı istemci iş istasyonları, Visual Studio 2017 gerçekleştirmek istediği bkz Kurumsal yönetici olması durumunda bizim [Visual Studio 2017 bir ağ yüklemesi oluşturmak](../install/create-a-network-installation-of-visual-studio.md) ve [Visual Studio çevrimdışı yükleme için gerekli sertifikaları yükleyin](../install/install-certificates-for-visual-studio-offline.md) sayfaları.

## <a name="get-support"></a>Destek alma

Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://visualstudio.microsoft.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:

* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunlarını izlemek ve yanıtlar bulmak [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/).
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio). (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)
