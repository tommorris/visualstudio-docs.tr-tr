---
title: Birden çok kullanıcı hesabıyla çalışma
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: edbe53458eafa833287cf48fec4870987a8ba81b
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749177"
---
# <a name="work-with-multiple-user-accounts"></a>Birden çok kullanıcı hesabıyla çalışma

Birden çok Microsoft hesabına ve/veya iş veya Okul hesapları varsa, böylece için ayrı olarak oturum açmak zorunda kalmadan herhangi bir hesabı kaynaklara erişebilir, bunları tüm Visual Studio ekleyebilirsiniz. Şu anda Azure, Application Insights, Team Foundation Server ve Office 365 Hizmetleri kolaylaştırılmış oturum açma deneyimini destekler. Ek Hizmetleri zaman devam ettiği kullanılabilir duruma gelebilir.

Bir makine üzerinde birden fazla hesap ekledikten sonra Visual Studio için başka bir makinede oturum hesapları kümesini sizinle dolaşıma. Hesap adlarını dolaşan rağmen kimlik bilgilerini desteklemez, dikkate almak önemlidir. Bu nedenle, yeni makineye kaynaklarını kullanma girişimi ilk kez diğer bu hesaplar için kimlik bilgilerini girmeniz istenir.

Bu anlatımda Visual Studio'ya birden fazla hesap ekleme gösterilir ve bu hesaplarından erişilebilir kaynakları yansıtılır görmek nasıl yerleştirir gibi **bağlı hizmet Ekle** iletişim kutusunda, **Sunucu Gezgini** , ve **Takım Gezgini**.

## <a name="sign-in-to-visual-studio"></a>Visual Studio’da oturum açma

- Visual Studio uygulamasına bir Microsoft hesabı veya kurumsal bir hesap ile oturum açın. Kullanıcı adınızın, aşağıdakine benzer şekilde penceresinin üst köşesindeki görünmesi görmeniz gerekir:

     ![Kullanıcı oturum Currentlly](../ide/media/vs2015_username.png)

### <a name="access-your-azure-account-in-server-explorer"></a>Sunucu Gezgininde Azure hesabınıza erişin

Tuşuna **Ctrl**+**Alt**+**S** açmak için **Sunucu Gezgini**. Seçin **Azure** simgesi ve ne zaman, genişletir, Visual Studio'ya oturum açmak için kullanılan kimliği ile ilişkili Azure hesabında kaynaklardır görmeniz gerekir. Ancak bu (kendi kaynakları görürsünüz) aşağıdakine benzer görünmelidir.

![Sunucu Gezgini gösteren Azure Araçları düğümünün genişletilmiş](../ide/media/vs2015_serverexplorer.png)

Visual Studio belirli bir cihazda ilk kullanışınızda iletişim yalnızca IDE'ye ile imzalanmış kimliği kayıtlı abonelikleri gösterir. Herhangi diğer hesaplarınızı doğrudan kaynaklara erişebilir **Sunucu Gezgini** sağ tıklayarak **Azure** düğümü ve seçme **yönetin ve filtre abonelikleri**ve hesap Seçici denetiminden hesaplarınızı ekleme. Başka bir hesap ardından, isterseniz aşağı oka tıklayarak ve hesapları listesinden seçim tarafından da seçebilirsiniz. Hesap seçtikten sonra hangi abonelikleri görüntülemek istediğiniz bu hesap altında seçebilirsiniz **Sunucu Gezgini**.

![Azure abonelikleri iletişim yönetme](../ide/media/vs2015_manage_subs.png)

Bir sonraki açışınızda **Sunucu Gezgini**, bu aboneliği için kaynakları görüntülenir.

### <a name="access-your-azure-account-via-add-connected-service-dialog"></a>Bağlı hizmet Ekle iletişim kutusu üzerinden Azure hesabınıza erişin

1. C# dilinde bir UWP uygulaması projesi oluşturun.

1. Proje düğümünde seçin **Çözüm Gezgini** ve ardından **Ekle** > **bağlı hizmet**. **Bağlı hizmet Ekle** Sihirbazı görünür ve Visual Studio oturum açma kimliğiyle ilişkili Azure hesabında hizmetlerin listesini gösterir Azure için ayrı olarak oturum açmak zorunda değilsiniz unutmayın. Ancak, diğer hesapları için belirli bir bilgisayardan kaynaklarına erişme girişimi ilk kez oturum açmak gerekir.

    > [!WARNING]
    > Bu ilk kez ise Visual Studio'da belirli bir bilgisayarda bir UWP uygulaması oluşturuyorsanız, giderek cihazınız için geliştirme modunu etkinleştirmek için istenir **ayarları** > **güncelleştirmeleri ve güvenlik**  >  **İçin geliştiriciler** bilgisayarınızda. Daha fazla bilgi için bkz: [cihazınız geliştirme için etkinleştirme](/windows/uwp/get-started/enable-your-device-for-development).

