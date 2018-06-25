---
title: Visual Studio 2017 ile ilgili bir sorun bildirme
description: Böylece biz tanılamak ve düzeltmek için Microsoft Visual Studio 2017 ile ilgili bir sorun bildirmek öğrenin.
ms.custom: ''
ms.date: 03/11/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: bee01179-cde5-4419-9095-190ee0ba5902
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a059e25546abf0d1624d3c8bc08a531d3fc4b382
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755930"
---
# <a name="how-to-report-a-problem-with-visual-studio-2017"></a>Visual Studio 2017 ile ilgili bir sorun bildirme

Visual Studio ile ilgili bir sorun yaşıyorsanız, bunları hakkında bilmek isteriz. Sorunu bildirmek nasıl işte [Geliştirici topluluğu](https://developercommunity.visualstudio.com/) böylece biz tanılayın ve düzeltin.

## <a name="report-a-problem-by-using-visual-studio"></a>Visual Studio kullanarak bir sorunu bildirin

Visual Studio için bir sorunu bildirmek için Visual Studio veya Visual Studio yükleyicisi rapordan başlatması gerekir. Doğrudan ile yapamayacağı [Geliştirici topluluğu](https://developercommunity.visualstudio.com/) Web sitesi. Visual Studio üzerinden raporlama otomatik olarak rapora dahil edilecek tanılama bilgileri sağlar.

![Visual Studio Geliştirici topluluğu sorunu açılır pencere raporu](media/report-an-issue.png)

1. Visual Studio'da seçin **yardımcı** > **geri bildirim gönder** > **bir sorun bildirmek**.

   > [!TIP]
   > Visual Studio yüklemeyi tamamlayamıyor veya Visual Studio içinde geri bildirim aracı erişemiyor kullanarak bir sorun raporlayabilirsiniz **Visual Studio yükleyicisi**. Bunu yapmak için geri bildirim simgesine sağ üst köşesinde seçin **Visual Studio yükleyicisi**.

1. Oturumunuz açık değil, seçin **oturum**; aşağıdaki ekran görüntüsünde gösterildiği gibi aracı sağ tarafta olur. Ekran oturum açmak için yönergeleri izleyin.

   ![Bir sorunu bildirmek oturum açın](../ide/media/sign-in-new-ux.png)

   Oturum açtığınızda karşılaştığınız sorunu bildirebilirsiniz. Ayrıca oy kullanabilir veya gördüğünüz herhangi bir sorun yorum gönderilen.

1. Oturum açtıktan sonra görmeye olacaktır, **sorunları** ve **etkinlik** içinde **izlediğim öğeleri** ekranı

    ![İzlediğim öğeleri](../ide/media/items-i-follow.png)

1. Visual Studio sorununuz için arama ve diğerlerinin bu rapor olmadığını görmek için bir arabirim sağlar. Birisi bildirdi, "yukarı-bize bildirin için oy".
   > [!NOTE]
   > Aramak için arama kutusunu ve'i Enter istediğiniz metni giriş veya arama simgesine basın.

   ![Arama ve oy benzer sorunlar için](../ide/media/search-and-vote.png)

1. Karşılaştığınız sorunu bulamazsanız, seçin **raporu yeni sorun** ekranın altındaki.

   > [!NOTE]
   > **Raporu yeni sorun** düğmesi yalnızca Visual Studio arabiriminde Geliştirici topluluğu için görünür. Doğrudan bir sorun raporlayamazsınız [Geliştirici topluluğu](https://developercommunity.visualstudio.com/) Web sitesi.

1. Bize doğru Visual Studio team rota yardımcı olacak sorun için açıklayıcı bir başlık oluşturun.

1. Bize ek ayrıntılar verin ve mümkünse sorunu yeniden oluşturma adımlarını sağlayın.

   ![Yeni bir sorun raporu](../ide/media/report-new-problem.png)

1. Seçin **sonraki** taşımak için **ekleri** sekmesi. Burada, Microsoft'a göndermek için geçerli ekranınızı yakalayabilirsiniz. Ek ekran görüntüleri veya diğer dosyaları eklemek için seçtiğiniz **ek dosya Ekle**.

   ![Visual Studio sorun raporu için bir ekran görüntüsü ekleme](media/report-a-problem-screenshot.png)

1. Bir ekran görüntüsü eklemek istemiyorsanız veya [bir yeniden oluşturma kayıt](#record-a-repro)seçin **sonraki** taşımak için **Özet** sekmesi.

1. Seçin **gönderme** tüm görüntü ve izleme veya döküm dosyaları yanı sıra, raporu göndermek için. (Varsa **gönderme** düğmesi gri çıkışı, başlık ve rapor için bir açıklama sağladığınızdan emin olun.)

   Hangi verilerin toplandığını hakkında daha fazla bilgi için bkz: [topladığımız veri](developer-community-privacy.md#data-we-collect).

## <a name="record-a-repro"></a>Kayıt bir yeniden oluşturma

İzleme ve yığın dökümü dosyaları, bize sorunlarını tanılamanıza yardımcı faydalıdır. Kullandığınızda, değer veriyoruz **bir sorun bildirmek** yeniden oluşturma adımları kaydetmek ve Microsoft'a veri göndermek için aracı. Bunun nasıl yapılacağı aşağıda verilmiştir:

1. Sorununuz için bir başlık ve açıklama girdikten sonra Seç **sonraki** taşımak için **ekleri** sekmesi.

1. Seçin **kaydı** sekmesi.

1. Altında **eylemlerinizi kaydetmek**, sorunu üretebilir, Visual Studio'nun geçerli örneği seçin. Visual Studio askıda, örneğin yapamazsınız seçin  **\<yeni bir örnek oluşturmak >** eylemleri Visual Studio yeni bir örneğini kaydetmek için.

1. Seçin **kaydı başlatmak**. Aracı çalıştırmak için izni verin.

   ![Visual Studio sorun raporu bir izleme ve yığın dökümü dosyasına sağlamak için "kaydı Başlat" ı seçin](../ide/media/record-dialog-box.png)

1. Zaman **adımları Kaydedicisi** aracı görüntülenir, sorunu yeniden oluşturma adımları gerçekleştirin.

1. İşiniz bittiğinde seçin **durdurmak kayıt** düğmesi.

1. Toplamak ve kaydettiğiniz bilgileri paketlemek Visual Studio için birkaç dakika bekleyin.

   Hangi verilerin toplandığını hakkında daha fazla bilgi için bkz: [topladığımız veri](developer-community-privacy.md#data-we-collect).

## <a name="when-further-information-is-needed-need-more-info"></a>Ne zaman daha fazla bilgi (daha fazla bilgi gerekiyor) gereklidir

Visual Studio 2017 sürüm 15,5 içinde başlayarak, kullanıcıların sorun raporları hakkında ek bilgiler sağlayan yardımcı olmak için yeni bir iş akışı yok.

1. Ne zaman bir Microsoft mühendisi ayarlar [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/) için sorun **daha bilgisini** durumunda, gönderilen, oy, ardından veya sorunu açıklamalı herhangi bir kullanıcı bir bildirim alır **Rapor bir sorun** Visual Studio'da aracı.

   ![Visual Studio'da daha fazla bilgi bildirim gerekir](../ide/media/nmi-notification.png)

1. Tıklayın **görünüm sorunları** filtrelemek ve dikkat etmeniz gereken sorunları görünümü sıralamak için bağlantı. Bu sorunları bunları yanında bir göstergesi de, ayırt etmek için bunları genel arayın.

1. Bir sorunu görüntülemek sorun ayrıntıları görmek için tıklatın.

   ![Daha fazla bilgi bildirim gerekir](../ide/media/nmi-details-view.png)

1. Görüntülemek için **daha bilgisini** isteği,'ı tıklatın **kendi isteği görüntüleyin ve yanıt** sorun Ayrıntıları görünümünde bağlantı. İstek bir iletişim kutusu gösterilir.

   ![Daha fazla bilgi bildirim gerekir](../ide/media/nmi-request.png)

1. Açıklamalar, ekler veya kayıt adımları ekleyerek daha fazla bilgi sağlayabilir. Bu deneyim, yeni bir sorun bildirme veya bir sorunu oylama zaman ek bilgi sağlayan benzerdir.

1. İstekte bulunan Microsoft mühendisi sağlanan ek bilgiler hakkında bir bildirim alır. Araştırmak için yeterli bilgiye sahip değilse, sorunu durumu değişir. Aksi takdirde, mühendislik bile daha fazla bilgi için sorar.

   > [!NOTE]
   > * Yanıtladığınızda, bildirim kaybolduktan. Onun yerine, teşekkür eder ve daha fazla bilgi sağlamak için bir yol kolaylaştıran bir başlık bakın.
   > * Bildirim sorunu değişiklikleri durumu sorunu aşağıdaki herkes için kaybolduğunda.
   > * Birden çok kişi aynı yanıtlayabilir **daha bilgisini** isteği.
   > * Hiç bir **daha bilgisini** iş akışında [Geliştirici topluluğu](https://developercommunity.visualstudio.com/) ne zaman doğrudan bir web tarayıcısı üzerinden erişirseniz, ancak açıklamaları ve ekleri var. de sağlayabilirsiniz.

## <a name="search-for-solutions-or-provide-feedback"></a>Çözümleri için arama veya geri bildirim sağlayın

İstemiyorsanız veya bir sorunu bildirmek için Visual Studio kullanamazsınız, sorun zaten bildirildi ve bir çözüm gönderilen bir fırsat yok [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/) sayfası.

Rapor için bir sorun yoksa, ancak ürün geri bildirim veya bir öneri sağlamak istiyorsanız, yoktur, bir yer çok. Daha fazla bilgi için bkz: [UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-ide) sayfası.

## <a name="see-also"></a>Ayrıca bkz.

* [Bizimle iletişime geçin](../ide/talk-to-us.md)
* [Mac için Visual Studio ile ilgili bir sorun raporu](/visualstudio/mac/report-a-problem)
* [C++ ile ilgili bir sorun raporu](/cpp/how-to-report-a-problem-with-the-visual-cpp-toolset)
* [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/)
* [Geliştirici topluluğu veri gizliliği](developer-community-privacy.md)