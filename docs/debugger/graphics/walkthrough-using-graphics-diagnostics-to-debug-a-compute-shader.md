---
title: 'İzlenecek yol: Gölgelendiricisinde hata ayıklamak için grafik tanılamayı kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 69287456-644b-4aff-bd03-b1bbb2abb82a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b26772dd0cb74d90a8b7a401961fd33f86521a82
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="walkthrough-using-graphics-diagnostics-to-debug-a-compute-shader"></a>İzlenecek Yol: Hesaplayıcı Gölgelendiricisinde Hata Ayıklamak İçin Grafik Tanılamayı Kullanma
Bu anlatımda Visual Studio grafik tanılama araçları hatalı sonuçlar oluşturan gölgelendiricisinde araştırmak için nasıl kullanılacağı gösterilir.  
  
 Bu kılavuzda bu görevler gösterilmektedir:  
  
-   Kullanarak **grafik olay listesi** sorunun olası kaynakları bulmak için.  
  
-   Kullanarak **grafik olay Çağırma yığını** gölgelendirici DirectCompute tarafından yürütülen işlem belirlemek için `Dispatch` olay.  
  
-   Kullanarak **grafik ardışık düzen aşamaları** penceresini açın ve HLSL hata ayıklayıcısı sorununun kaynağıdır işlem gölgelendirici incelemek için.  
  
## <a name="scenario"></a>Senaryo  
 Bu senaryoda, DirectCompute benzetimi güncelleştirmesinin en hesaplama yoğunluklu bölümlerini gerçekleştirmek için kullandığı bir sıvı dinamiği benzetimi yazmıştır. Uygulamayı çalıştırdığınızda, veri kümesi ve kullanıcı Arabirimi doğru bakın, ancak benzetimi beklendiği gibi davranıyor değil. Grafik Tanılama'yı kullanarak, böylece uygulama ayıklayabilirsiniz grafik günlüğüne sorun yakalayabilirsiniz. Sorun uygulamada şöyle görünür:  
  
 ![Benzetimli sıvı yanlış şekilde davranır. ] (media/gfx_diag_demo_compute_shader_fluid_problem.png "gfx_diag_demo_compute_shader_fluid_problem")  
  
 Grafik günlüğü'ndeki grafik sorunları yakalama hakkında daha fazla bilgi için bkz: [grafik bilgilerini yakalama](capturing-graphics-information.md).  
  
## <a name="investigation"></a>Araştırma  
 Grafik tanılama araçları, böylece yakalanan çerçeveleri inceleyebilirsiniz grafik günlük dosyasını yüklemek için kullanabilirsiniz.  
  
#### <a name="to-examine-a-frame-in-a-graphics-log"></a>Grafik günlük çerçevede incelemek için  
  
1.  Visual Studio'da yanlış benzetimi sonuçları sergiler bir çerçeve içeren bir grafik günlük yükleyin. Visual Studio'da yeni bir grafik Tanılama sekmesi görüntülenir. Bu sekme üst kısmında seçili çerçeve işleme hedef çıkışıdır. Alt parçasıdır **çerçeve listesi**, bir küçük resim her Yakalanan çerçevenin görüntüler.  
  
