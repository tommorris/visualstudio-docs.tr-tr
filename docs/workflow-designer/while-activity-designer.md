---
title: "While etkinlik Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.While.UI
ms.assetid: ea008091-2e4c-4f64-bfa5-afb919552446
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: b70e0c66813c474d5711538843da93a669df88d1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="while-activity-designer"></a>While etkinlik Tasarımcısı
<xref:System.Activities.Statements.While> Etkinlik yürütür içinde yer alan etkinlik kendi <xref:System.Activities.Statements.While.Body%2A> while belirtilen <xref:System.Activities.Statements.While.Condition%2A> değerlendiren **doğru**. Kapsanan etkinlik hiçbir zaman yürütür. En az bir kez çalıştırılacak kapsanan etkinlik istiyorsanız kullanın <xref:System.Activities.Statements.DoWhile> etkinlik yerine.  
  
## <a name="while-properties-in-workflow-designer"></a>While iş akışı Tasarımcısı'nda özellikleri  
 Aşağıdaki tabloda en kullanışlı gösterilmektedir <xref:System.Activities.Statements.While> etkinlik özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı belirtir <xref:System.Activities.Statements.While> etkinlik Tasarımcısı'nda başlığı. Varsayılan değer sırada. Değer içinde düzenlenebilir **özellikleri** penceresi veya doğrudan başlığındaki etkinlik Tasarımcısı.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|  
|<xref:System.Activities.Statements.While.Body%2A>|False|Yürütülecek etkinliği içeren sırada <xref:System.Activities.Statements.While.Condition%2A> değerlendiren **doğru**.|  
|<xref:System.Activities.Statements.While.Condition%2A>|Doğru|İçeren [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] belirlemek için hesaplanan ifadenin olup olmadığını etkinliğin <xref:System.Activities.Statements.While.Body%2A> yürütülür.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetim akışı](../workflow-designer/control-flow-activity-designers.md)   
 [DoWhile](../workflow-designer/dowhile-activity-designer.md)