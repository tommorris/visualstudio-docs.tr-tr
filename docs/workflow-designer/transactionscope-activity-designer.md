---
title: İş Akışı Tasarımcısı - TransactionScope etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.TransactionScope.UI
ms.assetid: 8d7ebfc6-7478-4888-b3b0-b14f296096af
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7622dc9b926124d0ed2b2ae759beafcbac3a475a
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755804"
---
# <a name="transactionscope-activity-designer"></a>TransactionScope Etkinlik Tasarımcısı

**TransactionScope** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.TransactionScope> etkinlik.

## <a name="the-transactionscope-activity"></a>TransactionScope etkinliği

<xref:System.Activities.Statements.TransactionScope> Etkinliği kapsanan etkinlik tek bir işlemde yürütür. İşlem zaman tamamlar <xref:System.Activities.Statements.TransactionScope.Body%2A> etkinliği ve diğer tüm katılımcılar işlem başarıyla tamamlandı.

### <a name="using-the-transactionscope-activity-designer"></a>TransactionScope etkinlik Tasarımcısı'nı kullanarak

Erişim **TransactionScope** etkinlik Tasarımcısı'nda **işlem** kategorisini **araç**. **TransactionScope** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve etkinlikleri genellikle yerleştirilir olduğunda, örneğin olarak içinde açın iş akışı Tasarımcısı yüzeyini bırakılan bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.TransactionScope> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> TransactionScope biri. <xref:System.Activities.Activity.DisplayName%2A> Değeri üstbilgisinde düzenlenebilir **TransactionScope** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.

### <a name="the-transactionscope-properties"></a>TransactionScope özellikleri

Aşağıdaki tabloda <xref:System.Activities.Statements.TransactionScope> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. <xref:System.Activities.Activity.DisplayName%2A> Ve <xref:System.Activities.Statements.TransactionScope.Body%2A> özellikleri iş akışı Tasarımcısı yüzeyine düzenlenebilir. Ancak, diğer özellikler ve özellik ızgarasının düzenlenmesi gerekir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adını <xref:System.Activities.Statements.TransactionScope> etkinlik. TransactionScope varsayılandır. Ancak <xref:System.Activities.Activity.DisplayName%2A> değeri kesinlikle gerekli değildir, kullanmak için en iyi bir uygulamadır.|
|<xref:System.Activities.Statements.TransactionScope.Body%2A>|Doğru|Tek bir işlemde yürütmek için etkinliği belirtir. Eklemek için <xref:System.Activities.Statements.TransactionScope.Body%2A> etkinlik, açılan bir etkinlikten **araç** içine **gövde** kutusuna **TransactionScope** ipucu metnini "açılan etkinliği ile etkinlik Tasarımcısı Burada".|
|<xref:System.Activities.Statements.TransactionScope.IsolationLevel%2A>|Doğru|Belirtir <xref:System.Transactions.IsolationLevel> bu <xref:System.Activities.Statements.TransactionScope>.|
|<xref:System.Activities.Statements.TransactionScope.Timeout%2A>|False|(00:00: saat: dakika: saniye gösterir 00, biçimlendirilmiş) zaman aralığını belirtir tamamlamak işlem sahip. Varsayılan değer 1 dakikadır (00: 01:00).|
|[System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure](https://msdn.microsoft.com/library/system.activities.statements.transactionscope.abortinstanceontransactionfailure.aspx)|Doğru|İşlem iptal olursa, iş akışı iptal olup olmadığını gösteren değeri belirtir.|

## <a name="see-also"></a>Ayrıca bkz.

- [İşlem](../workflow-designer/transaction-activity-designers.md)
- [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [Dengelemek](../workflow-designer/compensate-activity-designer.md)
- [Onayla](../workflow-designer/confirm-activity-designer.md)