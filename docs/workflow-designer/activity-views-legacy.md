---
title: "Aktivite görünümleri (eski) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- activities, activity views
- views, activity
- activity views
ms.assetid: 83dc68cd-2cb2-45c2-9a6e-10d82053171a
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 50f57684db32f601bd4cbf870456da458aa5ce7c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="activity-views-legacy"></a>Aktivite görünümleri (eski)
Tarafından sağlanan etkinliklerin birçok [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)], hangi iş akışları oluşan gelen eski kullanılabilen birkaç tasarım görünümleri sahip [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]. Bir etkinlik Tasarımcısı'ndan sürüklediğinizde **araç** tasarım yüzeyine ve bundan sonra etkinliği seçtiğinizde kullanarak ya da farklı tasarım görünümleri arasında geçiş yapabilirsiniz **iş akışı**menüsü veya seçili etkinliği sağ tıklanarak. Ayrıca, seçili etkinlik adı işaretçinin taşıdığınızda, sekmeler açılan kümesi farklı görünümleri arasında geçiş yapmak için kullanabileceğiniz görünür.  
  
 Her etkinlik en az bir görünüm; yine de sahip istiyor musunuz? Bu bir etkinlik Tasarımcısı'ndan sürüklediğinizde gösterilen varsayılan görünümdür **araç** tasarım yüzeyine. Bu etkinlik varsayılan görünüm olarak kullanılabilir **[etkinlik türü] görüntülemek** seçeneği menüleri ve sekmesinde, örneğin, **görünüm paralel**. Ek görünümler etkinliklerin çoğu sahiptir ve farklı etkinlikler farklı görünümleri olabilir. Örneğin, [TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093) etkinlik maaş görünümü vardır ve [EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030) etkinlik sahip bir olay görünümü. Çoğu Windows Workflow Foundation ile gelen etkinliklerin **iptal işleyicisini görüntüle** ve **görünümü hataları** Tasarım görünümüne görünümleri [CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050) ve [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) kendileriyle ilişkilendirilmiş.  
  
 Aşağıdaki tabloda, ad ve açıklama her görünümün listeler.  
  
|Menü/sekmesi seçeneği|Açıklama|  
|----------------------|-----------------|  
|**Görünüm [etkinlik türü]**|Seçili etkinlik varsayılan grafik gösterimi görüntülemek için bu menü veya sekme seçeneği seçin.|  
|**İptal işleyicisini görüntüle**|Bu menü veya sekmesinde görünüm için görünüm seçeneği [CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050) seçili aktivitesiyle ilişkilendirilmiş.|  
|**Hata işleyicisini görüntüle**|Bu menü veya sekmesinde görünüm için görünüm seçeneği [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) seçili aktivitesiyle ilişkilendirilmiş.|  
|**Dengeleme İşleyicisini Görüntüle**|Bu menü veya sekmesinde görünüm için görünüm seçeneği [CompensationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65053) seçili ile ilişkili [TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093).|  
|**Olay işleyicisini görüntüle**|Bu menü veya sekmesinde görünüm için görünüm seçeneği [EventHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65018) seçili ile ilişkili [EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030).|  
  
 Benzer görünümler hakkında daha fazla bilgi için bkz: [sıralı iş akışı görünümler (eski)](../workflow-designer/sequential-workflow-views-legacy.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski iş akışı etkinlikleri](../workflow-designer/legacy-workflow-activities.md)   
 [Sıralı iş akışı görünümler (eski)](../workflow-designer/sequential-workflow-views-legacy.md)