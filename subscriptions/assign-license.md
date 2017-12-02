---
Title: Assign licenses to Visual Studio Subscriptions
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 10/3/2017
Ms.topic: Get-Started-Article
Description: Learn how administrators can assign licenses to subscribers
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: d9d26c9519ec5cca1f7127f93d9d1ab60378ad3f
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2017
---
# <a name="assigning-licenses-in-the-visual-studio-subscriptions-administrator-portal"></a>Visual Studio abonelikleri Yönetici portalı'nı lisansları atama
## <a name="assigning-a-single-user"></a>Tek bir kullanıcı atama
Visual Studio abonelikler için kullanılabilir lisans varsa, abonelik faydaları erişmek için yeni kullanıcılar için bunları için bu lisansları atayabilirsiniz. 
1.  Tablonun üstündeki tek bir Visual Studio abone atamak için tıklatın **Ekle**.

    ![Abonelik Ekle](_img\assign-license-add\assign-license-add.png)

2.  Bilgileri form alanlarına yeni abone için girin. Kuruluşunuz Azure Active Directory kullanıyorsanız, doğru kullanıcı Arama sonuçlarından seçebilmeniz için geçerli dizininizde kişiler bulmak için bir arama işlevini Bu alan görür. Bu kişi seçtiğinizde, aşağıda gördüğünüz gibi kendi adı, e-posta oturum açma ve bildirim e-posta otomatik olarak doldurur. 

Kuruluşunuzun dışındaki oturum açmak için kullanılacak e-postaları almak için bir başka e-posta erişimi varsa, burada girme seçeneğiniz vardır. "Farklı e-posta için oturum açma daha iletişimi?" gösterir köprüyü seçin. 

İçine imzaladığınızda yazılım yüklemeleri için erişim sağlamak için bu abone istiyorsanız [Visual Studio abonelikleri Portal](https:/my.visualstudio.com), indirmeler kutunun işaretli olduğundan emin olun. Bu kutunun işaretini kaldırdığınızdan seçerseniz, kullanıcı yazılım yüklemelerini erişebilir değil, ancak hala aboneliğine dahil tüm diğer avantajları erişebilir. İşiniz bittiğinde tıklatın **Ekle**.

  ![Abone bilgilerini girin](_img\assign-license-add\add-subscriber-1.png)

  ![Abone bilgilerini girin](_img\assign-license-add\add-subscriber-2.png)

3.  Abone eklendikten sonra bir atama e-posta otomatik olarak yeni abone daha ayrıntılı yönergeler için gönderilir. Abone seçerek ve tıklayarak herhangi bir zamanda yeniden atama e-posta gönderebilirsiniz **yeniden gönder** üst menü düğmesi.

    ![Abonelik eklendi](_img\assign-license-add\add-subscriber-complete.png)

## <a name="bulk-assignments"></a>Toplu atamaları
1.  Aynı anda birden çok abone eklemek için aboneler sekmesine gidin. Üst Şeritte tıklatın **toplu ekleme**. 

    ![Toplu ekleme](_img\assign-license-add\bulk-assign-add.png)

2. Toplu Ata aboneleri karşıya yüklemek için Microsoft Excel şablonu kullanır. Birden çok aboneye Karşıya Yükle iletişim kutusunda tıklatın **karşıdan** şablonu karşıdan yüklemek için. Her zaman bu şablonun en son sürümünü yükleyin. Eski bir sürümünü kullanıyorsanız, toplu yükleme başarısız olabilir.

![Birden çok aboneye karşıya yükle](_img\assign-license-add\bulk-assign-upload.png)

3.  Excel elektronik tabloda abonelikleri atamak istediğiniz kişiler bilgilerle alanları doldurun. Başvuru isteğe bağlı bir alandır. Şablonu herhangi bir kısmını yanlış doldurduktan, sorunu açıklayan bir hata iletisi görürsünüz. İşiniz bittiğinde sabit diskinizde dosyayı kaydedin.
**Kesintisiz bir karşıya yükleme sağlamaya yardımcı olmak için aşağıdaki en iyi yöntemleri inceleyin:**
    - Form alanlarını hiçbiri virgül içerdiğinden emin olun.
    - Alanları önce ve sonra kullanıcıların adları gibi form alanlarını kaldırın.
    - Kullanıcıların adları iki parçalı ilk veya son adları arasında ek boşluk içeremez emin olun (sistem boşluk kırpma değil olarak örneğin iki parçalı ad "Maggie olabilir" gibi "Maggie olabilir" yazılmalıdır değil)

    ![Toplu ekleme şablonu](_img\assign-license-add\bulk-template.png)

4.  İade Visual Studio abonelikleri Yönetim Portalı ve birden çok aboneye Karşıya Yükle iletişim kutusunda, tıklatın **Gözat**. Kaydettiğiniz Excel dosyasına gidin ve tıklatın **Tamam**. Ekranda karşıya yükleme ilerleme durumunu görürsünüz. 

    ![Toplu ekleme karşıya yükleme](_img\assign-license-add\bulk-assign-upload-2.png)

Bu nedenle şablonu hatalar içeriyor, karşıya yükleme başarısız olur ve hataları gösterilen şablon düzeltin ve toplu karşıya yükleme yeniden denemeden.

   ![Karşıya yükleme başarısız](_img\assign-license-add\bulk-assign-upload-fail.png)

Karşıya yükleme başarılı olduğunda, aboneleri ve bir onay iletisi listesini görürsünüz.

   ![Karşıya yükleme tamamlandı](_img\assign-license-add\bulk-assign-upload-complete.png)