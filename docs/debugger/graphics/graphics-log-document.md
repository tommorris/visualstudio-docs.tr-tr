---
title: "Grafik günlük belgesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.graphics.vsglog.error
- vs.graphics.experiment
- vs.graphics.vsglog
ms.assetid: 6ccb1269-d55f-49c4-920d-baedf7de2888
caps.latest.revision: "31"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8429e7175ca6ab9a537952fb4a605f2281da69c8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="graphics-log-document"></a>Grafik Günlük Belgesi
Grafik günlük belgesi uygulamanızı bir grafik Tanılama oturumu altında çalışırken oluşan grafik olayları kaydıdır. Kaydedilen sonra Visual Studio grafik Çözümleyicisi aygıtını işleme ve performans sorunlarını tanılamak günlüğüne inceleyebilirsiniz.  
  
 Bu grafik Çözümleyicisi'nde gibi görünüyor hangi bir grafik günlük belgesi.  
  
 ![İki yakalanan çerçeveleri içeren grafik günlüğü. ] (media/gfx_diag_demo_graphics_log_orientation.png "gfx_diag_demo_graphics_log_orientation")  
  
## <a name="understanding-graphics-log-documents"></a>Belgeleri anlama grafik oturum  
 Grafik günlük belgesi incelemek için grafik Çözümleyicisi'ni kullanarak, yakalama sırasında oluştu işleme hedefi Direct3D olayları etkilerini görselleştirebilirsiniz. Beklenmeyen çıktı içeren bölgeleri oluşturma hedef saptayabilirler. Etkilenen bölgede bir piksel seçtiğinizde, kendi gölgelendiriciler, etkilenen Direct3D olayları, bu olaylarla öncülük uygulama çağrı yığını ve bu olayları destekleyen DirectX nesneleri incelemek için grafik tanılamayı kullanabilirsiniz. Oyun veya uygulama işleme sorunları tanılamak için bu bilgileri kullanın.  
  
 Pencerenin üst kısmında (**grafik Experiment.vsglog**) seçili kare ve alt bölümü görüntüler geçerli işleme hedef çıktısı görüntüler bir **çerçeve listesi** küçük resimlerini içeren Yakalanan çerçeveleri.  
  
#### <a name="to-inspect-a-frame"></a>Bir çerçeve incelemek için  
  
-   İçinde **çerçeve listesi**, incelemek istediğiniz çerçeveyi seçin. Grafik günlük belgesi üst kısmında işleme hedef çıkış seçili çerçeve görüntülenecek güncelleştirilir.  
  
#### <a name="to-inspect-a-pixel"></a>Bir piksel incelemek için  
  
-   Grafik günlük belgesi üst kısmında istediğiniz piksel işleme hedef çıkışı seçin. Bir piksel seçildiğinde, kullanabileceğiniz **grafik piksel geçmişi** penceresinde seçili piksel hakkındaki ayrıntılı bilgileri görüntüleyin. Daha fazla bilgi için bkz: [piksel geçmişi](graphics-pixel-history.md).  
  
## <a name="playback-machine"></a>Kayıttan yürütme makinesini  
 Ayrıca sağ üst köşesinde görüntülenen **çerçeve listesi** olan **kayıttan yürütme makinesini**. Kayıttan yürütme makinesini makine ya da daha yeni bir grafik Tanılama oturumu sırasında bir grafik günlük dosyasından grafik olayları kayıttan yürütmek için kullanılan aygıt ' dir. Farklı bir cihaz geliştirme makinenizde yerine yakalanan olayları çalmak için kullanarak, sorunun oluştuğu yürütme ortamı daha doğru bir şekilde üretebileceği — Örneğin, farklı bir grafik donanım veya sürücüleri olduğu bir makineye kullanabilirsiniz Geliştirme makinenizde kullanan dosyalardan veya diğer tür aygıtlar, bir Windows RT ARM tabanlı tablet veya Windows Phone cihazı gibi.  
  
 Kayıttan yürütme makinesini belirtme hakkında daha fazla bilgi için bkz: [nasıl yapılır: grafik tanılama kayıttan yürütme makinesini değiştirme](how-to-change-the-graphics-diagnostics-playback-machine.md).  
  
