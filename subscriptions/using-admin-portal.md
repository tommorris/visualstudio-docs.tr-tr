---
title: Yönetici portalı'nı kullanarak | Visual Studio Market
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 10/03/2017
ms.topic: Get-Started-Article
mescription: Learn how to manage your organization's Visual Studio subscriptions with the Administrator Portal.
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: 22351b94923777d5eb1fe40cd2e43e9dc20f2449
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/06/2018
---
#  <a name="using-the-visual-studio-subscriptions-administrator-portal"></a>Visual Studio abonelikleri Yönetici portalı'nı kullanarak

Visual Studio abonelikleri Yönetim Portalı'nı kullandığınızda, bunu göz önünde bulundurun:
 
- **Visual Studio abonelikleri kullanıcı başına lisanslanır.** Her abone yazılım geliştirme ve test için gerektiği şekilde sayıda bilgisayarlarda kullanabilirsiniz. 
- **Her abone için yalnızca bir abonelik düzeyi atayın**, kuruluşunuzun satın aldığı Visual Studio abonelik için ilgili. Kendisine atanmış birden fazla abonelik düzeyinde aboneleri varsa, bunların yalnızca birini böylece ayarlarını düzenleyin. 
- **Bir abonenin abonelik düzeyinde güncelleştirilmesi gereken** zaman abonelik (satın alınmış bir "geçmeksizin" Lisans sonra) yükseltti veya daha düşük düzeyde yenilendi. 
- **Abonelikleri aboneleri arasında paylaşmayın.** Abonelik avantajları (yazılım geliştirme ve test, Microsoft Azure e-öğrenme, vs.) bölümünü veya tümünü kullanan herkes için bir abonelik atamanız gerekir. 

## <a name="adminstrator-roles"></a>Yönetici rolleri

Yeni Visual Studio abonelikleri Yönetim Portalı'nda mevcut toplu lisans müşterileri için iki farklı roller vardır. Bu rolleri birincil/bildirimler kişi rolü ve VLSC abonelikleri Yöneticisi rolünde bugün gibidir. 

**Süper yönetici:** bir kuruluş ilk ayarlama bağlı birincil ya da bildirimler kişi Süper yönetici varsayılan olarak olur. Birincil ya da bildirimler kişi ek Süper admins ya da yöneticiler atamak seçebilirsiniz. Süper yönetici ekleyebilir ve abonelerin yanı sıra diğer yöneticiler kaldırabilirsiniz. Sistemde ikiden fazla Süper admins varsa, süper Yönetici güvenlik için son iki dışında tümünü silebilirsiniz. 

**Yöneticiler:** yönetici Süper Yöneticisi tarafından yalnızca ayarlanabilir Bir yönetici aboneleri Süper yönetici bunlara atar anlaşmaları yönetebilirsiniz. 

## <a name="getting-started"></a>Başlarken

Kuruluşunuzun Aboneliklerini yönetmek için Yönetici portalı'nı kullanabilmeniz için kuruluşunuzun portalına ilk yerleşik gerekir.  Onboarding tamamladıktan sonra bunlar burada, araçları ve abonelik yönetimi görevlerini gerçekleştirmek için gereken bilgileri bulabilirsiniz olarak aboneleri ve ayrıntıları sayfalarıyla aşina istersiniz.  

### <a name="onboarding"></a>Ekleme

