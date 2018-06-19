---
title: 'İzlenecek yol: Cihaz durumu nedeniyle nesnelerin eksikliği | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 1b0d2bbd-0729-4aa5-8308-70c5bf1468c5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 295177c6ea34923668b4751ac2c9f5e0fcf9aeb9
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31480508"
---
# <a name="walkthrough-missing-objects-due-to-device-state"></a>İzlenecek Yol: Cihaz Durumu Nedeniyle Nesnelerin Eksikliği
Bu kılavuzda nasıl kullanılacağı ortaya [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] nedeniyle eksik bir nesne araştırmak için grafik tanılamayı cihaz durumu yanlış.  
  
 Bu anlatımda gösterilir nasıl yapılır:  
  
-   Kullanım **grafik olay listesi** sorunun olası kaynakları bulmak için.  
  
-   Kullanım **grafik ardışık düzen aşamaları** etkisini denetlemek için pencere `DrawIndexed` Direct3D API'sini çağırır.  
  
-   Kullanım **grafik piksel geçmişi** sorunu daha açık belirtmek gerekirse bulmaya penceresi.  
  
-   Olası sorunları veya yapılandırma hataları için aygıt durumunu inceleyin.  
  
## <a name="scenario"></a>Senaryo  
 Nedenlerden biri dolayısıyla nesneleri 3-b bir uygulamada olduğu beklenen görünmeyebilir olduğu işleme çıkarılacak nesneleri neden olan grafik aygıtı yanlış yapılandırılması — Örneğin, ne zaman sarma siparişi neden olan hata culled üçgenler , veya derinliği test işlevi sebep olduğunda tüm pikselleri nesne reddedilir.  
  
 Bu kılavuzda açıklanan senaryoda, yalnızca ilk aşama 3-b uygulamanızı geliştirme ulaştınız ve ilk kez test etmek hazırsınız. Ancak, uygulamayı çalıştırdığınızda, yalnızca kullanıcı arabirimini ekrana işlenir. Böylece uygulama ayıklayabilirsiniz grafik Tanılama'yı kullanarak, bir grafik günlük dosyasına sorun yakalayın. Sorun uygulamada şöyle görünür:  
  
 ![Sorunun giderilmiş önce uygulama](media/vsg_walkthru1_firstview.png "vsg_walkthru1_firstview")  
  
 Grafik günlüğü'ndeki grafik sorunları yakalama hakkında daha fazla bilgi için bkz: [grafik bilgilerini yakalama](capturing-graphics-information.md).  
  
## <a name="investigation"></a>Araştırma  
 Grafik tanılama araçlarını kullanarak, test sırasında yakalanan çerçeveleri incelemek için grafik günlük dosyası yükleyebilirsiniz.  
  
#### <a name="to-examine-a-frame-in-a-graphics-log"></a>Grafik günlük çerçevede incelemek için  
  
