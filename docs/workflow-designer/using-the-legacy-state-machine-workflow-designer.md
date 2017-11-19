---
title: "Eski Durum makinesi iş akışı Tasarımcısı'nı kullanarak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- StateFinalizationActivity activity
- StateActivity activity
- SetStateActivity activity
- EventDrivenActivity activity
- state machine workflow designer
- state machine workflows, designer
- state machine workflows, activities
- StateInitializationActivity activity
ms.assetid: 2cd21123-35c2-4eaf-82f6-86fce7a8f04d
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3eefde445f5c8aca7199d4316472fe92c3160d00
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="using-the-legacy-state-machine-workflow-designer"></a>Eski Durum makinesi iş akışı Tasarımcısı'nı kullanarak
Oluştururken yeni bir durum makine iş akışı projesinde [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] ya da hedefleyen [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)], ya da kullanmayı tercih edebileceğiniz **Durum makinesi iş akışı konsol uygulaması** veya  **Durum makinesi iş akışı Kitaplığı** eski proje şablonu. Bu durum makinenin proje şablonlarından birini seçerseniz, durumu makine Tasarımcısı eski iş akışı Tasarımcısı kullanıcı arabirimi olarak sunulur. Eski durum makine proje şablonları hakkında daha fazla bilgi için bkz [nasıl yapılır: oluşturma durumu makine iş akışı konsol uygulamaları (eski)](../workflow-designer/how-to-create-state-machine-workflow-console-applications-legacy.md) ve [nasıl yapılır: bir Durum makinesi iş akışı kitaplığı (eski)oluşturun](../workflow-designer/how-to-create-a-state-machine-workflow-library-legacy.md).  
  
 Bir Durum makinesi iş akışı durumları kümesinden oluşur. Durum, bir başlangıç durumu belirtilir. Her bir durumu, belirli bir dizi olayları alabilir. Olaya bağlı olarak, başka bir duruma geçiş yapılabilir. Durum makinesi iş akışı, bir son duruma sahip olabilir. Son durumuna geçiş yapıldığında, iş akışı tamamlanır.  
  
## <a name="state-machine-designer-views"></a>Durum makinesi Tasarımcı görünümleri  
 Durum makinesi Tasarımcısı etkinlikleri serbestçe tasarım yüzeyine taşınabildiğinden, yani bir serbest Tasarımcı olur. İki görünüm durumu makine Tasarımcısı vardır: *durumu* Görünüm ve *olay denetimli* görünümü.  
  
 Durum görünümü durumu etkinlikleri ve içinde bir durumu etkinlik bulunan olay denetimli etkinlikleri gösterir. Bu görünümde, bir durumdan geçişleri genişleten olay denetimli etkinliğinden bir durumda başka bir duruma çizgilerle gösterilir. Satır kendiniz çizerek geçişleri de oluşturabilirsiniz. Geçiş çizmek için olay denetimli etkinliği seçin ve etkinlik işleyicilerinin birini seçin ve sürükleyin. Bu eylem bir çizgi çizer. Bu satırı durumları arasında geçiş gösteren hedef durum sonra bağlı.  
  
 Olay görünümü yönelimli erişmek için bir olay denetimli etkinliğe çift tıklayın. Görüntülenen Tasarımcısı sıralı iş akışı Tasarımcısı'nı benzer olur. Tasarımcı üstünde gezinti çubuğunda görüntülenen olay temelli bir eyleme kadar etkinlikleri hiyerarşisini gösterir. Görüntülenen hiyerarşideki herhangi bir öğeyi tıklatarak durum görünümüne gidebilirsiniz. Durum görünümü içinde başka bir durumdan diğerine geçiş çizilmiş ve bu etkinliği görünümünü güdümlü olay görüntülüyorsanız, kümesi durumu etkinlik size olay denetimli etkinliğe eklenir. Küme durumu etkinlik özelliklerini değiştirirseniz, durum görünümünde yansıtılır.  
  
## <a name="state-machine-workflow-activities"></a>Durum makinesi iş akışı etkinlikleri  
 Aşağıdaki tabloda bir Durum makinesi iş akışı Tasarımcısı'nda kullanılan anahtar etkinliklerini açıklar.  
  
