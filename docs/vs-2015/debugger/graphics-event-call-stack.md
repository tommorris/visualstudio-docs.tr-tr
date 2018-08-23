---
title: Grafik olay Çağırma yığını | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.graphics.callstack
ms.assetid: 8a30168d-8b39-4de1-b094-c7356ba101a3
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d866e63ecffbed5cd5e9a9e477f99fbd8e8c3fc9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694812"
---
# <a name="graphics-event-call-stack"></a>Grafik Olay Çağırma Yığını
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [grafik olay çağrı yığını](https://docs.microsoft.com/visualstudio/debugger/graphics/graphics-event-call-stack).  
  
Grafik olay çağrı yığını'nı Visual Studio grafik Çözümleyicisi sorunlu grafik olaylarını ve uygulamanızın kaynak kodu arasındaki ilişkiyi eşlemenize yardımcı olur.  
  
 Bu olay çağrı yığını penceresinde.  
  
 ![Çağrı yığını önceki DrawIndexed olay. ](../debugger/media/gfx-diag-demo-graphics-event-call-stack-orientation.png "gfx_diag_demo_graphics_event_call_stack_orientation")  
  
## <a name="understanding-the-graphics-event-call-stack"></a>Grafik olay çağrı yığını anlama  
 Olay çağrı yığını, belirli bir Direct3D olaya yol açan akışını anlamak için kullanabilirsiniz. Seçili Direct3D olayın gerçekleştiği edildiğinde bulunduğu gibi çalışan bir uygulamada etkin iş parçacığının geçerli çağrı yığınını görüntülemek yerine, çağrı yığınını görüntüler dışında Visual Studio çağrı yığını penceresini benzer. Olay çağrısı yığını, çevreleyen kod İnceleme seçili Direct3D olayın çağrı sitesini atlayabilirsiniz.  
  
 Bir sorun olay kaynaklandığı kod yolu belirlemek için olay çağrı yığını kullanarak olası sorun kaynaklarını çıkarmaya kod tabanının bilginizi kullanabilirsiniz veya Geleneksel kullanabilmesi için uygulamanızın kaynak kodunda kesme noktaları ekleyebilirsiniz. teknikleri, uygulama veya olay parametreleri durumunu işlemiyorsa olayın neden nasıl incelemek için hata ayıklama. Bu inceleme, yalnızca işleme sorunları bildirilen kaynak kodundaki sorunlarını bulmanıza yardımcı olabilir.  
  
### <a name="graphics-event-call-stack-information"></a>Grafik olay çağrı yığını bilgilerini  
 Olay Çağırma yığını öncesi çerçeve olayları veya kullanıcı tanımlı olayları desteklemez. Grafik olay çağrı yığını, tablo biçiminde görüntülenir.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Ad**|Çağrı sitesini içeren işlev benzersiz olarak tanımlayan bir simge. Hata ayıklama sembolü işlev için kullanılabilir hale geldiğinde görüntülenir; Aksi halde, işlev uzaklık görüntülenir.|  
|**Dosya**|Kaynak kodu dosyanızı veya çağrı sitesini içeren kitaplık dosyasının dosya adı.|  
|**Konum**|Çağrı sitesini satır sayısı.|  
  
### <a name="links-to-graphics-objects"></a>Grafik nesneleri bağlantılar  
 Seçilen grafik olay anlamak için ilişkili Direct3D nesneleri hakkındaki bilgileri gerekebilir. **Grafik olay çağrı yığını** penceresi bu bilgilere bağlantılar sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek Yol: Köşe Gölgeleme Nedeniyle Nesnelerin Eksikliği](../debugger/walkthrough-missing-objects-due-to-vertex-shading.md)



