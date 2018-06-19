---
title: Etkinlik Tasarımcısı çalışırken iş akışı Tasarımcısı-
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.While.UI
ms.assetid: ea008091-2e4c-4f64-bfa5-afb919552446
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 02f0e83f674378ca7f9297aedbeb580b4f2cad89
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31973408"
---
# <a name="while-activity-designer"></a>While etkinlik Tasarımcısı

<xref:System.Activities.Statements.While> Etkinlik yürütür içinde yer alan etkinlik kendi <xref:System.Activities.Statements.While.Body%2A> while belirtilen <xref:System.Activities.Statements.While.Condition%2A> değerlendiren **doğru**. Kapsanan etkinlik hiçbir zaman yürütür. En az bir kez çalıştırılacak kapsanan etkinlik istiyorsanız kullanın <xref:System.Activities.Statements.DoWhile> etkinlik yerine.

## <a name="while-properties-in-workflow-designer"></a>While iş akışı Tasarımcısı'nda özellikleri

Aşağıdaki tabloda en kullanışlı gösterilmektedir <xref:System.Activities.Statements.While> etkinlik özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı belirtir <xref:System.Activities.Statements.While> etkinlik Tasarımcısı'nda başlığı. Varsayılan değer sırada. Değer içinde düzenlenebilir **özellikleri** penceresi veya doğrudan başlığındaki etkinlik Tasarımcısı.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|
|<xref:System.Activities.Statements.While.Body%2A>|False|Yürütülecek etkinliği içeren sırada <xref:System.Activities.Statements.While.Condition%2A> değerlendiren **doğru**.|
|<xref:System.Activities.Statements.While.Condition%2A>|Doğru|Belirlemek için değerlendirilen Visual Basic ifade içeriyor olup olmadığını etkinliğin <xref:System.Activities.Statements.While.Body%2A> yürütülür.|

## <a name="see-also"></a>Ayrıca bkz.

- [Denetim Akışı](../workflow-designer/control-flow-activity-designers.md)
- [DoWhile](../workflow-designer/dowhile-activity-designer.md)