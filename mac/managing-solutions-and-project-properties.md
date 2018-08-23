---
title: Proje ve Çözüm Özelliklerini Yönetme
description: Bu makaleler, Mac için projeler ve çözümler Visual Studio'da özelliklerini yönetmek nasıl açıklar
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.assetid: 75247EB8-323A-4AFD-A451-6703A03D5D1F
ms.openlocfilehash: dbfff9dcb03958ce2a8aa6bd2d2940ee79908dee
ms.sourcegitcommit: 2597236a481afbaf1ad4915743898ee1aee49760
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42624312"
---
# <a name="managing-project-and-solution-properties"></a>Proje ve Çözüm Özelliklerini Yönetme

## <a name="project-options"></a>Proje seçenekleri

Proje seçenekleri, her proje için özeldir ve proje nasıl yazılır, yerleşik ve çalıştırma etkiler. (Bu kullanıcıya özgü seçenekleri ayarlar) Mac tercihleri ve (hangi çözümün tamamını seçeneklerini ayarlama) çözüm seçenekleri için Visual Studio ile karşılaştırır. Diğer geliştiriciler oluşturabilir ve doğru projeyi çalıştırın, proje seçenekleri proje (.csproj) dosyasında depolanır. Belirli proje seçenekleri dosyanın biçimlendirmesini ödün vermeden aynı belge üzerinde çalışmak birçok geliştiricinin sağlar.

Projeyi açmak için Mac için Visual Studio seçenekleri proje adına çift tıklayın veya bağlam menüsünü açmak için sağ tıklayın ve seçin **seçenekleri**:

 ![Bağlam menüsü seçeneği](media/projects-and-solutions-image2.png)

Oluşturma, çalıştırma ve kaynak kodu ve sürüm denetimi seçeneklerini düzenlenebilir seçenekleri içerir.

Proje seçenekleri beş farklı kategoride düzenlenmiştir:

* **Genel** -proje adını, açıklamasını ve varsayılan Namespace projenin konumunu yanı sıra, burada ayarlanan gibi bilgileri.
* **Derleme** -Bu, geliştiricilerin ayarlama veya taşınabilir sınıf kitaplıkları için PCL profillerini değiştirme olanak tanır. Ayrıca sağlar özel komutlar, yapılandırmaları, derleyici seçenekleri ayarlamak için. Çıkış yolu ve derleme adı da buradan ayarlanabilir.
* **Çalıştırma** -Bu, proje başına temelinde özel çalıştırma yapılandırmaları oluşturmanıza olanak sağlar.
* **Kaynak kodu** - Bu, birçok farklı dosya türleri biçimlendirme denetlemenize olanak tanır ve adlandırma kuralları. Ayrıca varsayılan üst bilgi stil ve adlandırma ilkeleri burada ayarlayabilirsiniz.
* **Sürüm denetimi** -bu sürüm denetimi projenizle kullanırken işleme iletisi stili düzenlemenizi sağlar.

Her proje, platforma bağlı olarak belirli proje seçenekleri içerebilir. Örneğin, aşağıdaki görüntüde gösterilen benzeyen bir Xamarin.Android projesi Android derleme - bağlayıcı seçenekleri gibi ilgili seçeneğe sahiptir; ve izinleri gibi uygulama:

 ![Android projesi seçenekleri](media/projects-and-solutions-image5.png)

Xamarin.iOS paket grubu imzalama - gerekli sağlama profilinin gibi ilgili seçeneklerini içerir:

 ![iOS projesi seçenekleri](media/projects-and-solutions-image6.png)

## <a name="solution-options"></a>Çözüm seçenekleri 

Çözüm seçenekleri gibi proje seçenekleri, ancak tüm çözümleri kapsamını kapsar. Derleme ayarları, kod stilleri ve sürüm denetimi, biçimlendirme, yazar bilgileri için bir yol sağlarlar ve başlangıç projesi çözümdeki atamak bir yol sağlar.  Çözüm Seçenekleri iletişim kutusunun yanından erişilebilen **Proje > çözüm seçenekleri** menü öğesi, gelen **seçenekleri** çözüm panelinde veya çift tıklatarak çözümdeki bağlam menüsü öğesi Çözümde, çözüm bölmesi:

 ![Çözüm seçenekleri](media/projects-and-solutions-image7.png)
