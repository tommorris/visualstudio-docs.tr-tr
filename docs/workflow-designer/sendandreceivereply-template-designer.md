---
title: İş Akışı Tasarımcısı - SendAndReceiveReply şablonu Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.ServiceModel.Activities.SendAndReceiveReply.UI
- System.ServiceModel.Activities.ReceiveReply.UI
ms.assetid: 818a8c84-6593-416d-b016-1d91b85ffb68
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 282ba94c026b885cb6f8250b33beb98616376e8d
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755817"
---
# <a name="sendandreceivereply-template-designer"></a>SendAndReceiveReply Şablon Tasarımcısı

**SendAndReceiveReply** şablonu çifti oluşturmak için kullanılan önceden yapılandırılmış <xref:System.ServiceModel.Activities.Send> ve <xref:System.ServiceModel.Activities.ReceiveReply> etkinlikler. Etkinlikler parçası olan bir <xref:System.Activities.Statements.Sequence> etkinliği ve bu bağlantılı bir istek/yanıt ileti değişim deseni istemcide bir parçası olarak.

## <a name="the-sendandreceivereply-template"></a>SendAndReceiveReply şablonu

Ekleme **SendAndReceiveReply** şablonu oluşturma yanı sıra üç şey yapar <xref:System.ServiceModel.Activities.Send> ve <xref:System.ServiceModel.Activities.ReceiveReply> içindeki etkinlikleri bir <xref:System.Activities.Statements.Sequence> etkinlik:

- Yapılandırır <xref:System.ServiceModel.Activities.Send.OperationName%2A> ve <xref:System.ServiceModel.Activities.Send.ServiceContractName%2A> özelliklerini <xref:System.ServiceModel.Activities.Send> etkinlik.

- Bağlar <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A> özelliği <xref:System.ServiceModel.Activities.ReceiveReply> etkinliğe <xref:System.ServiceModel.Activities.Send> etkinlik.

- Oluşturur bir <xref:System.ServiceModel.Activities.CorrelationHandle> bir değişken üst etkinlik olarak.

### <a name="use-the-sendandreceivereply-template-designer"></a>SendAndReceiveReply şablonu tasarımcısını kullanabilirsiniz

Erişim **SendAndReceiveReply** etkinlik Tasarımcısı'nda **ileti** kategorisini **araç**. **SendAndReceiveReply** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve etkinlikleri genellikle yerleştirilir her yerde iş akışı Tasarımcısı yüzeyini açın. Etkinlik Tasarımcısı bırakarak oluşturur bir <xref:System.ServiceModel.Activities.Send> ile yapılandırılmış etkinlik **Gönder** etkinlik Tasarımcısı ve bir ilişkili <xref:System.ServiceModel.Activities.ReceiveReply> ile yapılandırılabilir **ReceiveReplyForSend** Tasarımcısı.

Kullanma hakkında daha fazla bilgi için **Gönder** yapılandırmak için tasarımcı <xref:System.ServiceModel.Activities.Send> etkinliği bkz [Gönder](../workflow-designer/send-activity-designer.md).

### <a name="properties-of-receivereply"></a>ReceiveReply özellikleri

Aşağıdaki tabloda <xref:System.ServiceModel.Activities.ReceiveReply> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellikleri kılavuzunda düzenlenebilir ve bazı iş akışı Tasarımcısı yüzeyine düzenlenebilir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adını <xref:System.ServiceModel.Activities.ReceiveReply> etkinlik. ReceiveReplyForSend varsayılandır.<br /><br /> Ancak kolay için varsayılan olmayan bir değer kullanımını <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil gibi bir değer kullanmak en iyisidir.|
|<xref:System.ServiceModel.Activities.ReceiveReply.Request%2A>|Doğru|Başvuru <xref:System.ServiceModel.Activities.Send> etkinlik bu ile eşleştirilmiş <xref:System.ServiceModel.Activities.ReceiveReply> etkinlik. Bu özellik olmamalıdır **null**. <xref:System.ServiceModel.Activities.Send> ve <xref:System.ServiceModel.Activities.ReceiveReply> etkinlikleri birlikte istemcide bir istek/yanıt Mesajlaşma düzeni modellemek için kullanılır. Bu özellik belirten <xref:System.ServiceModel.Activities.Send> etkinlik eşleştirilmiş. Tasarımcıda için otomatik olarak bağlı olduğundan, bu özellik düzenlenemiyor <xref:System.ServiceModel.Activities.Send> , oluşturulduğu etkinlik <xref:System.ServiceModel.Activities.ReceiveReply> etkinlik.|
|<xref:System.ServiceModel.Activities.ReceiveReply.Content%2A>|False|Almak için ileti veya parametre içeriğini belirtir. Ya da olabilir bir <xref:System.ServiceModel.Activities.ReceiveMessageContent> etkinlik veya <xref:System.ServiceModel.Activities.ReceiveParametersContent> etkinlik. Yanındaki üç nokta düğmesine tıklayarak bu özellik düzenleme **içerik** özellik kılavuzunda veya tıklatarak alan **tanımla** düğmesine **içerik** üzerindeki etiket **Alma** etkinlik Tasarımcı yüzeyine. Her ikisi de görüntülemek **içerik tanımı** iletişim. Bu kutusunun nasıl kullanılacağı hakkında daha fazla bilgi için bkz: [içerik tanımı iletişim kutusunu](../workflow-designer/content-definition-dialog-box.md).|
|<xref:System.ServiceModel.Activities.ReceiveReply.CorrelationInitializers%2A>|False|Koleksiyonunu belirtir <xref:System.ServiceModel.Activities.CorrelationInitializer> birden çok başlatma nesneleri <xref:System.ServiceModel.Activities.CorrelationHandle> bu yapılandırma nesneleri <xref:System.ServiceModel.Activities.Receive> akışındaki etkinlikler. Yanındaki üç nokta düğmesini tıklayın <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> özelliğini açmak için özellikler kılavuzunda **eklemek bağıntı başlatıcıları** iletişim kutusu. Bu kutu kullanma hakkında daha fazla bilgi için bkz: [CorrelationInitializers iletişim kutusunu](../workflow-designer/add-correlationinitializers-dialog-box.md).|
|<xref:System.ServiceModel.Activities.ReceiveReply.Action%2A>|False|İletinin eylem üstbilgisini belirtir. Açıkça ayarlanırsa, değeri varsayılan olarak:<br /><br /> **https://tempuri.org/{service ad alanı sözleşme} / {hizmet sözleşmesi adı} / {işlem adı}.**|

## <a name="see-also"></a>Ayrıca bkz.

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [Alma](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Gönder](../workflow-designer/send-activity-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)