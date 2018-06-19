---
title: 'İzlenecek yol: Gölgeleme nedeniyle hataları işleme hata ayıklama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 01875b05-cc7b-4add-afba-f2b776f86974
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a8b03a8f88c5daa421a3d6a10870b8d66b209402
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31480052"
---
# <a name="walkthrough-debugging-rendering-errors-due-to-shading"></a>İzlenecek Yol: Gölgeleme Nedeniyle Çıkan Oluşturma Hatalarını Ayıklama
Bu anlatımda kullanmak nasıl gösterilir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] grafik Tanılama'nın hatalı bir gölgelendirici hata nedeniyle renkli bir nesne araştırın.  
  
 Bu anlatımda gösterilir nasıl yapılır:  
  
-   Sorun Göster piksel tanımlamak için grafik günlük belgesi inceleyin.  
  
-   Kullanım **grafik piksel geçmişi** penceresi piksel durumu daha yakından inceleyin.  
  
-   Kullanım **HLSL hata ayıklayıcısı** piksel ve köşe gölgelendiriciler incelemek için.  
  
## <a name="scenario"></a>Senaryo  
 Yaygın olarak yanlış renklendirme nesneler üzerinde oluşur köşe gölgelendirici piksel geçtiğinde gölgelendirici yanlış veya tamamlanmamış bilgiler.  
  
 Bu senaryoda, henüz bir nesne yeni köşe ve nesne dönüştürmek ve benzersiz bir görünüm vermek için piksel gölgelendiriciler yanı sıra uygulamanıza eklediniz. Test sırasında uygulamayı çalıştırdığınızda, nesne düz siyah işlenir. Böylece uygulama ayıklayabilirsiniz grafik Tanılama'yı kullanarak, bir grafik günlüğüne sorun yakalayın. Sorun uygulamada şöyle görünür:  
  
 ![Nesne yanlış renklerle işlenir. ] (media/gfx_diag_demo_render_error_shader_problem.png "gfx_diag_demo_render_error_shader_problem")  
  
## <a name="investigation"></a>Araştırma  
 Grafik tanılama araçlarını kullanarak, test sırasında yakalanan çerçeveleri incelemek için grafik günlük belgesi yükleyebilirsiniz.  
  
#### <a name="to-examine-a-frame-in-a-graphics-log"></a>Grafik günlük çerçevede incelemek için  
  
