---
title: "Etkinlik Tasarımcısı throw | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.Throw.UI
ms.assetid: 5e97c947-be39-4a1f-af04-000e2e09528a
caps.latest.revision: "4"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: a4dcc10419d5c1dbc0552aba62057cba2e82647f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Koleksiyonu](../workflow-designer/collection-activity-designers.md)   
 [Yeniden oluşturma](../workflow-designer/rethrow-activity-designer.md)   
 [Etkinlik Tasarımcısı throw](../workflow-designer/throw-activity-designer.md)   
 [TryCatch](../workflow-designer/trycatch-activity-designer.md)