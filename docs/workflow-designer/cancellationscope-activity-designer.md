---
title: İş Akışı Tasarımcısı - CancellationScope etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.CancellationScope.UI
ms.assetid: 2c85d663-b219-4142-9866-7693ffd46379
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1032df2f7ebcf4cbc1eae0d4b18757a3f90c4f68
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36758071"
---
# <a name="cancellationscope-activity-designer"></a>CancellationScope Etkinlik Tasarımcısı

**CancellationScope** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.CancellationScope> etkinlik.

## <a name="the-cancellationscope-activity"></a>CancellationScope etkinliği

<xref:System.Activities.Statements.CancellationScope> Etkinlik yürütme ve iptal mantığı için bu etkinliği için etkinlik belirtmenize olanak verir.

### <a name="using-the-cancellationscope-activity-designer"></a>CancellationScope etkinlik Tasarımcısı'nı kullanarak

**CancellationScope** etkinlik Tasarımcısı bulunabilir **işlem** kategorisini **araç**. Açmak için **araç**seçin **araç** sekmesi iş akışı Tasarımcısı'nın. Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya tuşuna **Ctrl**+**Alt** + **X**.

**CancellationScope** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve etkinlikleri yerleştirilir olduğunda, örneğin olarak içinde açın iş akışı Tasarımcısı yüzeyini bırakılan bir <xref:System.Activities.Statements.Sequence>. Bırakma **CancellationScope** etkinlik Tasarımcısı oluşturur bir <xref:System.Activities.Statements.CancellationScope> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> CancellationScope biri. Düzen <xref:System.Activities.Activity.DisplayName%2A> üstbilgisi değeri **CancellationScope** etkinlik Tasarımcısı. İçinde de düzenleyebilirsiniz **DisplayName** ve özellik ızgarasının kutusu.

### <a name="the-cancellationscope-properties"></a>CancellationScope özellikleri

Aşağıdaki tabloda <xref:System.Activities.Statements.CancellationScope> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. <xref:System.Activities.Activity.DisplayName%2A> Özelliği özellik kılavuzunda düzenlenebilir ancak diğer özellikler iş akışı Tasarımcısı yüzeyine düzenlenmesi gerekir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adını <xref:System.Activities.Statements.CancellationScope> etkinlik. CancellationScope varsayılandır. Ancak <xref:System.Activities.Activity.DisplayName%2A> değeri kesinlikle gerekli değildir, kullanmak için en iyi bir uygulamadır.|
|<xref:System.Activities.Statements.CancellationScope.Body%2A>|Doğru|Hangi iptalleri mantığı sağlanan etkinlik belirtir. Eklemek için <xref:System.Activities.Statements.CancellationScope.Body%2A> etkinlik, açılan bir etkinlikten **araç** içine **gövde** kutusuna **CancellationScope** etkinlik Tasarımcısı. "Buraya etkinliğini Drop" İpucu metnini ekleyin.|
|<xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>|Doğru|İptal ise çalıştırılan etkinlik belirtir. Eklemek için <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> etkinlik, açılan bir etkinlikten **araç** içine **CancellationHandler** kutusuna **CancellationScope** etkinlik Tasarımcısı. "Buraya etkinliğini Drop" İpucu metnini ekleyin.|

## <a name="see-also"></a>Ayrıca bkz.

- [İşlem](../workflow-designer/transaction-activity-designers.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [Dengelemek](../workflow-designer/compensate-activity-designer.md)
- [Onayla](../workflow-designer/confirm-activity-designer.md)
- [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)