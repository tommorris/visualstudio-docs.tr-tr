---
title: "CancellationScope etkinlik Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.CancellationScope.UI
ms.assetid: 2c85d663-b219-4142-9866-7693ffd46379
caps.latest.revision: "8"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4b2ad28e6b89273b5fdb55e4cfa35d1df292221a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="cancellationscope-activity-designer"></a>CancellationScope etkinlik Tasarımcısı
**CancellationScope** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.CancellationScope> etkinlik.  
  
## <a name="the-cancellationscope-activity"></a>CancellationScope etkinliği  
 <xref:System.Activities.Statements.CancellationScope> Etkinlik yürütme ve iptal mantığı için bu etkinliği için etkinlik belirtmenize olanak verir.  
  
### <a name="using-the-cancellationscope-activity-designer"></a>CancellationScope etkinlik Tasarımcısı'nı kullanarak  
 **CancellationScope** etkinlik Tasarımcısı bulunabilir **işlem** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç kutusu**  sekmesinde [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)  
  
 **CancellationScope** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir, gibi olarak içinde bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.CancellationScope> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> CancellationScope biri. <xref:System.Activities.Activity.DisplayName%2A> Değeri üstbilgisinde düzenlenebilir **CancellationScope** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.  
  
### <a name="the-cancellationscope-properties"></a>CancellationScope özellikleri  
 Aşağıdaki tabloda <xref:System.Activities.Statements.CancellationScope> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. <xref:System.Activities.Activity.DisplayName%2A> Özelliği özellik kılavuzunda düzenlenebilir ancak diğer özellikler üzerinde düzenlenmesi gerekir [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzeyini.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adını <xref:System.Activities.Statements.CancellationScope> etkinlik. CancellationScope varsayılandır. Ancak <xref:System.Activities.Activity.DisplayName%2A> değeri kesinlikle gerekli değildir, kullanmak için en iyi bir uygulamadır.|  
|<xref:System.Activities.Statements.CancellationScope.Body%2A>|Doğru|Hangi iptalleri mantığı sağlanan etkinlik belirtir. Eklemek için <xref:System.Activities.Statements.CancellationScope.Body%2A> etkinlik, açılan bir etkinlikten **araç** içine **gövde** kutusuna **CancellationScope** ipucu metnini "açılan ile etkinlik Tasarımcısı Burada etkinliği".|  
|<xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>|Doğru|İptal durumunda yürütüldüğünde etkinliğin belirtir. Eklemek için <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> etkinlik, açılan bir etkinlikten **araç** içine **CancellationHandler** kutusuna **CancellationScope** İpucu ile etkinlik Tasarımcısı "Buraya etkinliğini Drop" metin.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlem](../workflow-designer/transaction-activity-designers.md)   
 [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)   
 [Dengelemek](../workflow-designer/compensate-activity-designer.md)   
 [Onayla](../workflow-designer/confirm-activity-designer.md)   
 [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)