1.  İçinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], eksik model sergiler bir çerçeve içeren bir grafik günlük yükleyin. Yeni bir grafik günlük belgesi pencere görünür [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Bu pencere üst kısmında seçili çerçeve işleme hedef çıkışıdır. Alt parçasıdır **çerçeve listesi**, küçük resim olarak her yakalanan çerçeve görüntüler.  
  
2.  İçinde **çerçeve listesi**, hangi nesne yok doğru görünüm çerçeve seçin. İşleme hedefi seçili çerçeve yansıtacak şekilde güncelleştirilir. Bu senaryoda, grafik şöyle belge penceresi görünür oturum:  
  
     ![Grafik belge Visual Studio'da oturum açın. ] (media/gfx_diag_demo_render_error_shader_step_1.png "gfx_diag_demo_render_error_shader_step_1")  
  
 Sorun gösteren bir çerçeve seçtikten sonra kullanabileceğiniz **grafik piksel geçmişi** onu tanılamak için penceresi. **Grafik piksel geçmişi** penceresi belirli piksel, kendi gölgelendiriciler ve ne etkilerini işleme hedefte, kronolojik sırada olan üzerinde bir etkisi beklendiğinden temelleri gösterir.  
  
#### <a name="to-examine-a-pixel"></a>Bir piksel incelemek için  
  
1.  Açık **grafik piksel geçmişi** penceresi. Üzerinde **grafik tanılama** araç seçin **piksel geçmişi**.  
  
2.  İncelemek için piksel seçin. Grafik günlük belgesi penceresinde yanlış renkli nesne üzerinde piksel birini seçin:  
  
     ![Bir piksel seçme geçmişi hakkında bilgileri görüntüler. ] (media/gfx_diag_demo_render_error_shader_step_2.png "gfx_diag_demo_render_error_shader_step_2")  
  
     **Grafik piksel geçmişi** penceresinde seçili piksel yansıtacak şekilde güncelleştirilir. Bu senaryoda, **grafik piksel geçmişi** penceresi şu şekilde görünür:  
  
     ![Piksel geçmişi bir DrawIndexed olay gösterir. ] (media/gfx_diag_demo_render_error_shader_step_3.png "gfx_diag_demo_render_error_shader_step_3")  
  
     Piksel gölgelendirici'nın sonucunu tamamıyla opak siyah (0, 0, 0, 1) ve fark **çıkış birleşme** bu ile birlikte **önceki** şekilde piksel rengi, **sonuç** ayrıca tamamıyla opak siyah olur.  
  
 Yanlış renkli bir piksel inceleyin ve piksel gölgelendirici çıktısı beklenen renk değil Bul sonra piksel gölgelendirici inceleyin ve nesnenin renge neler olduğunu öğrenmek için HLSL hata ayıklayıcısı kullanabilirsiniz. HLSL hata ayıklayıcısı yürütülürken adım HLSL kodlarda HLSL değişkenleri durumunu incelemek için kullanın ve sorunu tanılamak yardımcı olması için kesme noktaları ayarlayın.  
  
#### <a name="to-examine-the-pixel-shader"></a>Piksel gölgelendirici incelemek için  
  
1.  Piksel gölgelendirici hata ayıklamayı Başlat. İçinde **grafik piksel geçmişi** nesnesinin altındaki penceresi ilkel yanına **piksel gölgelendirici**, seçin **hata ayıklamayı Başlat** düğmesi.  
  
2.  Piksel gölgelendirici rengi üzerinden köşe gölgelendirici, yalnızca geçirir. çünkü bu senaryoda, piksel gölgelendirici sorunun kaynağını değil izlemek kolaydır.  
  
3.  Fare işaretçisini üzerinde `input.color`. Değeri (0, 0, 0, 1) tamamıyla opak siyah olduğuna dikkat edin.  
  
     !["Renk", "Giriş" siyah üyesidir. ] (media/gfx_diag_demo_render_error_shader_step_5.png "gfx_diag_demo_render_error_shader_step_5")  
  
     Bu senaryoda, inceleme yanlış renk büyük olasılıkla üzerinde çalışılacak piksel gölgelendirici doğru renk bilgi sağlamaz köşe gölgelendirici sonucu olduğunu gösterir.  
  
 Köşe gölgelendirici doğru bilgileri piksel gölgelendirici sağladığını büyük olasılıkla saptadıktan sonra sonraki adıma köşe gölgelendirici incelemektir.  
  
#### <a name="to-examine-the-vertex-shader"></a>Köşe gölgelendirici incelemek için  
  
1.  Köşe gölgelendirici hata ayıklamayı Başlat. İçinde **grafik piksel geçmişi** nesnesinin altındaki penceresi ilkel yanına **köşe gölgelendirici**, seçin **hata ayıklamayı Başlat** düğmesi.  
  
2.  Köşe gölgelendirici'nın çıkış yapısı bulun — piksel gölgelendirici girdisi budur. Bu senaryoda, bu yapıyı adıdır `output`. Köşe gölgelendirici kodu inceleyin ve dikkat `color` üyesi `output` yapısı tamamıyla opak siyah bir açıkça ayarlamak, belki de sonucunda birisi çalışmalarını hata ayıklama.  
  
3.  Renk üye giriş yapısında hiçbir zaman kopyalandığını onaylayın. Çünkü değerini `output.color` tamamıyla opak siyah hemen önce ayarlanır `output` yapısı döndürülür, emin olmak için iyi bir fikirdir değerini `output` düzgün bir şekilde bir önceki satıra başlatıldığından değildi. Adım ayarlar satır ulaşana kadar köşe gölgelendirici kodlarda `output.color` değerini izlerken siyah `output.color`. Dikkat değerini `output.color` siyah olarak ayarlamadığınız başlatılmadı. Bu kod satırı ayarlayan onaylar `output.color` için siyah değiştiren yerine silindi.  
  
     !["Output.color" siyah değeri. ] (media/gfx_diag_demo_render_error_shader_step_7.png "gfx_diag_demo_render_error_shader_step_7")  
  
 İşleme sorunun nedenini köşe gölgelendirici piksel gölgelendirici doğru renk değeri sağlamaz olduğunu belirledikten sonra sorunu düzeltmek için bu bilgileri kullanabilirsiniz. Bu senaryoda, köşe gölgelendirici aşağıdaki kodda değiştirerek düzeltebilirsiniz  
  
```  
output.color = float3(0.0f, 0.0f, 0.0f);  
```  
  
 to  
  
```hlsl  
output.color = input.color;  
```  
  
 Bu kod, köşe rengi üzerinden yalnızca nesnenin köşeleri'ı değiştirilmemiş şekilde iletir. — daha karmaşık köşe gölgelendiriciler değiştirme rengi üzerinden geçirmeden önce. Düzeltilmiş köşe gölgelendirici kod şuna benzemelidir:  
  
 ![Düzeltilmiş köşe gölgelendirici kodu. ] (media/gfx_diag_demo_render_error_shader_step_8.png "gfx_diag_demo_render_error_shader_step_8")  
  
 Kod düzelttikten sonra yeniden oluşturmak ve uygulamayı yeniden işleme sorun çözülür bulmak için çalıştırın.  
  
 ![Nesne doğru renklerle işlenir. ] (media/gfx_diag_demo_render_error_shader_resolution.png "gfx_diag_demo_render_error_shader_resolution")