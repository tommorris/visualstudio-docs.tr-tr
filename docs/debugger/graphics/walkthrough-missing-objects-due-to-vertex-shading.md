---
title: 'İzlenecek yol: Köşe gölgeleme nedeniyle nesnelerin eksikliği | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: e42b54a0-8092-455c-945b-9ecafb129d93
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 226f6177b98aae8159de10f752cde37632dca901
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-missing-objects-due-to-vertex-shading"></a>İzlenecek Yol: Köşe Gölgeleme Nedeniyle Nesnelerin Eksikliği
Bu kılavuzda nasıl kullanılacağı ortaya [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] köşe gölgelendirici aşamasında oluşan bir hata nedeniyle eksik bir nesne araştırmak için grafik tanılama araçları.  
  
 Bu kılavuzda bu görevler gösterilmektedir:  
  
-   Kullanarak **grafik olay listesi** sorunun olası kaynakları bulmak için.  
  
-   Kullanarak **grafik ardışık düzen aşamaları** etkisini denetlemek için pencere `DrawIndexed` Direct3D API'sini çağırır.  
  
-   Kullanarak **HLSL hata ayıklayıcısı** köşe gölgelendirici incelemek için.  
  
-   Kullanarak **grafik olay Çağırma yığını** yanlış bir HLSL sabiti kaynağı bulmaya yardımcı olacak.  
  
## <a name="scenario"></a>Senaryo  
 3-b uygulama eksik nesnesinde'nin genel nedenlerinden biri oluşur köşe gölgelendirici nesnenin köşeleri yanlış veya beklenmeyen bir şekilde dönüştürür — Örneğin, nesne çok küçük bir boyuta göre ölçeklenebilir veya kamera göründüğü şekilde dönüştürülmüş , yerine onu önünde.  
  
 Bu senaryoda, test etmek için uygulamayı çalıştırdığınızda, arka plan beklendiği gibi işlenir ancak nesnelerden görünmez. Böylece uygulama ayıklayabilirsiniz grafik Tanılama'yı kullanarak, bir grafik günlüğüne sorun yakalayın. Sorun uygulamada şöyle görünür:  
  
 ![Nesne görülebilir değildir. ] (media/gfx_diag_demo_missing_object_shader_problem.png "gfx_diag_demo_missing_object_shader_problem")  
  
## <a name="investigation"></a>Araştırma  
 Grafik tanılama araçlarını kullanarak, test sırasında yakalanan çerçeveleri incelemek için grafik günlük dosyası yükleyebilirsiniz.  
  
#### <a name="to-examine-a-frame-in-a-graphics-log"></a>Grafik günlük çerçevede incelemek için  
  
