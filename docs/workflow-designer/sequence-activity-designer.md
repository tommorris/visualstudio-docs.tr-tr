---
title: "Sıralı etkinlik Tasarımcısı | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Sequence.UI
ms.assetid: 51c8d3cb-4d43-458f-9631-b63755f9ac94
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 64ec037433ca4ff984628994ba2bf353ad8e365c
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="sequence-activity-designer"></a>Sıralı etkinlik Tasarımcısı
<xref:System.Activities.Statements.Sequence> Etkinlik sırayla yürütür alt etkinliklerin sıralı bir koleksiyonu içerir.

 Etkinlikler kümesini sırayla yürütmek için başka bir yolu bir <xref:System.Activities.Statements.Flowchart> etkinlik. Kullanmayı [akış çizelgesi](../workflow-designer/flowchart-activity-designer.md) basit dallanma veya diagrammatically modellemek için istediğiniz program akışı döngü olduğunda.

## <a name="using-the-sequence-activity-designer"></a>Sıralı etkinlik Tasarımcısı'nı kullanarak
 Eklemek için bir <xref:System.Activities.Statements.Sequence> etkinlik, sürükle **dizisi** etkinlik Tasarımcısı'ndan **araç** ve Windows iş akışı Tasarımcısı yüzeyini açın bırakın. Bunun için bir alt etkinlik eklemek için <xref:System.Activities.Statements.Sequence> etkinlik, diğer bazı etkinliğinden sürükleyin **araç** ve üçgen İpucu metin kutusundaki "Buraya etkinliğini Drop" bırakın.

### <a name="sequence-activity-properties-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda sıralı etkinlik özellikleri
 Aşağıdaki tabloda <xref:System.Activities.Statements.Sequence> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikler, özellik kılavuzu veya tasarımcı yüzeyine düzenlenebilir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı belirtir <xref:System.Activities.Statements.Sequence> etkinlik Tasarımcısı'nda başlığı. Varsayılan değer sırasıdır. Değeri, özellik kılavuzu veya etkinlik Tasarımcısı başlığındaki doğrudan düzenlenebilir.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|

## <a name="see-also"></a>Ayrıca bkz.

- [Akış Çizelgesi](../workflow-designer/flowchart-activity-designer.md)
- [Denetim Akışı](../workflow-designer/control-flow-activity-designers.md)