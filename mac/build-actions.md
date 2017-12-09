---
title: Eylemler derleme
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 5399BCB1-E317-4C7B-87B1-C531E985DE6E
ms.openlocfilehash: 78b0e715ca44c613b6a7ee839c0656e301308588
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2017
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

Ayrıca, belirli projeler için yapı eylemler vardır. Örneğin, Xamarin.iOS projeleri sahip **BundleResource** derleme dosyası uygulama paketi bir parçası olarak ekleyecek eylemi. Xamarin.Android belirli yapı eylemler hakkında bilgi bulunabilir [derleme işlemi](https://developer.xamarin.com/guides/android/under_the_hood/build_process/#Build_Actions) developer.xamarin.com Kılavuzu.