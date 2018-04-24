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
ms.openlocfilehash: 6d70005a7e876b299e93ac2891ce6774a6300792
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="create-an-offline-installation-of-visual-studio-2017"></a>Visual Studio 2017 çevrimdışı yüklemesini oluşturma

Biz de çok çeşitli ağ ve makine koşullar içinde çalışmak için Visual Studio 2017 yükleyici tasarlanmıştır.

- Yeni iş yükü tabanlı modeli gerekir indirmek şimdiye kadar küçüktür, Visual Studio'nun önceki sürümleri ile anlamına gelir: en az 300 MB olarak en küçük yükleme;
- Bir genel "ISO" veya zip dosyası ile karşılaştırıldığında, biz yalnızca makine için gereksinim duyduğunuz paketlerini yükleyin. Örneğin, bunları gerekmiyorsa, biz 64-bit dosyalar yüklemeyin;
- Yükleme işlemi sırasında şu üç farklı indirme teknolojileri (WebClient, BITS ve WinINet) yazılımıyla; virüsten koruma ve proxy girişim en aza indirmek için deneyin
- Biz bunları sizin için bir yerel sunucudan alabilmek için Visual Studio'yu yüklemek için gereken dosyaları genel teslim ağ üzerinde dağıtılır.

Denemenizi öneririz [Visual Studio web yükleyicisi](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocsOL)&mdash;bulabilirsiniz, iyi bir deneyim düşünüyoruz.

 > [!div class="button"]
 > [Visual Studio 2017 İndir](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocsOL)

Internet bağlantınız kullanılabilir veya güvenilir olmayan, bkz: olduğundan çevrimdışı yüklemek istiyorsanız, [yükleme Visual Studio 2017 düşük bant genişliği veya güvenilmeyen ağ ortamları](../install/install-vs-inconsistent-quality-network.md). Çevrimdışı bir yüklemeyi tamamlamak için gereken dosyaları yerel önbelleği oluşturmak için komut satırını kullanabilirsiniz. Bu işlem önceki sürümler için ISO dosyaları değiştirir.

> [!NOTE]
> İnternet'ten dağıtımına bir ağ güvenlik duvarı istemci iş istasyonları, Visual Studio 2017 gerçekleştirmek istediği bkz Kurumsal yönetici olması durumunda bizim [Visual Studio 2017 bir ağ yüklemesi oluşturmak](../install/create-a-network-installation-of-visual-studio.md) ve [Visual Studio çevrimdışı yükleme için gerekli sertifikaları yükleyin](../install/install-certificates-for-visual-studio-offline.md) sayfaları.

## <a name="get-support"></a>Destek alma

Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:

* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunlarını izlemek ve yanıtlar bulmak [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/).
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio). (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)
