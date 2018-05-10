---
title: Proje ve Çözüm Özelliklerini Yönetme
description: Bu makalede açıklanır Mac için projeler ve çözümler Visual Studio'da özelliklerini yönetme
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: 75247EB8-323A-4AFD-A451-6703A03D5D1F
ms.openlocfilehash: 7eec0bdecd09a0776df4ab0a9cb21ea37fbabf0b
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="managing-project-and-solution-properties"></a>Proje ve Çözüm Özelliklerini Yönetme

## <a name="project-options"></a>Proje seçenekleri

Proje seçenekleri her proje için özeldir ve proje nasıl yazılmış, yerleşik ve Çalıştır etkiler. Bu Mac (kullanıcıya özgü seçeneklerini ayarlar) Tercihler ve (hangi çözümün tamamı için seçenekleri ayarlayın) çözüm seçenekleri için Visual Studio ile karşılaştırır. Diğer geliştiriciler oluşturmak ve projeyi düzgün çalışması için Proje seçenekleri proje (.csproj) dosyasında depolanır. Belirli proje seçenekleri sahip birçok geliştiricilerin dosyanın biçimlendirmesini tehlikeye atmadan aynı belge üzerinde çalışmanıza olanak tanır.

Projeyi açmak için Mac için Visual Studio seçenekleri proje adına çift tıklayın veya etiketin bağlam menüsünü açmak için sağ tıklatın ve seçin **seçenekleri**:

 ![Bağlam menüsü seçeneği](media/projects-and-solutions-image2.png)

Düzenlenebilir seçenekler, oluşturmak, çalıştırmak ve kaynak kodu ayarlamak için seçenekler ve sürüm denetimi seçenekleri içerir.

Proje seçenekleri beş farklı kategoriler halinde düzenlenir:

* **Genel** -proje bilgileri gibi adını, açıklamasını ve varsayılan Namespace proje konumunu birlikte burada ayarlanır.
* **Yapı** -bu ayarlamak veya PCL profilleri için taşınabilir sınıf kitaplıkları değiştirmek geliştiricilere sağlar. Ayrıca tanır özel komutlar, yapılandırmaları, ayarlanacak derleyici seçenekleri. Çıkış yolu ve derleme adı da burada ayarlanabilir.
* **Çalıştırma** -Bu, bir proje başına temelinde özel çalıştırma yapılandırmaları oluşturmanıza olanak sağlar.
* **Kaynak kodu** - bu adlandırma kuralları ve biçimlendirme birçok farklı dosya türlerini denetlemenize olanak tanır. Ayrıca adlandırma ilkeleri ve varsayılan üstbilgi stilleri burada ayarlayabilirsiniz.
* **Sürüm denetimi** -bu sürüm denetimi ile projenizi kullanırken kaydetme iletisi stilini düzenlemenize olanak sağlar.

Her proje platforma bağlı olarak belirli bir proje seçenekleri içerebilir. Örneğin, aşağıdaki görüntüde gösterildiği bir gibi bir Xamarin.Android projesi Android derleme - bağlayıcı seçenekleri gibi ilgili seçenekleri vardır; ve izinleri gibi uygulama:

 ![Android proje seçenekleri](media/projects-and-solutions-image5.png)

Xamarin.iOS kullanmak için ilgili paket imzalama - gerekli sağlama profili gibi seçenekler vardır:

 ![iOS proje seçenekleri](media/projects-and-solutions-image6.png)

## <a name="solution-options"></a>Çözüm seçenekleri 

Çözüm seçenekleri gibi proje seçenekleri, ancak tüm çözümleri kapsamını kapsar. Yazar bilgilerini ayarlama, yapı ayarları, biçimlendirme stilleri ve sürüm denetimi, kod için bir yol sağlar ve çözüm başlangıç projesi atamak bir yol sağlar.  Çözüm Seçenekleri iletişim kutusu erişilebilen **Proje > çözüm seçenekleri** menü öğesini gelen **seçenekleri** bağlam menüsü öğesini çözüm panelinde ya da çift çözüm üzerinde Çözüm çözüm panelinde:

 ![Çözüm seçenekleri](media/projects-and-solutions-image7.png)