|Araç kutusu adı|Etkinlik|Açıklama|  
|------------------|--------------|-----------------|  
|**Durum**|[Buraya StateActivity](http://go.microsoft.com/fwlink?LinkID=65042)|Durum makinesinin durumda temsil eder; Ek içeren **buraya StateActivity** etkinlikler. Daha fazla bilgi için bkz: [kullanarak buraya StateActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65083).|  
|**SetState**|[SetStateActivity](http://go.microsoft.com/fwlink?LinkID=65041)|Yeni bir durum geçiş belirtir. Daha fazla bilgi için bkz: [SetStateActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65082).|  
|**StateInitialization**|[StateInitializationActivity](http://go.microsoft.com/fwlink?LinkID=65044)|Bir durum girildiğinde çalıştırır; diğer etkinlikleri içerebilir. Daha fazla bilgi için bkz: [StateInitialization etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65006).|  
|**StateFinalization**|[StateFinalizationActivity](http://go.microsoft.com/fwlink?LinkID=65043)|İçerilen etkinlikleri ayrılırken yürütür bir [buraya StateActivity](http://go.microsoft.com/fwlink?LinkID=65042) etkinlik. Daha fazla bilgi için bkz: [StateFinalizationActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65008).|  
|**EventDriven**|[EventDrivenActivity](http://go.microsoft.com/fwlink?LinkID=65029)|Çalıştırmaya başlamak için bir dış olay kullanan durumları için kullanılır. **EventDrivenActivity** etkinlik uygulayan bir etkinlik olmalıdır [IEventActivity](http://go.microsoft.com/fwlink?LinkID=65032) ilk alt etkinlik olarak arabirimi. Daha fazla bilgi için bkz: [kullanarak EventDrivenActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65068).|  
  
 Bir iş akışındaki durumu makine ana bileşeni [buraya StateActivity](http://go.microsoft.com/fwlink?LinkID=65042) etkinlik. Olayları bir Durum makinesi iş akışı çeşitli yerlerinde yakalanır gibi farklı durumlara olaylarla ilişkili görevlerin işlenmesi için girilir. İş akışı ömrü boyunca, iş akışı bırakın ve birkaç farklı durumlara. Bu durumu kullanarak birbirine bağlayan [SetStateActivity](http://go.microsoft.com/fwlink?LinkID=65041) etkinlik.  
  
 Yeni bir sürüklediğinizde **buraya StateActivity** iş akışı tasarım yüzeyine eklediğiniz [EventDrivenActivity](http://go.microsoft.com/fwlink?LinkID=65029), [StateInitializationActivity](http://go.microsoft.com/fwlink?LinkID=65044), [ StateFinalizationActivity](http://go.microsoft.com/fwlink?LinkID=65043), veya ek **buraya StateActivity** etkinlikleri alt etkinlikler olarak.  
  
> [!CAUTION]
>  İş akışları oluşturmak için Durum makinesi iş akışı Tasarımcısı'nı kullandığınızda, tasarlama konusunda iş akışı yapısını izlemelisiniz **belge anahattı** Görünümü penceresi. Görünüm durumu makine akışında yapısının **belge anahattı** Görünüm penceresi etkinlikleri iş akışı biçimlendirme dosyasındaki mantıksal düzenini yansıtır. Tasarım yüzeyine göründükleri gibi iş akışı etkinlikleri fiziksel düzenini etkinlikleri iş akışı biçimlendirme dosyasındaki mantıksal düzenini yansıtma değil.  
>   
>  Açmak için **belge anahattı** penceresi, **Görünüm** menüsündeki **diğer pencereler**ve ardından **belge anahattı**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Durum makinesi iş akışı konsol uygulamaları (eski) oluşturma](../workflow-designer/how-to-create-state-machine-workflow-console-applications-legacy.md)   
 [Nasıl yapılır: bir Durum makinesi iş akışı kitaplığı (eski) oluşturun](../workflow-designer/how-to-create-a-state-machine-workflow-library-legacy.md)   
 [Durum makinesi iş akışları](http://go.microsoft.com/fwlink?LinkID=65016)   
 [Buraya StateActivity etkinliğini kullanma](http://go.microsoft.com/fwlink?LinkID=65083)   
 [StateInitializationActivity etkinliğini kullanma](http://go.microsoft.com/fwlink?LinkID=65006)   
 [StateFinalizationActivity etkinliğini kullanma](http://go.microsoft.com/fwlink?LinkID=65008)   
 [SetStateActivity etkinliğini kullanma](http://go.microsoft.com/fwlink?LinkID=65082)   
 [EventDrivenActivity etkinliğini kullanma](http://go.microsoft.com/fwlink?LinkID=65068)