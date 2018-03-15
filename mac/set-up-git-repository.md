---
title: "Mac için Visual Studio'da bir Git deposu ayarlama | Microsoft Docs"
description: "Git ve alt sürüme Mac için Visual Studio kullanarak"
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: E992FA1D-B2AD-4A28-ADC6-47E4FC471060
ms.openlocfilehash: 3eb3e0874cfc46fc98209113cf60a32cdb92787d
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="setting-up-a-git-repository"></a>Bir Git deposu ayarlama

Git takımlar aynı belgelerde aynı anda çalışmasına izin veren bir dağıtılmış sürüm denetim sistemidir. Bu, tüm dosyaları içeren tek bir sunucu yoktur, ancak bu merkezi kaynağından bir depo kullanıma olduğunda, tüm depo makinenize yerel olarak kopyalanan anlamına gelir.

GitHub ancak yaygın bir ana bilgisayardır sürüm denetimi için Git ile çalışmaya izin birçok uzak ana bilgisayarda vardır. Aşağıdaki örnek, bir GitHub konak kullanır, ancak Visual Studio'daki sürüm denetimi için Mac için herhangi bir Git ana kullanabilirsiniz

GitHub kullanmak istiyorsanız, bir hesap oluşturulur ve bu makaledeki adımları izlemeden önce yapılandırılmış olduğundan emin olun. 

## <a name="creating-a-remote-repo-on-github"></a>Uzak bağlantıların Github'da oluşturma

Aşağıdaki örnek, bir GitHub konak kullanır, ancak Visual Studio'daki sürüm denetimi için Mac için herhangi bir Git ana kullanabilirsiniz

Bir Git deposu ayarlama için aşağıdaki adımları yürütün:

1. Yeni bir Git deposu github.com'u oluşturma:

    ![Yeni git deposu oluşturma](media/version-control-git1-sml.png)

2. Depo adını, açıklamasını ve gizlilik ayarlayın. Yapmak **değil** depo başlatılamadı. .Gitignore ve lisans None olarak ayarlayın:

    ![Git deposu ayarlama ayrıntıları](media/version-control-git2.png)

3. Sonraki sayfada görüntülemek ve HTTPS veya SSH adresi oluşturduğunuz deposuna kopyalamak için bir seçenek sunar:

    ![görüntüleme ve kopyalama adresi](media/version-control-git3.png)

  Mac için bu depoya noktası Visual Studio için HTTPS adresi gerekir.


## <a name="publishing-an-existing-project"></a>Varolan projeyi yayımlama

Varolan bir, proje varsa _değil_ zaten sürüm denetimindeki Git içinde ayarlamak için aşağıdaki adımları kullanın:

4.  Mac için Visual Studio çözümü defterinde çözüm adı seçin 

5. Menü çubuğunda seçin **sürüm denetimi > Sürüm denetimi Yayımla...** Görüntülenecek **depo seçin** iletişim:

    ![Mac için Visual Studio Başlangıç checkout](media/version-control-git4-sml.png)

    Bu menü öğesi menüde gri renkte görüntülenir, çözüm adı seçtiğinizden emin olun.  

6. Seçin **kayıtlı depoları** sekmesi ve tuşuna **Ekle** düğmesi:

    ![](media/version-control-git5.png)

7. Yerel olarak görüntülemek ve #3. adımındaki URL'nin yapıştırmak için istediğiniz şekilde depo adını girin. Depo yapılandırması iletişim aşağıdakine benzer görünmelidir. Tamam'a basın: 

    ![Git Ayrıntıları iletişim girin](media/version-control-git6.png)

    Git için bağlanmak için SSH kullanmak da mümkündür unutmayın.

8. Git için uygulamayı yayımlama girişimi için depo seçin ve emin her ikisi de **modül adı** ve **ileti** metin alanları tamamlanır:

    ![Proje için git yayımlamayı deneyin](media/version-control-git7.png)

9. Tıklatın **Tamam**ve ardından **Yayımla** uyarı iletişim kutusundan.