2.  İçinde **çerçeve listesi**, yanlış benzetimi davranışı gösteren bir çerçeve seçin. Hata benzetimi kod ve işleme kod değil gibi görünüyor olsa bile, yine DirectCompute olayları Direct3D olayları ile birlikte bir çerçeve kare temelinde yakalanır çünkü bir çerçeve seçmeniz gerekir. Bu senaryoda, grafik şöyle sekmesi görünür oturum:  
  
     ![Grafik belge Visual Studio'da oturum açın. ] (media/gfx_diag_demo_compute_shader_fluid_step_1.png "gfx_diag_demo_compute_shader_fluid_step_1")  
  
 Sorun gösteren bir çerçeve seçtikten sonra kullanabileceğiniz **grafik olay listesi** onu tanılamak için. **Grafik olay listesi** her DirectCompute çağrısı ve etkin çerçevesinde yapıldığı Direct3D API çağrısı için bir olay içerir — örneğin, bir hesaplama GPU üzerinde çalıştırmak için veya veri kümesi veya UI işlemek için API çağırır. Bu durumda, biz ilgilendiğiniz `Dispatch` GPU üzerinde çalıştırmak benzetimi bölümlerini temsil eden olaylar.  
  
#### <a name="to-find-the-dispatch-event-for-the-simulation-update"></a>Gönderme olay benzetimi güncelleştirmesi bulmak için  
  
1.  Üzerinde **grafik tanılama** araç seçin **olay listesi** açmak için **grafik olay listesi** penceresi.  
  
2.  İnceleme **grafik olay listesi** dataset işler çizim olayı için. Bu işlemi kolaylaştırmak için girin `Draw` içinde **arama** sağ üst köşesinde kutusunda **grafik olay listesi** penceresi. Yalnızca "Çiz" başlıklarını olayları içeren bu listeyi filtreler. Bu senaryoda, bu olayları çizin Bul oluştu:  
  
     ![Olay listesi &#40;EL&#41; çizin olayları gösterir. ] (media/gfx_diag_demo_compute_shader_fluid_step_2.png "gfx_diag_demo_compute_shader_fluid_step_2")  
  
3.  Grafik günlük belgesi sekmesini işleme hedef izlerken her çizim olay taşıyın.  
  
4.  İşleme hedefi ilk kez işlenmiş dataset görüntülediğinde durdurun. Bu senaryoda, veri kümesi ilk çizim olay işlenir. Benzetimde hata gösterilir:  
  
     ![Bu benzetimi veri kümesi olay işler çizin. ] (media/gfx_diag_demo_compute_shader_fluid_step_3.png "gfx_diag_demo_compute_shader_fluid_step_3")  
  
5.  Şimdi incelemek **grafik olay listesi** için `Dispatch` benzetimi güncelleştirmeleri olay. Bunu işlenmeden önce benzetimi güncelleştirilir olası olduğundan, ilk üzerinde yoğunlaşabilirsiniz `Dispatch` sonuçları işler çizim olay önce meydana gelen olayları. Bu işlemi kolaylaştırmak için değişiklik **arama** okumak için kutusunu `Draw;Dispatch;CSSetShader(`. Hem de içeren bu listeyi filtreler `Dispatch` ve `CSSetShader` çizim olayları ek olaylar. Bu senaryoda, olduğunu fark birkaç `Dispatch` olayları önce çizim olay oluştu:  
  
     ![Çizim EL gösterir, gönderme ve CSSetShader olayları](media/gfx_diag_demo_compute_shader_fluid_step_4.png "gfx_diag_demo_compute_shader_fluid_step_4")  
  
 Artık, potansiyel olarak pek çok bildiğinize göre `Dispatch` olayları sorun için karşılık gelen, daha ayrıntılı olarak inceleyin.  
  
#### <a name="to-determine-which-compute-shader-a-dispatch-call-executes"></a>Hangi gölgelendirici gönderme çağrı işlem belirlemek için yürütür  
  
1.  Üzerinde **grafik tanılama** araç seçin **olay çağrı yığını** açmak için **grafik olay Çağırma yığını** penceresi.  
  
2.  Benzetim sonuçları işleyen çizim olaydan itibaren geriye doğru her taşıma önceki `CSSetShader` olay. Ardından **grafik olay Çağırma yığını** penceresinde, çağrı siteye gitmek için en üstteki işlevi seçin. Çağrı sitede ilk parametresi kullanabilirsiniz [CSSetShader](http://msdn.microsoft.com/library/ff476402.aspx) işlev çağrısı gölgelendirici sonraki tarafından yürütülen işlem belirlemek için `Dispatch` olay.  
  
 Bu senaryoda üç çiftlerini vardır `CSSetShader` ve `Dispatch` her çerçevesinde olaylar. Geriye doğru tümleştirme adım (Sıvı parçacık gerçekte taşındığı) üçüncü çifti temsil çalışma, (burada her parçacık etkileyen zorlar hesaplanır) zorla hesaplama adımı ikinci çiftini temsil eder ve ilk çiftini temsil eder yoğunluğu hesaplama adımı.  
  
#### <a name="to-debug-the-compute-shader"></a>İşlem gölgelendirici hata ayıklamak için  
  
1.  Üzerinde **grafik tanılama** araç seçin **ardışık düzen aşamaları** açmak için **grafik ardışık düzen aşamaları** penceresi.  
  
2.  Üçüncü seçin `Dispatch` olayı (çizim olay hemen önce gelen bir) ve ardından **grafik ardışık düzen aşamaları** penceresi altında **işlem gölgelendirici** aşama, seçin  **Hata Ayıklamayı Başlat**.  
  
     ![Üçüncü gönderme olay EL. seçerek](media/gfx_diag_demo_compute_shader_fluid_step_6.png "gfx_diag_demo_compute_shader_fluid_step_6")  
  
     HLSL hata ayıklayıcısı tümleştirme adımı gerçekleştirir gölgelendirici başlatılır.  
  
3.  Hatanın kaynağını aramak tümleştirme adım için işlem gölgelendirici kaynak kodu inceleyin. HLSL gölgelendirici işlem kodun hatalarını ayıklamak için grafik tanılamayı kullandığınızda, kod üzerinden adım ve Gözcü pencerelerini gibi diğer bilinen hata ayıklama araçlarını kullanın. Bu senaryoda, yok görünüyor, tümleştirme adımı gerçekleştirir işlem gölgelendirici hata olarak belirleyin.  
  
     ![IntegrateCS işlem gölgelendirici hata ayıklama. ] (media/gfx_diag_demo_compute_shader_fluid_step_7.png "gfx_diag_demo_compute_shader_fluid_step_7")  
  
4.  Üzerinde işlem gölgelendirici hata ayıklamasını durdurmak için **hata ayıklama** araç seçin **durdurma hata ayıklama** (klavye: Shift + F5).  
  
5.  Ardından, ikinci seçin `Dispatch` olay ve önceki adımda yaptığınız gibi işlem gölgelendirici hata ayıklamayı Başlat.  
  
     ![İkinci gönderme olay EL. seçerek](media/gfx_diag_demo_compute_shader_fluid_step_8.png "gfx_diag_demo_compute_shader_fluid_step_8")  
  
     HLSL hata ayıklayıcısı her sıvı parçacık üzerinde hareket zorlar hesaplar gölgelendirici adresindeki başlatılır.  
  
6.  Zorla hesaplama adımı için işlem gölgelendirici kaynak kodu inceleyin. Bu senaryoda, hatanın kaynağını İşte belirler.  
  
     ![Hata ayıklama ForceCS&#95;basit gölgelendirici işlem. ] (media/gfx_diag_demo_compute_shader_fluid_step_9.png "gfx_diag_demo_compute_shader_fluid_step_9")  
  
 Hatanın konumunu belirledikten sonra hata ayıklamayı durdurun ve doğru şekilde etkileşen parçacık arasındaki uzaklığı hesaplamak için işlem gölgelendirici kaynak kodu değiştirin. Bu senaryoda, yalnızca satır değiştirme `float2 diff = N_position + P_position;` için `float2 diff = N_position - P_position;`:  
  
 ![Düzeltilmiş işlem&#45;gölgelendirici kodu. ] (media/gfx_diag_demo_compute_shader_fluid_step_10.png "gfx_diag_demo_compute_shader_fluid_step_10")  
  
 İşlem gölgelendiriciler çalışma zamanında derlenen çünkü benzetimi nasıl etkilediklerini izlemek için değişiklikleri yaptıktan sonra bu senaryoda, yalnızca uygulama yeniden başlatabilirsiniz. Uygulama yeniden oluşturmanız gerekmez. Uygulamayı çalıştırdığınızda, benzetimi şimdi düzgün şekilde davranan bulur.  
  
 ![Benzetimli sıvı düzgün şekilde davranır. ] (media/gfx_diag_demo_compute_shader_fluid_resolution.png "gfx_diag_demo_compute_shader_fluid_resolution")