---
title: İş Akışı Tasarımcısı - gecikme etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Delay.UI
ms.assetid: f51742a8-2c9a-47d1-8a23-18459d03ae19
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 31b632177ba941ad0e5ddb5700ae430573fd817d
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36758459"
---
# <a name="delay-activity-designer"></a>Delay Etkinlik Tasarımcısı

**Gecikme** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.Delay> etkinlik.

## <a name="the-delay-activity"></a>Gecikme etkinliği

<xref:System.Activities.Statements.Delay> Etkinlik gecikmeler bir iş akışı yürütme için belirtilen bir zaman miktarıdır.

### <a name="use-the-delay-activity-designer"></a>Gecikme etkinlik Tasarımcısı'nı kullanın

**Gecikme** etkinlik Tasarımcısı bulunabilir **Temelleri** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç**sekmesi iş akışı Tasarımcısı'nın. Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya tuşuna **Ctrl**+**Alt** + **X**.

**Gecikme** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve etkinlikleri genellikle yerleştirilir olduğunda, örneğin olarak içinde açın iş akışı Tasarımcısı yüzeyini bırakılan bir <xref:System.Activities.Statements.Sequence>. Etkinlik Tasarımcısı bırakarak oluşturur bir <xref:System.Activities.Statements.Delay> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> gecikme. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **gecikme** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.

### <a name="the-delay-properties"></a>Gecikme özellikleri

Aşağıdaki tabloda <xref:System.Activities.Statements.Delay> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikler ve özellik ızgarasının düzenlenebilir ve bazı iş akışı Tasarımcısı yüzeyine düzenlenebilir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.Delay> etkinlik. Gecikme varsayılandır. Ancak <xref:System.Activities.Activity.DisplayName%2A> değeri kesinlikle gerekli değilse, bunu kullanmak en iyi uygulamadır.|
|<xref:System.Activities.Statements.Delay.Duration%2A>|Doğru|İş akışı gecikme süre miktarı. Bu özellik özellik kılavuzunda ayarlanır. Ya da bir hazır değer türü <xref:System.TimeSpan> 00:00:00 biçimi veya süreyi belirtmek için bir Visual Basic ifade.|

## <a name="see-also"></a>Ayrıca bkz.

- [Temel Türler](../workflow-designer/primitives-activity-designers.md)
- [Ata](../workflow-designer/assign-activity-designer.md)
- [Delay Etkinlik Tasarımcısı](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)
- [WriteLine](../workflow-designer/writeline-activity-designer.md)