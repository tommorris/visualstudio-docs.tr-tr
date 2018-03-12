---
title: ReceiveAndSendReply Template Designer | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.ReceiveAndSendReply.UI
- System.ServiceModel.Activities.SendReply.UI
ms.assetid: d1d9a058-df7e-48f5-a2e7-3caeeba7eaa6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4c1236f8c3f86362ba49aa4b985dcc601a66c476
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="receiveandsendreply-template-designer"></a>ReceiveAndSendReply şablonu Tasarımcısı

**ReceiveAndSendReply** şablonu çifti oluşturmak için kullanılan önceden yapılandırılmış <xref:System.ServiceModel.Activities.Receive> ve <xref:System.ServiceModel.Activities.SendReply> içindeki etkinlikleri bir <xref:System.Activities.Statements.Sequence> istek/yanıt iletisi exchange bir parçası olarak bağıntılı etkinliği Sunucu üzerindeki deseni.

## <a name="the-receiveandsendreply-template"></a>ReceiveAndSendReply şablonu
 Ekleme **ReceiveAndSendReply** şablonu oluşturma yanı sıra üç şey yapar <xref:System.ServiceModel.Activities.Receive> ve <xref:System.ServiceModel.Activities.SendReply> etkinliklerle bir <xref:System.Activities.Statements.Sequence> etkinlik:

1.  Yapılandırır <xref:System.ServiceModel.Activities.Receive.OperationName%2A>, <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A> özelliklerini <xref:System.ServiceModel.Activities.Receive> etkinlik.

2.  Bağlar <xref:System.ServiceModel.Activities.SendReply.Request%2A> özelliği <xref:System.ServiceModel.Activities.Receive> etkinliğe <xref:System.ServiceModel.Activities.Send> etkinlik.

3.  Oluşturur bir <xref:System.ServiceModel.Activities.CorrelationHandle> bir değişken üst etkinlik olarak.

### <a name="using-the-receiveandsendreply-template-designer"></a>ReceiveAndSendReply şablonu Tasarımcısı'nı kullanarak
 **ReceiveAndSendReply** etkinlik Tasarımcısı bulunabilir **ileti** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç kutusu**  sekmesinde [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)

 **ReceiveAndSendReply** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir. Bu oluşturur bir <xref:System.ServiceModel.Activities.Receive> ile yapılandırılmış etkinlik **Gönder** etkinlik Tasarımcısı ve bir ilişkili <xref:System.ServiceModel.Activities.SendReply> SendReplyToReceive Tasarımcısı ile yapılandırılabilir.

 Kullanma hakkında daha fazla bilgi için **alma** yapılandırmak için tasarımcı <xref:System.ServiceModel.Activities.Receive> etkinliği bkz [alma](../workflow-designer/receive-activity-designer.md) konu.

 Kullanma hakkında daha fazla bilgi için **SendReplyToReceive** yapılandırmak için tasarımcı <xref:System.ServiceModel.Activities.SendReply> etkinlik, aşağıdaki bölüme bakın.

### <a name="properties-of-sendreply"></a>SendReply özellikleri
 Aşağıdaki tabloda <xref:System.ServiceModel.Activities.SendReply> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellikleri kılavuzunda düzenlenebilir ve bazı üzerinde düzenlenebilir [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] Tasarımcı yüzeyine.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adını <xref:System.ServiceModel.Activities.SendReply> etkinlik. SendReplyToReceive varsayılandır.<br /><br /> Ancak kolay için varsayılan olmayan bir değer kullanımını <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil gibi bir değer kullanmak için en iyi bir uygulamadır.|
|<xref:System.ServiceModel.Activities.SendReply.Request%2A>|Doğru|Başvuru <xref:System.ServiceModel.Activities.Receive> etkinlik bu ile eşleştirilmiş <xref:System.ServiceModel.Activities.SendReply> etkinlik. Bu özellik olmamalıdır **null**. <xref:System.ServiceModel.Activities.Receive> ve <xref:System.ServiceModel.Activities.SendReply> etkinlikleri birlikte sunucuda bir istek/yanıt Mesajlaşma düzeni modellemek için kullanılır. Bu özellik belirten <xref:System.ServiceModel.Activities.Send> etkinlik eşleştirilmiş. Tasarımcıda için otomatik olarak bağlı olduğundan, bu özellik düzenlenemiyor <xref:System.ServiceModel.Activities.Send> , oluşturulduğu etkinlik <xref:System.ServiceModel.Activities.SendReply> etkinlik.|
|<xref:System.ServiceModel.Activities.SendReply.Content%2A>|False|Almak için ileti veya parametre içeriğini belirtir. Ya da olabilir bir <xref:System.ServiceModel.Activities.ReceiveMessageContent> etkinlik veya <xref:System.ServiceModel.Activities.ReceiveParametersContent> etkinlik. Bu özelliğin yanındaki üç nokta düğmesine tıklayarak Düzenle **içerik** özellik kılavuzu veya tıklatarak alanındaki **tanımla...**  yanındaki düğmesini **içerik** üzerinde etiket **alma** etkinlik Tasarımcı yüzeyine. Her ikisi de görüntülemek **içerik tanımı** iletişim. Bu kutusunun nasıl kullanılacağı hakkında daha fazla bilgi için bkz: [içerik tanımı iletişim kutusunu](../workflow-designer/content-definition-dialog-box.md) konu.|
|<xref:System.ServiceModel.Activities.SendReply.CorrelationInitializers%2A>|False|Koleksiyonunu belirtir <xref:System.ServiceModel.Activities.CorrelationInitializer> birden çok başlatma nesneleri <xref:System.ServiceModel.Activities.CorrelationHandle> bu yapılandırma nesneleri <xref:System.ServiceModel.Activities.Receive> akışındaki etkinlikler. Yanındaki üç nokta düğmesini tıklayın <xref:System.ServiceModel.Activities.SendReply.CorrelationInitializers%2A> özelliğini açmak için özellikler kılavuzunda **eklemek bağıntı başlatıcıları** iletişim kutusu. Bu kutu kullanma hakkında daha fazla bilgi için bkz: [CorrelationInitializers iletişim kutusunu](../workflow-designer/add-correlationinitializers-dialog-box.md) konu.|
|<xref:System.ServiceModel.Activities.SendReply.Action%2A>|False|İletinin eylem üstbilgisini belirtir. Açıkça ayarlanmazsa değerini varsayılan olarak:<br /><br /> **https://tempuri.org/{service contract namespace}/{service contract name}/{operation name}**|
|<xref:System.ServiceModel.Activities.SendReply.PersistBeforeSend%2A>|False|Yanıt iletisi gönderilmeden önce iş akışı örneği kalıcı olup olmadığını belirtir. Varsayılan değer **false**.|

## <a name="see-also"></a>Ayrıca bkz.

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [Alma](../workflow-designer/receive-activity-designer.md)
- [Gönder](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)