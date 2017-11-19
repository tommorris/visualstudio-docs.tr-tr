---
title: Grafik olay listesi | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.graphics.eventlist
ms.assetid: a1252e19-b27d-4dc7-a16b-fdac894c1f0e
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cc520e9d28e8cc02262833d2de4cba088b879dab
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="graphics-event-list"></a>Grafik Olay Listesi
Grafik olay listesi Visual Studio grafik Çözümleyicisi'nde bir çerçeve oyun veya uygulama oluşturulmaya çalışılırken kaydedilmiş Direct3D olayları keşfetmek için kullanın.  
  
 Bu olay listesidir:  
  
 !["Dizin" adında olayları listesi. ] (media/gfx_diag_demo_event_list_orientation.png "gfx_diag_demo_event_list_orientation")  
  
## <a name="using-the-event-list"></a>Olay listesi kullanma  
 Olay listesi, onu diğer grafik analiz araçları tarafından görüntülenen bilgileri yansıtılan bir olay seçtiğinizde, Bu diğer araçlar birlikte olay listesi kullanarak bir işleme sorunun nedenini belirlemek için ayrıntılı inceleyebilirsiniz. Olay listesi diğer grafik analiz araçları ile birlikte kullanarak işleme sorunları nasıl çözebilir hakkında daha fazla bilgi için bkz: [örnekleri](graphics-diagnostics-examples.md).  
  
 Olay listesi özelliklerini etkili bir şekilde kullanarak olayları binlerce içerebilir karmaşık çerçevelerinin çevresinde almak için önemlidir. Olay listesi verimli kullanmak, görünüm sizin için en iyi seçin, Ara'yı kullanın olay listesini filtrelemek için bir olayla ilişkili Direct3D nesneleri hakkında daha fazla bilgi için bağlantıları izleyin ve oku kullanın arasında hareket etmek için düğmeler çağrıları hızla çizin.  
  
### <a name="color-coded-events-in-direct3d-12"></a>Direct3D 12 ren kodlu olaylar  
 Direct3D 12 farklı donanım işlevselliği için karşılık gelen birden çok sıraya kullanıma sunar. Direct3D 12 uygulamasının bir yakalama çalışırken Direct3D 12 belirli grafik olayda ile ilişkili sıra tanımlamaya yardımcı olmak üzere olayları kendi sıra göre olay listesinde kodludur.  
  
|Direct3D 12 sırası|Renk|  
|-----------------------|-----------|  
|Sıra oluştur|Yeşil|  
|Sıra işlem|Sarı|  
|Sıra kopyalayın|Turuncu|  
  
 Direct3D 11 birden çok sıraya kullanıma, olayları ren kodlu kalmayacak Direct3D 11 uygulamasının yakalama ile çalışırken olay listesinde değil.  
  
### <a name="event-list-views"></a>Olay liste görünümleri  
 Olay listesi grafik olayları iş akışı ve tercihleri desteklemek için farklı şekillerde düzenlemek iki farklı görünümleri destekler. İlk görünümdür *GPU iş Görünüm* hangi düzenler olaylar ve ilişkili durumlarına hiyerarşik olarak. İkinci görünüm *Zaman Çizelgesi görünümüne* hangi düzenler olayları kronolojik, düz bir liste.  
  
 **GPU iş** görünümü  
 Görüntüler, olaylar ve durumlarına bir hiyerarşideki yakalandı. Hiyerarşinin üst düzeyi çizim çağrıları, temizler, mevcut ve görünümleri ile ilgili olanlar gibi olayların oluşur. Olay listesi, çizim çağrısı aynı anda geçerli olan aygıt durumunu görüntülemek için çizim çağrıları genişletebilirsiniz; ve daha fazla durum değerlerine ayarlayın olayları görüntülemek için her tür genişletebilirsiniz. Bu düzeyde, belirli bir durumdaki bir önceki çerçevede ayarlanmış olup olmadığını ya da son çizin beri çağrısı birden çok kez ayarlanmış de görebilirsiniz.  
  
 **Zaman çizelgesi** görünümü  
 Yakalanan her olay kronolojik sırada görüntüler. Olay listesi düzenlenmesi bu şekilde, Visual Studio'nun önceki sürümleri ile aynı olur.  
  
##### <a name="to-change-the-event-list-view-mode"></a>Olay listesi görünümü modunu değiştirmek için  
  
-   İçinde **grafik olay listesi** , olayların listesinin penceresi bulun **Görünüm** açılır ve ya da seçtiğiniz **zaman çizelgesi** görünüm veya **GPU iş** görünümü.  
  