1.  İçinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], eksik nesne sergiler bir çerçeve içeren bir grafik günlük yükleyin. Yeni bir grafik günlük sekmesi görünür [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Bu sekme üst kısmında seçili çerçeve işleme hedef çıkışıdır. Alt parçasıdır **çerçeve listesi**, küçük resim olarak her yakalanan çerçeve görüntüler.  
  
2.  İçinde **çerçeve listesi**, nesne görüntülenmez gösteren bir çerçeve seçin. İşleme hedefi seçili çerçeve yansıtacak şekilde güncelleştirilir. Bu senaryoda, grafik şöyle sekmesi görünür oturum:  
  
     ![Grafik belge Visual Studio'da oturum](media/gfx_diag_demo_missing_object_shader_step_1.png "gfx_diag_demo_missing_object_shader_step_1")  
  
 Sorun gösteren bir çerçeve seçtikten sonra kullanarak tanılamak başlayabilirsiniz **grafik olay listesi**. **Grafik olay listesi** etkin çerçeve için işlemek için yapılan her Direct3D API çağrısı aygıt durumunu ayarlamak için oluşturun ve arabellek güncelleştirmek ve çerçevede görünen nesneler çizmek için API çağrılarını içerir. Olduğundan çok çeşitli çağrıları ilginç genellikle (ancak her zaman) karşılık gelen bir değişiklik uygulama beklendiği gibi çalışırken işleme hedef örneğin çizin, gönderme, kopyalama veya Temizle çağrıları. Her bir uygulama oluşturulmasını geometri olabilmesinden dolayı çizim çağrıları özellikle ilginç (gönderme çağrıları ayrıca de geometri oluşturma).  
  
 Eksik nesne işleme hedef (Bu örnekte) çizilen değil olduğunu bildiğiniz için — Sahne kalan beklendiği gibi çizilir ancak bu — kullanabileceğiniz **grafik olay listesi** ile birlikte **grafik ardışık düzen Aşamaları** hangi çağrısı çizin belirlemek için aracı eksik nesnenin geometriye karşılık gelir. **Grafik ardışık düzen aşamaları** penceresi işleme hedef üzerindeki etkisini bağımsız olarak her çizim çağrı gönderildiği geometri gösterir. Draw çağrılar ilerlerken, ardışık düzen aşamaları o çağrısı ile ilişkili geometri göstermek için güncelleştirilir ve işleme hedef çıkış aramayı tamamladıktan sonra işleme hedefi durumunu gösterecek şekilde güncelleştirilir.  
  
#### <a name="to-find-the-draw-call-for-the-missing-geometry"></a>Draw çağrısı için eksik geometri bulmak için  
  
1.  Açık **grafik olay listesi** penceresi. Üzerinde **grafik tanılama** araç seçin **olay listesi**.  
  
2.  Açık **grafik ardışık düzen aşamaları** penceresi. Üzerinde **grafik tanılama** araç seçin **ardışık düzen aşamaları**.  
  
3.  Her taşırken çağrısı çizim **grafik olay listesi** penceresinde, izleme **grafik ardışık düzen aşamaları** eksik nesne penceresi. Bu işlemi kolaylaştırmak için "Çiz" girin **arama** sağ üst köşesinde kutusunda **grafik olay listesi** penceresi. Yalnızca "Çiz" başlıklarını olayları içeren bu listeyi filtreler.  
  
     İçinde **grafik ardışık düzen aşamaları** penceresinde **giriş Assembler** aşama, dönüştürülmüş önce nesnenin geometri gösterir ve **köşe gölgelendirici** aşama aynı gösterir Bunu dönüştürüldükten sonra nesnesi. Bu senaryoda, görüntülendiğinde eksik nesne buldunuz bilmeniz **giriş Assembler** aşama ve hiçbir şey görüntülenir **köşe gölgelendirici** aşaması.  
  
    > [!NOTE]
    >  Varsa diğer geometri aşamalar — Örneğin, Hull gölgelendirici, etki alanı gölgelendirici veya geometri gölgelendirici aşamaları — nesneyi işlemek, sorunun nedenini olabilir. Genellikle, sorun sonucu görüntülenmez veya beklenmeyen bir biçimde görüntülenen erken aşamada ilişkilidir.  
  
4.  Eksik nesnesine karşılık gelen çizim çağrısı ulaştığında durdurun. Bu senaryoda, **grafik ardışık düzen aşamaları** penceresi geometri (giriş Assembler küçük resim tarafından gösterilen) GPU verildiğini gösterir, ancak bir sırasında hata oluştuğundan olduğundan işleme hedef görünmüyor Köşe gölgelendirici aşama (köşe gölgelendirici küçük resim gösterilir):  
  
     ![DrawIndexed olay ve ardışık düzen üzerindeki etkisi](media/gfx_diag_demo_missing_object_shader_step_2.png "gfx_diag_demo_missing_object_shader_step_2")  
  
 Uygulama eksik nesnenin geometri çizim çağrısı verilen onaylayın ve sorun köşe gölgelendirici aşamasında olur Bul sonra köşe gölgelendirici incelemek ve nesnenin geometriye neler olduğunu öğrenmek için HLSL hata ayıklayıcısı kullanabilirsiniz. HLSL hata ayıklayıcısı yürütülürken adım HLSL kodlarda HLSL değişkenleri durumunu incelemek için kullanın ve sorunu tanılamak yardımcı olması için kesme noktaları ayarlayın.  
  
#### <a name="to-examine-the-vertex-shader"></a>Köşe gölgelendirici incelemek için  
  
1.  Köşe gölgelendirici aşama hata ayıklamayı Başlat. İçinde **grafik ardışık düzen aşamaları** penceresi altında **köşe gölgelendirici** aşama, seçin **hata ayıklamayı Başlat** düğmesi.  
  
2.  Çünkü **giriş Assembler** aşama görünür köşe gölgelendirici iyi veri sağlamak için ve **köşe gölgelendirici** aşama görünür herhangi bir çıktı oluşturmak için köşe gölgelendirici çıktısı incelemek istediğiniz yapısı, `output`. HLSL kod üzerinden adım olarak, bir daha yakın Al ne zaman Ara `output` değiştirilir.  
  
3.  İlk kez `output` değiştirilmiş, üye `worldPos` yazılır.  
  
     !["Output.worldPos" değerini makul görünür](media/gfx_diag_demo_missing_object_shader_step_4.png "gfx_diag_demo_missing_object_shader_step_4")  
  
     Değerini makul gibi göründüğünden, kod değiştirir sonraki satıra kadar atlama devam `output`.  
  
4.  Bir sonraki `output` değiştirilmiş, üye `pos` yazılır.  
  
     !["Output.pos" değerini sıfırlanmasını](media/gfx_diag_demo_missing_object_shader_step_5.png "gfx_diag_demo_missing_object_shader_step_5")  
  
     Bu süre, değeri `pos` üye — sıfırlardan — şüpheli görünüyorsa. Ardından, belirlemek istediğiniz nasıl `output.pos` tümü sıfır değerine sahip olacak şekilde gelen.  
  
5.  Olduğunu fark `output.pos` adlı bir değişken değerini alır `temp`. Önceki satıra, gördüğünüz değerini `temp` adlı bir sabit tarafından önceki değerine çarparak sonucu `projection`. Şüpheleniyorsanız `temp`'s şüpheli değerdir bu Çarpım sonucunu. Üzerinde işaretçiyi getirdiğinizde `projection`, değerini de sıfırlardan olduğuna dikkat edin.  
  
     ![Projeksiyon matris hatalı bir dönüşüm içeren](media/gfx_diag_demo_missing_object_shader_step_6.png "gfx_diag_demo_missing_object_shader_step_6")  
  
     İnceleme Bu senaryoda, gösterir `temp`'s şüpheli değer büyük olasılıkla tarafından kendi çarpım nedeni `projection`ve çünkü `projection` projeksiyon matris içerecek şekilde amacı bir sabit değer olmaması gerektiği olduğunu bildiğiniz sıfırlardan içerir.  
  
 Belirledikten sonra HLSL sabiti `projection`— gölgelendirici uygulamanız tarafından geçirilen — büyük olasılıkla kaynak sorun, sonraki adım, uygulamanızın kaynak kodunda konumu bulmak için burada sabit arabellek girilir. Kullanabileceğiniz **grafik olay Çağırma yığını** bu konumu bulunamıyor.  
  
#### <a name="to-find-where-the-constant-is-set-in-your-apps-source-code"></a>Uygulamanızın kaynak kodunda sabiti ayarlandığı bulmak için  
  
1.  Açık **grafik olay Çağırma yığını** penceresi. Üzerinde **grafik tanılama** araç seçin **grafik olay Çağırma yığını**.  
  
2.  Çağrı yığınına uygulamanızın kaynak kodunu gidin. İçinde **grafik olay Çağırma yığını** penceresinde, sabit arabellek var. dolu olmadığını görmek için en üstteki arama seçin. Değilse, burada, doldurulur bulana kadar çağrı yığınına devam edin. Bu senaryoda, sabit arabellek doldurulmuş olduğunu bulmak — kullanarak `UpdateSubresource` Direct3D API — adlı bir işlev çağrı yığınında'daha fazla yukarı `MarbleMaze::Render`, ve değeri adlı bir sabit arabellek nesnesinden gelen `m_marbleConstantBufferData` :  
  
     ![Nesnenin sabit arabelleği ayarlar kodu](media/gfx_diag_demo_missing_object_shader_step_7.png "gfx_diag_demo_missing_object_shader_step_7")  
  
    > [!TIP]
    >  Uygulamanız aynı anda ayıkladığınız, sonraki çerçeve işlendiğinde temas eder ve bu konumda bir kesme noktası ayarlayabilirsiniz. Ardından üyelerini inceleyebilirsiniz `m_marbleConstantBufferData` doğrulamak için değeri `projection` üye sabit arabellek dolduğunda tümü sıfır olarak ayarlayın.  
  
 Burada sabit arabellek doldurulur konumunu bulmak ve değerlerini değişkeninden gelen olduğunu fark sonra `m_marbleConstantBufferData`, sonraki adıma nereye bulmaktır `m_marbleConstantBufferData.projection` üye tümü sıfır olarak ayarlanır. Kullanabileceğiniz **tüm başvuruları Bul** değerini değiştirir kodunu hızlı tarama için `m_marbleConstantBufferData.projection`.  
  
#### <a name="to-find-where-the-projection-member-is-set-in-your-apps-source-code"></a>Projeksiyon üye uygulamanızın kaynak kodunda ayarlandığı bulmak için  
  
1.  Başvuruları Bul `m_marbleConstantBufferData.projection`. Değişken için kısayol menüsünü açın `m_marbleConstantBufferData`ve ardından **tüm başvuruları Bul**.  
  
2.  Uygulamanızın kaynak kodu satır konumunu gitmek için burada `projection` üyesi değiştirilmiş, bu satırda seçin **Bul simgesi sonuçlarınızı** penceresi. Projeksiyon üye değiştirir ilk sonuç sorunun nedenini olmayabileceğinden, uygulamanızın kaynak kodunun birkaç alanları incelemek olabilir.  
  
 Konumun bulduktan sonra burada `m_marbleConstantBufferData.projection` , yanlış bir değer kökenini belirlemek için çevresindeki kaynak kodunu incelemek ayarlanmadı. Bu senaryoda, olduğunu fark değerini `m_marbleConstantBufferData.projection` adlı yerel bir değişkene ayarlamak `projection` kod tarafından verilen bir değere başlatılmadan önce `m_camera->GetProjection(&projection);` sonraki satıra.  
  
 ![Mermer projeksiyon başlatma önce ayarlanır](media/gfx_diag_demo_missing_object_shader_step_9.png "gfx_diag_demo_missing_object_shader_step_9")  
  
 Sorunu düzeltmek için değeri ayarlar kod satırı taşıma `m_marbleConstantBufferData.projection` yerel değişkenin değerini başlatır satırdan `projection`.  
  
 ![Düzeltilmiş C&#43; &#43; kaynak kodu](media/gfx_diag_demo_missing_object_shader_step_10.png "gfx_diag_demo_missing_object_shader_step_10")  
  
 Kod düzelttikten sonra yeniden oluşturmak ve uygulamayı yeniden işleme sorun çözülür bulmak için çalıştırın:  
  
 ![Şimdi nesnesinde görüntülenir. ] (media/gfx_diag_demo_missing_object_shader_resolution.png "gfx_diag_demo_missing_object_shader_resolution")