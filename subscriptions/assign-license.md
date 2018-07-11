---
title: Visual Studio abonelikleri için lisans atama | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 10/03/2017
ms.topic: Get-Started-Article
description: Yöneticiler abonelere lisansları nasıl atayabilirsiniz öğrenin
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: d0dbd509d60ed3528186e41c98f374ab6db60fa3
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "36327030"
---
# <a name="assigning-licenses-in-the-visual-studio-subscriptions-administrator-portal"></a>Visual Studio abonelikleri Yönetici portalında lisans atama

Visual Studio abonelikleri Yöneticisi olarak, abonelikleri bireysel kullanıcılara atamak için Visual Studio abonelikleri Yönetici portalını kullanabilirsiniz.  
Bunları teker teker atayın veya aboneleri abonelik bilgileriyle listesini hızla ve kolayca karşıya yüklemek için "toplu ekleme" özelliğini kullanın. 

## <a name="assigning-a-single-user"></a>Tek kullanıcı atama
Visual Studio abonelikleri için kullanılabilir lisans varsa, abonelik avantajlarının erişmek için yeni kullanıcılara için bu lisansları atayabilirsiniz. 
1.  Oturum [Yönetici portalı](https://manage.visualstudio.com)

2.  Tablonun üstündeki tek bir Visual Studio abone atamak için tıklatın **Ekle**.
   
3.  Bilgileri yeni bir abone için form alanlara girin. Kuruluşunuz Azure Active Directory kullanıyorsa, bu alan doğru kullanıcı Arama sonuçlarından seçebilmeniz için kişi geçerli dizinde bulmak için bir arama işlevi görür. Söz konusu kişinin seçtikten sonra aşağıda görebileceğiniz gibi ad, oturum açma e-posta ve bildirim e-posta otomatik olarak doldurur. 

    Kuruluşunuz Azure Active Directory (Azure AD) kullanmıyor, ancak oturum açmak için kullanılacak bir e-postaları almak için farklı bir e-içerir, burada girmek için seçeneğiniz vardır. "Alan iletişimi için farklı bir e-posta Ekle" etiketli köprüyü seçin. 

    **İndirmelere erişim:**  
    Oturum açtığınızda yazılım indirme işlemleri için erişim sağlamak için bu abone istiyorsanız [Visual Studio abonelikleri portalında](https://my.visualstudio.com?wt.mc_id=o~msft~docs), etkin indirmeler bırakmayı emin olun. İndirmeler devre dışı bırakmak isterseniz, kullanıcı yazılım indirme işlemleri erişimi olmaz ancak aboneliğine dahil tüm avantajlara erişime sahip olmaya devam. 
    
    Bitirdiğinizde bu abone için seçenekleri belirleyerek, tıklayın **Ekle**.

    <img alt="Enter subscriber information" src="_img\assign-license-add\add-subscriber-1.png" style="border: 1px solid #CCCCCC" />
    <img alt="Enter subscriber information" src="_img\assign-license-add\add-subscriber-2.png" style="border: 1px solid #CCCCCC" />

4.  Abone ekledikten sonra bir atama e-posta otomatik olarak yeni abone ile daha fazla yönerge için gönderilir. Abone seçerek ve tıklayarak dilediğiniz zaman yeniden atama e-posta gönderebilir **Gönder** üst menü düğmesi.


## <a name="bulk-assignments"></a>Toplu atama
1.  Aynı anda birden çok abone ekleme için gidin **aboneleri yönetme** sekmesi. Üstteki Şeritte tıklayın **toplu ekleme**. 

2. Toplu atama aboneyi karşıya yükleme için Microsoft Excel şablonu kullanır. Birden çok aboneyi karşıya yükleme iletişim kutusuna tıklayın **indirme** şablonu indirilemedi. Her zaman bu şablonun en son sürümünü indirin. Eski bir sürümünü kullanıyorsanız, toplu karşıya yükleme işleminiz başarısız olabilir.

3.  Excel elektronik tablosunda abonelikleri atamak istediğiniz kişilerin bilgilerle alanları doldurun. Başvuru isteğe bağlı bir alandır. Şablonu herhangi bir bölümünü yanlış doldurduktan, sorunu açıklayan bir hata iletisini görmeniz gerekir. Dosyayı yerel olarak bir kez yapılır.
**Kesintisiz bir karşıya yükleme emin olmak için aşağıdaki en iyi yöntemleri inceleyin:**
    - Form alanlarını hiçbiri virgül içerdiğinden emin olun.
    - Boşluk önce ve sonra kullanıcıların adları gibi form alanlarını kaldırın.
    - Kullanıcı adlarının ilk veya son adlar iki parçalı arasındaki fazladan boşlukları içermiyor olduğundan emin olun (sistem fazladan boşluk kesim değil olarak ör "Maggie olabilir" gibi iki parçalı ad "Maggie olabilir" yazılmalıdır değil.)

4.  Visual Studio abonelikleri Yönetim Portalı ve birden çok aboneyi karşıya yükleme iletişim kutusuna dönmek, tıklayın **Gözat**. Kaydettiğiniz Excel dosyasına gidin ve tıklayın **Tamam**. Ekranda, karşıya yükleme ilerleme durumunu görürsünüz. 

    <img alt="Bulk add upload" src="_img\assign-license-add\bulk-assign-upload-2.png" style="border: 1px solid #CCCCCC" />

Bu nedenle şablonu hatalar içeriyor, karşıya yükleme başarısız olur ve hataları gösterilir şablon düzeltin ve toplu karşıya yükleme yeniden denemeden kullanabilirsiniz.
    <img alt="Upload fail" src="_img\assign-license-add\bulk-assign-upload-fail.png" style="border: 1px solid #CCCCCC" />

Karşıya yükleme başarılı olduğunda, aboneleri ve bir onay iletisi listesini görürsünüz.

