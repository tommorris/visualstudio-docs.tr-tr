---
title: "TerminateWorkflow etkinlik Tasarımcısı | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.TerminateWorkflow.UI
ms.assetid: 08e632ed-0724-4fb4-9df1-f8d443eaf0ac
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 683c482436e968ff9d2a1bd4ce0bbb8e173a5520
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="terminateworkflow-activity-designer"></a>TerminateWorkflow etkinlik Tasarımcısı
**TerminateWorkflow** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.TerminateWorkflow> etkinlik.

## <a name="the-terminateworkflow-activity"></a>TerminateWorkflow etkinliği
 <xref:System.Activities.Statements.TerminateWorkflow> Etkinlik bir iş akışının yürütülmesini sonlanır.

### <a name="using-the-terminateworkflow-activity-designer"></a>TerminateWorkflow etkinlik Tasarımcısı'nı kullanarak
 **TerminateWorkflow** etkinlik Tasarımcısı bulunabilir **çalışma zamanı** kategorisini **araç**, hangi tıklayarak erişildiğinde **araçkutusu** sekmesinde (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)

 **TerminateWorkflow** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir, gibi olarak içinde bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.TerminateWorkflow> varsayılan etkinlik **DisplayName** TerminateWorkflow biri. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **TerminateWorkflow** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.

### <a name="the-terminateworkflow-properties"></a>TerminateWorkflow özellikleri
 Aşağıdaki tabloda <xref:System.Activities.Statements.TerminateWorkflow> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellik kılavuzunda düzenlenebilir ve bunların bazıları üzerinde düzenlenebilir [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzeyini.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.TerminateWorkflow> etkinlik. TerminateWorkflow varsayılandır. Görünen ad kesinlikle gerekli olmamakla birlikte, bir görünen ad kullanmak için en iyi bir uygulamadır.|
|<xref:System.Activities.Statements.TerminateWorkflow.Exception%2A>|False|İş akışı sonlandırıldığında atmak için özel durum. Bu özellik özellik kılavuzunda ayarlayın.|
|<xref:System.Activities.Statements.TerminateWorkflow.Reason%2A>|False|İş akışı neden sonlandırıldı açıklar açıklaması. Bu özellik özellik kılavuzunda ayarlayın.|

## <a name="see-also"></a>Ayrıca bkz.

- [Çalışma Zamanı](../workflow-designer/runtime-activity-designers.md)
- [Sürdür](../workflow-designer/persist-activity-designer.md)