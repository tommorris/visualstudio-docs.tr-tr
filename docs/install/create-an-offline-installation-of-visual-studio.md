---
title: Visual Studio'nun çevrimdışı yüklemesini oluşturma
description: Visual Studio'yu çevrimdışı yükleme öğrenin.
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
ms.openlocfilehash: d19eabe10234ca2a1670ae04f99a45a85a6cac14
ms.sourcegitcommit: 6b092e7d466377f06913d49d183dbbdca16730f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/28/2018
ms.locfileid: "43138883"
---
# <a name="create-an-offline-installation-of-visual-studio-2017"></a>Visual Studio 2017'in çevrimdışı yüklemesini oluşturma

Biz, Visual Studio 2017 yükleyicisi ağ ve makine koşullar çok çeşitli iyi çalışacak şekilde tasarlanmıştır.

- Yeni iş yükü tabanlı modeli gerekir indirmek şimdiye kadar küçüktür Visual Studio'nun önceki sürümüyle anlamına gelir: en az 300 MB olarak en küçük yükleme;
- Bir genel "ISO" ya da zip dosyası karşılaştırıldığında, biz yalnızca makineniz için gereksinim duyduğunuz paketlerini indirin. Örneğin, biz ihtiyacınız yoksa 64 bit dosyaları yüklemeyin;
- Yükleme işlemi sırasında biz (WebClient, BITS ve WinINet) ile virüsten koruma ve ara yazılım; girişim en aza indirmek için üç farklı indirme teknolojileri deneyin
- Biz bunları sizin için bir yerel sunucudan alabilmeniz için Visual Studio'yu yüklemek için ihtiyacınız dosyaları bir küresel teslim ağı üzerinde dağıtılır.

Denemenizi öneririz [Visual Studio web yükleyicisini](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)&mdash;bulabilirsiniz, iyi bir deneyim düşünüyoruz.

 > [!div class="button"]
 > [Visual Studio 2017 İndir](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

Internet bağlantısı kullanılamıyorsa veya güvenilir, bkz: olduğundan çevrimdışı yüklemek istiyorsanız [düşük bant genişliği veya güvenilir olmayan ağ ortamlarında Visual Studio 2017 yükleme](../install/install-vs-inconsistent-quality-network.md). Yerel önbellek, bir çevrimdışı yüklemeyi tamamlamak için gereken dosyaları oluşturmak için komut satırını kullanabilirsiniz. Bu işlem, önceki sürümler için ISO dosyalarını değiştirir.

> [!NOTE]
> Visual Studio 2017'in bir dağıtım için bir ağ güvenlik duvarı istemci iş istasyonları, internet'ten gerçekleştirmek isterse bkz Kurumsal Yönetici olduğunuz bizim [Visual Studio 2017'in bir ağ yüklemesini oluşturma](../install/create-a-network-installation-of-visual-studio.md) ve [Visual Studio'yu çevrimdışı yükleme için gerekli sertifikaları yükleme](../install/install-certificates-for-visual-studio-offline.md) sayfaları.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]
