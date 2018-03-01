---
title: "WriteLine etkinlik Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.Activities.Statements.WriteLine.UI
ms.assetid: 1b5f29a8-b7fd-477e-949e-2f689cae3c96
caps.latest.revision: 
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload:
- multiple
ms.openlocfilehash: 3f531539737389938a7ff0a757235d8c5c2af263
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temelleri](../workflow-designer/primitives-activity-designers.md)   
 [Ata](../workflow-designer/assign-activity-designer.md)   
 [Gecikme](../workflow-designer/delay-activity-designer.md)   
 [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)