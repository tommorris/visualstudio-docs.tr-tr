---
title: Visual Studio abonelik lisansları atama | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 10/03/2017
ms.topic: Get-Started-Article
description: Yöneticiler abonelere lisansları nasıl atayabilirsiniz öğrenin
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: 4325921bbaa75e0fb8a8a16947c45901b6f01649
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34477385"
---
# <a name="assigning-licenses-in-the-visual-studio-subscriptions-administrator-portal"></a>Visual Studio abonelikleri Yönetici portalı'nı lisansları atama

Visual Studio Abonelik Yöneticisi olarak, abonelikleri bireysel kullanıcılara atamak için Visual Studio abonelikleri Yönetici portalı'nı kullanabilirsiniz.  
Bir kerede atayın veya abonelik bilgileriyle aboneleri listelerini hızlı ve kolay bir şekilde yüklemek için "toplu Ekle" özelliğini kullanın. 

## <a name="assigning-a-single-user"></a>Tek bir kullanıcı atama
Visual Studio abonelikler için kullanılabilir lisans varsa, abonelik faydaları erişmek için yeni kullanıcılar için bunları için bu lisansları atayabilirsiniz. 
1.  Oturum [Yönetici portalı](https://manage.visualstudio.com)

2.  Tablonun üstündeki tek bir Visual Studio abone atamak için tıklatın **Ekle**.

    <img alt="Add subscriber" src="_img\assign-license-add\assign-license-add.png" style="border: 1px solid #CCCCCC" />

3.  Bilgileri form alanlarına yeni abone için girin. Kuruluşunuz Azure Active Directory kullanıyorsanız, bu alan arama sonuçlarından doğru kullanıcı seçebilmeniz için geçerli dizininizde kişiler bulmak için bir arama işlevini görür. Bu kişi seçtiğinizde, aşağıda gördüğünüz gibi kendi adı, e-posta oturum açma ve bildirim e-posta otomatik olarak doldurur. 

    Kuruluşunuz Azure Active Directory (Azure AD) kullanmıyor, ancak daha oturum açmak için kullanılacak e-postaları almak için bir başka e-posta varsa, burada girme seçeneğiniz vardır. "Farklı bir e-posta alıcı iletişimi için Ekle" etiketli köprüyü seçin. 

    **Erişim yüklemeler için:**  
    İçine imzaladığınızda yazılım yüklemeleri için erişim sağlamak için bu abone istiyorsanız [Visual Studio abonelikleri Portal](https://my.visualstudio.com?wt.mc_id=o~msft~docs), etkin yüklemeleri geçiş bıraktığınızdan emin olun. Yüklemeleri devre dışı bırakmak seçerseniz, kullanıcı yazılım yüklemelerini erişemeyecektir ancak hala aboneliğine dahil tüm diğer avantajları erişebilir. 
    
    Tamamladığınızda bu abone için seçenekleri belirleyerek, tıklatın **Ekle**.

    <img alt="Enter subscriber information" src="_img\assign-license-add\add-subscriber-1.png" style="border: 1px solid #CCCCCC" />
    <img alt="Enter subscriber information" src="_img\assign-license-add\add-subscriber-2.png" style="border: 1px solid #CCCCCC" />

4.  Abone eklendikten sonra bir atama e-posta otomatik olarak yeni abone daha ayrıntılı yönergeler için gönderilir. Abone seçerek ve tıklayarak herhangi bir zamanda yeniden atama e-posta gönderebilirsiniz **yeniden gönder** üst menü düğmesi.

    <img alt="Subscriber added" src="_img\assign-license-add\add-subscriber-complete.png" style="border: 1px solid #CCCCCC" />

## <a name="bulk-assignments"></a>Toplu atamaları
1.  Aynı anda birden çok abone eklemek için gidin **yönetmek aboneleri** sekmesi. Üst Şeritte tıklatın **toplu ekleme**. 

    <img alt="Bulk add" src="_img\assign-license-add\bulk-assign-add.png" style="border: 1px solid #CCCCCC" />

2. Toplu Ata aboneleri karşıya yüklemek için Microsoft Excel şablonu kullanır. Birden çok aboneye Karşıya Yükle iletişim kutusunda tıklatın **karşıdan** şablonu karşıdan yüklemek için. Her zaman bu şablonun en son sürümünü yükleyin. Eski bir sürümünü kullanıyorsanız, toplu yükleme başarısız olabilir.

    <img alt="Upload multiple subscribers" src="_img\assign-license-add\bulk-assign-upload.png" style="border: 1px solid #CCCCCC" />

3.  Excel elektronik tabloda abonelikleri atamak istediğiniz kişiler bilgilerle alanları doldurun. Başvuru isteğe bağlı bir alandır. Şablonu herhangi bir kısmını yanlış doldurduktan, sorunu açıklayan bir hata iletisi görürsünüz. Dosyayı yerel olarak bir kez yapılır.
**Kesintisiz bir karşıya yükleme sağlamaya yardımcı olmak için aşağıdaki en iyi yöntemleri inceleyin:**
    - Form alanlarını hiçbiri virgül içerdiğinden emin olun.
    - Alanları önce ve sonra kullanıcıların adları gibi form alanlarını kaldırın.
    - Kullanıcıların adları iki parçalı ilk veya son adları arasında ek boşluk içeremez emin olun (sistem boşluk kırpma değil olarak örneğin iki parçalı ad "Maggie olabilir" gibi "Maggie olabilir" yazılmalıdır değil.)
    <img alt="Bulk add template" src="_img\assign-license-add\bulk-template.png" style="border: 1px solid #CCCCCC" />

4.  İade Visual Studio abonelikleri Yönetim Portalı ve birden çok aboneye Karşıya Yükle iletişim kutusunda, tıklatın **Gözat**. Kaydettiğiniz Excel dosyasına gidin ve tıklatın **Tamam**. Ekranda karşıya yükleme ilerleme durumunu görürsünüz. 

    <img alt="Bulk add upload" src="_img\assign-license-add\bulk-assign-upload-2.png" style="border: 1px solid #CCCCCC" />

Bu nedenle şablonu hatalar içeriyor, karşıya yükleme başarısız olur ve hataları gösterilen şablon düzeltin ve toplu karşıya yükleme yeniden denemeden.
    <img alt="Upload fail" src="_img\assign-license-add\bulk-assign-upload-fail.png" style="border: 1px solid #CCCCCC" />

Karşıya yükleme başarılı olduğunda, aboneleri ve bir onay iletisi listesini görürsünüz.

   <img alt="Upload complete" src="_img\assign-license-add\bulk-assign-upload-complete.png" style="border: 1px solid #CCCCCC" />