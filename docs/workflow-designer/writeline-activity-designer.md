---
title: "WriteLine etkinlik Tasarımcısı | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.WriteLine.UI
ms.assetid: 1b5f29a8-b7fd-477e-949e-2f689cae3c96
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 8596aa9f00e75ec31a29042473d728310027bc36
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="writeline-activity-designer"></a>WriteLine etkinlik Tasarımcısı
**WriteLine** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.WriteLine> etkinlik.

## <a name="the-writeline-activity"></a>WriteLine etkinliği
 <xref:System.Activities.Statements.WriteLine> Etkinlik metni belirtilen bir yazar <xref:System.IO.TextWriter> nesnesi. Öyle değilse <xref:System.IO.TextWriter> belirtilirse, <xref:System.Activities.Statements.WriteLine> metni konsola yazar.

### <a name="using-the-writeline-activity-designer"></a>WriteLine etkinlik Tasarımcısı'nı kullanarak
 **WriteLine** etkinlik Tasarımcısı bulunabilir **Temelleri** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç**sekmesinde [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)

 **WriteLine** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir, gibi olarak içinde bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.WriteLine> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> WriteLine biri. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **WriteLine** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.

### <a name="the-writeline-properties"></a>WriteLine özellikleri
 Aşağıdaki tabloda <xref:System.Activities.Statements.WriteLine> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellik kılavuzunda düzenlenebilir ve bunların bazıları üzerinde düzenlenebilir [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]Tasarımcı yüzeyine.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.WriteLine> etkinlik. WriteLine varsayılandır. Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil bir kullanmak için en iyi bir uygulamadır.|
|<xref:System.Activities.Statements.WriteLine.Text%2A>|False|Yazma metin. Özelliğini ayarlamak için bir Visual Basic ifadesini yazın **metin** kutusuna **WriteLine** etkinlik Tasarımcısı veya özellik kılavuzunda.|
|<xref:System.Activities.Statements.WriteLine.TextWriter%2A>|False|<xref:System.IO.TextWriter> Hangi <xref:System.Activities.Statements.WriteLine> Yazar <xref:System.Activities.Statements.WriteLine.Text%2A>. Konsol varsayılandır.|

## <a name="see-also"></a>Ayrıca bkz.

- [Temel Türler](../workflow-designer/primitives-activity-designers.md)
- [Ata](../workflow-designer/assign-activity-designer.md)
- [gecikme](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)