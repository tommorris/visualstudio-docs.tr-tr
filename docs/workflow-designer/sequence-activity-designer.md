---
title: "Sıralı etkinlik Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.Sequence.UI
ms.assetid: 51c8d3cb-4d43-458f-9631-b63755f9ac94
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 51f138d17c2b0f8d8a483ef09c298d1dbbf9345c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="sequence-activity-designer"></a>Sıralı etkinlik Tasarımcısı
<xref:System.Activities.Statements.Sequence> Etkinlik sırayla yürütür alt etkinliklerin sıralı bir koleksiyonu içerir.  
  
 Etkinlikler kümesini sırayla yürütmek için başka bir yolu bir <xref:System.Activities.Statements.Flowchart> etkinlik. Kullanmayı [akış çizelgesi](../workflow-designer/flowchart-activity-designer.md) basit dallanma veya diagrammatically modellemek için istediğiniz program akışı döngü olduğunda.  
  
## <a name="using-the-sequence-activity-designer"></a>Sıralı etkinlik Tasarımcısı'nı kullanarak  
 Eklemek için bir <xref:System.Activities.Statements.Sequence> etkinlik, sürükle **dizisi** etkinlik Tasarımcısı'ndan **araç** ve oturum bırakın [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] yüzeyini. Bunun için bir alt etkinlik eklemek için <xref:System.Activities.Statements.Sequence> etkinlik, diğer bazı etkinliğinden sürükleyin **araç** ve üçgen İpucu metin kutusundaki "Buraya etkinliğini Drop" bırakın.  
  
### <a name="sequence-activity-properties-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda sıralı etkinlik özellikleri  
 Aşağıdaki tabloda <xref:System.Activities.Statements.Sequence> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikler, özellik kılavuzu veya tasarımcı yüzeyine düzenlenebilir.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı belirtir <xref:System.Activities.Statements.Sequence> etkinlik Tasarımcısı'nda başlığı. Varsayılan değer sırasıdır. Değeri, özellik kılavuzu veya etkinlik Tasarımcısı başlığındaki doğrudan düzenlenebilir.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış Çizelgesi](../workflow-designer/flowchart-activity-designer.md)   
 [Denetim akışı](../workflow-designer/control-flow-activity-designers.md)