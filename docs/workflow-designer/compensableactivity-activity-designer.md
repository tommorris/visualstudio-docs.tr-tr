---
title: İş Akışı Tasarımcısı - CompensableActivity etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.CompensableActivity.UI
ms.assetid: e0340d89-d39e-4a52-8557-13e27040d7b5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d723b50fe0267939119239861c5ae951e01cd445
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36758300"
---
# <a name="compensableactivity-activity-designer"></a>CompensableActivity Etkinlik Tasarımcısı

**CompensableActivity** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.CompensableActivity> etkinlik.

## <a name="the-compensableactivity-activity"></a>CompensableActivity etkinliği
 <xref:System.Activities.Statements.CompensableActivity> Onaylanabilir veya başarıyla tamamlandıktan sonra dengelendi iş birimi tanımlar.

### <a name="using-the-compensableactivity-activity-designer"></a>CompensableActivity etkinlik Tasarımcısı'nı kullanarak
 **CompensableActivity** etkinlik Tasarımcısı bulunabilir **işlem** kategorisini **araç**. Açmak için **araç**seçin **araç** iş akışı Tasarımcısı sol tarafındaki sekmesinde. Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya tuşuna **Ctrl**+**Alt** + **X**.

 **CompensableActivity** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve iş akışı Tasarımcısı yüzeyini açın. Etkinlik Tasarımcısı içinde bırakma bir <xref:System.Activities.Statements.Sequence>. Etkinlik Tasarımcısı bırakarak oluşturur bir <xref:System.Activities.Statements.CompensableActivity> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> CompensableActivity biri. Düzen <xref:System.Activities.Activity.DisplayName%2A> üstbilgisi değeri **CompensableActivity** etkinlik Tasarımcısı. İçinde de düzenlenebilir **DisplayName** ve özellik ızgarasının kutusu.

### <a name="the-compensableactivity-properties"></a>CompensableActivity özellikleri
 Aşağıdaki tabloda <xref:System.Activities.Statements.CompensableActivity> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. <xref:System.Activities.Activity.DisplayName%2A> Ve <xref:System.Activities.Activity%601.Result%2A> özellik özellik kılavuzunda düzenlenebilir ancak diğer özellikler iş akışı Tasarımcısı yüzey üzerinde düzenlenmesi gerekir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adını <xref:System.Activities.Statements.CompensableActivity> etkinlik. CompensableActivity varsayılandır.|
|<xref:System.Activities.Activity%601.Result%2A>|False|Dönüş değerini belirtir <xref:System.Activities.Statements.CompensableActivity>. Bu özellik özellik kılavuzunda düzenlenmesi gerekir.|
|<xref:System.Activities.Statements.CompensableActivity.Body%2A>|Doğru|Maaş, iptal etme ve Doğrulama mantığı sağlanan etkinlik belirtir. Eklemek için <xref:System.Activities.Statements.CompensableActivity.Body%2A> etkinlik, açılan bir etkinlikten **araç** içine **gövde** kutusuna **CompensableActivity** etkinlik Tasarımcısı. "Buraya Bırak etkinlik" İpucu metnini ekleyin.|
|<xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>|False|İptal olduğunda çalıştırılan etkinlik belirtir. Etkinlik eklemek için kendi Tasarımcısından bırakma **araç** içine **CancellationHandler** kutusuna **CompensableActivity** etkinlik Tasarımcısı. "Buraya etkinliğini Drop" İpucu metnini ekleyin.|
|<xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>|False|Dengelemesi zaman yürütülecek etkinlik belirtir <xref:System.Activities.Statements.CompensableActivity.Body%2A> etkinlik. Bu işleyici açıkça kullanılarak etkinleştirilebilir <xref:System.Activities.Statements.Compensate> etkinlik.<br /><br /> Etkinlik eklemek için etkinlik Tasarımcısı'ndan bırakma **araç** içine **CompensationHandler** kutusuna **CompensableActivity** etkinlik Tasarımcısı. "Buraya etkinliğini Drop" İpucu metnini ekleyin.|
|<xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>|False|Onaylarken yürütülecek etkinlik belirtir <xref:System.Activities.Statements.CompensableActivity.Body%2A> etkinlik. Bu işleyici açıkça kullanılarak etkinleştirilebilir <xref:System.Activities.Statements.Confirm> etkinlik.<br /><br /> Etkinlik eklemek için etkinlik Tasarımcısı'ndan bırakma **araç** içine **ConfirmationHandler** kutusuna **CompensableActivity** etkinlik Tasarımcısı. "Buraya etkinliğini Drop" İpucu metnini ekleyin.|

## <a name="see-also"></a>Ayrıca bkz.

- [İşlem](../workflow-designer/transaction-activity-designers.md)
- [CancellationScope](../workflow-designer/cancellationscope-activity-designer.md)
- [Dengelemek](../workflow-designer/compensate-activity-designer.md)
- [Onayla](../workflow-designer/confirm-activity-designer.md)
- [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)