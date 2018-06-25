---
title: İş Akışı Tasarımcısı - ReceiveAndSendReply şablonu Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.ServiceModel.Activities.ReceiveAndSendReply.UI
- System.ServiceModel.Activities.SendReply.UI
ms.assetid: d1d9a058-df7e-48f5-a2e7-3caeeba7eaa6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: acfe9f80a5125ef13996e7cd8ec88a35cfb83211
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756392"
---
# <a name="receiveandsendreply-template-designer"></a>ReceiveAndSendReply Şablon Tasarımcısı

**ReceiveAndSendReply** şablonu çifti oluşturmak için kullanılan önceden yapılandırılmış <xref:System.ServiceModel.Activities.Receive> ve <xref:System.ServiceModel.Activities.SendReply> etkinlikler. Etkinlikler parçası olan bir <xref:System.Activities.Statements.Sequence> etkinliği ve bu bağlantılı bir istek/yanıt ileti değişim deseni sunucudaki bir parçası olarak.

## <a name="the-receiveandsendreply-template"></a>ReceiveAndSendReply şablonu

Ekleme bir **ReceiveAndSendReply** şablonu oluşturma yanı sıra üç şey yapar <xref:System.ServiceModel.Activities.Receive> ve <xref:System.ServiceModel.Activities.SendReply> etkinliklerle bir <xref:System.Activities.Statements.Sequence> etkinlik:

- Yapılandırır <xref:System.ServiceModel.Activities.Receive.OperationName%2A> ve <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A> özelliklerini <xref:System.ServiceModel.Activities.Receive> etkinlik.

- Bağlar <xref:System.ServiceModel.Activities.SendReply.Request%2A> özelliği <xref:System.ServiceModel.Activities.Receive> etkinliğe <xref:System.ServiceModel.Activities.Send> etkinlik.

- Oluşturur bir <xref:System.ServiceModel.Activities.CorrelationHandle> bir değişken üst etkinlik olarak.

### <a name="use-the-receiveandsendreply-template-designer"></a>ReceiveAndSendReply şablonu tasarımcısını kullanabilirsiniz

Erişim **ReceiveAndSendReply** etkinlik Tasarımcısı'nda **ileti** kategorisini **araç**. **ReceiveAndSendReply** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve etkinlikleri genellikle yerleştirilir her yerde iş akışı Tasarımcısı yüzeyini açın. Etkinlik Tasarımcısı bırakarak oluşturur bir <xref:System.ServiceModel.Activities.Receive> ile yapılandırılmış etkinlik **Gönder** etkinlik Tasarımcısı ve bir ilişkili <xref:System.ServiceModel.Activities.SendReply> SendReplyToReceive Tasarımcısı ile yapılandırılabilir.

Kullanma hakkında daha fazla bilgi için **alma** yapılandırmak için tasarımcı <xref:System.ServiceModel.Activities.Receive> etkinliği bkz [alma etkinlik Tasarımcısı](../workflow-designer/receive-activity-designer.md).

### <a name="properties-of-sendreply"></a>SendReply özellikleri

Aşağıdaki tabloda <xref:System.ServiceModel.Activities.SendReply> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellikleri kılavuzunda düzenlenebilir ve bazı iş akışı Tasarımcısı yüzeyine düzenlenebilir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adını <xref:System.ServiceModel.Activities.SendReply> etkinlik. SendReplyToReceive varsayılandır.<br /><br /> Ancak kolay için varsayılan olmayan bir değer kullanımını <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil gibi bir değer kullanmak en iyisidir.|
|<xref:System.ServiceModel.Activities.SendReply.Request%2A>|Doğru|Başvuru <xref:System.ServiceModel.Activities.Receive> etkinlik bu ile eşleştirilmiş <xref:System.ServiceModel.Activities.SendReply> etkinlik. Bu özellik olmamalıdır **null**. <xref:System.ServiceModel.Activities.Receive> ve <xref:System.ServiceModel.Activities.SendReply> etkinlikleri birlikte sunucuda bir istek/yanıt Mesajlaşma düzeni modellemek için kullanılır. Bu özellik belirten <xref:System.ServiceModel.Activities.Send> etkinlik eşleştirilmiş. Tasarımcıda için otomatik olarak bağlı olduğundan, bu özellik düzenlenemiyor <xref:System.ServiceModel.Activities.Send> , oluşturulduğu etkinlik <xref:System.ServiceModel.Activities.SendReply> etkinlik.|
|<xref:System.ServiceModel.Activities.SendReply.Content%2A>|False|Almak için ileti veya parametre içeriğini belirtir. Ya da olabilir bir <xref:System.ServiceModel.Activities.ReceiveMessageContent> etkinlik veya <xref:System.ServiceModel.Activities.ReceiveParametersContent> etkinlik. Yanındaki üç nokta düğmesine tıklayarak bu özellik düzenleme **içerik** özellik kılavuzu veya tıklatarak alan **tanımla** düğmesine **içerik** etiketi **Alma** etkinlik Tasarımcı yüzeyine. Her ikisi de görüntülemek **içerik tanımı** iletişim. Bu kutusunun nasıl kullanılacağı hakkında daha fazla bilgi için bkz: [içerik tanımı iletişim kutusunu](../workflow-designer/content-definition-dialog-box.md) konu.|
|<xref:System.ServiceModel.Activities.SendReply.CorrelationInitializers%2A>|False|Koleksiyonunu belirtir <xref:System.ServiceModel.Activities.CorrelationInitializer> birden çok başlatma nesneleri <xref:System.ServiceModel.Activities.CorrelationHandle> bu yapılandırma nesneleri <xref:System.ServiceModel.Activities.Receive> akışındaki etkinlikler. Yanındaki üç nokta düğmesini tıklayın <xref:System.ServiceModel.Activities.SendReply.CorrelationInitializers%2A> özelliğini açmak için özellikler kılavuzunda **eklemek bağıntı başlatıcıları** iletişim kutusu. Bu kutu kullanma hakkında daha fazla bilgi için bkz: [CorrelationInitializers iletişim kutusunu](../workflow-designer/add-correlationinitializers-dialog-box.md) konu.|
|<xref:System.ServiceModel.Activities.SendReply.Action%2A>|False|İletinin eylem üstbilgisini belirtir. Açıkça ayarlanırsa, değeri varsayılan olarak:<br /><br /> **https://tempuri.org/{service ad alanı sözleşme} / {hizmet sözleşmesi adı} / {işlem adı}**|
|<xref:System.ServiceModel.Activities.SendReply.PersistBeforeSend%2A>|False|Yanıt iletisi gönderilmeden önce iş akışı örneği kalıcı olup olmadığını belirtir. Varsayılan değer **false**.|

## <a name="see-also"></a>Ayrıca bkz.

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [Alma](../workflow-designer/receive-activity-designer.md)
- [Gönder](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)