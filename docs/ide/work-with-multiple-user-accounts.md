---
title: "Birden çok kullanıcı hesabı ile çalışma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b73c865c-74e0-420e-89cc-43524f4aafd0
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 33f8c8c8068f14d7cdf8bf32c4cff960b98957f0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="work-with-multiple-user-accounts"></a>Birden çok kullanıcı hesabıyla çalışma

Birden çok Microsoft hesabına ve/veya iş veya Okul hesapları varsa, böylece için ayrı olarak oturum açmak zorunda kalmadan herhangi bir hesabı kaynaklara erişebilir, bunları tüm Visual Studio ekleyebilirsiniz. Şu anda Azure, Application Insights, Team Foundation Server ve Office 365 Hizmetleri kolaylaştırılmış oturum açma deneyimini destekler. Ek Hizmetleri zaman devam ettiği kullanılabilir duruma gelebilir.

Bir makine üzerinde birden fazla hesap ekledikten sonra Visual Studio için başka bir makinede oturum hesapları kümesini sizinle dolaşıma. Hesap adlarını dolaşan rağmen kimlik bilgilerini desteklemez, dikkate almak önemlidir. Bu nedenle, yeni makineye kaynaklarını kullanma girişimi ilk kez diğer bu hesaplar için kimlik bilgilerini girmeniz istenir.

Bu anlatımda Visual Studio'ya birden fazla hesap ekleme gösterilir ve bu hesaplarından erişilebilir kaynakları yansıtılır görmek nasıl yerleştirir gibi **bağlı hizmet Ekle** iletişim kutusunda, **Sunucu Gezgini** , ve **Takım Gezgini**.

## <a name="sign-in-to-visual-studio"></a>Visual Studio'da oturum açın

- Visual Studio uygulamasına bir Microsoft hesabı veya kurumsal bir hesap ile oturum açın. Kullanıcı adınızın, aşağıdakine benzer şekilde penceresinin üst köşesindeki görünmesi görmeniz gerekir:

     ![Currentlly oturum açmış kullanıcı](../ide/media/vs2015_username.png "VS2015_UserName")

### <a name="access-your-azure-account-in-server-explorer"></a>Sunucu Gezgininde Azure hesabınıza erişin

Tuşuna **Ctrl + Alt + S** açmak için **Sunucu Gezgini**. Azure simgesini ve ne zaman, genişletir, Visual Studio'ya oturum açmak için kullanılan kimliği ile ilişkili Azure hesabında kaynaklardır görmelisiniz seçin. Ancak bu (kendi kaynakları görürsünüz) aşağıdakine benzer görünmelidir.

![Sunucu Gezgini gösteren Azure Araçları düğümünün genişletilmiş](../ide/media/vs2015_serverexplorer.png "VS2015_ServerExplorer")

Visual Studio belirli bir cihazda ilk kullanışınızda iletişim yalnızca IDE'ye ile imzalanmış kimliği kayıtlı abonelikleri gösterir. Herhangi diğer hesaplarınızı doğrudan kaynaklara erişebilir **Sunucu Gezgini** Azure düğümde sağ tıklayarak ve seçme **yönetin ve filtre abonelikleri** ve, hesapları ekleme Hesap Seçicisi. Başka bir hesap ardından, isterseniz aşağı oka tıklayarak ve hesapları listesinden seçim tarafından da seçebilirsiniz. Hesap seçtikten sonra sunucu Gezgini'nde görüntülemek istediğiniz bu hesap altında hangi abonelikleri seçebilirsiniz.

![Azure abonelikleri iletişim yönetmek](../ide/media/vs2015_manage_subs.png "vs2015_manage_subs")

Sunucu Gezgini, bir sonraki açışınızda bu aboneliği için kaynakları görüntülenir.

### <a name="access-your-azure-account-via-add-connected-service-dialog"></a>Bağlı hizmet Ekle iletişim kutusu üzerinden Azure hesabınıza erişin

1. C# dilinde bir UWP uygulaması projesi oluşturun.

1. Çözüm Gezgini'nde proje düğümünü seçin ve ardından **Ekle, bağlı hizmet**. **Bağlı hizmet Ekle** Sihirbazı görünür ve Visual Studio oturum açma kimliğiyle ilişkili Azure hesabında hizmetlerin listesini gösterir Azure için ayrı olarak oturum açmak zorunda değilsiniz unutmayın. Ancak, diğer hesapları için belirli bir bilgisayardan kaynaklarına erişme girişimi ilk kez oturum açmak gerekir.

    > [!WARNING]
    > Bu ilk kez ise Visual Studio'da belirli bir bilgisayarda bir UWP uygulaması oluşturuyorsanız, giderek cihazınız için geliştirme modunu etkinleştirmek için istenir **ayarlarını &#124;  Güncelleştirmeler ve güvenlik &#124; Geliştiriciler için** bilgisayarınızda. Daha fazla bilgi için bkz: [aygıtı etkinleştir geliştirme](https://msdn.microsoft.com/en-us/library/windows/apps/dn706236.aspx).