## <a name="graphics-log-summary-information"></a>Grafik Özet bilgileri günlüğe kaydet  
 Grafik günlük dosyası etkin belgede olduğunda **özellikleri** penceresi grafik tanılama yakalama oturumu barındırılan ortamıyla ilgili bilgileri görüntüler. Bilgi çeşitli kategorilerde görüntülenir.  
  
 **Direct3D bilgileri**  
 Yakalama oturumu sırasında kullanılan görüntü bağdaştırıcısı donanım ve sürücü özellikleri hakkında bilgileri listeler.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|**10-bit XR yüksek renk biçimi**|**Doğru** 10 bit XR yüksek renk biçimi, desteklenen Aksi takdirde **False**.|  
|**DirectCompute CS 4.x**|**Doğru** işlem gölgelendirici 4.0, desteklenen Aksi takdirde **False**.|  
|**Çift duyarlık gölgelendiriciler**|**Doğru** çift duyarlıklı kayan nokta değerlerini (64 bit); görüntü bağdaştırıcısı destekliyorsa, aksi takdirde, **False**.|  
|**Sürücü komutunu listeler**|**Doğru** komutu listeler; sürücü destekliyorsa, aksi takdirde, **False**.|  
|**Sürücü eşzamanlı oluşturur**|**Doğru** eşzamanlı (zaman uyumsuz) oluşturma; sürücü destekliyorsa, aksi takdirde, **False**.|  
|**Genişletilmiş biçimleri (BGRA, vb.)**|**Doğru** BGRA gibi Genişletilmiş biçimleri, desteklenen Aksi takdirde **False**.|  
|**Max donanım özelliği düzeyi**|Görüntü bağdaştırıcısı tarafından desteklenen en yüksek özellik düzeyini görüntüler.|  
  
 **Görüntü bilgileri**  
 Yakalama oturumu sırasında kullanılan görüntü bağdaştırıcısı hakkındaki bilgiler listelenir.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|**Açıklama**|Görüntü bağdaştırıcısı açıklama dizesi.|  
|**Bellek görüntüleme**|Grafik bağdaştırıcısında yüklü bellek miktarı.|  
|**Sürücü adı**|Grafik bağdaştırıcısı sürücüsü adı.|  
|**Sürücü sürümü**|Grafik Bağdaştırıcısı Sürücüsü sürümü.|  
|**Ad**|Grafik Bağdaştırıcı adı.|  
  
 **Deneme dosyası**  
 Yakalama oturumla ilişkili deneme dosya hakkındaki bilgileri listeler.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|**Yol**|.Vsglog dosyasının yolu. **Not:** eski yakalama altında bu özellik kullanılmaz.|  
  
 **Modül bilgilerini**  
 Uygulama tarafından yakalama oturumu sırasında yüklenen dinamik bağlantı kitaplıklarını (DLL'ler) sürümünü ve adını listeler.  
  
 **Sistem bilgileri**  
 Donanım ve işletim sistemi, uygulama yakalama oturumu sırasında barındırılan hakkında bilgileri listeler.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|**Bellek**|Bilgisayarda yüklü bellek miktarı.|  
|**İşletim sistemi mimarisi**|Hedef işletim sistemi CPU mimarisi.|  
|**İşletim sistemi sürümü**|İşletim sistemi sürümü.|  
|**İşlemci**|İşlemci, uygulama bilgisayarda yüklü.|  
|**Hedef uygulama mimarisi**|Hedef uygulama CPU mimarisi. Bu farklı olabilir **işletim sistemi mimarisi**.|  
  
 **Hedef uygulama**  
 Yakalama oturumunu konu uygulama hakkında bilgi listeler.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|**Son değişiklik tarihi/saati**|Uygulama oluşturuldu saat ve tarihi.|  
|**Yol**|Uygulamasının yolu.|  
|**İşlem kimliği**|Uygulama için verilen işlem kimliği.|  
|**Sürüm**|Uygulama sürümü.|  
  
 **VSG günlük dosyası**  
 Grafik günlük belgesi hakkındaki bilgiler listelenir.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|**Tarafından oluşturulan**|Grafik oluşturulan uygulama adını belge oturum açın. Örneğin, gelen yakalama oturumunu başlatılmışsa [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (el ile yakalama) Bu özellik değeri [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].|  
|**Oturum başlangıç saati**|Yakalama oturumunu başladığı saat ve tarihi.|  
|**Boyutu**|Grafik günlük belgesi boyutu.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Köşe gölgeleme nedeniyle nesnelerin eksikliği](walkthrough-missing-objects-due-to-vertex-shading.md)   
 [İzlenecek yol: Gölgeleme nedeniyle hataları işleme hata ayıklama](walkthrough-debugging-rendering-errors-due-to-shading.md)