### <a name="filtering-events"></a>Olayları filtreleme  
 Arama kutusunu kullanabilirsiniz — sağ üst köşesinde bulunan **grafik olay listesi** penceresi — yalnızca, adları içeren belirli anahtar sözcükleri olayları içermek üzere olayların listesini filtrelemek için. Tek anahtar sözcükleri ister belirtebilirsiniz `Vertex`— önceki örnekte gösterildiği gibi — veya benzer bir noktalı virgülle ayrılmış liste kullanarak birden çok anahtar sözcükleri `Draw;Primitive`— ya da olaylar eşleşen `Draw` veya `Primitive` adlarında. Aramaları için boşluk hassas — Örneğin, `VSSet` ve `VS Set` farklı aramalar — böylece form aramaları için dikkatle emin olun.  
  
### <a name="moving-between-draw-calls"></a>Draw çağrıları arasında taşıma  
 İncelemek için `Draw` çağrıdır kullanabileceğiniz özellikle önemli **sonraki Git çizin çağrısı** ve **önceki Git çizin çağrısı** düğmeleri — solüstköşesindebulunan**Grafik olay listesi** penceresi — bulmak ve çizim çağrıları arasında hızlıca taşımak için.  
  
### <a name="links-to-graphics-objects"></a>Grafik nesneleri bağlantılar  
 Belirli grafik olaylar anlamak için bir olay tarafından başvurulan Direct3D nesneleri veya Direct3D geçerli durumu hakkında ek bilgi gerekebilir. Çok sayıda olay daha fazla ayrıntı için izleyebileceğiniz bu bilgilere bağlantılar sağlar.  
  
## <a name="kinds-of-events-and-event-markers"></a>Olayların ve olay işaretçileri türleri  
 Liste düzenlenir olay dört kategoriye görüntülenen olayları: Genel olayları olayları, olay kullanıcı tanımlı grupları ve kullanıcı tanımlı olay işaretçileri çizin. Genel olaylar dışında her olay ait olduğu kategoriyi belirten bir simge ile birlikte görüntülenir.  
  