1.  İçinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], eksik model sergiler bir çerçeve içeren bir grafik günlük yükleyin. Yeni bir grafik Tanılama sekmesi görünür [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Bu sekme üst kısmında seçili çerçeve işleme hedef çıkışıdır. Alt parçasıdır **çerçeve listesi**, küçük resim olarak her yakalanan çerçeve görüntüler.  
  
2.  İçinde **çerçeve listesi**, model görüntülenmez gösteren bir çerçeve seçin. İşleme hedefi seçili çerçeve yansıtacak şekilde güncelleştirilir. Bu senaryoda, grafik şöyle sekmesi görünür oturum:  
  
     ![.Vsglog sekmesi framebuffer Önizleme ve çerçeve listesi](media/vsg_walkthru1_experiment.png "vsg_walkthru1_experiment")  
  
 Sorun gösteren bir çerçeve seçtikten sonra kullanabileceğiniz **grafik olay listesi** onu tanılamak için. **Grafik olay listesi** etkin çerçeve için işlemek için yapılan her Direct3D API çağrısı aygıt durumunu ayarlamak için oluşturun ve arabellek güncelleştirmek ve çerçevede görünen nesneler çizmek için API çağrılarını içerir. Olduğundan çok çeşitli çağrıları ilginç genellikle (ancak her zaman) karşılık gelen bir değişiklik uygulama beklendiği gibi çalışırken işleme hedef örneğin çizin, gönderme, kopyalama veya Temizle çağrıları. Her bir uygulama oluşturulmasını geometri olabilmesinden dolayı çizim çağrıları özellikle ilginç (gönderme çağrıları ayrıca de geometri oluşturma).  
  
#### <a name="to-ensure-that-draw-calls-are-being-made"></a>Çağrıları yapılan bu çizim emin olmak için  
  
1.  Açık **grafik olay listesi** penceresi. Üzerinde **grafik tanılama** araç seçin **olay listesi**.  
  
2.  İnceleme **grafik olay listesi** çağrıları çizmek için. Bu işlemi kolaylaştırmak için "Çiz" girin **arama** sağ üst köşesinde kutusunda **grafik olay listesi** penceresi. Yalnızca "Çiz" başlıklarını olayları içeren bu listeyi filtreler. Bu senaryoda, birkaç çizim çağrı yapıldı Bul:  
  
     ![Grafik olay listesi yakalanan olayları gösteren](media/vsg_walkthru1_.png "vsg_walkthru1_")  
  
 Çağrıları yapılan bu çizim onayladıktan sonra hangisinin eksik geometriye karşılık gelen belirleyebilirsiniz. Eksik geometri işleme hedef (Bu örnekte) çizilen değil olduğunu bildiğiniz için kullanabileceğiniz **grafik ardışık düzen aşamaları** hangi çağrısı çizin belirlemek için penceresini eksik geometriye karşılık gelir. **Grafik ardışık düzen aşamaları** penceresi işleme hedef üzerindeki etkisini bağımsız olarak her çizim çağrı gönderildiği geometri gösterir. Draw çağrılar ilerlerken, ardışık düzen aşamaları o çağrısı ile ilişkili geometri göstermek için güncelleştirilir ve işleme hedef çıkış aramayı tamamladıktan sonra işleme hedefi durumunu gösterecek şekilde güncelleştirilir.  
  
#### <a name="to-find-the-draw-call-for-the-missing-geometry"></a>Draw çağrısı için eksik geometri bulmak için  
  
1.  Açık **grafik ardışık düzen aşamaları** penceresi. Üzerinde **grafik tanılama** araç seçin **ardışık düzen aşamaları**.  
  
2.  İzleme sırasında her çizim çağrı hareket **grafik ardışık düzen aşamaları** eksik model penceresi. **Giriş Assembler** aşama ham model verileri gösterir. **Köşe gölgelendirici** aşama dönüştürülmüş model verileri gösterir. **Piksel gölgelendirici** aşama piksel gölgelendirici çıktısı gösterir. **Çıkış birleşme** aşama Bu çizim çağrı ve tüm önceki çizim çağrıları birleştirilmiş işleme hedefi gösterir.  
  
3.  Eksik modeline karşılık gelen çizim çağrısı ulaştınız geldiğinizde durun. Bu senaryoda, **grafik ardışık düzen aşamaları** penceresi geometri işlendiğine ancak işleme hedef görünmedi gösterir:  
  
     ![Ardışık Düzen Görüntüleyicisi eksik nesne gösteren](media/vsg_walkthru1_pipeline.png "vsg_walkthru1_pipeline")  
  
 Eksik geometri uygulama oluşturulur ve karşılık gelen çizim çağrısı bulun onayladıktan sonra bir kısmı eksik geometri Göster ve ardından işleme hedef çıkış seçebilirsiniz **grafik piksel geçmişi** piksel neden dışlanan bulmak için penceresini açın. Piksel geçmişi belirli piksel üzerinde bir etkisi sahip olabileceği her çizim arama listesini içerir. Her çizim Çağır **grafik piksel geçmişi** penceresi de görüntülenir numarasına göre tanımlanır **grafik olay listesi** penceresi. Bu, piksel eksik geometri görüntülenmelidir doğrulamanıza yardımcı olur ve piksel neden dışlandığına bulmak için  
  
#### <a name="to-determine-why-the-pixel-was-excluded"></a>Piksel neden dışlandı belirlemek için  
  
1.  Açık **grafik piksel geçmişi** penceresi. Üzerinde **grafik tanılama** araç seçin **piksel geçmişi**.  
  
2.  Temel **piksel gölgelendirici** bir kısmı eksik geometri içermesi gereken bir piksel framebuffer çıkış küçük resim seçin. Bu senaryoda, piksel gölgelendirici çıkış işleme hedefi çoğunu kapsamalıdır; bir piksel seçildikten sonra **grafik piksel geçmişi** penceresi şu şekilde görünür:  
  
     ![Piksel Geçmişi penceresini ilgili gösteren çizim çağrıları](media/vsg_walkthru1_hist1.png "vsg_walkthru1_hist1")  
  
3.  İnceleniyor çizim çağrı sayısı eşleştirerek seçili işleme hedef piksel geometri bir kısmı yer aldığını onaylayın (gelen **grafik olay listesi** penceresi) çizim çağrılarında birine **grafik Piksel geçmişi** penceresi. Çağrılarında hiçbiri **grafik piksel geçmişi** penceresi eşleşme inceleniyor, çizim çağrı (dışında adım 1) bu adımları yineleyin bir eşleşme bulana kadar. Bu senaryoda, eşleşen çizim çağrı şuna benzer:  
  
     ![Parça bilgilerini gösteren piksel Geçmişi penceresini](media/vsg_walkthru1_hist2.png "vsg_walkthru1_hist2")  
  
4.  Bir eşleşme bulduğunuzda, eşleşen çizim çağrısında genişletin **grafik piksel geçmişi** penceresi ve piksel dışlandı onaylayın. Her çizim Çağır **grafik piksel geçmişi** penceresi, o piksel karşılık gelen nesne geometri sonucunda kesiştiğinden bir veya daha fazla geometrik temelleri (noktaları, çizgiler veya üçgenler) karşılık gelir. Her tür kesişim piksel son renge katkıda bulunabilir. Derinlik test başarısız oldu çünkü dışlandı bir temel eleman soldan sağa doğru aşağı slopes bir ok üzerinden Harf Z gösteren bir simge ile temsil edilir.  
  
5.  Daha fazla çıkarılmasına neden durumunu incelemek için hariç tutulan bir ilkel genişletin. İçinde **çıkış birleşme** grubunda, işaretçiyi **sonuç**. Bir araç ipucu temel neden dışlandı gösterir. Bu senaryoda, basit derinliği sınaması başarısız oldu ve bu nedenle piksel son renge katkıda değil çünkü hariç tutuldu İnceleme ortaya çıkarır.  
  
 Kendi temelleri derinliği test başarısız olduğundan geometri görünmez belirledikten sonra bu sorunu yanlış yapılandırılmış cihaz durumuna ilgili olduğunu düşündüğünüz. Cihaz durumunu ve diğer Direct3D nesne verileri incelenmesi kullanarak **grafik nesnesi tablosu**.  
  
#### <a name="to-examine-device-state"></a>Aygıt durumunu incelemek için  
  
1.  Açık **grafik nesnesi tablosu** penceresi. Üzerinde **grafik tanılama** araç seçin **nesnesi tablosu**.  
  
2.  Bulun **D3D10 aygıt** nesnesinde **grafik nesnesi tablosu**ve ardından açın **D3D10 aygıt** nesnesi. Yeni bir **d3d10 aygıt** sekmesi açılır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Bu işlemi kolaylaştırmak için sıralayabilirsiniz **grafik nesnesi tablosu** tarafından **türü**:  
  
     ![Grafik nesnesi tablosu ve ilgili cihaz durumu](media/vsg_walkthru1_objtable.png "vsg_walkthru1_objtable")  
  
3.  Görüntülenen aygıt durumunu incelemek **d3d10 aygıt** olası sorunları sekmesi. Kendi temelleri derinliği test başarısız olduğundan geometri görünmüyor çünkü derinliği test etkileyen derinliği şablon gibi cihaz durumuna odaklanabilirsiniz. Bu senaryoda, **derinliği şablon açıklama** (altında **çıkış birleşme durumu**) için seyrek bir değer içeriyor **derinliği işlevi** üyesi `D3D10_COMPARISON_GREATER`:  
  
     ![Derinlik şablon bilgilerini gösteren D3D10 aygıt penceresi](media/vsg_walkthru1_devicestate.png "vsg_walkthru1_devicestate")  
  
 İşleme sorunun nedenini yanlış yapılandırılmış derinliği işlevi olabilir belirledikten sonra burada derinliği işlevi yanlış ayarlanmış bulmak için kod bilginiz birlikte bu bilgileri kullanın ve sorunu düzeltin. Kodla tanımıyorsanız, hata ayıklama sırada topladığınız ipuçları kullanarak sorun için arama — Örneğin, temel **derinliği şablon açıklama** Bu senaryoda, kod sözcük araması yapabilirsiniz "derinliği" veya "GREATER" gibi. Kod düzelttikten sonra yeniden oluşturmak ve uygulamayı yeniden işleme sorun çözülür bulmak için çalıştırın:  
  
 ![Sorun çözüldükten sonra uygulama](media/vsg_walkthru1_finalview.png "vsg_walkthru1_finalview")