---
title: Visual Studio grafik tanılama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.graphics
ms.assetid: fa69c550-62a7-41b5-bb1f-7eb04af1a6e8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1974480a2abefaaa38c05f4b1e4588eaddfd480e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="visual-studio-graphics-diagnostics"></a>Visual Studio grafik tanılama
Visual Studio*grafik tanılama* kaydı ve Direct3D uygulamalar oluşturma ve performans sorunları çözümlemek için araç kümesidir. Grafik Tanılama'yı, Windows bilgisayarınızdaki bir Windows aygıt benzeticisi veya bir uzak bilgisayar veya cihaz üzerinde yerel olarak çalışan uygulamalar üzerinde kullanılabilir.  
  
 Grafik tanılama iş akışının nasıl Direct3D, uygulamanızın kullandığı kaydını yakalayarak başlar — çalışan Canlı — davranışını hemen çözümlenebilir böylece paylaşılan veya daha sonrası için kaydedilmiş. Yakalama oturumları başlatılabilir ve controled Visual Studio'dan el ile veya komut satırı Yakalama aracıyla **dxcap.exe**. Yakalama oturumları da başlatılabilir ve grafik tanılama yakalama API'leri kullanarak program aracılığıyla controled.  
  
 Yakalama oturumunu kaydedilen sonra içeriği yeniden Visual Studio tarafından çalınabilir *grafik Çözümleyicisi* tam aynı kaynakları kullanarak ve kullanılan uygulaması komutları işleme yakalanan çerçeveleri herhangi bir zamanda yeniden oluşturma. Ardından, grafik Analyer penceresinde sağlanan araçları kullanarak, yakalanan çerçeveleri birini ayrıntılı olarak çözümlenebilir. Bu araçların herhangi Direct3D API çağrısı, kaynak, ardışık düzen durum nesnesi, ardışık düzen aşaması veya yakalanan çerçevesindeki tüm piksel bile tam geçmişini incelemek için kullanılabilir. Birlikte bu araçları kullanarak, bir işleme sorun sezgisel, yakalanan bir çerçevede görünme öğesinden başlayarak ve uygulamanın kaynak kodu, gölgelendiriciler ya da grafik varlıklar, temel nedeni aşağıya doğru ayrıntılara incelediniz.  
  
 Performans sorunlarını tanılamak için yakalanan çerçevede kullanılarak çözümlenebilir *çerçeve analizi* aracı. Bu araç, otomatik olarak uygulama Direct3D nasıl kullanacağını değiştirip, tüm çeşitlemelerini değerlendirmesi olası performans iyileştirmelerini araştırır. Geçmişte, yapmış olabilirsiniz ve bu tür değişiklikleri bulmak için el ile yalnızca benchmarked hangilerinin yapılan bir fark giden. Çerçeve Analizi ile yalnızca faydalı olur bildiğiniz değişiklik gerekir.  
  
 Grafik tanılama arayın ve en iyi çalıştırın, grafik zengin Direct3D uygulamanızın yardımcı olur.  
  
 Devam [genel bakış](overview-of-visual-studio-graphics-diagnostics.md) ne Visual Studio grafik tanılama sunar hakkında daha fazla bilgi edinmek için.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Genel bakış](overview-of-visual-studio-graphics-diagnostics.md)  
 Grafik tanılama iş akışı ve araçlar sunar.  
  
 [Başlarken](getting-started-with-visual-studio-graphics-diagnostics.md)  
 Bu bölümde, Visual Studio grafik Tanılama'yı yükleme ve grafik tanılama Direct3D uygulamanızı kullanmaya başlamak nasıl öğreneceksiniz.  
  
 [Grafik Bilgilerini Yakalama](capturing-graphics-information.md)  
 Grafik tanılama işleme sorunu uygulamanızda incelemek üzere kullanmak için önce uygulama DirectX nasıl kullandığı hakkında bilgi kaydedin. Kayıt oturumu sırasında uygulamanızın çalıştırdığı normalde, *yakalama* (diğer bir deyişle, seçin) ilgilendiğiniz çerçeve. Yakalamaları çerçeveleri nasıl işlendiğini hakkında ayrıntılı bilgi içerir. Yakalanan bilgiler bir grafik olarak kaydedebilirsiniz daha sonra incelemek veya ekibiniz diğer üyeleriyle paylaşmak için günlük belgesi.  
  
 [GPU kullanımı](gpu-usage.md)  
 Grafik Tanılama, uygulamanızın profilini kullanmak için GPU kullanım aracını kullanın. GPU kullanımı CPU kullanımı gibi diğer profil oluşturma araçları birlikte, uygulamanızda performans sorunları katkıda bulunabilir CPU ve GPU'ya etkinlik ilişkilendirmek için kullanılabilir.  
  
 [Grafik Günlük Belgesi](graphics-log-document.md)  
 Kaydedilen grafik günlüğü incelendiğinde başlatmak için grafik günlük belgesi penceresi yakalanan kareyi seçmek için kullandığınız — ve hatta belirli piksel — böylece ayrıntılı olarak inceleyin *olayları* (diğer bir deyişle, DirectX API, etkileyen çağrıları) .  
  
 [Çerçeve analizi](graphics-frame-analysis.md)  
 Bir çerçeve seçtikten sonra inceleyin ve işleme performansı ayarlamak için grafik çerçeve çözümlemesi kullanın.  
  
 [Olay Listesi](graphics-event-list.md)  
 Bir çerçeve seçtikten sonra kullandığınız **grafik olay listesi** işleme sorunla ilgili olup olmadığını belirlemek için olaylarını incelemek için.  
  
 [Durumu](graphics-state.md)  
 Durum pencere, geçerli olay sırasında etkin olan grafik durumu anlamanıza yardımcı olur.  
  
 [Ardışık Düzen Aşamaları](graphics-pipeline-stages.md)  
 İçinde **grafik ardışık düzen aşamaları** penceresinde oluşturma sorununu ilk göründüğü belirleyebilir şu anda seçili olay her aşaması grafik ardışık düzen tarafından nasıl işleneceğini araştırın. Ardışık Düzen aşamaları inceleyerek bir nesne nedeniyle yanlış bir dönüşüm görünmüyor veya aşamalar birini ne sonraki aşamaya bekliyor eşleşmeyen bir çıktı üretir özellikle yararlıdır.  
  
 [Olay Çağırma Yığını](graphics-event-call-stack.md)  
 Kullandığınız **grafik olay Çağırma yığını** işleme sorunla ilgili uygulama kodu gidebilirsiniz böylece şu anda seçili olay çağrı yığınını incelemek için.  
  
 [Piksel Geçmişi](graphics-pixel-history.md)  
 Kullanarak **grafik piksel geçmişi** penceresinde seçili piksel, etkilediği olaylar tarafından nasıl etkilendiğini çözümlemek için olay veya belirli türdeki işleme sorunları neden olan olaylar birleşimi tanımlayabilirsiniz. Piksel gölgelendirici çıktısı olduğundan bir nesne yanlış işlendiğinde piksel geçmişi özellikle yararlıdır hatalı veya yanlış çerçeve arabelleği ile ya da kendi piksel atılan çünkü nesne bile görünmüyor birleştirilmiştir çerçeve arabelleği düşmeden önce.  
  
 [Nesne Tablosu](graphics-object-table.md)  
 Kullandığınız **grafik nesnesi tablosu** özellikleri ve belirli Direct3D nesneleri ve şu anda seçili olayı için geçerli olan kaynaklar içeriğini incelemek için. Nesne tablosu, bir olayı sırasında etkin grafik cihaz bağlamı belirlemek ve sabit arabellekleri, köşe arabellek ve dokular gibi grafik kaynakları içerikleri inceleyin yardımcı olabilir.  
  
 [HLSL hata ayıklayıcısı](hlsl-shader-debugger.md)  
 Gölgelendirici kod şu anda seçili olay ve grafik aşama kanalı için nasıl davranacağını incelemek için kullandığınız **HLSL hata ayıklayıcısı** aracılığıyla koda adım için değişkenleri içeriğini incelemek ve diğer genel hata ayıklama görevleri gerçekleştirmek. HLSL hata ayıklayıcısı, sonuçlar daha fazla grafik ardışık düzen tarafından işlenen veya yalnızca, uygulamanız tarafından okunan bağımsız olarak işlem gölgelendirici kodu incelemek için de kullanabilirsiniz.  
  
 [Komut satırı Yakalama Aracı](command-line-capture-tool.md)  
 Hızlı bir şekilde yakalamak ve Visual Studio veya programlı yakalama kullanmadan grafik bilgilerini çalmak için komut satırı Yakalama aracını kullanın. Özellikle, bir test ortamında veya Otomasyon için komut satırı Yakalama aracını kullanabilirsiniz.  
  
 [Örnekler](graphics-diagnostics-examples.md)  
 Çeşitli örnekler grafik tanılama araçları birlikte çeşitli işleme sorunları tanılamak için nasıl kullanılacağını gösterir.  
  
## <a name="related-sections"></a>İlgili Bölümler  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Hata ayıklayıcı özelliği turu](../debugging-in-visual-studio.md)|Hata ayıklama işlevleri tanıtır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].|  
|[DirectX grafikler ve oyun](http://go.microsoft.com/fwlink/?LinkId=256498)|DirectX grafik teknolojilerini ele makaleleri sağlar.|