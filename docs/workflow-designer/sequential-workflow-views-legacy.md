---
title: "Sıralı iş akışı görünümler (eski) | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- sequential workflow views
- sequential workflows, views
ms.assetid: 135f24b9-1b37-442b-9ef8-f0f2108a3212
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 9f412fa9afee6aa768447fc226553fd68970e646
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="sequential-workflow-views-legacy"></a>Sıralı iş akışı görünümler (eski)
[!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] bir eski Windows iş akışı kullanılabilecek Tasarımcısı sağlar hedef [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] Grafik oluşturmak için bir yol sağlar [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] bilinen kullanan uygulamalar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] kullanıcı arabirimi. [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] uygulamaları etkinlikler olarak adlandırılan iş akışı işlem adımlarından oluşur. Bir iş akışı oluşturmak için kendi ilgili etkinlik tasarımcıları gelen sürükleyerek tasarım yüzeyine etkinliklerini oluşturan **araç** tasarım yüzeyine.

 Olan bir sıralı iş akışı oluşturduğunuzda bir [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040), iş akışının üç görünüm mevcuttur. Bu görünümlere erişilebilir **iş akışı** menü ve tasarım yüzeyine bağlam menüsünden.

 Aşağıdaki tabloda, ad ve açıklama her görünümün listeler.

|Menü/sekmesi seçeneği|Açıklama|
|----------------------|-----------------|
|**Görünüm sıralı iş akışı**|Tasarım yüzeyi ve select sağ **görünüm sıralı iş akışı** görüntülemek için bağlam menüsünden seçeneği **sıralı iş akışı** etkinlik tabanlı gösteren görünüm grafik Sıralı iş akışı gösterimi. Ya da seçin **görünüm sıralı iş akışı** gelen **iş akışı** menüsü.|
|**İptal işleyicisini görüntüle**|Tasarım yüzeyi ve select sağ **iptal işleyicisini görüntüle** görüntülemek için bağlam menüsünden seçeneği **sıralı iş akışı** görüntülemek, hangi gösterir [CancellationHandlerActivity ](http://go.microsoft.com/fwlink?LinkID=65050) etkinliği iş akışı ile ilişkilendirilmiş. Ya da seçin **iptal işleyicisini görüntüle** gelen **iş akışı** menüsü.|
|**Hata işleyicisini görüntüle**|Tasarım yüzeyi ve select sağ **hata işleyicisini görüntüle** görüntülemek için bağlam menüsünden seçeneği **hataları** görüntülemek, hangi gösterir [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) etkinliği iş akışı ile ilişkilendirilmiş. Ya da seçin **hata işleyicisini görüntüle** gelen **iş akışı** menüsü.|

 Benzer görünümler hakkında daha fazla bilgi için bkz: [aktivite görünümleri (eski)](../workflow-designer/activity-views-legacy.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Etkinlik Görünümleri (Eski)](../workflow-designer/activity-views-legacy.md)
- [Eski İş Akışı Projeleri Oluşturma](../workflow-designer/creating-legacy-workflow-projects.md)
- [İş akışı yazma modları](http://go.microsoft.com/fwlink?LinkID=65014)