|Simge|Olay açıklaması|  
|----------|-----------------------|  
|(simge yok)|Genel olay<br /> Değil bir kullanıcı tarafından tanımlanan olay, kullanıcı tanımlı olay grubu veya olay çizin herhangi bir olay.|  
|![Draw olay simgesi](media/vsg_eventlist_icon_draw.png "vsg_eventlist_icon_draw")|Olay çizme<br /> Yakalanan çerçevesinde oluşan bir çizim olay işaretler.|  
|![Kullanıcı &#45; tanımlanan olay işaretçi simgesi](media/vsg_eventlist_icon_user.png "vsg_eventlist_icon_user")|Kullanıcı tanımlı olay grubu<br /> Grupları, uygulama tarafından tanımlanan olayları, ilgili.|  
|![Kullanıcı &#45; tanımlanan olay işaretçi simgesi](media/vsg_eventlist_icon_user.png "vsg_eventlist_icon_user")|Kullanıcı tanımlı olay işaretçisi<br /> Belirli bir konuma uygulama tarafından tanımlandığı şekilde işaretler.|  
  
## <a name="marking-user-defined-events-in-your-app"></a>Uygulamanızda işaretlenmesi kullanıcı tanımlı olayları  
 Kullanıcı tanımlı olayları uygulamanıza özeldir. Grafik olay listesi içindeki olaylarla uygulamanızda oluşan önemli olayları ilişkilendirmek için bunları kullanabilirsiniz. Örneğin, ilgili olaylar düzenlemek için kullanıcı tanımlı olay gruplar oluşturabilirsiniz — kullanıcı arabirimini oluşturmak olanlar gibi — böylece daha kolay olay listesine göz atabilir veya işaretçileri nesneleri belirli bir türde olduğunda oluşturabilirsiniz grubu veya Hiyerarşiler olan Grafik etkinliklerini olay listesinde kolayca bulabilmek çizilmiştir.  
  
 Grupları ve işaretçileri uygulamanızı oluşturmak için hata ayıklama araçları kullanımına yöneliktir diğer Direct3D Direct3D sağlayan aynı API'ları kullanın. Bu API'leri bazen Direct3D sürümleri arasında değişiklik, ancak temel işlevleri aynıdır.  
  
### <a name="user-defined-events-in-direct3d-12"></a>Kullanıcı tanımlı olayları Direct3D 12  
 Grupları ve işaretçileri Direct3D 12'de oluşturmak için bu bölümde açıklanan API'leri kullanın. Aşağıdaki tabloda bir komut sırasındaki olayları işaretleme mı listesi komutu bağlı olarak kullanabileceğiniz API'ları özetler.  
  
|API açıklaması|[ID3D12CommandQueue](https://msdn.microsoft.com/library/dn788627.aspx)|[ID3D12GraphicsCommandList](https://msdn.microsoft.com/library/dn903537.aspx)|  
|---------------------|----------------------------------------------------------------------------|-----------------------------------------------------------------------------------|  
|Kullanıcı tanımlı olay kullanılabilirliğini denetleyin|[PIXGetStatus](http://msdn.microsoft.com/en-us/f7ebd985-fb5d-46d7-abec-099df4b9be0e)|[PIXGetStatus](http://msdn.microsoft.com/en-us/1046ac43-a0a3-42bf-bae8-14aa72fa7567)|  
|Olay grubu başlayın|[PIXBeginEvent](http://msdn.microsoft.com/en-us/5f51fff7-f313-4558-965b-2a443653cd7b)|[PIXBeginEvent](http://msdn.microsoft.com/en-us/4ddb3311-b9b5-449a-bbfb-7634e0d56e87)|  
|Son olay grubu|[PIXEndEvent](http://msdn.microsoft.com/en-us/fb526bf2-c17d-4a2a-8665-3b577a0f7fba)|[PIXEndEvent](http://msdn.microsoft.com/en-us/a3cd34a9-9dd9-40e1-ae86-0214b25ff185)|  
|Bir olay işaret oluşturma|[PIXSetMarker](http://msdn.microsoft.com/en-us/0caf49ed-c99d-405e-89f4-0c887b8474ad)|[PIXSetMarker](http://msdn.microsoft.com/en-us/6610e5b9-a0c5-4236-b551-b6eb9fac64c1)|  
  
### <a name="user-defined-events-in-direct3d-11-and-earlier"></a>Kullanıcı tanımlı olayları Direct3D 11 ve önceki sürümleri  
 Grupları ve işaretçileri Direct3D 11 veya önceki oluşturmak için bu bölümde açıklanan API'leri kullanın. Aşağıdaki tabloda farklı Direct3D 11 ve önceki sürümleri Direct3D için kullanabileceğiniz API'ları özetler.  
  
|API açıklaması|[ID3D11DeviceContext2](http://msdn.microsoft.com/library/windows/desktop/dn280498.aspx) (Direct3D 11.2)|[ID3DUserDefinedAnnotation](http://go.microsoft.com/fwlink/p/?LinkID=250967) (Direct3D 11.1)|D3DPerf_ API ailesi (Direct3D 11.0 ve önceki sürümler)|  
|---------------------|---------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------|  
|Olay grubu başlayın|`BeginEventInt`|`BeginEvent`|`D3DPerf_BeginEvent`|  
|Son olay grubu|`EndEventInt`|`EndEvent`|`D3DPerf_EndEvent`|  
|Bir olay işaret oluşturma|`SetMarkerInt`|`SetMarker`|`D3DPerf_SetMarker`|  
  
 Direct3D sürümünüz destekleyen bu API'leri birini kullanabilirsiniz — Direct3D 11.1 API hedefliyorsanız, örneğin, kullanabilirsiniz `SetMarker` veya `D3DPerf_SetMarker` bir olay işaret oluşturmamayı ancak `SetMarkerInt` çünkü Direct3D kendi yalnızca kullanılabilir 11.2 — ve hatta Direct3D farklı sürümlerini birlikte aynı uygulamada destekleyen karıştırabilirsiniz.  

<!-- VERSIONLESS -->
<a name="resource-history"></a>
##Kaynak geçmiş Visual Studio 2017 ve daha sonraki sürümleri içeren **kaynak geçmişi** penceresi.  İzleme simgesini seçerek ![izleme simgesi](media/gfx_watch.png) bir girişi yanındaki **olay listesi** penceresi getirecek **kaynak geçmişi** penceresi aşağıda gösterildiği:

![Kaynak geçmişi](media/gfx_diag_resource_history.png)

Bu pencere olay listesinde seçili öğenin geçmişini görüntülemek sağlar.  Üstteki açılan geçmişini görüntülemek için diğer öğelerini seçmek için kullanılabilir.  Pencerenin üst yarısı içeren **çerçeve Kurulum olayları**.  İçine kalan olayları bunlar *oluşturma* kategori yazın ve genellikle başlatın ve kaynak oluşturma çağrıları.  Pencere yarısı içeren alt **çerçeve olayları** bölümü.  Bunlar normal okuma ve yazma kaynak kullanımı sırasında meydana gelen olayları.  

Sütun|Açıklama
---|---
**Türü** | Giriş türü genellikle gösterilir *oluşturma*, *okuma* ve *yazma*.  
**Görünümü** | O anda bir küçük resim kaynağının adını gösterir.  Küçük resim o anda kaynağın Ayrıntılar görünümünü açmak için çift tıklayın.  
**Olay**| Oluştuğu yöntem çağrısı gösterir olayı oluşturulur.  Tüm ek geçmişi ayrı ayrı öğeler üzerinde İzleme simgesini seçerek görüntülenebilir ![izleme simgesi](media/gfx_watch.png) uygun satırındaki.  Ayrıca, mavi renkte gibi çizilir herhangi öğesi `m_commandList` yukarıdaki ekran görüntüsünde, daha fazla ayrıntı için seçilebilir.
<!-- /VERSIONLESS -->

## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Cihaz durumu nedeniyle nesnelerin eksikliği](walkthrough-missing-objects-due-to-device-state.md)