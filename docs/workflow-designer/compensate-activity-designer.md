---
title: "Etkinlik Tasarımcısı dengelemek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.Compensate.UI
ms.assetid: 7347c947-bfff-4bad-becd-5cd23e7b24cd
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 7d6317299bef78b4f5ee882bcf8d1353b81b5100
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="compensate-activity-designer"></a>Etkinlik Tasarımcısı dengelemek
**Compensate** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.Compensate> etkinlik.  
  
## <a name="the-compensate-activity"></a>Etkinlik dengelemek  
 <xref:System.Activities.Statements.Compensate> Etkinlik açıkça çağırır <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> bulunan bir etkinlik için bir <xref:System.Activities.Statements.CompensableActivity>. Varsa <xref:System.Activities.Statements.Compensate> içinde etkinlik kullanılmaz <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>, <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>, veya <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> , bir <xref:System.Activities.Statements.CompensableActivity>, sonra da belirtmeniz gerekir <xref:System.Activities.Statements.Compensate.Target%2A> özelliği.  
  
 <xref:System.Activities.Statements.CompensationToken> Tarafından belirtilen <xref:System.Activities.Statements.Compensate.Target%2A> açıkça onaylamak veya dengelemek için bir yol sağlayan bir <xref:System.Activities.Statements.CompensableActivity> sonra <xref:System.Activities.Statements.CompensableActivity.Body%2A> , <xref:System.Activities.Statements.CompensableActivity> başarıyla tamamlandı.  
  
### <a name="using-the-compensate-activity-designer"></a>Kullanarak etkinlik Tasarımcısı dengelemek  
 **Compensate** etkinlik Tasarımcısı bulunabilir **işlem** kategorisini **araç**, hangi tıklayarak erişildiğinde **araçkutusu** sol tarafındaki sekmesinde [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)  
  
 **Compensate** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir, gibi olarak içinde bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.Compensate> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> Compensate biri. <xref:System.Activities.Activity.DisplayName%2A> Değeri üstbilgisinde düzenlenebilir **Compensate** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.  
  
### <a name="the-compensate-properties"></a>Özellikler dengelemek  
 Aşağıdaki tabloda <xref:System.Activities.Statements.CancellationScope> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. <xref:System.Activities.Activity.DisplayName%2A> Özelliği, özellik kılavuzu veya üzerinde düzenlenebilir [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzeyini, ancak <xref:System.Activities.Statements.Compensate.Target%2A> özellik kılavuzunda özelliği düzenlenemiyor.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adı belirtir <xref:System.Activities.Statements.Compensate> etkinlik. Compensate varsayılandır.|  
|<xref:System.Activities.Statements.Compensate.Target%2A>|Doğru|Belirtir <xref:System.Activities.InArgument%601> içeren <xref:System.Activities.Statements.CompensationToken> bu <xref:System.Activities.Statements.Compensate> etkinlik.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlem](../workflow-designer/transaction-activity-designers.md)   
 [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)   
 [Etkinlik Tasarımcısı dengelemek](../workflow-designer/compensate-activity-designer.md)   
 [Onayla](../workflow-designer/confirm-activity-designer.md)   
 [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)