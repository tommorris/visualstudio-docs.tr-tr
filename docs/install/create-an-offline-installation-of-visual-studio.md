---
title: "Visual Studio çevrimdışı yüklemesini oluşturma | Microsoft Docs"
description: "Visual Studio çevrimdışı nasıl yükleneceğini öğrenin."
ms.custom: 
ms.date: 08/30/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- offline installation [Visual Studio]
- offline install [Visual Studio]
- layout [Visual Studio]
ms.assetid: f8625d5e-f6ea-4db0-83c0-619b77fab3cf
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 8b0902c7e2d3c2b51ecd915647a3e8a03e49c641
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="create-an-offline-installation-of-visual-studio-2017"></a>Visual Studio 2017 çevrimdışı yüklemesini oluşturma

Biz de çok çeşitli ağ ve makine koşullar içinde çalışmak için Visual Studio 2017 yükleyici tasarlanmıştır.

- Yeni iş yükü tabanlı modeli gerekir indirmek şimdiye kadar küçüktür, Visual Studio'nun önceki sürümleri ile anlamına gelir: en az 300 MB olarak en küçük yükleme;
- Bir genel "ISO" veya zip dosyası ile karşılaştırıldığında, biz yalnızca makine için gereksinim duyduğunuz paketlerini yükleyin. Örneğin, bunları gerekmiyorsa, biz 64-bit dosyalar yüklemeyin;
- Yükleme işlemi sırasında şu üç farklı indirme teknolojileri (WebClient, BITS ve WinINet) yazılımıyla; virüsten koruma ve proxy girişim en aza indirmek için deneyin
- Biz bunları sizin için bir yerel sunucudan alabilmek için Visual Studio'yu yüklemek için gereken dosyaları genel teslim ağ üzerinde dağıtılır.

Denemenizi öneririz [Visual Studio web yükleyicisi](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocsOL)&mdash;bulabilirsiniz, iyi bir deneyim düşünüyoruz.

 > [!div class="button"]
 > [Visual Studio 2017 indirin](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocsOL)
<br/>

Internet bağlantınız kullanılabilir veya güvenilir olmayan, bkz: olduğundan çevrimdışı yüklemek istiyorsanız, [yükleme Visual Studio 2017 düşük bant genişliği veya güvenilmeyen ağ ortamları](../install/install-vs-inconsistent-quality-network.md). Çevrimdışı bir yüklemeyi tamamlamak için gereken dosyaları yerel önbelleği oluşturmak için komut satırını kullanabilirsiniz. Bu işlem önceki sürümler için ISO dosyaları değiştirir.

> [!NOTE]
> İnternet'ten dağıtımına bir ağ güvenlik duvarı istemci iş istasyonları, Visual Studio 2017 gerçekleştirmek istediği bkz Kurumsal yönetici olması durumunda bizim [Visual Studio 2017 bir ağ yüklemesi oluşturmak](../install/create-a-network-installation-of-visual-studio.md) ve [Çevrimdışı bir ortamda Visual Studio'yu yükleme için özel hususlar](../install/install-visual-studio-in-offline-environment.md) sayfaları.

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sorun giderme ipuçları için sayfa. Ürün sorunları bize de bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) aracı Visual Studio IDE içinde veya üzerinde bir öneri bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579). Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun. Bize ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio) (gerektiren bir [GitHub](https://github.com/) hesabı).
