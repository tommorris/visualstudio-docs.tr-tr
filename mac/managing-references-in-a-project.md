---
title: Bir projedeki başvuruları yönetme
description: Bu makalede Mac için Visual Studio'da bir projedeki başvuruları yönetme
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: 4AD51385-B0A8-4BA7-B2D4-BF2BD167A142
ms.openlocfilehash: 82875955e861ec25e1444874afaa8b7f2e807fa7
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2018
---
# <a name="managing-references-in-a-project"></a>Bir projedeki başvuruları yönetme

Mac için Visual Studio, projenizin ek başvuruları ekleme iki sağlar:

![Proje başvuruları](media/projects-and-solutions-image10.png)

Bunlar:

* Referanslar
* NuGets (eklenen paketler klasörü aracılığıyla)

Ayrıca, Web başvuruları ve yerel başvuruları da herhangi bir projesine eklenebilir.

## <a name="assembly-references"></a>Derleme başvuruları

Xamarin her Framework'te üzerinde bir düzine derlemeleri ile birlikte gelir. Bu derleme paketleri tüm projenizde varsayılan olarak başvurulur. 

Projenizde başvurulan paketleri düzenlemek için kullanın _Düzenle başvuruları_ başvuruları klasörü çift veya bağlam menüsü eylemlerini seçin Düzenle başvurular tarafından görüntülenen iletişim:

![Derleme başvuruları iletişim](media/projects-and-solutions-image11.png)

Her Xamarin çerçevesi için kullanılabilir derlemeler hakkında daha fazla bilgi için bkz [kullanılabilir derlemeleri](https://developer.xamarin.com/guides/cross-platform/advanced/available-assemblies/) Kılavuzu.

## <a name="nuget"></a>NuGet

NuGet en popüler .NET geliştirme paket yöneticisidir. Visual Studio Mac'ın NuGet desteği için projenize eklemek paketler için aramanıza olanak sağlar.

Bunu yapmak için sağ **paket** klasöründe çözüm paneli ve paketleri Ekle'i seçin.

Bir NuGet paketi kullanma hakkında daha fazla bilgi sağlanan [dahil olmak üzere bir NuGet paketini projenize](nuget-walkthrough.md) gözden geçirme.
