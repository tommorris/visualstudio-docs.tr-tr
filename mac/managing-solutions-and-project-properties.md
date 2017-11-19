---
title: "Proje ve çözüm özelliklerini yönetme | Microsoft Docs"
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 75247EB8-323A-4AFD-A451-6703A03D5D1F
ms.openlocfilehash: 8871ab002a94a9c0bbc0063a25b4dea9cb271142
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="managing-project-and-solution-properties"></a>Proje ve Çözüm Özelliklerini Yönetme

## <a name="project-options"></a>Proje seçenekleri

Proje seçenekleri her proje için özeldir ve proje nasıl yazılmış, yerleşik ve Çalıştır etkiler. Bu çözümün tamamı için seçenekleri ayarlayın çözüm seçenekleri ve kullanıcıya özgü seçeneklerini ayarlama, Mac tercihleri için Visual Studio ile karşılaştırır. Diğer geliştiriciler oluşturmak ve projeyi düzgün çalışması için Proje seçenekleri proje (.csproj) dosyasında depolanır. Bu dosyanın biçimlendirmesini ödün vermeden aynı belge üzerinde çalışmak birçok geliştiriciler sağlar.

Mac proje adına çift tıklatarak veya bağlam menüsünü açmak için sağ tıklatıp seçerek başlatılabilir için Visual Studio seçenekleri proje **seçenekleri**:

 ![Bağlam menüsü seçeneği](media/projects-and-solutions-image2.png)

Düzenlenebilir seçenekleri oluşturmak için çalıştırın ve kaynak kodu ve sürüm denetimi seçeneklerini içerir.

Proje seçenekleri aşağıdaki özellikleri olan beş farklı kategoriler halinde düzenlenir:

* **Genel** -proje bilgileri adını, açıklamasını ve varsayılan Namespace gibi ayarlanabilir Burada, projenin konumu yanı sıra.
* **Yapı** -bu ayarlamak veya PCL profilleri için taşınabilir sınıf kitaplıkları değiştirmek geliştiricilere sağlar. Ayrıca tanır özel komutlar, yapılandırmaları, ayarlanacak derleyici seçenekleri. Çıkış yolu ve derleme adı da burada ayarlanabilir.
* **Çalıştırma** -Bu, bir proje başına temelinde özel çalıştırma yapılandırmaları oluşturmanıza olanak sağlar.
* **Kaynak kodu** - bu adlandırma kuralları ve biçimlendirme birçok farklı dosya türlerini denetlemenize olanak tanır. Ayrıca adlandırma ilkeleri ve varsayılan üstbilgi stilleri burada ayarlayabilirsiniz.
* **Sürüm denetimi** -bu sürüm denetimi ile projenizi kullanırken kaydetme iletisi stilini düzenlemenize olanak sağlar.

Her proje platforma bağlı olarak belirli bir proje seçenekleri de içerebilir. Örneğin, aşağıda gösterildiği gibi bir Xamarin.Android projesi Android derleme - bağlayıcı seçenekleri gibi ilgili seçeneğiniz; ve izinleri gibi uygulama:

 ![Android proje seçenekleri](media/projects-and-solutions-image5.png)

Xamarin.iOS ilgili paket imzalama - gerekli sağlama profili gibi seçeneklerini içerir; ve IPA paketleme seçenekleri ile ilgili:

 ![iOS proje seçenekleri](media/projects-and-solutions-image6.png)

## <a name="solution-options"></a>Çözüm seçenekleri 

Çözüm seçenekleri gibi proje seçenekleri, ancak tüm çözümleri kapsamını kapsar. Yazar bilgilerini ayarlama, yapı ayarları, biçimlendirme stilleri ve sürüm denetimi, kod için bir yol sağlar ve çözüm başlangıç projesi atamak bir yol sağlar.  Çözüm Seçenekleri iletişim kutusu erişilebilen **Proje > çözüm seçenekleri** menü öğesini gelen **seçenekleri** bağlam menüsü öğesini çözüm panelinde ya da çift çözüm üzerinde Çözüm çözüm panelinde:

 ![Çözüm seçenekleri](media/projects-and-solutions-image7.png)
