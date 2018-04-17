---
title: While etkinlik Tasarımcısı | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.While.UI
ms.assetid: ea008091-2e4c-4f64-bfa5-afb919552446
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2c5b75a2575a7e8d6eeed4f42a269849bc2df899
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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

## <a name="see-also"></a>Ayrıca bkz.

- [Denetim Akışı](../workflow-designer/control-flow-activity-designers.md)
- [DoWhile](../workflow-designer/dowhile-activity-designer.md)