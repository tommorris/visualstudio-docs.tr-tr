---
title: İş Akışı Tasarımcısı - TransactedReceiveScope etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.ServiceModel.Activities.TransactedReceiveScope.UI
ms.assetid: 7ca93aad-4e83-4d81-90f4-998ee114d9b6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 97a4871f3f9f7726f8e0f62008c22aef5e22234e
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755150"
---
# <a name="transactedreceivescope-activity-designer"></a>TransactedReceiveScope Etkinlik Tasarımcısı

**TransactedReceiveScope** Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.ServiceModel.Activities.TransactedReceiveScope> etkinlik.

## <a name="the-transactedreceivescope-activity"></a>TransactedReceiveScope etkinliği

<xref:System.ServiceModel.Activities.TransactedReceiveScope> Etkinliğini bir iş akışı veya gönderen tarafından oluşturulan sunucu hareketleri harekete akış olanak sağlar.

### <a name="using-the-transactedreceivescope-activity-designer"></a>TransactedReceiveScope etkinlik Tasarımcısı'nı kullanarak

Erişim **TransactedReceiveScope** etkinlik Tasarımcısı'nda **ileti** kategorisini **araç**. **TransactedReceiveScope** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve etkinlikleri genellikle yerleştirilir her yerde iş akışı Tasarımcısı yüzeyini açın. Bu oluşturur bir <xref:System.ServiceModel.Activities.TransactedReceiveScope> varsayılan etkinlik **DisplayName** TransactedReceiveScope biri. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **TransactedReceiveScope** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.

**TransactedReceiveScope** Tasarımcısı içeren **isteği** ve **gövde** kutuları. Bunlar yapılandırmak için kullanılan <xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A> belirtir özelliği bir <xref:System.ServiceModel.Activities.Receive> etkinliği ve bir <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> başka belirtir özelliği <xref:System.Activities.Activity>. <xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A> Bir işlem oluşturur. İşlemin ardından kapsamını ortam yapılan <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> böylece bu kapsam içinde herhangi bir etkinlik bu işlem içinde yürütür.

### <a name="the-transactedreceivescope-properties"></a>TransactedReceiveScope özellikleri

Aşağıdaki tabloda <xref:System.ServiceModel.Activities.TransactedReceiveScope> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bunlar <xref:System.Activities.Activity.DisplayName%2A> özelliği, özellik kılavuzu veya iş akışı Tasarımcısı yüzeyinde düzenlenebilir, ancak diğer tasarım yüzeyine düzenlenmesi gerekir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adını <xref:System.ServiceModel.Activities.TransactedReceiveScope> etkinlik. TransactedReceiveScope varsayılandır.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> adı kesinlikle gerekli değil, bir görünen ad kullanmak için en iyi bir uygulamadır.|
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A>|Doğru|Düşme bir <xref:System.ServiceModel.Activities.Receive> etkinliğini **isteği** etkinlik Tasarımcısı yüzeyinde bloğu.|
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>|False|Düşme bir <xref:System.Activities.Activity> içine **gövde** etkinlik Tasarımcısı yüzeyinde bloğu.|

## <a name="see-also"></a>Ayrıca bkz.

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [Alma](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Gönder](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)