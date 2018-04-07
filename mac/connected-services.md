---
title: Mac için Visual Studio'da Hizmetleri bağlı | Microsoft Docs
description: Visual Studio mobil uygulamaları için Azure veri depolama, kimlik doğrulaması ve anında iletme bildirimleri için Mac ekleyin
ms.prod: xamarin
ms.assetid: 41CB62FF-0F39-4CE8-8917-6A77F058719F
author: asb3993
ms.author: amburns
ms.date: 04/04/2018
ms.openlocfilehash: cff322e25e19179ae7da79585d8880ce7565936a
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/06/2018
---
# <a name="connected-services-walkthrough"></a>Bağlı hizmetler gözden geçirme

Hizmet eklemek için projenizin bırakmak zorunda kalmamak için bağlantılı hizmetler iş akışı Azure portal iş akışını Visual Studio'ya Mac için getirir.

Bu kılavuzda, bulut verilerini depolama, kimlik doğrulama ve platformlar arası Xamarin.Forms taşınabilir sınıf kitaplığı (PCL) uygulamasına anında iletme bildirimleri getirir bir Azure arka uç hizmetini nasıl ekleyeceğiniz gösterilir.


1.  Başlangıç çift tıklayarak **bağlantılı Hizmetler** getirir çözüm düğümünde **Services Galerisi**.
  Bu uygulama türü için tüm kullanılabilir hizmetler listesidir. Bir hizmet seçin (gibi **Azure uygulama hizmetiyle mobil arka uç**) üzerinde tıklatarak.

    [![Mac için Visual Studio'da bağlı hizmetler düğümünü](media/connected-services-image001-sml.png "Mac için Visual Studio'da bağlı hizmetler düğümünü")](media/connected-services-image001.png#lightbox)

2. Hizmet Ayrıntıları sayfası, hizmeti ve bağımlılıklarını yüklenmesi için bir açıklama vardır.
  Tıklatın **Ekle** düğmesi bağımlılıkları uygulamaya eklemek için:

    [![Azure ile mobil arka uç](media/connected-services-image002-sml.png "Azure ile mobil arka uç")](media/connected-services-image002.png#lightbox)

3. Bağımlılıkları hem PCL ve platforma özgü projelerine çalışmaya eklenmesi gerekir.
  Hizmet (doğrudan veya dolaylı olarak) başvurur her projeye eklemek için onay kutularını seçin:

    [![Hizmet başvurması gereken tüm projeleri denetleyin](media/connected-services-image003-sml.png "hizmet başvurması gereken tüm projeleri denetleyin")](media/connected-services-image003.png#lightbox)

4. Seçin **kabul** üzerinde **lisans kabulünü** iletişim kutuları için NuGet paketleri.
  Kabul etmek için MobileClient ve bağımlılıklar için diğeri SQLiteStore için çevrimdışı veri eşitleme için gerekli olan iki iletişim kutuları olabilir:

    [![Lisans sözleşmelerini kabul](media/connected-services-image004-sml.png "lisans sözleşmelerini kabul edin")](media/connected-services-image004.png#lightbox)

    ![Lisans kabulünü penceresini](media/connected-services-image005.png "lisans kabulünü penceresi")

5. Bağımlılıkları eklendikten sonra Azure ile iletişim kurmak için kullanmak istediğiniz hesapla oturum istenir.
  A Microsoft ID oturum zaten oturum açtınız, Mac için Visual Studio, Azure aboneliklerinize ve bunlarla ilişkili tüm uygulama hizmetleri getirme girişiminde bulunur. Herhangi bir aboneliğiniz yoksa, ücretsiz deneme için kaydolan veya Azure portalında abonelik planı satın tarafından ekleyebilirsiniz.

6. Bir uygulama hizmeti listeden seçin. Bu şablon kodunu doldurur `MobileServiceClient` Azure uygulama hizmeti karşılık gelen URL'sini nesnesiyle:

    [![Uygulama hizmeti listesinden](media/connected-services-image006-sml.png "uygulama hizmeti listeden seçin")](media/connected-services-image006.png#lightbox)

    Listelenen hiçbir Hizmetleri varsa tıklatın **yeni** düğmesini (bkz. adım 9.)

7. Şablon kodu kopyalamak `MobileServiceClient` PCL içine. Yalnızca bir örneği var olduğu sürece dosya konumu önemli değil.
  Oluşturmak için önerilen yaklaşımdır bir `AzureService` tüm Azure etkileşimleri işler ve kullandığı sınıf `MobileServiceClient`:

    ![Config kodu ap kopyalamak](media/connected-services-image007.png "uygulamaya config kodu Kopyala")

8. Belgelerde izleyin **sonraki adımlar** eklemek verileri, çevrimdışı eşitleme, kimlik doğrulama ve uygulamanıza anında iletme bildirimleri için:

    [![Sonraki adımlar yönergelerini gözden geçirmek](media/connected-services-image008-sml.png "sonraki adımları yönergeleri gözden geçirin")](media/connected-services-image008.png#lightbox)

9. Mevcut tüm uygulama hizmetleri yoksa, Mac için Visual Studio içinde yeni hizmetlerinden oluşturabilirsiniz.
  Tıklatın **yeni** açmak için hizmetleri listesinin altındaki sol düğmesini **yeni uygulama hizmeti** iletişim:

    [![Mac için Visual Studio'da yeni bir uygulama hizmeti oluşturma](media/connected-services-image009-sml.png "Mac için Visual Studio'da yeni bir uygulama hizmeti oluşturma")](media/connected-services-image009.png#lightbox)

Yeni bir hizmet aşağıdaki parametreleri gerektirir:

-   **Uygulama hizmeti adını** – plan için benzersiz ad/kimliği
-   **Abonelik** – hizmet için ödeme yapmak için kullanmak istediğiniz aboneliği
-   **Kaynak grubu** – bir yol ya da bir proje için tüm Azure kaynakları düzenleme. Varolanı kullanma veya yeni bir tane oluşturmak için seçeneği. İlk Azure hizmetiniz varsa, yeni bir tane oluşturun.
-   **Hizmet planı** – kullanan herhangi bir kaynağa maliyetini ve konumunu belirler. Varolanı kullanma veya yeni bir tane oluşturmak için seçeneği. İlk Azure hizmetiniz varsa, varsayılan kullanın veya ücretsiz katmanda (F1) yeni bir tane oluşturun.

Ziyaret [Azure App Service belgeleri](https://azure.microsoft.com/documentation/learning-paths/appservice-mobileapps/) daha fazla bilgi için.