Kuruluşunuz Visual Studio abonelikleri yönetim portalına edildi olması hazır olduğunda bir e-posta birincil ve bunları davet kişiler bildirimler ekleme işlemini tamamlamak için gönderilir. Aşağıdaki ayrıntıları yeni portalına onboarding için yapılması gereken adımlar yer almaktadır. Gözden geçirme işleminin isterseniz, bu denetleyin [yönetici ekleme video](https://channel9.msdn.com/Series/Visual-Studio-Subscriptions-Administration/Onboarding-your-organization-to-the-new-Visual-Studio-Subscription-Administration-Portal-and-setting) ya da bu [destek makalesine](https://support.microsoft.com/help/4013931/visual-studio-subscriptions-administrator-migration-process "Visual Studio abonelikleri yönetici geçiş işlemi").   
1.  **PCN bulma ve oturum açma:**
    - E-posta ile birincil ve bildirimler kişiler benzersiz bir bağlantı ve bunların genel müşteri numarası (PCN), son üç basamak ile sağlanır. * 
    - Tüm PCN elde etmek için birincil ilgili kişinin VLSC'ye oturum açmak gerekir (PCN bulmak için yönergeler vardır bulunabilir). 
    - PCN aldıktan sonra bunları oturum açmak için ister kendi benzersiz bağlantı seçmeniz gerekir. Bunlar, kuruluşunuzun AAD üzerinde değilse, bir iş/Okul hesabı (Kuruluşunuz AAD üzerinde ise) ya da bir Microsoft hesabı (MSA) kullanarak oturum mümkün olacaktır. 
    - Ardından, bunlar PCN girmeniz gerekir. 
2.  **Yöneticilerinizi ayarlayın.** PCN girdikten sonra yeni sisteminde Süper Yöneticisi olarak kaydedilir ve diğer Süper yöneticileri ve administrators (daha önce Abonelik Yöneticisi olarak da bilinir) eklemeniz mümkün olacaktır. Bu erişim kaybını önlemek için kuruluşunuzun geçiş tarihinden önce tamamlanmalıdır. 
3.  **Yeni Abonelik Yönetim portalına erişim.**  Kuruluşunuz geçirildikten sonra e-postalar yeni eklenen Süper yöneticileri ve yeni portalına erişmek ve abonelik yönetimi başlamak için Yöneticiler bunları davet gönderilir.  

> [!NOTE]
> Birincil ya da bildirimler kişiler birden fazla e-posta almaya devam ederseniz, bu, birden fazla PCN sahip oldukları anlamına gelir. Her email.* başvurulan PCN için benzersiz bağlantıyı kullanarak işlemini tamamlamak gerekir

Yeni Visual Studio abonelikleri yönetim portalına eklenmesi gerekir ve, birincil/bildirimler kişiniz olan emin değilseniz, oturum açtıktan sonra bu bilgileri bulabilirsiniz [VLSC](https://www.microsoft.com/Licensing/servicecenter/default.aspx). Göz atın [Bul bilgisayarınızı birincil ilgili kişinin](/find-primary-contact/) birincil/bildirimler kişiniz VLSC bulmak için adımları için konu.
Zaten bir yönetici olarak ayarlanmış olan sonra doğrudan gidebilirsiniz [Visual Studio abonelikleri Yönetim Portalı](https://manage.visualstudio.com).

### <a name="understanding-the-subscribers-page"></a>Aboneler sayfa anlama
Abonelikleri atadığınız sonra aboneler sekmesi dahil olmak üzere abonelerinizin hakkında ayrıntılı bilgi sağlar:
- Her abone ilk ve son adı.
- Bu kullanıcı için e-posta adresi.
- Kendisine atanmış abonelik düzeyi.
- Aboneliğini atanmış tarih. 
- Aboneliğini sona erme tarihi.
- Bir isteğe bağlı metin açıklaması.
- Abone olup indirir, ilişkin bir gösterge etkin veya devre dışı. 
- Bunlar bulunduğu ülke.
- Yönetim Portalı'ndan kendi dil tercihi atama iletişim e-posta için.
- Oturum açma daha iletişimleri için kullanılan farklı bir e-posta adresi için isteğe bağlı bir alan. 

Bu sayfanın sol tarafında, abonelik lisanslarını satın alınan, atanan ve kuruluşunuzdaki her anlaşması için hala kullanılabilir sayısı hakkında ek bilgi görebilirsiniz.

   ![Visual Studio abonelikler Yönetici portalı Subscibers sayfası](_img/using-admin-portal/subscribers-page.png)

### <a name="understanding-the-details-page"></a>Ayrıntılar sayfası anlama
Görüntülemekte olduğunuz Sözleşmesi hakkında daha fazla bilgi için Ayrıntılar sekmesini seçin. Sözleşmesi durumu gösterir, hesap, kuruluş ayrıntıları, birincil kişiler (VLSC), süper yöneticileri (varsa) ve diğer ilgili bilgileri satın alın.

   ![Visual Studio abonelikleri Yönetici portalı Ayrıntıları sayfası](_img/using-admin-portal/details-page.png)

