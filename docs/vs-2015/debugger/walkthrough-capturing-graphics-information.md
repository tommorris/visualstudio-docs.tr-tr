---
title: 'İzlenecek yol: Grafik bilgilerini yakalama | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48f12f6e-57b4-48ec-a145-89fa71a42424
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: de553729d37bb82d1b30c6a142f7e65c983bb1c1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631008"
---
# <a name="walkthrough-capturing-graphics-information"></a>İzlenecek Yol: Grafik Bilgilerini Yakalama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [izlenecek yol: grafik bilgilerini yakalama](https://docs.microsoft.com/visualstudio/debugger/graphics/walkthrough-capturing-graphics-information).  
  
Bu izlenecek yolda nasıl kullanılacağını gösterir [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] el ile bir Direct3D uygulamadan grafik bilgilerini yakalamak için grafik tanılama.  
  
 Bu örneklerde bu görevler gösterilir:  
  
-   Grafik tanılama uygulamanıza takma  
  
-   Graf bilgilerini yakalama  
  
## <a name="capturing-graphics-information"></a>Graf bilgilerini yakalama  
 Grafik tanılama araçlarını kullanmak için öncelikle kullanır grafik bilgilerini yakalama olması. Yakalama özelliğini etkinleştirmek için kullanın **tanılamayı Başlat** başladığında uygulamanızı grafik tanılama yeteneklerinizi komutu.  
  
#### <a name="to-enable-the-capture-of-graphics-information-after-a-project-or-solution-is-loaded"></a>Bir proje veya çözüm sonra grafik bilgilerini yakalama etkinleştirmek için yüklenir  
  
1.  İçinde [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], grafik bilgilerini yakalamak istediğiniz uygulama için bir proje veya çözüm dosya yükleyin.  
  
2.  Grafik tanılama araç çubuğunda **tanılamayı Başlat**.  
  
#### <a name="to-enable-the-capture-of-graphics-information-without-loading-a-project-or-solution"></a>Bir proje veya çözüm yüklemeden grafik bilgilerini yakalamayı etkinleştirme  
  
1.  Menü çubuğunda, **dosya**, **açık**, **proje/çözüm**. **Açık proje** iletişim kutusu görüntülenir.  
  
2.  Yürütülebilir dosya, grafik bilgilerini yakalamak ve ardından istediğiniz uygulama için bir proje veya çözüm dosyası yerine belirtin **açık**.  
  
3.  Menü çubuğunda, **hata ayıklama**, **grafik**, **tanılamayı Başlat**.  
  
 Uygulamayı başlatın ve işleme çerçeveler olduktan sonra grafik bilgilerini yakalayabilir.  
  
#### <a name="to-capture-graphics-information"></a>Grafik bilgilerini yakalamak için  
  
-   Grafik tanılama araç çubuğunda **yakalama** düğmesi. ![Grafik yakalama düğmesinin simgesi](../debugger/media/debuggingdirectxgraphics.png "DebuggingDirectXGraphics")  
  
     veya  
  
     Odak uygulamayla basın **Print Screen**.  
  
 Her zaman bir kare hakkında bilgi yakalama grafik tanılama Direct3D olayları ve ilişkili durumu kaydeder ve bu verileri bir grafik günlüğüne ekler. Yeni bir grafik günlüğü, her bir grafik Tanılama oturumu için oluşturulur. Grafik günlükleri hakkında daha fazla bilgi için bkz: [genel bakış](../debugger/overview-of-visual-studio-graphics-diagnostics.md).  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bu izlenecek yol, grafik bilgilerini elle yakalama gösterilmiştir. Sonraki adım olarak, bu seçenek göz önünde bulundurun:  
  
-   Grafik tanılama araçlarını kullanarak yakalanan grafik bilgileri analiz etmeyi öğrenin. Bkz: [genel bakış](../debugger/overview-of-visual-studio-graphics-diagnostics.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Grafik Bilgilerini Yakalama](../debugger/capturing-graphics-information.md)



