---
title: Eylemler derleme
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.assetid: 5399BCB1-E317-4C7B-87B1-C531E985DE6E
ms.openlocfilehash: 3e876bbc20f2f2e86ba7ec4806f67f4a2573a089
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="build-actions"></a>Eylemler derleme

Visual Studio'da tüm dosyaları Mac projesi için yapılandırma sırasında dosyaya olanlar denetleyen bir yapı eylemi sahiptir. Bu, üzerinde herhangi bir dosyayı sağ tıklayarak ve göz ayarlanabilir **yapı eylemi**aşağıda gösterildiği gibi:

![](media/projects-and-solutions-image1.png)

C# projeleri için bazı yaygın eylemler oluşturun:

* **Hiçbiri** -dosya derleme herhangi bir şekilde bir parçası değil - yalnızca IDE kolay erişim için projedeki eklenmiştir.
* **Derleme** -dosya C# Derleyici kaynak dosyası olarak geçirilecektir.
* **EmbeddedResource** -C# derleyici dosya derlemede katıştırılmış bir kaynak olarak geçirilir. `System.Reflection` Ad alanı sonra derlemeden dosyasını okumak için kullanılabilir.
* **İçerik** -için ASP.NET projeleri, bu dosyaları olacaktır sitesinin bir parçası olarak dahil dağıtıldığında. Xamarin.iOS ve Xamarin.Mac projeleri için bunlar uygulama pakette bulunan.

Yapı eylem aynı anda çok sayıda dosyaya ayarlamanıza olanak veren Çözüm Gezgini'nde, birden fazla dosyayı seçmek mümkündür.

Ayrıca, belirli projeler için yapı eylemler vardır. Örneğin, Xamarin.iOS projeleri sahip **BundleResource** derleme dosyası uygulama paketi bir parçası olarak ekleyecek eylemi. Xamarin.Android belirli yapı eylemler hakkında bilgi bulunabilir [derleme işlemi](/xamarin/android/deploy-test/building-apps/build-process#Build_Actions) Kılavuzu.