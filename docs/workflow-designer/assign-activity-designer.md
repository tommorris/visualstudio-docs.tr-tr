---
title: İş Akışı Tasarımcısı - Ata etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Assign.UI
ms.assetid: ba3feb3c-f144-47ea-926d-cf752b804153
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 44d825d5d6ee36876c807ce067c71c1b10896623
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31971439"
---
# <a name="assign-activity-designer"></a>Etkinlik Tasarımcısı atayın

**Atamak** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.Assign> etkinlik.

## <a name="the-assign-activity"></a>Ata etkinliği

<xref:System.Activities.Statements.Assign> Etkinlik bir değişken veya değişken değeri atar.

### <a name="using-the-assign-activity-designer"></a>Ata etkinlik Tasarımcısı'nı kullanarak

**Atamak** etkinlik Tasarımcısı bulunabilir **Temelleri** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç**sekmesini (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)

**Atamak** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve etkinlikleri yerleştirilir burada ever, gibi olarak içinde açın iş akışı Tasarımcısı yüzeyini bırakılan bir <xref:System.Activities.Statements.Sequence>. Bırakma **atamak** etkinlik Tasarımcısı oluşturur bir <xref:System.Activities.Statements.Assign> varsayılan etkinlik **DisplayName** Ata. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **atamak** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.

### <a name="the-assign-properties"></a>Ata özellikleri

Aşağıdaki tabloda <xref:System.Activities.Statements.Assign> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellik kılavuzunda düzenlenebilir ve bazı iş akışı Tasarımcısı yüzeyine düzenlenebilir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.Assign> etkinlik. Ata varsayılandır. Ancak <xref:System.Activities.Activity.DisplayName%2A> değeri kesinlikle gerekli değildir, kullanmak için en iyi bir uygulamadır.|
|<xref:System.Activities.Statements.Assign.To%2A>|Doğru|Değişken veya bağımsız değişken olarak <xref:System.Activities.Statements.Assign.Value%2A> atanır. Değerin geçerli bir Visual Basic tanımlayıcı olması gerekir. Özelliğini ayarlamak için bir Visual Basic ifadesini yazın **için** kutusuna **atamak** etkinlik Tasarımcısı veya özellik kılavuzunda.|
|<xref:System.Activities.Statements.Assign.Value%2A>|Doğru|Değişkenine atanan değeri. Ayarlamak için <xref:System.Activities.Statements.Assign.Value%2A>, bir Visual Basic ifadesi yazın **değeri** kutusuna **atamak** etkinlik Tasarımcısı veya özellik kılavuzunda.|

## <a name="see-also"></a>Ayrıca bkz.

- [Temel Türler](../workflow-designer/primitives-activity-designers.md)
- [gecikme](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)
- [WriteLine](../workflow-designer/writeline-activity-designer.md)