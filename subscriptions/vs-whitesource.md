---
title: WhiteSource Cıvata avantajı | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 01/11/2017
ms.topic: Get-Started-Article
description: Visual Studio aboneliğinizde yer alan WhiteSource Cıvata abonelik etkinleştirme konusunda bilgi edinin.
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: 0c2eed9efdcca076c20a240d60b4d38cdda23019
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31199407"
---
#  <a name="whitesource-bolt-in-visual-studio-subscriptions"></a>Visual Studio Aboneliklerde WhiteSource Cıvata

Bul ve açık kaynak güvenlik açıkları düzeltin ve yapı içinde tüm açık kaynak bileşenlerinin kapsamlı Envanter ve lisans raporları oluşturun.  Visual Studio abonelikleri altı ay ücretsiz erişim içerir seçin. 

## <a name="activation-steps"></a>Etkinleştirme adımları

1.  WhiteSource Cıvata avantajı etkinleştirmek için oturumu [ https://my.visualstudio.com/benefits ](https://my.visualstudio.com/benefits?wt.mc_id=o~msft~docs) .

2.  Araçlar bölümünde WhiteSource Cıvata döşeme bulun ve tıklayın **kodunu Al** avantajı döşemenin altındaki bağlantıyı.    

    ![WhiteSource avantajı döşeme](_img\vs-whitesource\vs-whitesource-tile.png)

2.  Etkinleştirme kodunuzun görüntüleyen bir bildirim alırsınız.  **Kodunu panonuza kopyalayın**, ardından **etkinleştirme**. 

    ![WhiteSource avantajı kodu ](_img\vs-whitesource\vs-whitesource-code.png)

3.  WhiteSource web sayfasında tıklayın **etkinleştirme** düğmesini tıklatın veya aşağı kaydırın **hesabınızı etkinleştirmek** sayfasının bölümünde.  

    ![WhiteSource avantajı etkinleştir](_img\vs-whitesource\vs-whitesource-activate-page-cropped.png)

4.  İçinde **hesabınızı etkinleştirmek** bölüm sayfasının, dört adımlara destekli:
    - [Yükleme](https://marketplace.visualstudio.com/items?itemName=whitesource.ws-bolt) Microsoft Visual Studio Marketi'nden WhiteSource Cıvata uzantısı. Uzantıları yükleme izniniz yok, lütfen ziyaret [bu sayfayı](https://www.visualstudio.com/docs/marketplace/get-vsts-extensions#request).

    Yeşil tıklatın **yükleme** VSTS, kullanıyorsanız düğmesini veya **karşıdan** düğmesi Team Foundation Server için.  Bu örnekte, VSTS kullanacağız. 

    ![WhiteSource avantajı yükleme uzantısı](_img\vs-whitesource\vs-whitesource-download-install.png)

    - Ardından, önce kullanmak istediğiniz VSTS hesabı seçin **Onayla**.  (VSTS henüz ayarlamadıysanız ziyaret [avantajları](https://my.visualstudio.com/benefits) sayfasında ve VSTS avantajı etkinleştirin.)

    ![WhiteSource avantajı hesap onaylayın](_img\vs-whitesource\vs-whitesource-confirm-account.png)

    - Uzantısı yüklü ve kullanıma hazır bir onay iletisi alırsınız.  Tıklatın **başlama** WhiteSource Cıvata sayfasına dönün ve devam edin.  

    ![WhiteSource avantajı yükleme tamamlandı](_img\vs-whitesource\vs-whitesource-install-complete.png)

5.  Visual Studio Team Services (VSTS) proje panonuz açın, üzerinde **yapı & yayın** menü ve **WhiteSource Cıvata**.

    ![WhiteSource avantajı uzantı Ekle](_img\vs-whitesource\vs-whitesource-installed-cropped.png)

6. WhiteSource Cıvata avantajı döşeme etkinleştirme kodu yapıştırın ve tıklatın **etkinleştirme**. Etkinleştirme kodunun her biri yalnızca bir proje etkinleştirmek için kullanılabilir. 

    ![WhiteSource avantajı etkinleştirme kodu](_img\vs-whitesource\vs-whitesource-activate-code-cropped.png)

7.  Etkinleştirme tamamlanmıştır ve aboneliğinizde 180 gün gerekir. 

8.  Derleme adımları biri olarak WhiteSource Cıvata uzantısı eklemeniz gerekir.  Bir video kullanılabilir [WhiteSource Cıvata sayfa](https://www.whitesourcesoftware.com/whitesource_bolt_visualstudio_2017/#activate) nasıl göstermek için.  

9. Yapınızın çalıştırdıktan sonra aşağıdaki kapsamlı raporlar ve panolar otomatik olarak oluşturulur:
    - Güvenlik açıklarını Panosu
    - Güvenlik açıklarını raporu
    - Eski kitaplıkları raporu
    - Lisans riskleri ve uyumluluk Panosu
    - Envanter raporu

## <a name="eligibility"></a>Uygunluk
| Abonelik düzeyi                                                 |     Kanallar                                            | Faydası                                                          | Yenilenebilir?    |
|--------------------------------------------------------------------|---------------------------------------------------------|------------------------------------------------------------------|---------------|
| Visual Studio Enterprise (standart, yıllık bulut)   | Toplu Lisans, Azure, perakende, seçili NFR<sup>1</sup> | 6 ay       |  Evet          |
| Visual Studio Professional (standart, yıllık bulut) | Toplu Lisans, Azure, perakende                                       | Mevcut değil                                                           |Yok         |
| Visual Studio Test uzmanı (standart)                         | Toplu Lisans, perakende                                              | Yok                                             |  Yok         |
| MSDN platformları (standart)                                          | Toplu Lisans, perakende                                              | Yok                                              | Yok         |
| Visual Studio Dev Essentials | Yok  | Yok |Yok |
| Visual Studio Enterprise, Visual Studio Professional (aylık bulut) | Azure                                       | Yok                                                           |Yok|

<sup>1</sup>*içerir: Microsoft iş ortağı ağı (Kurumsal).    Dışlar: Diğer değil Microsoft iş ortağı satışı (NFR), Visual Studio Endüstri ortağı (VSIP), FTE, MCT yazılım ve Hizmetleri geliştirici, BizSpark, Microsoft değerli iş ortağı (MVP), bölge Yöneticisi (RD), MCT yazılım ve hizmetlerini düşünün için (ağ Professional).*

Emin değil hangi abonelik kullanmakta olduğunuz?  Bağlanmak [ https://my.visualstudio.com/subscriptions ](https://my.visualstudio.com/subscriptions?wt.mc_id=o~msft~docs) e-posta adresinizi atanan tüm abonelikleri görmek için. Tüm aboneliklerinizi görmüyorsanız, bir veya daha farklı bir e-posta adresi için atanmış olabilir.  Bu abonelikleri görmek için bu e-posta adresinizle oturum açmanız gerekir. 


## <a name="support-resources"></a>Destek kaynakları
-  Yardım WhiteSource Cıvata mı gerekiyor?  Sohbet WhiteSource Cıvata temsilcisi ile canlı https://www.whitesourcesoftware.com/vse_whitesource_bolt/ 
-  Satış, abonelikler, hesapları ve Visual Studio abonelikler için faturalama daha fazla yardım için Visual Studio başvurun [abonelikleri Destek](https://www.visualstudio.com/subscriptions/support/).
-  Visual Studio IDE, Visual Studio Team Services veya diğer Visual Studio ürün veya hizmetler hakkında bir sorunuz mu var?  Ziyaret [Visual Studio desteği](https://www.visualstudio.com/support/). 

