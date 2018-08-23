---
title: Bir projedeki başvuruları yönetme
description: Bu makalede, Mac için Visual Studio'da bir projedeki başvuruları yönetme işlemi açıklanır
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.assetid: 4AD51385-B0A8-4BA7-B2D4-BF2BD167A142
ms.openlocfilehash: 79d96ac61bcec198c899d709677df775332db383
ms.sourcegitcommit: 2597236a481afbaf1ad4915743898ee1aee49760
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42624183"
---
# <a name="managing-references-in-a-project"></a>Bir projedeki başvuruları yönetme

Mac için Visual Studio projenize ek başvurular ekleme iki yöntem sunar:

![Proje başvuruları](media/projects-and-solutions-image10.png)

Bunlar:

* Referanslar
* Nuget'lar (eklenen Packages klasörünü aracılığıyla)

Ayrıca, Web başvuruları ve yerel başvurular da herhangi bir projesine eklenebilir.

## <a name="assembly-references"></a>Derleme başvuruları

Xamarin içindeki her bir çerçeve üzerinde bir düzine derlemeleri ile birlikte gelir. Bu derleme paketlerin hepsini projenizde varsayılan olarak başvurulur. 

Projenizde başvurulan paketleri düzenlemek için _başvuruları Düzenle_ başvuruları klasörü çift tıklayarak veya bağlam menüsünde eylemlerini seçin Düzenle başvurular görüntülenebilen iletişim kutusunda:

![Bütünleştirilmiş kod başvuruları iletişim](media/projects-and-solutions-image11.png)

Her bir Xamarin çerçeve için kullanılabilir derlemeler hakkında daha fazla bilgi için bkz [kullanılabilir derlemeler](https://developer.xamarin.com/guides/cross-platform/advanced/available-assemblies/) Kılavuzu.

## <a name="nuget"></a>NuGet

NuGet, .NET geliştirme için en popüler paket yöneticisidir. NuGet desteği Mac için Visual Studio, projenize eklenecek paketleri aramak sağlar.

Bunu yapmak için sağ **paket** klasöründe çözüm bölmesi ve paketleri Ekle'i seçin.

Bir NuGet paketi kullanma hakkında daha fazla bilgi sağlanır [dahil olmak üzere bir NuGet paketini projenize](nuget-walkthrough.md) gözden geçirme.
