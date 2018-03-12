---
title: "While etkinlik Tasarımcısı | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.While.UI
ms.assetid: ea008091-2e4c-4f64-bfa5-afb919552446
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 541113e598246cf20f9fe625f57c51f68d7e9ca8
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
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