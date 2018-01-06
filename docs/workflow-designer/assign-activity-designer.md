---
title: "Etkinlik Tasarımcısı Ata | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.Assign.UI
ms.assetid: ba3feb3c-f144-47ea-926d-cf752b804153
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: bb816aee41f86e2cbdc71e93b78f1a9e09249a00
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="assign-activity-designer"></a>Etkinlik Tasarımcısı atayın
**Atamak** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.Assign> etkinlik.  
  
## <a name="the-assign-activity"></a>Ata etkinliği  
 <xref:System.Activities.Statements.Assign> Etkinlik bir değişken veya değişken değeri atar.  
  
### <a name="using-the-assign-activity-designer"></a>Ata etkinlik Tasarımcısı'nı kullanarak  
 **Atamak** etkinlik Tasarımcısı bulunabilir **Temelleri** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç**sekmesini (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)  
  
 **Atamak** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey burada herhangi bir zamanda etkinlikleri genellikle yerleştirilir, gibi olarak içinde bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.Assign> varsayılan etkinlik **DisplayName** Ata. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **atamak** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.  
  
### <a name="the-assign-properties"></a>Ata özellikleri  
 Aşağıdaki tabloda <xref:System.Activities.Statements.Assign> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellik kılavuzunda düzenlenebilir ve bunların bazıları üzerinde düzenlenebilir [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzeyini.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.Assign> etkinlik. Ata varsayılandır. Ancak <xref:System.Activities.Activity.DisplayName%2A> değeri kesinlikle gerekli değildir, kullanmak için en iyi bir uygulamadır.|  
|<xref:System.Activities.Statements.Assign.To%2A>|Doğru|Değişken veya bağımsız değişken olarak <xref:System.Activities.Statements.Assign.Value%2A> atanır. Bu geçerli bir Visual Basic tanımlayıcı olmalıdır. Özelliğini ayarlamak için bir Visual Basic ifadesini yazın **için** kutusuna **atamak** etkinlik Tasarımcısı veya özellik kılavuzunda.|  
|<xref:System.Activities.Statements.Assign.Value%2A>|Doğru|Değişkenine atanan değeri. Ayarlamak için <xref:System.Activities.Statements.Assign.Value%2A>, bir Visual Basic ifadesi yazın **değeri** kutusuna **atamak** etkinlik Tasarımcısı veya özellik kılavuzunda.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temelleri](../workflow-designer/primitives-activity-designers.md)   
 [Gecikme](../workflow-designer/delay-activity-designer.md)   
 [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)   
 [WriteLine](../workflow-designer/writeline-activity-designer.md)