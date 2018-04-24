---
title: 'İzlenecek yol: Yanlış yapılandırılmış ardışık düzen nedeniyle nesnelerin eksikliği | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: ed8ac02d-b38f-4055-82fb-67757c2ccbb9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2833c3ae2a8f03b69314db9e3723a640c4327587
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="walkthrough-missing-objects-due-to-misconfigured-pipeline"></a>İzlenecek Yol: Yanlış Yapılandırılmış Ardışık Düzen Nedeniyle Eksik Nesneler
Bu kılavuzda nasıl kullanılacağı ortaya [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] unset piksel gölgelendirici nedeniyle eksik olan bir nesneyi araştırmak için grafik tanılama araçları.  
  
 Bu kılavuzda bu görevler gösterilmektedir:  
  
-   Kullanarak **grafik olay listesi** sorunun olası kaynakları bulmak için.  
  
-   Kullanarak **grafik ardışık düzen aşamaları** etkisini incelemek için penceresine `DrawIndexed` Direct3D API çağrısı.  
  
-   Gölgelendirici aşama ayarlanmadı onaylamak için cihaz bağlamı inceleniyor.  
  
-   Kullanarak **grafik ardışık düzen aşamaları** penceresi ile birlikte **grafik olay Çağırma yığını** unset piksel gölgelendirici kaynağı bulmaya yardımcı olacak.  
  
## <a name="scenario"></a>Senaryo  
 3-b bir uygulamada bir nesne eksik olduğunda bunun bazen nesne işlenmeden önce gölgelendirici aşamaları birini ayarlanmamış olmasıdır. Basit işleme gereksinimlerine sahip uygulamalar bu hatanın kaynağını genellikle bir yerde nesnenin çizim çağrısı çağrı yığınında bulunur. Ancak, bir iyileştirme gölgelendirici programları, dokuları veya ortak en aza indirmek için diğer verileri bazı uygulamalar toplu birlikte nesneleri durumu-yükü değiştirin. Bu uygulamaların hatanın kaynağını toplu sistemde kaçınma yerine çizim çağrısı çağrı yığınında bulunan. Basit işleme gereksinimlerine sahip bir uygulama bu kılavuzda senaryosunu gösterir ve böylece hatanın kaynağını çağrı yığınında bulunabilir.  
  
 Bu senaryoda, test etmek için uygulamayı çalıştırdığınızda, arka plan beklendiği gibi işlenir ancak nesnelerden görünmüyor. Böylece uygulama ayıklayabilirsiniz grafik Tanılama'yı kullanarak, bir grafik günlüğüne sorun yakalayın. Sorun uygulamada şöyle görünür:  
  
 ![Nesne görülemeyen](media/gfx_diag_demo_misconfigured_pipeline_problem.png "gfx_diag_demo_misconfigured_pipeline_problem")  
  
## <a name="investigation"></a>Araştırma  
 Grafik tanılama araçlarını kullanarak, test sırasında yakalanan çerçeveleri incelemek için grafik günlük belgesi yükleyebilirsiniz.  
  
#### <a name="to-examine-a-frame-in-a-graphics-log"></a>Grafik günlük çerçevede incelemek için  
  
