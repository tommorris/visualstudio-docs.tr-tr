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
ms.openlocfilehash: 735f0d5160466c81560ba5afb6bfc0e696d88230
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36302941"
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

   Oturum açtığınızda, bir sorun yaşıyorsanız, veya oy verin veya açıklama üzerinde bildirebilirsiniz. Ayrıca oy kullanabilir veya gördüğünüz herhangi bir sorun yorum gönderilen.

1. Visual Studio sorununuz için arama ve diğerleri, çok rapor olmadığını görmek için bir arabirim sağlar. Birisi bildirdi, "yukarı-bize bildirin için oy".

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

## <a name="search-for-solutions-or-provide-feedback"></a>Çözümleri için arama veya geri bildirim sağlayın

İstemiyorsanız veya bir sorunu bildirmek için Visual Studio kullanamazsınız, sorun zaten bildirildi ve bir çözüm gönderilen bir fırsat yok [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/) sayfası.

Rapor için bir sorun yoksa, ancak ürün geri bildirim veya bir öneri sağlamak istiyorsanız, yoktur, bir yer çok. Daha fazla bilgi için bkz: [UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-ide) sayfası.

## <a name="see-also"></a>Ayrıca bkz.

* [Bizimle iletişime geçin](../ide/talk-to-us.md)
* [Mac için Visual Studio ile ilgili bir sorun raporu](/visualstudio/mac/report-a-problem)
* [C++ ile ilgili bir sorun raporu](/cpp/how-to-report-a-problem-with-the-visual-cpp-toolset)
* [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/)
* [Geliştirici topluluğu veri gizliliği](developer-community-privacy.md)