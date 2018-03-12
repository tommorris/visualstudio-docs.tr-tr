---
title: "CancellationScope etkinlik Tasarımcısı | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.CancellationScope.UI
ms.assetid: 2c85d663-b219-4142-9866-7693ffd46379
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 406e46ccc3f8d0fd70b185a0e5f02151592e85d4
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
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

## <a name="see-also"></a>Ayrıca bkz.

- [İşlem](../workflow-designer/transaction-activity-designers.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [Dengelemek](../workflow-designer/compensate-activity-designer.md)
- [Onayla](../workflow-designer/confirm-activity-designer.md)
- [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)