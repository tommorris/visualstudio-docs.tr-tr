---
title: Visual Studio abonelikleri Yönetici portalı'nda yönetici hakları yönetme
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 1/19/2018
Ms.topic: Get-Started-Article
Description: Learn how manage admins & super admins in the Visual Studio Subscriptions Administrator Portal.
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 83bf27d5aaa99c2095ad8a1fafd7541df90f316b
ms.sourcegitcommit: a0a49cceb0fdc1465ddf76d131c6575018b628b8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2018
---
# <a name="managing-administrator-rights-in-the-visual-studio-subscriptions-administrator-portal"></a>Visual Studio abonelikleri Yönetici portalı'nda yönetici hakları yönetme

## <a name="overview"></a>Genel Bakış 
Visual Studio abonelikleri Yönetici portalı'nda (https://manage.visualstudio.com), iki Yönetim rolü vardır:

**Süper yönetici:** bir kuruluş ilk ayarlama bağlı birincil ya da bildirimler kişi Süper yönetici varsayılan olarak olur. Birincil ya da bildirimler kişi ek Süper admins ya da yöneticiler atamak seçebilirsiniz. Tek tek aboneleri için abonelikler yönetmeye ek olarak, süper yöneticileri ekleyin ve diğer yöneticiler ve Süper admins kaldırın. Sistemde ikiden fazla Süper admins varsa, bir süper Yönetici güvenlik için son iki dışında tümünü silebilirsiniz. 

**Yöneticiler:** yönetici aboneleri Süper yönetici bunlara atar anlaşmaları yönetebilirsiniz.  Abonelikleri kişilere atayın, abonelikler, düzenleme ve yeniden atama açabilecekleri bunları kaldırın.   (Yöneticiler Süper yöneticileri tarafından tayin.)  

## <a name="adding-an-administrator-with-super-admin-rights"></a>Yönetici ekleme **ile** Süper yönetici hakları:

1. Visual Studio abonelikleri oturum [Yönetici portalı](https://manage.visualstudio.com) zaten Süper yönetici haklarına sahip bir hesabı kullanarak.

2. Tıklayın **yönetmesine** sayfanın üst kısmındaki sekme. (Süper yöneticileri Bu sekme yalnızca erişebilir.  Yöneticiler Süper yönetici hakları kullanmadan **yönetmek aboneleri** tek tek aboneleri yönetmek için sekme.)

3. Tıklatın **Ekle** yeni bir yönetici oluşturmak için. 

4. Tüm istenen ayrıntıları Yöneticisi Ekle açılır pencerede doldurun.
  - Kuruluşunuz Azure Active Directory (AAD) içinde zaten kaydedilmişse adını yazmaya başlayın **adı** alan ve doğru öğeyi aşağı açılan listesinde seçin. Yeni kullanıcılar ile tam adını yazın ve göz ardı *bulunan hiçbir kimlikleri* bildirim.
  - Doğru kullanıcı belirlendikten sonra oturum açma e-posta adresi alanı otomatik olarak doldurulur. Henüz sağladıysanız yeni yöneticinin e-posta adresi yazın.

5. Seçin **PCN** altındaki açılır listede tıklayarak yönetmek için yeni yönetim istediğiniz **anlaşmaları**. Onboarding olduğunuz PCN altındaki birden fazla sözleşmesi varsa, erişimli anlaşmaları bir bölümünü veya tamamını yöneticiniz sağlayabilir. 

**Daha fazla sözleşmelerine:** kullanılabilir yalnızca tek bir anlaşma olduğunda anlaşmaları altındaki açılan işlevselliği devre dışı bırakıldı.  Süper yönetici hakları yapılandırmakta kullanıcı verildiğinde tüm anlaşmalar otomatik olarak denetlenir.

6. Tıklatın **Süper yönetici** Bu yönetici için süper yönetici hakları etkinleştirmek için.  

7. Bu yönetici ekleme işlemini tamamlamak için tıklatın **Ekle**.

**Yöneticileri eklenirken alınan olası hata:** bazı kullanıcılar yönetici eklenmeye çalışılırken bir hata iletisi alabilirsiniz. Eklenmekte olan Süper yöneticinin e-posta adresi şirket AAD'de listelenmemişse oluştuğu budur. Yeni yönetici ekleme işlemini sonlandırmak için basitçe hatayı yok sayıp öğesini tıklatıp **Ekle** yeniden. 

8. Süper yönetici oluşturulduktan sonra Yöneticiler listesinde görürsünüz ve hesaplarına Süper yönetici durumlarını göstermek için yeşil bir onay işareti işaretlenir. 

### <a name="optional--add-a-different-notification-email"></a>İsteğe bağlı: farklı bildirim e-posta ekleyin.
Kuruluşunuz farklı bir adres sahip / hesabı alma için e-postalar, artık "İletişim" adresi girmek için bir seçenek vardır Seçin **iletişim almak için bir farklı bildirim e-posta ekleme**. 

*Örnek:* ye kullanan rene@contoso.com kendisinin açtığında kendi şirket kimlik bilgilerini kullanarak.  Ancak, ye'nın şirket yalnızca bu adrese dizin erişimi yönetmek için kullanır.  E-posta gönderilip alınırken ye kullanan rene.collado@contoso.com, müşterinin Süper yönetici kendisinin alır Hoş Geldiniz postalar emin olmak için ikinci bir adres girmiştir.  Şirketiniz bu şekilde yapılandırılmazsa, yalnızca oturum açma e-posta adresini girerek yeterli olacaktır.

## <a name="adding-an-administrator-without-super-admin-rights"></a>Yönetici ekleme **olmadan** Süper yönetici hakları:

Aynı işlem yukarıda açıklandığı gibi Yöneticiler Süper yönetici hakları, ancak aşağıdaki açıları dikkate alarak olmadan eklemek için izlenmesi:
-  Yöneticiler Süper yönetici hakları olmadan eklerken, eklenecek ek e-posta adresi gerek yoktur ve Süper yönetici onay kutusu boş kalır.
-  Süper yönetici hakları olmayan kullanıcıları kendi profili yapılandırma girişinde "Yönetmesine" altında yeşil denetleyin simgesi almaz.
