---
title: Visual Studio abonelikler için oturum açma başarısız olabilir diğer adlar kullanırken | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 01/02/2018
ms.topic: Get-Started-Article
description: Diğer adlar veya kolay adlar kullanılıyorsa, oturum açma başarısız olabilir
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: 869835e53b1975d86501660b3e4ca34a41a1a7d4
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/06/2018
---
# <a name="signing-in-to-visual-studio-subscriptions-may-fail-when-using-aliases"></a>Visual Studio abonelikler için oturum açma diğer adlar kullanırken başarısız olabilir

Oturum açmak için kullandığınız hesap türüne bağlı olarak, kullanılabilir abonelikler doğru için oturum açarken görüntülenmeyebilir [ https://my.visualstudio.com ](https://my.visualstudio.com?wt.mc_id=o~msft~docs). Bir olası neden "aliases" veya "kolay adlar" kullanımını abonelik atandığı oturum açma kimliği yerine değildir. Bu, "yumuşatma" adı verilir. 

## <a name="what-is-aliasing"></a>Yumuşatma nedir?

"Yumuşatma" terimi farklı kimlikler sahip kullanıcılara Windows (veya Active Directory) oturum açın ve e-postaya erişmeye anlamına gelir.

Yumuşatma karşılaştı şirket Microsoft çevrimiçi hizmeti için kendi directory oturum açma gibi olduğunda JohnD@contoso.com, ancak kullanıcıların erişim gibi diğer adları veya kolay adlar kullanarak, e-posta hesaplarını John.Doe@contoso.com.  Toplu Lisanslama hizmeti Merkezi (VLSC) aracılığıyla aboneliği yöneten birçok müşteri için bu bir başarısız oturum açma deneyimi e-posta adresi olarak sağlanan sonuçlanabilir (John.Doe@contoso.com) dizin adresi eşleşmiyor (JohnD@contoso.com) "İş veya Okul hesabı" seçeneği aracılığıyla başarılı bir kimlik doğrulaması için gereklidir.

## <a name="as-an-administrator-what-options-do-i-have"></a>Yönetici olarak, hangi seçenekleri ı var mı?

Bir yönetici olarak abonelerinizin sahip başarılı bir oturum açma deneyimi sağlamak için iki seçenek vardır [ https://my.visualstudio.com ](https://my.visualstudio.com?wt.mc_id=o~msft~docs). 
- (Önerilen), ilk seçenektir directory hesabına atanan adresi içinde Toplu Lisanslama hizmeti Merkezi (VLSC) olarak yararlanmak için. Başvurmak [bir dizin hesabı atama abonelere](#assigning-subscribers-to-a-directory-account) daha fazla ayrıntı için bu makaledeki bölümü.
- (Daha az güvenli), ikinci seçenek olan kendi "Kişisel" hesap "İş veya Okul" e-posta adresine (paketini ilişkilendirilecek abonelerinizin izin vermek için Microsoft hesabı veya MSA). Başvurmak [bir iş veya Okul hesabı kişisel hesabıyla tanımlama ](#defining-a-work-or-school-account-as-a-personal-account ) daha fazla ayrıntı için bu makaledeki bölümü.

> [!NOTE]
> Şirketiniz yeni Visual Studio abonelikleri geçirildikten sonra [Yönetim Portalı](https://manage.visualstudio.com), bir parçası olarak sağlanacak dizin ve e-posta adresleri sağlayan yeni bir yönetim deneyimi yararlanmak olacaktır abonenin profili.  Daha fazla bilgi edinmek [geçiş](https://support.microsoft.com/help/4013930/visual-studio-subscriptions-administrator-migration-details).

## <a name="as-a-subscriber-what-options-do-i-have"></a>Bir abone olarak hangi seçenekleri ı var mı?

Abone açısından bakıldığında, yöneticiniz, şirketinizin kimlik yapılandırması anlamak için ilk çalışmak için önemlidir.  Gerekirse, yöneticiniz hesap ayarlarınızı kendi Yönetim Portalı'ndan güncelleştirmeniz gerekiyor olabilir veya bir Microsoft hesabı (MSA) kullanarak şirket e-posta adresinizi oluşturmanız gerekebilir.  Bir MSA oluşturmak için aşağıdaki adımları gerçekleştirmeden önce herhangi bir ilke veya bu eylemi gerçekleştirmeden sorunlar ilgili yöneticinizle konuşun.  Başvurmak [bir iş veya Okul hesabı kişisel hesabıyla tanımlama ](#defining-a-work-or-school-account-as-a-personal-account ) daha fazla ayrıntı için bu makaledeki bölümü.  

## <a name="assigning-subscribers-to-a-directory-account"></a>Bir dizin hesabı aboneleri atama 

Her durumda, yeni aboneler için dizin adresi kullanın veya "var" aboneleri için e-posta adresi güncelleştirmek Abonelik Yöneticisi'ni Toplu Lisanslama hizmeti Merkezi (VLSC) içinde gerekir.  Dizin adresini kullanarak tüm yeni aboneler Hoş Geldiniz e-posta almaz ve yönetici bir abonelik kendilerine atanmış olan abone bildir gerekecek anlamına gelir olduğunu dikkate almak önemlidir.  Aşağıdaki sonra aşağıdaki adımları, lütfen ayrıca e-posta kullanılacak çekinmeyin [şablonu](#notifying-your-subscribers-with-directory-addresses) abonelerinizin bilgilendirin ve oturum açma işleminde size yardımcı olmak için.

### <a name="adding-new-subscribers"></a>Yeni aboneler ekleme
Lütfen bir dizin hesabı ile yeni bir abonelik eklemek için aşağıdaki adımları izleyin.

1. Ziyaret [Toplu Lisans Hizmet Merkezi](https://www.microsoft.com/Licensing/servicecenter/default.aspx) (VLSC) ve oturum açın.
2. VLSC yönetim sayfasından tıklatın **abonelikleri** ve ardından **Visual Studio abonelikleri**.

    ![Abonelikleri menüsü](_img//vlsc/vlsc-subscriptions.png)

3. Tıklatın **anlaşma numarası** Visual Studio abonelikle ilişkili.

    ![Anlaşma Seç](_img/vlsc/vlsc-agreement.png)

4. Tıklatın **atamak abonelik**.

    ![Abonelik atayın](_img/vlsc/vlsc-assign.png)

5. İstenen seçin **abonelik düzeyinde**.

    ![Abonelik düzeyi](_img/vlsc/vlsc-subscription-level.png)
    
6. Doğrulama atayın ve kullanılabilir abonelikler sahip **sonraki**.
7.  E-posta adresi alanı abone ayrıntıları ve dizin adresi girip'ı tıklatın **sonraki**.

    ![E-posta Adresi](_img/vlsc/vlsc-email-address.png)
    
8. Abone bilgisi doğrulamak ve tıklatın **son**.

9. Aboneliğini kullanarak sağlanmış abone bildir aşağıda [şablon](#notifying-your-subscribers-with-directory-addresses).

### <a name="updating-an-existing-subscriber"></a>Mevcut bir aboneyi güncelleştiriliyor
Lütfen izleyin sahip bir dizin hesabı var olan aboneyi güncelleştirmek için aşağıdaki adımları.

1. Ziyaret [Toplu Lisans Hizmet Merkezi](https://www.microsoft.com/Licensing/servicecenter/default.aspx) (VLSC) ve oturum açın.

2. VLSC yönetim sayfalarından tıklatın **abonelikleri** ve ardından **Visual Studio abonelikleri**.

3. Tıklatın **anlaşma numarası** Visual Studio abonelikle ilişkili.

4. Tıklatın **aşağı ok** arama çubuğunda.

5. "E-posta adresi" alanını kullanarak abone arayın.

6. Sonuçları listesinden tıklatın **Soyadı** abonenin.

7. 
              **Düzenle**‘ye tıklayın.

8. İstenen dizin adresine e-posta adresi alanı değiştirin ve **kaydetmek**.

9. Aboneliğini kullanarak sağlanmış abone bildirim e-posta şablonu aşağıda.

### <a name="notifying-your-subscribers-with-directory-addresses"></a>Dizin adresleriyle abonelerinizin bildirme
Hoş Geldiniz e-posta, abone başarılı bir şekilde ulaşmaz olduğundan, Lütfen kopyalama ve yapıştırma bir e-posta ve gönderme, aboneye iletisine aşağıda. Her abonelik için uygun bilgilerle WORD % değiştirin.

----------- Copy Below (Ctrl+C) -----------

Merhaba % abone adı %

Visual Studio abonelik atanmıştır.  Lütfen şu adresi ziyaret https://my.visualstudio.comve etkinleştirmek ve aboneliğinizi erişmek için % dizin adresi % adresinizi oturum. 

Sorun yaşıyorsanız Lütfen Destek ekibine başvurun (https://www.visualstudio.com/subscriptions/support/).

Sayfanın alt kısmındaki aşağıdakileri seçin:
   - Hesapları, abonelikleri ve faturalama desteği
   - Sorundan, abonelik oturum desteği seçin.
   - İlgili ülke seçin
   - İstenen Yardım ve Destek seçeneğini belirleyin

---Son kopyalama---



## <a name="defining-a-work-or-school-account-as-a-personal-account"></a>Bir iş veya Okul hesabı kişisel hesabıyla tanımlama 
Lütfen bölümünde açıklanan yönergeleri yararlanan [bir dizin hesabı atama abonelere](#assigning-subscribers-to-a-directory-account) yeni bir kullanıcı eklemek veya bir kullanıcının e-posta adresi içinde Toplu Lisanslama hizmeti Merkezi (VLSC) güncelleştirmek için bölüm.  Burada e-posta adresi directory tarafından tanınmıyor durumlarda, kullanıcının e-posta adresi kişisel hesap tanımlamak için yeni bir hesap oluşturma işlemi adım adım gerekecektir.  Kısa vadeli için Visual Studio abonelikleri takım aşağıda tanımlanan Kimlik İlkesi bir muafiyet güvenli var. ancak Biz bu ilkeyi kaldırmak gerekli özellikleri yatırım.

> [!WARNING]
> Microsoft, "Kişisel" kimlik "İş veya Okul" kimliklerle birleştirme önermez.  Bu eylem kuruluş sahipliği ve denetimi hesabının kaybetmenize neden olur ve çalışan bile şirket bırakarak sonra belirli ürünleri veya hizmetleri, erişmeye devam edebilirsiniz.  Lütfen bu başvuru [blog gönderisi](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/15/cleaning-up-the-azure-ad-and-microsoft-account-overlap/), ek bilgi için Microsoft Identity ekibinden.

### <a name="defining-an-email-address-as-a-personal-account"></a>Bir e-posta adresi kişisel hesap tanımlama
Bir abonelik için abonelik atandıktan sonra bunları ziyaret etmek isteyen bir e-posta alırsınız https://my.visualstudio.com abonelik faydaları yararlanmak için.  Çalışılırken oturum açma, Visual Studio abonelik oturum açma bir hesap tanınmıyor belirten hata ile başarısız olur.  Önce oturum içine https://my.visualstudio.com deneyimi, aşağıdaki yönergeleri izleyin, abone isteyin.  Gerekirse, bu kullanabilirsiniz, [şablonu](#notifying-your-subscribers-using-personal-accounts) bir abonelik atandıktan sonra abone bildirmek için.

1. Gidin https://my.visualstudio.com, tıklatıp **yeni bir Microsoft hesabı oluşturmak**.

2. Alanları doldurun:
    - Hoş Geldiniz e-postayla alınan e-posta adresi girin Someone@example.com kutusu
    - Parolanızı oluşturun
    - Promosyon ayarlarınızı seçin
    - **İleri**'ye tıklayın.

3. Doğrulama adımları tamamlayın ve tıklatın **sonraki**.

4. Yeni kullanıcılar, Visual Studio profil gerçekleştirmeniz gerekebilir.

5. Abonelik ve avantajları artık görünür olması gerekir.

### <a name="notifying-your-subscribers-using-personal-accounts"></a>Kişisel hesapları kullanarak abonelerinizin bildirme

Yukarıda özetlenen senaryoda, abone bir "Hoş Geldiniz e-posta" alırsınız, ancak yumuşatma nedeniyle oturum açamıyor buldukları.  Kullanabileceğiniz altındaki metin, yukarıdaki adımları abonesi bilgilendirin ve gerekirse destek seçenekleri öneririz.  Her abonelik için uygun bilgilerle WORD % değiştirin.

----------- Copy Below (Ctrl+C) -----------

Merhaba % abone adı %

Visual Studio abonelik atandığından ve oturum açın yönlendirilmiş https://my.visualstudio.com Hoş Geldiniz e-postalarınızı tabanlı.  Bu avantajlar tüketimi için doğru Web sitesi olmakla birlikte, kuruluşunuzun site erişebilmeniz için bazı ek adımlar gerektirir.  Lütfen izleyin, "Microsoft bizim şirket e-posta adresine bağlı Account" oluşturmanıza yardımcı olacak yönergeler aşağıda.  Bu adımları tamamladıktan sonra abonelik avantajları erişmek için e-posta adresinizi kullanır.
1. Ziyaret edin https://my.visualstudio.com

2. Sağ taraftaki oluştur yeni Microsoft Account tıklayın

3. Formu doldurun: 
    - Şirket e-posta adresinizi someone@example.com kutusu
    - Bir parola girin
    - Promosyon tercihinizi seçin
    - İleri'yi tıklatın

4. Hesap doğrulama adımları tamamlayın

5. Gerekirse, Visual Studio profilini tamamlayın

6. Şimdi Avantajlarınızı görmeniz gerekir

Not: ziyaret eden https://my.visualstudio.com gelecekte (örneğin, kullanmak istediğiniz hangi hesap seçmek için istenebilir "İş veya Okul hesabı" veya "Kişisel hesap").  Yukarıdaki adımları tamamladıktan sonra "Kişisel hesap" seçeneğini yararlanan gerekecektir.

Sorun yaşıyorsanız Lütfen Destek ekibine başvurun (https://www.visualstudio.com/subscriptions/support/).

Sayfanın alt kısmındaki aşağıdakileri seçin:
   - Hesapları, abonelikleri ve faturalama desteği
   - Sorundan, abonelik oturum desteği seçin.
   - İlgili ülke seçin
   - İstenen Yardım ve Destek seçeneğini belirleyin

---Son kopyalama---