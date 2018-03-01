---
title: "CompensableActivity etkinlik Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.Activities.Statements.CompensableActivity.UI
ms.assetid: e0340d89-d39e-4a52-8557-13e27040d7b5
caps.latest.revision: 
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload:
- multiple
ms.openlocfilehash: 670fc24ee800794bd9b013d5e5aaab6dbb98bcd9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="compensableactivity-activity-designer"></a>CompensableActivity etkinlik Tasarımcısı
**CompensableActivity** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.CompensableActivity> etkinlik.  
  
## <a name="the-compensableactivity-activity"></a>CompensableActivity etkinliği  
 <xref:System.Activities.Statements.CompensableActivity> Onaylanabilir veya başarıyla tamamlandıktan sonra dengelendi iş birimi tanımlar.  
  
### <a name="using-the-compensableactivity-activity-designer"></a>CompensableActivity etkinlik Tasarımcısı'nı kullanarak  
 **CompensableActivity** etkinlik Tasarımcısı bulunabilir **işlem** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç kutusu**  sol tarafındaki sekmesinde [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)  
  
 **CompensableActivity** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir, gibi olarak içinde bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.CompensableActivity> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> CompensableActivity biri. <xref:System.Activities.Activity.DisplayName%2A> Değeri üstbilgisinde düzenlenebilir **CompensableActivity** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.  
  
### <a name="the-compensableactivity-properties"></a>CompensableActivity özellikleri  
 Aşağıdaki tabloda <xref:System.Activities.Statements.CompensableActivity> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. <xref:System.Activities.Activity.DisplayName%2A> Ve <xref:System.Activities.Activity%601.Result%2A> özelliği özellik kılavuzunda düzenlenebilir ancak diğer özellikler üzerinde düzenlenmesi gerekir [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzeyini.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adını <xref:System.Activities.Statements.CompensableActivity> etkinlik. CompensableActivity varsayılandır.|  
|<xref:System.Activities.Activity%601.Result%2A>|False|Dönüş değerini belirtir <xref:System.Activities.Statements.CompensableActivity>. Bu özellik özellik kılavuzunda düzenlenmesi gerekir.|  
|<xref:System.Activities.Statements.CompensableActivity.Body%2A>|Doğru|Maaş, iptal etme ve Doğrulama mantığı sağlanan etkinlik belirtir. Eklemek için <xref:System.Activities.Statements.CompensableActivity.Body%2A> etkinlik, açılan bir etkinlikten **araç** içine **gövde** kutusuna **CompensableActivity** ipucu metnini "açılan ile etkinlik Tasarımcısı Burada etkinliği".|  
|<xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>|False|İptal durumunda yürütüldüğünde etkinliğin belirtir. Etkinlik eklemek için kendi Tasarımcısından bırakma **araç** içine **CancellationHandler** kutusuna **CompensableActivity** ipucu metnini "açılan ile etkinlik Tasarımcısı Burada etkinliği".|  
|<xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>|False|Dengelemesi zaman yürütülecek etkinlik belirtir <xref:System.Activities.Statements.CompensableActivity.Body%2A> etkinlik. Bu işleyici açıkça kullanılarak etkinleştirilebilir <xref:System.Activities.Statements.Compensate> etkinlik.<br /><br /> Etkinlik eklemek için etkinlik Tasarımcısı'ndan bırakma **araç** içine **CompensationHandler** kutusuna **CompensableActivity** ipucu metnini ile etkinlik Tasarımcısı " Etkinlik Buraya Bırak".|  
|<xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>|False|Onaylarken yürütülecek etkinlik belirtir <xref:System.Activities.Statements.CompensableActivity.Body%2A> etkinlik. Bu işleyici açıkça kullanılarak etkinleştirilebilir <xref:System.Activities.Statements.Confirm> etkinlik.<br /><br /> Etkinlik eklemek için etkinlik Tasarımcısı'ndan bırakma **araç** içine **ConfirmationHandler** kutusuna **CompensableActivity** ipucu metnini ile etkinlik Tasarımcısı " Etkinlik Buraya Bırak".|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlem](../workflow-designer/transaction-activity-designers.md)   
 [CancellationScope](../workflow-designer/cancellationscope-activity-designer.md)   
 [Dengelemek](../workflow-designer/compensate-activity-designer.md)   
 [Onayla](../workflow-designer/confirm-activity-designer.md)   
 [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)