### <a name="access_azure"></a> Erişim Azure Active Directory'de bir Web projesi

Azure AD son kullanıcı çoklu oturum açma ASP.NET MVC web uygulamaları veya Web API Hizmetleri AD kimlik doğrulaması için destek sağlar. Etki alanı kimlik doğrulaması, tek tek kullanıcı hesabı kimlik doğrulamasını farklıdır; Active Directory etki alanınıza erişimi olan kullanıcılar, web uygulamalarınızı bağlanmak için var olan Azure AD hesaplarına kullanabilirsiniz. Office 365 uygulamaları, etki alanı kimlik doğrulamasını da kullanabilirsiniz. Bu eylem görmek için bir web uygulaması oluşturma (**dosya** > **yeni proje** > **C#** > **bulut**  >  **ASP.NET Web uygulaması**). İçinde **yeni ASP.NET projesi** iletişim kutusunda, seçin **kimlik doğrulamayı Değiştir**. Kimlik Doğrulama Sihirbazı'nı görünür ve uygulamanızda kullanılacak kimlik doğrulama türlerini seçmenize olanak tanır.

![ASP.NET kimlik doğrulaması iletişim kutusu değişimi](../ide/media/vs2015_change_authentication.png)

ASP.NET kimlik doğrulaması farklı türleri hakkında daha fazla bilgi için bkz: [oluşturma ASP.NET web projeleri Visual Studio 2013'te](http://www.asp.net/visual-studio/overview/2013/creating-web-projects-in-visual-studio#orgauth) (kimlik doğrulaması hakkında bilgi hala geçerli Visual Studio sürümleri için geçerlidir).

### <a name="access-your-visual-studio-team-services-account"></a>Visual Studio Team Services hesabınıza erişemiyor

Ana menüden **takım** > **Team Foundation Server'a Bağlan** ortaya çıkarmak için **Takım Gezgini** penceresi. Tıklayın **takım projelerini seçin**ve ardından altında liste kutusunda **Team Foundation Server Seç**, Visual Studio Team Services hesabınız için URL görmeniz gerekir. URL seçtiğinizde, kimlik bilgilerinizi yeniden girmek zorunda kalmadan oturum açmanız.

## <a name="add-a-second-user-account-to-visual-studio"></a>Visual Studio için ikinci bir kullanıcı hesabı Ekle

Visual Studio üst köşedeki kullanıcı adınıza yanındaki aşağı oka tıklayın. Ardından **hesap ayarlarını** menü öğesi. **Hesap Yöneticisi** iletişim kutusu görüntülenir ve oturum ile hesabı görüntüler. Seçin **Hesap Ekle** yeni bir Microsoft hesabı veya yeni bir iş veya Okul hesabı eklemek için iletişim kutusunun alt köşedeki bağlantı.

![Visual Studio hesap Seçici](../ide/media/vs2015_acct_picker.png)

Yeni hesap kimlik bilgilerini girmek için istemleri izleyin. Aşağıdaki çizimde gösterildiği **Hesap Yöneticisi** bir kullanıcı parolasını ekledikten sonra *Contoso.com* iş hesabı.

![Hesap Yöneticisi](../ide/media/vs2015_accountmanager.gif)

## <a name="revisit-the-add-connected-services-wizard-and-server-explorer"></a>Bağlı hizmetler Ekleme Sihirbazı'nı ve Sunucu Gezgini yeniden ziyaret

Şimdi gidin **Sunucu Gezgini** tekrar sağ tıklayın **Azure** düğümü seçin **yönetin ve filtre abonelikleri**. Geçerli hesap yanında aşağı açılan tıklatarak yeni hesabı seçin ve ardından görüntülemek istediğiniz abonelikleri seçin **Sunucu Gezgini**. Belirtilen abonelikle ilişkili tüm hizmetlerin görmeniz gerekir. Şu an için Visual Studio IDE ikinci hesabı ile oturum olsa bile, bu hesabın hizmet ve kaynakların oturum açtınız. Aynı için doğrudur **proje** > **bağlı hizmet Ekle** ve **takım** > **TeamFoundationServer'aBağlan**.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio’da oturum açma](signing-in-to-visual-studio.md)
