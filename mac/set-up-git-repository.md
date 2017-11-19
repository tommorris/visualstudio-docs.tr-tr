---
title: "Mac için Visual Studio'da bir Git deposu ayarlama | Microsoft Docs"
description: "Git ve alt sürüme Mac için Visual Studio kullanarak"
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: E992FA1D-B2AD-4A28-ADC6-47E4FC471060
ms.openlocfilehash: 2f6c06ff640007f28cfaed6512fdedc5dcb16e65
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="setting-up-a-git-repository"></a>Bir Git deposu ayarlama

Git takımlar aynı belgelerde aynı anda çalışmasına izin veren bir dağıtılmış sürüm denetim sistemidir. Bu, tüm dosyaları içeren tek bir sunucu yoktur, ancak bu merkezi kaynağından bir depo kullanıma olduğunda, tüm depo makinenize yerel olarak kopyalanan anlamına gelir.

GitHub bunlardan ancak en yaygın bir durumdur, sürüm denetimi için Git ile çalışmanıza olanak sağlayan birçok uzak ana bilgisayarların vardır. Aşağıdaki örnek bir GitHub konak kullanır, ancak Visual Studio'daki sürüm denetimi için Mac için herhangi bir Git ana kullanabilirsiniz

GitHub kullanmak istiyorsanız, bir hesap oluşturulur ve aşağıdaki adımları izlemeden önce yapılandırılmış olduğundan emin olun. 

## <a name="creating-a-remote-repo-on-github"></a>Uzak bağlantıların Github'da oluşturma

Aşağıdaki örnek bir GitHub konak kullanır, ancak Visual Studio'daki sürüm denetimi için Mac için herhangi bir Git ana kullanabilirsiniz

Bir Git deposu ayarlama için aşağıdaki adımları yürütün:

1. Yeni bir Git deposu github.com'u oluşturma:

    ![Yeni git deposu oluşturma](media/version-control-git1-sml.png)

2. Depo adını, açıklamasını ve gizlilik ayarlayın. Yapmak **değil** depo başlatılamadı. .Gitignore ve lisans None olarak ayarlayın:

    ![Git deposu ayarlama ayrıntıları](media/version-control-git2.png)

3. Sonraki yer görüntülemek ve az önce oluşturduğunuz depoya HTTPS veya SSH adresi kopyalamak için bir seçenek verecektir:

    ![görüntüleme ve kopyalama adresi](media/version-control-git3.png) Mac için bu depoya noktası Visual Studio için HTTPS adresi gerekir.


## <a name="publishing-an-existing-project"></a>Varolan projeyi yayımlama

4. Mac için açık projenizi Visual Studio'da dönün 

5. Menü çubuğunda seçin **sürüm denetimi > Sürüm denetimi Yayımla...** :

    ![Mac için Visual Studio Başlangıç checkout](media/version-control-git4-sml.png)

6. Bu görüntüler **depo seçin** iletişim. Seçin **kayıtlı depoları** sekmesi ve tuşuna **Ekle** düğmesi:

    ![](media/version-control-git5.png)

7. Yerel olarak görüntülemek ve #3. adımındaki URL'nin yapıştırmak için istediğiniz şekilde depo adını girin. Depo yapılandırması iletişim aşağıdakine benzer görünmelidir. Tamam'a basın: 

    ![Git Ayrıntıları iletişim girin](media/version-control-git6.png)

    Git için bağlanmak için SSH kullanmak da mümkündür unutmayın.

8. Git için uygulamayı yayımlama girişimi için oluşturduğunuz havuzu seçin ve emin olun her ikisi de **modül adı** ve **ileti** metin alanları tamamlanır:

    ![Proje için git yayımlamayı deneyin](media/version-control-git7.png)

9. Tıklatın **Tamam**ve ardından **Yayımla** uyarı iletişim kutusundan.

10. Zaten Git kimlik bilgilerinizi Visual Studio'da Mac tercihlerini girmediyseniz, şimdi girin. İlk olarak, bir erişim yerine bir parola kullanılan belirteç, oluşturmanız gerekir. Git adımları [erişim belirteci](https://help.github.com/articles/creating-an-access-token-for-command-line-use/) Bunu yapmak için belgeleri.

11. Kullanıcı adı ve kişisel erişim belirteci, girin ve basın **Tamam**:

    ![Git için kullanıcı adı ve parola girin](media/version-control-git9-sml.png)

12. Birkaç saniye sonra çözümü kendi ilk işleme ile yayımlanması gerekir. Bu, artık birçok seçenek ile doldurulması gerekir sürüm denetimi menü öğesi göz atarak onaylayın: 

    ![Sürüm Denetim menüsü](media/version-control-git10.png)

13. Ek yapmak başladığınızda değişiklikleri seçin **anında değişiklikleri...**  değişiklikleri göndermek için **uzak** deposu. Bu, tüm uygun kullanıcıların üzerinde github.com'u görüntülemesine izin verir: 

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