1.  İçinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], eksik nesne sergiler bir çerçeve içeren bir grafik günlük belgesi yükleyin. Yeni bir grafik günlük sekmesi görünür [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Bu sekme üst kısmında seçili çerçeve işleme hedef çıkışıdır. Alt parçasıdır **çerçeve listesi**, küçük resim olarak her yakalanan çerçeve görüntüler.  
  
2.  İçinde **çerçeve listesi**, nesne görüntülenmez gösteren bir çerçeve seçin. İşleme hedefi seçili çerçeve yansıtacak şekilde güncelleştirilir. Bu senaryoda, grafik şöyle sekmesi görünür oturum:  
  
     ![Grafik belge Visual Studio'da oturum](media/gfx_diag_demo_misconfigured_pipeline_step_1.png "gfx_diag_demo_misconfigured_pipeline_step_1")  
  
 Sorun gösteren bir çerçeve seçtikten sonra kullanarak tanılamak başlayabilirsiniz **grafik olay listesi**. **Grafik olay listesi** etkin çerçeveyi işlemek için yapılan her Direct3D API çağrısı içerir — örneğin, aygıt durumunu ayarlamak için oluşturun ve arabellek güncelleştirmek ve çerçevede görünen nesneler çizmek için. Çok çeşitli çağrıları — çizim, gönderme, kopyalama veya Temizle çağrıları — genellikle (ancak her zaman) olduğundan ilginç olan uygulama beklendiği gibi çalışırken işleme hedefi karşılık gelen bir değişiklik. Draw çağrıları özellikle ilginç olduklarından her bir uygulama oluşturulmasını geometri temsil eder.  
  
 İşleme hedefi içermiyor bildiğiniz için eksik nesne aynı zamanda var. yok görünüyor, diğer hataları, kullanabileceğiniz **grafik olay listesi** ile birlikte **grafik ardışık düzen aşamaları**hangi çağrısı çizin belirlemek için aracı eksik nesnenin geometriye karşılık gelir. **Grafik ardışık düzen aşamaları** penceresi işleme hedef üzerindeki etkisini bağımsız olarak her çizim çağrı gönderildiği geometri gösterir. Draw çağrılar ilerlerken, ardışık düzen aşamaları etkin her aşamanın akıp, her çağrısı ile ilişkili olan geometrinin göstermek için güncelleştirilir ve işleme hedef çıkış aramayı tamamladıktan sonra işleme hedefi durumunu gösterecek şekilde güncelleştirilir.  
  
#### <a name="to-find-the-draw-call-for-the-missing-geometry"></a>Draw çağrısı için eksik geometri bulmak için  
  
1.  Açık **grafik olay listesi** penceresi. Üzerinde **grafik tanılama** araç seçin **olay listesi**.  
  
2.  Açık **grafik ardışık düzen aşamaları** penceresi. Üzerinde **grafik tanılama** araç seçin **ardışık düzen aşamaları**.  
  
3.  Her taşırken çağrısı çizim **grafik olay listesi** penceresinde, izleme **grafik ardışık düzen aşamaları** eksik nesne penceresi. Bu işlemi kolaylaştırmak için "Çiz" girin **arama** sağ üst köşesinde kutusunda **grafik olay listesi** penceresi. Yalnızca "Çiz" başlıklarını olayları içeren bu listeyi filtreler.  
  
     İçinde **grafik ardışık düzen aşamaları** penceresinde **giriş Assembler** aşama, dönüştürülmüş önce nesnenin geometri gösterir ve **köşe gölgelendirici** aşama aynı gösterir Bunu dönüştürüldükten sonra nesnesi. Bu senaryoda, dikkat **grafik ardışık düzen aşamaları** penceresi şunu gösterir **giriş Assembler** ve **köşe gölgelendirici** aşamaları ancak **piksel gölgelendirici**  çizim çağrıların biri için aşaması.  
  
    > [!NOTE]
    >  Başka kanal aşamaları — Örneğin, hull gölgelendirici, etki alanı gölgelendirici veya geometri gölgelendirici aşamaları — nesneyi işlemek, sorunun nedenini herhangi biri olabilir. Genellikle, sorun sonucu görüntülenmez veya beklenmeyen bir biçimde görüntülenen erken aşamada ilişkilidir.  
  
4.  Eksik nesnesine karşılık gelen çizim çağrısı ulaştığında durdurun. Bu senaryoda, **grafik ardışık düzen aşamaları** penceresi gösterir geometri GPU verilmiş (varlığını tarafından gösterilen **giriş Assembler** aşama) ve dönüştürülen ( tarafındanbelirtildiğigibi **Köşe gölgelendirici** aşama), bir etkin piksel gölgelendirici olmasını değil gözükmüyor olduğundan işleme hedef görünmüyor ancak (yokluğu tarafından gösterilen **piksel gölgelendirici** aşama). Bu senaryoda, eksik nesnesinde siluet bile görebilirsiniz **çıkış birleşme** aşaması:  
  
     ![DrawIndexed olay ve ardışık düzen üzerindeki etkisi](media/gfx_diag_demo_misconfigured_pipeline_step_2.png "gfx_diag_demo_misconfigured_pipeline_step_2")  
  
 Uygulama eksik nesnenin geometri çizim çağrısı verilen onaylayın ve piksel gölgelendirici aşama etkin olmayan Bul sonra bulguları onaylamak için aygıt durumunu inceleyebilirsiniz. Kullanabileceğiniz **grafik nesnesi tablosu** cihaz bağlamı ve diğer Direct3D nesne verilerini incelemek için.  
  
#### <a name="to-examine-device-context"></a>Cihaz bağlamı incelemek için  
  
1.  Açık **d3d11 cihaz bağlamı**. İçinde **grafik ardışık düzen aşamaları** penceresinde, seçin **ID3D11DeviceContext** parçası olan bağlantıyı `DrawIndexed` pencerenin üst kısmında görüntülenir çağrısı.  
  
2.  Görüntülenen aygıt durumunu incelemek **d3d11 cihaz bağlamı** sekmesini hiçbir piksel gölgelendirici çizim araması sırasında etkin olduğunu doğrulayın. Bu senaryoda, **gölgelendirici genel bilgiler**— altında görüntülenen **piksel gölgelendirici durumu**— gölgelendirici gösterir **NULL**:  
  
     ![Piksel gölgelendirici durumunu D3D 11 cihaz bağlamı gösterir](media/gfx_diag_demo_misconfigured_pipeline_step_4.png "gfx_diag_demo_misconfigured_pipeline_step_4")  
  
 Piksel gölgelendirici ayarlandı olduğunu doğruladıktan sonra uygulama tarafından sonraki adım, uygulamanızın kaynak kodunda konumu bulmak için gölgelendirici ayarlandığı NULL'dur. Kullanabileceğiniz **grafik olay listesi** ile birlikte **grafik olay Çağırma yığını** bu konumu bulunamıyor.  
  
#### <a name="to-find-where-the-pixel-shader-is-set-in-your-apps-source-code"></a>Uygulamanızın kaynak kodunda piksel gölgelendirici ayarlandığı bulmak için  
  
1.  Bul `PSSetShader` eksik nesnesine karşılık gelen çağrısı. İçinde **grafik olay listesi** penceresinde "çizin; girin "İçinde PSSetShader **arama** sağ üst köşesinde kutusunda **grafik olay listesi** penceresi. Böylece yalnızca "PSSetShader" olayları ve "Çiz" başlıklarını olayları içeren bu listeyi filtreler. İlk seçin `PSSetShader` eksik nesne çizim çağrısından önce görüntülenen çağrısı.  
  
    > [!NOTE]
    >  `PSSetShader` içinde görünmez **grafik olay listesi** penceresini bu çerçevesinde ayarlanmadı. Bu genellikle yalnızca tek bir piksel gölgelendirici tüm nesneler için kullanılıyorsa veya varsa oluşur `PSSetShader` çağrısı bu çerçevesinde istemeden atlandı. Her iki durumda da, uygulamanızın kaynak kodunu arama olan öneririz `PSSetShader` çağrıları ve kullanım ayıklama teknikleri geleneksel bu çağrıları davranışını incelemek için.  
  
2.  Açık **grafik olay Çağırma yığını** penceresi. Üzerinde **grafik tanılama** araç seçin **grafik olay Çağırma yığını**.  
  
3.  Çağrı yığını bulmaya `PSSetShader` uygulamanızın kaynak kodunu çağırın. İçinde **grafik olay Çağırma yığını** penceresinde en üstteki arama seçin ve piksel gölgelendirici ayarlanmış değerini inceleyin. Piksel gölgelendirici ayarlanabilir, doğrudan boş veya null değeri, işlev veya başka bir duruma geçirilen bağımsız değişken nedeniyle oluşabilir. Doğrudan ayarlı değilse null değeri çağrı yığını yere kaynağını bulun olabilir. Bu senaryoda, piksel gölgelendirici doğrudan ayarlayın, Bul `nullptr` en üstteki işlevinde adlı `CubeRenderer::Render`:  
  
     ![Piksel gölgelendirici başlatma değil kod](media/gfx_diag_demo_misconfigured_pipeline_step_5.png "gfx_diag_demo_misconfigured_pipeline_step_5")  
  
    > [!NOTE]
    >  Çağrı yığını inceleyerek null değer Kaynak bulamazsanız, üzerinde koşullu kesme noktası ayarlamanızı öneririz `PSSetShader` çağrısı sağlayacak şekilde piksel gölgelendirici ayarladığınızda programın yürütülmesi keser null. Sonra uygulamayı hata ayıklama modunda yeniden başlatın ve null değer kaynağı bulmak için geleneksel hata ayıklama teknikleri kullanabilirsiniz.  
  
 Sorunu gidermek için ilk parametresinin kullanarak doğru piksel gölgelendirici atama `ID3D11DeviceContext::PSSetShader` API çağrısı.  
  
 ![Düzeltilmiş C&#43; &#43; kaynak kodu](media/gfx_diag_demo_misconfigured_pipeline_step_6.png "gfx_diag_demo_misconfigured_pipeline_step_6")  
  
 Kod düzelttikten sonra yeniden oluşturmak ve uygulamayı yeniden işleme sorun çözülür doğrulamak için çalıştırın:  
  
 ![Nesne şimdi görüntülenen](media/gfx_diag_demo_misconfigured_pipeline_resolution.jpg "gfx_diag_demo_misconfigured_pipeline_resolution")