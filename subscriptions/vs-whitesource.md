---
title: WhiteSource Bolt avantajı | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 01/11/2017
ms.topic: Get-Started-Article
description: Visual Studio aboneliğinize dahil olan WhiteSource Bolt aboneliği etkinleştirmek öğrenin.
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: a7c384a8bc4b84aea4982bd195b0d92820c68ecb
ms.sourcegitcommit: a749c287ec7d54148505978e8ca55ccd406b71ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46542357"
---
#  <a name="whitesource-bolt-in-visual-studio-subscriptions"></a>WhiteSource Bolt, Visual Studio abonelikleri

Bulun, açık kaynak güvenlik açıklarını düzeltin ve derlemenizdeki tüm açık kaynaklı bileşenlerin kapsamlı Envanter ve lisans raporlarını oluşturun. Bazı Visual Studio abonelikleri altı ay boyunca ücretsiz erişim içerir.

## <a name="activation-steps"></a>Etkinleştirme adımları

1.  WhiteSource Bolt avantajınızı etkinleştirmek için oturum açın [ https://my.visualstudio.com/benefits ](https://my.visualstudio.com/benefits?wt.mc_id=o~msft~docs) .

2.  WhiteSource Bolt kutucuğu Araçlar bölümünde bulun ve tıklayarak **kodunu Al** avantajı kutucuğun alt kısmındaki bağlantı.
    > [!div class="mx-imgBorder"]
    > ![WhiteSource avantajı kutucuğu](_img\vs-whitesource\vs-whitesource-tile.png)

2.  Etkinleştirme kodunuzu görüntüleyen bir bildirim alacaksınız.  **Kodunu panonuza kopyalayın**, ardından **etkinleştirme**.
    > [!div class="mx-imgBorder"]
    > ![WhiteSource avantajı kod ](_img\vs-whitesource\vs-whitesource-code.png)

3.  WhiteSource web sayfasında tıklayarak **etkinleştirme** düğmesine veya doğru aşağı kaydırın **hesabınızı etkinleştirmek** sayfasının bölümünde.
    > [!div class="mx-imgBorder"]
    > ![WhiteSource avantajı etkinleştirin](_img\vs-whitesource\vs-whitesource-activate-page-cropped.png)

4.  İçinde **hesabınızı etkinleştirmek** Bölümü sayfasının, dört adımı gösterilmesini:

    - [Yükleme](https://marketplace.visualstudio.com/items?itemName=whitesource.ws-bolt) Microsoft Visual Studio Market'ten WhiteSource Bolt uzantısı. Uzantıları yüklemek için izinlere sahip değilseniz, bkz. [Azure DevOps Hizmetleri için ücretsiz uzantı yükleme](/azure/devops/marketplace/install-vsts-extension?view=vsts).


    Yeşil tıklayın **yükleme** Azure DevOps Hizmetleri kullanıyorsanız düğmesini veya **indirin** Team Foundation Server için düğme.  Bu örnekte, Azure DevOps Hizmetleri kullanacağız.
    > [!div class="mx-imgBorder"]
    > ![WhiteSource avantajı yükleme uzantısı](_img\vs-whitesource\vs-whitesource-download-install.png)

    - Ardından,'e tıklayın, istediğiniz Azure DevOps kuruluş seçin **Onayla**.  (Azure DevOps Hizmetleri henüz ayarlamadıysanız ziyaret [avantajları](https://my.visualstudio.com/benefits) sayfasında ve DevOps Hizmetleri Azure avantajınızı etkinleştirin.)

    > [!div class="mx-imgBorder"]
    > ![WhiteSource teklifi, hesap onaylayın](_img\vs-whitesource\vs-whitesource-confirm-account.png)

    - Uzantı yüklü ve kullanılmaya hazır bir onay alırsınız.  Tıklayın **başlama** WhiteSource Bolt sayfasına geri dönün ve devam etmek için.
    > [!div class="mx-imgBorder"]
    > ![WhiteSource avantajı yüklenmesi tamamlandı](_img\vs-whitesource\vs-whitesource-install-complete.png)

5.  Azure DevOps projesi panonuzu açın, üzerinde **Azure işlem hatları** menü ve **WhiteSource Bolt**.
    > [!div class="mx-imgBorder"]
    > ![WhiteSource avantajı uzantı Ekle](_img\vs-whitesource\vs-whitesource-installed-cropped.png)

6. WhiteSource Bolt avantajı kutucuğundan etkinleştirme kodu yapıştırın ve tıklayın **etkinleştirme**. Her biri, etkinleştirme kodu yalnızca bir proje etkinleştirmek için kullanılabilir.
    > [!div class="mx-imgBorder"]
    > ![WhiteSource avantajı etkinleştirme kodu](_img\vs-whitesource\vs-whitesource-activate-code-cropped.png)

7.  Etkinleştirme tamamlanır ve 180 gün aboneliğinizde gerekir.

8.  WhiteSource Bolt uzantısı derleme adımlarınızı biri olarak eklemeniz gerekecektir.  Bir video bulunur [WhiteSource Bolt sayfa](https://www.whitesourcesoftware.com/whitesource_bolt_visualstudio_2017/#activate) nasıl göstermek için.

9. Derleme çalıştırdıktan sonra aşağıdaki kapsamlı raporlar ve panolar otomatik olarak oluşturulur:
    - Güvenlik açıklarını Panosu
    - Güvenlik açıklarını raporu
    - Güncel olmayan kitaplıklar raporu
    - Lisans riskleri ve uyumluluk Panosu
    - Envanter raporu

## <a name="eligibility"></a>Uygunluk

| Abonelik düzeyi                                                 |     Kanallar                                            | Faydası                                                          | Yenilenebilir?    |
|--------------------------------------------------------------------|---------------------------------------------------------|------------------------------------------------------------------|---------------|
| Visual Studio Enterprise (standart, yıllık bulut)   | VL, Azure, perakende, seçili NFR<sup>1</sup> | 6 ay       |  Evet          |
| Visual Studio Professional (standart, yıllık bulut) | VL, Azure, perakende                                       | Kullanılabilir değil                                                           |Yok         |
| Visual Studio Test Professional (standart)                         | Toplu Lisans, perakende                                              | Yok                                             |  Yok         |
| MSDN platformları (standart)                                          | Toplu Lisans, perakende                                              | Yok                                              | Yok         |
| Visual Studio Dev Essentials | Yok  | Yok |Yok |
| Visual Studio Enterprise, Visual Studio Professional (aylık bulut) | Azure                                       | Yok                                                           |Yok|

<sup>1</sup>*içerir: Microsoft iş ortağı ağı (Kurumsal).  Dışlar: Diğer değil satışıyla (NFR), Visual Studio Endüstri ortağı (VSIP), FTE, MCT yazılım ve geliştirici Hizmetleri, BizSpark, Microsoft değerli ortak (MVP), bölge Yöneticisi (RD), MCT yazılımı ve Hizmetleri, Imagine için Microsoft iş ortağı ağ () Professional).*

Emin değil hangi aboneliği, kullanmakta olduğunuz?  Bağlanma [ https://my.visualstudio.com/subscriptions ](https://my.visualstudio.com/subscriptions?wt.mc_id=o~msft~docs) e-posta adresinizi atanan tüm abonelikleri görmek için. Tüm aboneliklerinizi görmüyorsanız, bir veya daha çok farklı bir e-posta adresine atanmış olabilir.  Bu Aboneliklerdeki görmek için bu e-posta adresiyle oturum açmanız gerekir.

## <a name="support-resources"></a>Destek kaynakları

-  WhiteSource Bolt yardıma mı ihtiyacınız var?  WhiteSource Bolt temsilci ile Sohbet Canlı https://www.whitesourcesoftware.com/vse_whitesource_bolt/
-  Satışlar, abonelikler, hesaplar ve faturalandırma için Visual Studio abonelikleri ile ilgili Yardım almak için Visual Studio başvurun [abonelikleri desteği](https://visualstudio.microsoft.com/subscriptions/support/).
-  Visual Studio IDE, Azure DevOps Hizmetleri veya diğer Visual Studio ürün veya hizmetler hakkında bir sorunuz mu var?  Ziyaret [Visual Studio desteği](https://visualstudio.microsoft.com/support/).