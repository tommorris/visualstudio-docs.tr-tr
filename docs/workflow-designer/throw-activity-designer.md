---
title: "Etkinlik Tasarımcısı throw | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Throw.UI
ms.assetid: 5e97c947-be39-4a1f-af04-000e2e09528a
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e0b41fb8fcbbb80f2f99558f07c5e5a4f9e4a85b
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="throw-activity-designer"></a>Etkinlik Tasarımcısı throw
**Throw** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.Throw> etkinlik.

## <a name="the-throw-activity"></a>Throw etkinliği
 <xref:System.Activities.Statements.Throw> Etkinlik bir özel durum oluşturur.

### <a name="using-the-throw-activity-designer"></a>Throw etkinlik Tasarımcısı'nı kullanarak
 **Throw** etkinlik Tasarımcısı bulunabilir **işleme hatası** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç**sol tarafındaki sekmesinde [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)

 **Throw** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir, gibi olarak içinde bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.Throw> varsayılan etkinlik **DisplayName** Throw biri. <xref:System.Activities.Activity.DisplayName%2A> Değeri üstbilgisinde düzenlenebilir **Throw** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu. <xref:System.Activities.Statements.Throw.Exception%2A> Özelliği ve özellik ızgarasının düzenlenmesi gerekir.

### <a name="the-throw-properties"></a>Throw özellikleri
 Aşağıdaki tabloda <xref:System.Activities.Statements.Throw> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adı belirtir <xref:System.Activities.Statements.Throw> etkinlik. Throw varsayılandır.|
|<xref:System.Activities.Statements.Throw.Exception%2A>|Doğru|Throw için özel durum. Bu özel durumun öğesinden türetilmelidir <xref:System.Exception>. Özel durum belirtmek için özellik kılavuzunda bir Visual Basic ifadesi yazın.|

## <a name="see-also"></a>Ayrıca bkz.

- [Koleksiyon](../workflow-designer/collection-activity-designers.md)
- [yeniden oluşturma](../workflow-designer/rethrow-activity-designer.md)
- [Throw Etkinlik Tasarımcısı](../workflow-designer/throw-activity-designer.md)
- [TryCatch](../workflow-designer/trycatch-activity-designer.md)