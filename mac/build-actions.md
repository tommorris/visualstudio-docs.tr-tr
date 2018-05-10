---
title: Eylemler derleme
description: Bu makalede C# projeleri için kullanılabilecek çeşitli yapı eylemleri
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: 5399BCB1-E317-4C7B-87B1-C531E985DE6E
ms.openlocfilehash: 889414d391a4a894879399317d782df58a8bacb3
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="build-actions"></a>Eylemler derleme

Visual Studio'da tüm dosyaları Mac projesi için yapılandırma sırasında dosyaya olanlar denetleyen bir yapı eylemi sahiptir. Bu, üzerinde herhangi bir dosyayı sağ tıklayarak ve göz ayarlanabilir **yapı eylemi**aşağıda gösterildiği gibi:

![Derleme yapı eylemi fom Çözüm Gezgini seçme](media/projects-and-solutions-image1.png)

C# projeleri için bazı yaygın eylemler oluşturun:

* **Hiçbiri** -dosya derleme herhangi bir şekilde bir parçası değil - yalnızca IDE kolay erişim için projedeki eklenmiştir.
* **Derleme** -dosya C# Derleyici kaynak dosyası olarak geçirilecektir.
* **EmbeddedResource** -C# derleyici dosya derlemede katıştırılmış bir kaynak olarak geçirilir. `System.Reflection` Ad alanı sonra derlemeden dosyasını okumak için kullanılabilir.
* **İçerik** -için ASP.NET projeleri, bu dosyaları olacaktır sitesinin bir parçası olarak dahil dağıtıldığında. Xamarin.iOS ve Xamarin.Mac projeleri için bunlar uygulama pakette bulunan.

Yapı eylem aynı anda çok sayıda dosyaya ayarlamanıza olanak veren Çözüm Gezgini'nde, birden fazla dosyayı seçmek mümkündür.

Ayrıca, belirli projeler için yapı eylemler vardır. Örneğin, Xamarin.iOS projeleri sahip **BundleResource** derleme dosyası uygulama paketi bir parçası olarak ekleyecek eylemi. Xamarin.Android belirli yapı eylemler hakkında bilgi bulunabilir [derleme işlemi](/xamarin/android/deploy-test/building-apps/build-process#Build_Actions) Kılavuzu.