10. Zaten Git kimlik bilgilerinizi Visual Studio'da Mac tercihlerini girmediyseniz, şimdi girin. İlk olarak, bir erişim yerine bir parola kullanılan belirteç, oluşturmanız gerekir. Bir erişim belirteci oluşturmadıysanız, Git adımları [erişim belirteci](https://help.github.com/articles/creating-an-access-token-for-command-line-use/) belgeleri.

11. Kullanıcı adı ve kişisel erişim belirteci, girin ve basın **Tamam**:

    ![Git için kullanıcı adı ve parola girin](media/version-control-git9-sml.png)

12. Birkaç saniye sonra çözümü kendi ilk işleme ile yayımlanması gerekir. Şimdi birçok seçenek ile doldurulması gerekir sürüm denetimi menü öğesi göz atarak yayımlandı onaylayın: 

    ![Sürüm Denetim menüsü](media/version-control-git10.png)

13. Ek değişiklikler yapmak başladıktan sonra seçin **anında değişiklikleri...**  değişiklikleri göndermek için **uzak** deposu. Bu, tüm uygun kullanıcıların üzerinde github.com'u görüntülemesine izin verir: 

    ![Uzak depo değişiklikleri gönderin](media/version-control-git11.png)

## <a name="publishing-a-new-project"></a>Yeni bir proje yayımlama

Yeni Proje iletişim kutusu, git kullanarak yeni bir proje yayımlamak için kullanılabilir. Etkinleştirmek için seçin **git sürüm denetimi için kullanın.** onay kutusu, aşağıdaki ekran görüntüsünde gösterildiği gibi. Bu, depodaki başlatmak ve isteğe bağlı .gitignore dosyası ekleyin:

![Uzak depo değişiklikleri gönderin](media/version-control-git12.png)

## <a name="checkout-an-existing-repository"></a>Checkout var olan bir depo

Yalnızca yerel makinenizde değil uzaktan üzerinde bulunan bir GitHub deposuna ile çalışmanız gerekir olasılığı yüksektir. Mac için Visual Studio için checkout bu depodaki hızla sağlar. Makinenize kopyalamak için aşağıdaki adımları izleyin:

1. Menü çubuğunda seçin **sürüm denetimi > Checkout...** :

2. Bu görüntüler **depo Bağlan** sekmesi:

    ![Girilen ayrıntılarla deposu sekmesine Bağlan](media/version-control-git13.png)

3. Uzak depo GitHub sayfasında basın **kopyalama veya indirme** düğmesini tıklatın ve sağlanan URL'yi kopyalayın:

    ![Görüntülenen github URL'si](media/version-control-git14.png)

4. Tüm metni değiştirin **URL** giriş alanına **depo Bağlan** sekmesi. Bu çoğu diğer alanlar bu sekmede, #2. adımda görüntüde gösterildiği gibi doldurur.

5. İçine depoyu kopyalama ve basın istediğiniz dizini girin **Checkout**.

> [!NOTE]
Depodaki 4 GB boyutunda ise sorunlarla karşılaşabilirsiniz.

## <a name="troubleshooting"></a>Sorun giderme

Projenizi boş bir uzak depo ile başlatma ile ilgili sorununuz olursa, aşağıdaki adımları deneyebilirsiniz:

- Çözüm klasörüne gidin.
- Tuşuna `Command + Shift + . ` gizli dosya ve klasörleri göstermek için.
- Varsa bir **.git** klasörünü silin.
- Varsa bir **gitignore** dosya, silin.
- Tuşuna `Command + Shift + . ` dosyaları ve klasörleri gizlemek için.
- Mac için VS üzerinde çözümünüzü açın
- Çözüm panelinde, çözüm düğümünü seçin.
- Sürüm denetimi menüsüne gidin ve seçin **sürüm denetimindeki yayımlama**.
- Adım 6 ' başlayarak yukarıdaki öğreticinin adımları izleyin.