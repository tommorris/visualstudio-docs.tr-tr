---
title: "Etkinlik Tasarımcısı yeniden oluşturulması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Rethrow.UI
ms.assetid: 9cfa2eda-395f-4cf3-9154-83fadd4f7452
caps.latest.revision: 
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload:
- multiple
ms.openlocfilehash: 93315ed4028ba4ded598fd07373df43150b70aa3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="rethrow-activity-designer"></a>Etkinlik Tasarımcısı yeniden oluşturma
**Yeniden oluşturulması** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.Rethrow> etkinlik.  
  
## <a name="the-rethrow-activity"></a>Yeniden oluşturma etkinliği  
 <xref:System.Activities.Statements.Rethrow> Etkinlik önceden oluşturulan bir özel durum oluşturur. Bu etkinlik yalnızca, kullanılabilir bir <xref:System.Activities.Statements.Catch> işleyicisinde <xref:System.Activities.Statements.TryCatch> etkinlik.  
  
### <a name="using-the-rethrow-activity-designer"></a>Etkinlik yeniden oluşturulması Tasarımcısı'nı kullanarak  
 **Yeniden oluşturulması** etkinlik Tasarımcısı bulunabilir **işleme hatası** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç**sol tarafındaki sekmesinde [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)  
  
 **Yeniden oluşturulması** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir, gibi olarak içinde bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.Rethrow> varsayılan etkinlik **DisplayName** Throw biri. <xref:System.Activities.Activity.DisplayName%2A> Değeri üstbilgisinde düzenlenebilir **yeniden oluşturulması** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.  
  
### <a name="the-rethrow-properties"></a>Yeniden oluşturma özellikleri  
 Aşağıdaki tabloda <xref:System.Activities.Statements.Rethrow> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adı belirtir <xref:System.Activities.Statements.Rethrow> etkinlik. Yeniden oluşturma varsayılandır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Koleksiyonu](../workflow-designer/collection-activity-designers.md)   
 [Throw](../workflow-designer/throw-activity-designer.md)   
 [TryCatch](../workflow-designer/trycatch-activity-designer.md)