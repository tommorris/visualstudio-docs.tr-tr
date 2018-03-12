---
title: "Etkinlik Tasarımcısı gecikme | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Delay.UI
ms.assetid: f51742a8-2c9a-47d1-8a23-18459d03ae19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: cddf4be42d05ebfc3c2df3e64f011b93673eead6
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="delay-activity-designer"></a>Gecikme etkinlik Tasarımcısı
**Gecikme** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.Delay> etkinlik.

## <a name="the-delay-activity"></a>Gecikme etkinliği
 <xref:System.Activities.Statements.Delay> Etkinlik gecikmeler bir iş akışı yürütme için belirtilen bir zaman miktarıdır.

### <a name="using-the-delay-activity-designer"></a>Gecikme etkinlik Tasarımcısı'nı kullanarak
 **Gecikme** etkinlik Tasarımcısı bulunabilir **Temelleri** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç**sekmesinde [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)

 **Gecikme** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir, gibi olarak içinde bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.Delay> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> gecikme. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **gecikme** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.

### <a name="the-delay-properties"></a>Gecikme özellikleri
 Aşağıdaki tabloda <xref:System.Activities.Statements.Delay> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellik kılavuzunda düzenlenebilir ve bunlarla ilgili bazı üzerinde düzenlenebilir [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]Tasarımcı yüzeyine.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.Delay> etkinlik. Gecikme varsayılandır. Ancak <xref:System.Activities.Activity.DisplayName%2A> değeri kesinlikle gerekli değildir, kullanmak için en iyi bir uygulamadır.|
|<xref:System.Activities.Statements.Delay.Duration%2A>|Doğru|İş akışı gecikme süre miktarı. Bu özellik özellik kılavuzunda ayarlanır. Ya da bir hazır değer türü <xref:System.TimeSpan> 00:00:00 biçimi veya süreyi belirtmek için bir Visual Basic ifade.|

## <a name="see-also"></a>Ayrıca bkz.

- [Temel Türler](../workflow-designer/primitives-activity-designers.md)
- [Ata](../workflow-designer/assign-activity-designer.md)
- [Delay Etkinlik Tasarımcısı](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)
- [WriteLine](../workflow-designer/writeline-activity-designer.md)