---
title: "Durum makinesi etkinlik Tasarımcısı | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- StateMachine Designer
- System.Activities.Statements.StateMachine.UI
ms.assetid: 474d5fb3-1049-4b3f-bc6b-7524dbbe1672
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 41215bea8c437d35d62448617eb5575b07bbca6a
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="statemachine-activity-designer"></a>Durum makinesi etkinlik Tasarımcısı
<xref:System.Activities.Statements.StateMachine> Etkinlik durumlar koleksiyonunu içerir ve tanıdık durumu makine kip kullanarak da iş akışları modeller.

## <a name="using-the-statemachine-activity-designer"></a>Durum makinesi etkinlik Tasarımcısı'nı kullanarak
 Eklemek için bir <xref:System.Activities.Statements.StateMachine> etkinlik, sürükle **Durum makinesi** etkinlik Tasarımcısı'ndan **Durum makinesi** bölümünü **araç** ve Windows iş akışını açın bırakma Tasarımcı yüzeyine. Bunun için bir alt durum eklemek için <xref:System.Activities.Statements.StateMachine> etkinlik, sürükle bir <xref:System.Activities.Statements.State> veya <xref:System.Activities.Core.Presentation.FinalState> gelen **araç** ve üzerine bırakın **Durum makinesi**.

### <a name="statemachine-activity-properties-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda Durum makinesi etkinlik özellikleri
 Aşağıdaki tabloda <xref:System.Activities.Statements.StateMachine> Tasarımcısı'nda nasıl kullanıldığını açıklar ve iş akışı Tasarımcısı'nı kullanarak ayarlanabilir özellikleri. Bu özellikler ve özellik ızgarasının düzenlenebilir ve bazı Tasarımcı yüzeyine düzenlenebilir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı belirtir <xref:System.Activities.Statements.StateMachine> etkinlik Tasarımcısı'nda başlığı. Varsayılan değer **Durum makinesi**. Değeri, özellik kılavuzu veya etkinlik Tasarımcısı başlığındaki doğrudan düzenlenebilir. <xref:System.Activities.Activity.DisplayName%2A> İş akışı Tasarımcısı'nı üstünde görüntülenen içerik haritası Gezinti kullanılır.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|

## <a name="see-also"></a>Ayrıca bkz.

- [Akış Çizelgesi](../workflow-designer/flowchart-activity-designer.md)
- [Denetim Akışı](../workflow-designer/control-flow-activity-designers.md)