### <a name="access_azure"></a>Erişim Azure Active Directory'de bir Web projesi

Azure AD son kullanıcı çoklu oturum açma ASP.NET MVC web uygulamaları veya Web API Hizmetleri AD kimlik doğrulaması için destek sağlar. Etki alanı kimlik doğrulaması, tek tek kullanıcı hesabı kimlik doğrulamasını farklıdır; Active Directory etki alanınıza erişimi olan kullanıcılar, web uygulamalarınızı bağlanmak için var olan Azure AD hesaplarına kullanabilirsiniz. Office 365 uygulamaları, etki alanı kimlik doğrulamasını da kullanabilirsiniz. Bu eylem görmek için bir web uygulaması oluşturma (**dosya, yeni proje C#, bulut, ASP.NET Web uygulaması**). Yeni ASP.NET projesi iletişim kutusunda seçin **kimlik doğrulamayı Değiştir**. Kimlik Doğrulama Sihirbazı'nı görünür ve uygulamanızda kullanılacak kimlik doğrulama türlerini seçmenize olanak tanır.

![ASP.NET kimlik doğrulaması iletişim kutusu değişimi](../ide/media/vs2015_change_authentication.png "VS2015_change_authentication")

ASP.NET kimlik doğrulaması farklı türleri hakkında daha fazla bilgi için bkz: [Visual Studio 2013'da ASP.NET Web projeleri oluşturma](http://www.asp.net/visual-studio/overview/2013/creating-web-projects-in-visual-studio#orgauth) (kimlik doğrulaması hakkında bilgi hala geçerli Visual Studio sürümleri için geçerlidir).

### <a name="access-your-visual-studio-team-services-account"></a>Visual Studio Team Services hesabınıza erişemiyor

Ana menüden **takım, Team Foundation Server'a Bağlan** ortaya çıkarmak için **Takım Gezgini** penceresi. Tıklayın **takım projelerini seçin**ve ardından altında liste kutusunda **Team Foundation Server Seç**, Visual Studio Team Services hesabınız için URL görmeniz gerekir. URL seçtiğinizde, kimlik bilgilerinizi yeniden girmek zorunda kalmadan oturum açmanız.

## <a name="add-a-second-user-account-to-visual-studio"></a>Visual Studio için ikinci bir kullanıcı hesabı Ekle

Visual Studio üst köşedeki kullanıcı adınıza yanındaki aşağı oka tıklayın. Ardından **hesap ayarlarını** menü öğesi. **Hesap Yöneticisi** iletişim kutusu görüntülenir ve oturum ile hesabı görüntüler. Seçin **Hesap Ekle** yeni bir Microsoft hesabı veya yeni bir iş veya Okul hesabı eklemek için iletişim kutusunun alt köşedeki bağlantı.

![Visual Studio hesap Seçici](../ide/media/vs2015_acct_picker.png "VS2015_acct_picker")

Yeni hesap kimlik bilgilerini girmek için istemleri izleyin. Bir kullanıcı kendi Contoso.com iş hesabı ekledikten sonra Hesap Yöneticisi'ni aşağıda gösterilmektedir.

![Hesap Yöneticisi](../ide/media/vs2015_accountmanager.gif "VS2015_AccountManager")

## <a name="revisit-the-add-connected-services-wizard-and-server-explorer"></a>Sunucu Gezgini ve ekleme bağlı hizmetler Sihirbazı'nı tekrar ziyaret

Şimdi gidin **Sunucu Gezgini** yeniden Azure düğümüne sağ tıklayın ve seçin **yönetin ve filtre abonelikleri**. Geçerli hesap yanında aşağı açılan tıklatarak yeni hesabı seçin ve ardından sunucu Gezgini'nde görüntülemek istediğiniz abonelikleri seçin. Belirtilen abonelikle ilişkili tüm hizmetlerin görmeniz gerekir. Şu an için Visual Studio IDE ikinci hesabı ile oturum olsa bile, bu hesabın hizmet ve kaynakların oturum açtınız. Aynı için doğrudur **proje, bağlı hizmet Ekle** ve **takım, Team Foundation Server'a Bağlan**.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'da oturum açın](signing-in-to-visual-studio.md)