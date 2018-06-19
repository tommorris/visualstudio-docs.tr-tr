---
title: İş Akışı Tasarımcısı - TerminateWorkflow etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.TerminateWorkflow.UI
ms.assetid: 08e632ed-0724-4fb4-9df1-f8d443eaf0ac
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5dfd7438a14f0bcbedcf5cdc5add78020604c355
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31975565"
---
# <a name="terminateworkflow-activity-designer"></a>TerminateWorkflow etkinlik Tasarımcısı

**TerminateWorkflow** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.TerminateWorkflow> etkinlik.

## <a name="the-terminateworkflow-activity"></a>TerminateWorkflow etkinliği

<xref:System.Activities.Statements.TerminateWorkflow> Etkinlik bir iş akışının yürütülmesini sonlanır.

### <a name="using-the-terminateworkflow-activity-designer"></a>TerminateWorkflow etkinlik Tasarımcısı'nı kullanarak

**TerminateWorkflow** etkinlik Tasarımcısı bulunabilir **çalışma zamanı** kategorisini **araç**, hangi tıklayarak erişildiğinde **araçkutusu** sekmesinde (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)

**TerminateWorkflow** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve etkinlikleri genellikle yerleştirilir olduğunda, örneğin olarak içinde açın iş akışı Tasarımcısı yüzeyini bırakılan bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.TerminateWorkflow> varsayılan etkinlik **DisplayName** TerminateWorkflow biri. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **TerminateWorkflow** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.

### <a name="the-terminateworkflow-properties"></a>TerminateWorkflow özellikleri

Aşağıdaki tabloda <xref:System.Activities.Statements.TerminateWorkflow> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellik kılavuzunda düzenlenebilir ve bazı iş akışı Tasarımcısı yüzeyine düzenlenebilir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.TerminateWorkflow> etkinlik. TerminateWorkflow varsayılandır. Görünen ad kesinlikle gerekli olmamakla birlikte, bir görünen ad kullanmak için en iyi bir uygulamadır.|
|<xref:System.Activities.Statements.TerminateWorkflow.Exception%2A>|False|İş akışı sonlandırıldığında atmak için özel durum. Bu özellik özellik kılavuzunda ayarlayın.|
|<xref:System.Activities.Statements.TerminateWorkflow.Reason%2A>|False|İş akışı neden sonlandırıldı açıklar açıklaması. Bu özellik özellik kılavuzunda ayarlayın.|

## <a name="see-also"></a>Ayrıca bkz.

- [Çalışma Zamanı](../workflow-designer/runtime-activity-designers.md)
- [Sürdür](../workflow-designer/persist-activity-designer.md)