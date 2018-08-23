---
title: Derleme eylemleri
description: Bu makalede, C# projeleri için kullanılabilecek çeşitli yapı eylemleri açıklanır.
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.assetid: 5399BCB1-E317-4C7B-87B1-C531E985DE6E
ms.openlocfilehash: 6ef2cc3347480fceab23df12e53be65dd5432183
ms.sourcegitcommit: 2597236a481afbaf1ad4915743898ee1aee49760
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42623918"
---
# <a name="build-actions"></a>Derleme eylemleri

Visual Studio'da tüm dosyaları Mac projesi için bir yapı sırasında dosyaya ne denetleyen bir derleme eylemi var. Bu, herhangi bir dosyaya sağ tıklayıp göz ayarlanabilir **derleme eylemi**, aşağıda gösterildiği gibi:

![Derleme derleme eylemi fom Çözüm Gezgini seçme](media/projects-and-solutions-image1.png)

C# projeleri için bazı ortak eylemler oluşturun:

* **Hiçbiri** -dosya herhangi bir şekilde oluşturma işleminin bir parçası değil.-yalnızca IDE üzerinden kolay erişim için projedeki dahildir.
* **Derleme** -dosya, kaynak dosyası olarak C# Derleyici geçirilecek.
* **EmbeddedResource** -C# derleyicisi dosyanın derleme içine gömülü olması için bir kaynak olarak geçirilir. `System.Reflection` Ad alanı derlemeden dosyayı okumak için kullanılabilecek.
* **İçerik** -için ASP.NET projeleri, bu dosyaları olacaktır sitenin bir parçası olarak dahil dağıtıldığında. Xamarin.iOS ve Xamarin.Mac projelerinde bunlar uygulama paketi içinde yer alan.

Birden fazla dosya seçin Çözüm Gezgini'nde, tek seferde çok sayıda dosyaya derleme eylemi ayarlamanızı izin verme mümkündür.

Ayrıca, belirli projeleri için derleme eylemler vardır. Örneğin, Xamarin.iOS projeleri sahip **BundleResource** uygulama paket grubunu bir parçası olarak dosya ekleyecektir eylem oluşturun. Xamarin.Android belirli yapı eylemler hakkında bilgi bulunabilir [derleme işlemi](/xamarin/android/deploy-test/building-apps/build-process#Build_Actions) Kılavuzu.