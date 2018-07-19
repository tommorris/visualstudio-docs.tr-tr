---
title: Visual Studio abonelikleri için lisans atama | Microsoft Docs
author: TerryGLee
ms.author: tglee
manager: douge
ms.date: 07/16/2018
ms.topic: conceptual
description: Yöneticiler abonelere lisansları nasıl atayabilirsiniz öğrenin
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: e43e9050e2b021025ed4ae104f4345bce6e8eee3
ms.sourcegitcommit: 7a11a094a353f2e2a2077ad863ca4c0fb97f7ec5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2018
ms.locfileid: "39131937"
---
# <a name="assign-licenses-in-the-visual-studio-subscriptions-administrator-portal"></a>Visual Studio abonelikleri Yönetici portalında lisansları atama

Visual Studio abonelikleri Yöneticisi olarak, abonelikleri bireysel kullanıcılar ve kullanıcı gruplarını atamak için Yönetici portalını kullanabilirsiniz.

Kullanıcı grupları için abonelikler için saat veya kullanım atayabilirsiniz **toplu ekleme** aboneleri abonelik bilgileriyle listesini hızla ve kolayca karşıya yüklemek için özellik. 

## <a name="individual-assignments"></a>Her bir atama

Abonelik avantajları erişebilmesi için yeni bir kullanıcı için bir Visual Studio abonelikleri lisansı atamak açıklanmıştır.

1. Oturum [Yönetici portalı](https://manage.visualstudio.com).

2. Tablonun üstündeki tek bir Visual Studio abonesi için bir lisans atamak için **Ekle**.

   ![Tek abone ekleme](media\add-single-subscriber.png)

3. Bilgileri yeni bir abone için form alanlara girin. Kuruluşunuz Azure Active Directory kullanıyorsa, bu alan doğru kullanıcı Arama sonuçlarından seçebilmeniz için kişi geçerli dizinde bulmak için bir arama işlevi görür. Söz konusu kişinin seçtikten sonra bunların adı, oturum açma e-posta ve bildirim e-posta otomatik olarak doldurulur. 

   ![Yeni bir bildirim e-posta adresi ekleyin](media\add-new-subscriber-notification-email.png)

   Oturum açtığınızda yazılım indirme işlemleri için erişim sağlamak için bu abone istiyorsanız [Visual Studio abonelikleri portalında](https://my.visualstudio.com?wt.mc_id=o~msft~docs), etkin indirmeler bırakmayı emin **indirme ayarları** bölümü. İndirmeler devre dışı bırakmak isterseniz, kullanıcı yazılım indirme işlemleri erişimi olmaz ancak aboneliğine dahil tüm avantajlara erişime sahip olmaya devam.

   ![İndirmelere erişim](media\access-to-downloads.png)

   Abone bilgi alır dilini değiştirmek istiyorsanız, bu nedenle, bunu yapabilirsiniz **iletişim tercihleri** bölümü.

   ![Bildirim e-postalar gönderildiğinde kullanılacak dili](media\change-subscriber-communication-preference.png)

   Kendi başvuru notları aboneliğe eklemek istiyorsanız, bu nedenle, bunu yapabilirsiniz **Başvurusu Ekle** bölümü.

   ![Her abonelik için kendi başvuru Not Ekle](media\add-subscriber-reference-notes.png) 

    Zaman seçim seçenekleri işiniz bittiğinde ve abone için veri girme seçin **Ekle** kısmındaki **abone ekleme** çıkış.

   ![Ekle düğmesini seçin.](media\add-button.png)

4. Abone ekledikten sonra yeni abone ile daha fazla yönerge için otomatik olarak atama e-posta gönderilir. Abone seçerek ve tıklayarak dilediğiniz zaman yeniden atama e-posta gönderebilir **Gönder** üst menü düğmesi.

   ![İstediğiniz zaman etkinleştirme e-posta bir veya birden çok kullanıcıya yeniden gönder](media\resend-subscriber-activation-emails.png) 

## <a name="bulk-assignments"></a>Toplu atama

1. Tek seferde birden çok abone ekleme için gidin **aboneleri yönetme** sekmesi. Üstteki Şeritte tıklayın **toplu ekleme**.

  ![Birden çok abone ekleme](media\add-multiple-subscribers.png)

1. Toplu atama aboneyi karşıya yükleme için Microsoft Excel şablonu kullanır. Birden çok aboneyi karşıya yükleme iletişim kutusuna tıklayın **indirme** şablonu indirilemedi.

  ![Excel şablonunu birden çok aboneyi karşıya yükle](media\download-template-upload-subscribers.png)

  >! [NOT] Her zaman bu şablonun en son sürümünü indirin. Eski bir sürümünü kullanıyorsanız, toplu karşıya yükleme işleminiz başarısız olabilir.

1. Excel elektronik tablosunda abonelikleri atamak istediğiniz kişiler için bilgilerle alanları doldurun. (*Başvuru* isteğe bağlı bir alandır.) Yerel olarak bitirdikten sonra dosyayı kaydedin.

  Kesintisiz bir karşıya yükleme emin olmak için aşağıdaki en iyi yöntemleri inceleyin:

    - Form alanlarını hiçbiri virgül içerdiğinden emin olun.
    - Form alanlardan önce ve sonra boşlukları Kaldır.
    - Kullanıcı adlarını iki parçalı ilk veya son adları arasındaki fazladan boşlukları içermiyor olduğundan emin olun (bir kişinin "Maggie olabilir" gibi iki parçalı ad varsa, sistem fazladan boşluk kesim gerekmez çünkü Örneğin, "MaggieMay" yazılmalıdır.)

1. Visual Studio abonelikleri Yönetim Portalı'na dönün. İçinde **birden çok aboneyi karşıya** iletişim kutusu, tıklayın **Gözat**.

  ![Birden çok aboneyi karşıya yükleme için kaydedilen şablonunuza göz atın](media\bulk-add-browse-saved-template.png)

1. Kaydettiğiniz Excel dosyasına gidin ve ardından **Tamam**.

  ![Excel şablonunu birden çok aboneyi karşıya yükleme](media\bulk-upload-subscribers.png)

  Bir karşıya yükleme ilerleme durumu iletişim kutusu görünür.

  Şablon hatalıysa, karşıya yükleme başarısız olur ve şablon düzeltin ve toplu karşıya yükleme yeniden deneme hatalar gösterilir.

  ![Birden çok aboneyi karşıya yüklenmesi başarısız olursa hata iletisi](media\bulk-add-template-failed.png)

  Karşıya yükleme başarılı olduğunda, aboneleri ve bir onay iletisi listesini görürsünüz.

  ![Birden çok aboneyi karşıya yükleme başarılı olursa onay iletisi](media\bulk-add-template-success.png)