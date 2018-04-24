---
title: Grafik olay Çağırma yığını | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.graphics.callstack
ms.assetid: 8a30168d-8b39-4de1-b094-c7356ba101a3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 879189fe71a4bf9dc0b7c56afe81d85d4316b6a4
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="graphics-event-call-stack"></a>Grafik Olay Çağırma Yığını
Grafik olay çağrı yığınında Visual Studio grafik Çözümleyicisi sorunlu grafik olayları ve uygulamanızın kaynak kodunu arasındaki ilişkiyi eşleme yardımcı olur.  
  
 Bu olay çağrı yığını penceresi.  
  
 ![Çağrı yığını önceki DrawIndexed olay. ] (media/gfx_diag_demo_graphics_event_call_stack_orientation.png "gfx_diag_demo_graphics_event_call_stack_orientation")  
  
## <a name="understanding-the-graphics-event-call-stack"></a>Grafik olay Çağırma yığını anlama  
 Olay Çağırma yığını, belirli bir Direct3D olay öncülük akışını anlamak için kullanabilirsiniz. Seçili Direct3D olay oluştuğunda var olarak çalışan bir uygulamanın geçerli iş parçacığının geçerli çağrı yığını yerine çağrı yığını görüntülediği dışında Visual Studio çağrı yığını penceresini benzer. Olay Çağırma yığını, çevresindeki kodu incelemek için seçilen Direct3D olay çağrısı siteye atlayabilirsiniz.  
  
 Olay çağrı yığını sorun olay kaynaklandığı kod yolu tanımlamak için kullanarak, codebase bilginiz sorunun olası kaynakları türetme için kullanabileceğiniz veya Geleneksel kullanabilmesi için uygulamanızın kaynak kodunda kesme noktaları ekleyebilirsiniz. hata ayıklama teknikleri uygulama veya olay parametreleri durumunu olay işlemiyorsa neden nasıl inceleyin. Bu inceleme, yalnızca işleme sorunları bildirilmiş kaynak kodundaki sorunlarını bulmanıza yardımcı olabilir.  
  
### <a name="graphics-event-call-stack-information"></a>Grafik olay Çağırma yığını bilgileri  
 Olay Çağırma yığını öncesi çerçeve olayları veya kullanıcı tanımlı olayları desteklemiyor. Grafik olay Çağırma yığını tablo biçiminde görüntülenir.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Ad**|Call sitesini içeren işlevi benzersiz olarak tanımlayan bir simge. Kullanılabilir olduğunda işlevi için hata ayıklama simgesi görüntülenir; Aksi takdirde işlevi uzaklığı görüntülenir.|  
|**Dosya**|Kaynak kodu dosyasının veya call sitesini içeren kitaplık dosyasının dosya adı.|  
|**Konum**|Call sitesini satır sayısı.|  
  
### <a name="links-to-graphics-objects"></a>Grafik nesneleri bağlantılar  
 Seçili grafik olay anlamak için kendisiyle ilişkili Direct3D nesneler hakkındaki bilgileri gerekebilir. **Grafik olay Çağırma yığını** pencere, bu bilgilere bağlantılar sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek Yol: Köşe Gölgeleme Nedeniyle Nesnelerin Eksikliği](walkthrough-missing-objects-due-to-vertex-shading.md)