---
title: İş Akışı Tasarımcısı - yeniden oluşturulması etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Rethrow.UI
ms.assetid: 9cfa2eda-395f-4cf3-9154-83fadd4f7452
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1d441724afa1cf481bc15e2a43e6ec744a951187
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31973842"
---
# <a name="rethrow-activity-designer"></a>Etkinlik Tasarımcısı yeniden oluşturma

**Yeniden oluşturulması** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.Rethrow> etkinlik.

## <a name="the-rethrow-activity"></a>Yeniden oluşturma etkinliği
 <xref:System.Activities.Statements.Rethrow> Etkinlik önceden oluşturulan bir özel durum oluşturur. Bu etkinlik yalnızca, kullanılabilir bir <xref:System.Activities.Statements.Catch> işleyicisinde <xref:System.Activities.Statements.TryCatch> etkinlik.

### <a name="using-the-rethrow-activity-designer"></a>Etkinlik yeniden oluşturulması Tasarımcısı'nı kullanarak
 **Yeniden oluşturulması** etkinlik Tasarımcısı bulunabilir **işleme hatası** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç**sekmesi iş akışı Tasarımcısı'nın sol tarafındaki (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)

 **Yeniden oluşturulması** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve etkinlikleri genellikle yerleştirilir olduğunda, örneğin olarak içinde açın iş akışı Tasarımcısı yüzeyini bırakılan bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.Rethrow> varsayılan etkinlik **DisplayName** Throw biri. <xref:System.Activities.Activity.DisplayName%2A> Değeri üstbilgisinde düzenlenebilir **yeniden oluşturulması** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.

### <a name="the-rethrow-properties"></a>Yeniden oluşturma özellikleri
 Aşağıdaki tabloda <xref:System.Activities.Statements.Rethrow> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adı belirtir <xref:System.Activities.Statements.Rethrow> etkinlik. Yeniden oluşturma varsayılandır.|

## <a name="see-also"></a>Ayrıca bkz.

- [Koleksiyon](../workflow-designer/collection-activity-designers.md)
- [Throw](../workflow-designer/throw-activity-designer.md)
- [TryCatch](../workflow-designer/trycatch-activity-designer.md)