---
title: İş Akışı Tasarımcısı - gönderme etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.ServiceModel.Activities.Send.UI
ms.assetid: b514f2e4-767c-4b94-ac61-dd3a54d4b96d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 099a512bcbca7136541c9896e32f43b9e518ed8b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31978355"
---
# <a name="send-activity-designer"></a>Etkinlik Tasarımcısı Gönder

**Gönder** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.ServiceModel.Activities.Send> etkinlik.

## <a name="the-send-activity"></a>Gönder etkinliği

 A <xref:System.ServiceModel.Activities.Send> etkinlik, bir hizmet için bir ileti göndermek için kullanılır. A <xref:System.ServiceModel.Activities.ReceiveReply> etkinlik bağlanabilir bir <xref:System.ServiceModel.Activities.Send> etkinlik bir istek/yanıt ileti değişim deseni istemcide bir parçası olarak bir ileti alır.

### <a name="using-the-send-activity-designer"></a>Gönderme etkinlik Tasarımcısı'nı kullanarak
 **Gönder** etkinlik Tasarımcısı bulunabilir **ileti** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç** İş Akışı Tasarımcısı'nda sekmesinde (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)

 **Gönder** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve etkinlikleri genellikle yerleştirilir her yerde iş akışı Tasarımcısı yüzeyini açın. Bu oluşturur bir <xref:System.ServiceModel.Activities.Send> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> gönderme. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **Gönder** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.

 Oluşturmak için bir <xref:System.ServiceModel.Activities.ReceiveReply> etkinlik ve seçili bağlayın <xref:System.ServiceModel.Activities.Send> etkinliği sağ tıklatın **göndermek** etkinlik Tasarımcısı, tıklatın **oluşturma ReceiveReply** bağlam menüsü öğesini ve **ReceiveReplyForSend** Tasarımcısı görünür aşağıda **Gönder** Tasarımcısı. <xref:System.ServiceModel.Activities.ReceiveReply> Bir istek/yanıt ileti değişim deseni istemcide bir parçası olarak bir ileti alır bir etkinlik bir etkinliktir. İle yapılandırılabilir **ReceiveReplyForSend** Tasarımcısı.

 Alternatif olarak, **SendAndReceiveReply** şablonu Tasarımcısı'nda **ileti** kategorisini **araç** önceden yapılandırılmış çiftioluşturmakiçinkullanılan<xref:System.ServiceModel.Activities.Send>ve <xref:System.ServiceModel.Activities.ReceiveReply> etkinlikler. Kullanımı hakkında daha fazla bilgi için **SendAndReceiveReply** ve **ReceiveReplyForSend** şablonları için bkz: [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md) konu.

### <a name="the-send-activity-properties"></a>Gönder etkinliği özellikleri
 Aşağıdaki tabloda <xref:System.ServiceModel.Activities.Send> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellikleri ızgara veya iş akışı Tasarımcısı yüzeyinde düzenlenebilir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.ServiceModel.Activities.Send> etkinlik. Varsayılan değer olan gönderin. Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|
|<xref:System.ServiceModel.Activities.Send.OperationName%2A>|Doğru|Hizmet işlemini adını adlı bu tarafından <xref:System.ServiceModel.Activities.Send> etkinlik. Bu özellik için varsayılan değer oluşturmak için kullanılan **eylem** özelliği, **eylem** özelliği açıkça ayarlı değil.|
|<xref:System.ServiceModel.Activities.Send.ServiceContractName%2A>|Doğru|Çağrılacak hizmet uygulayan hizmet sözleşmesi adı.|
|<xref:System.ServiceModel.Activities.Send.Content%2A>|False|Almak için ileti veya parametre içeriğini belirtir. Ya da olabilir bir <xref:System.ServiceModel.Activities.ReceiveMessageContent> etkinlik veya <xref:System.ServiceModel.Activities.ReceiveParametersContent> etkinlik. Bu özelliğin yanındaki üç nokta düğmesine tıklayarak Düzenle **içerik** özellik kılavuzu veya tıklatarak alanındaki **tanımla...**  yanındaki düğmesini **içerik** üzerinde etiket **alma** etkinlik Tasarımcı yüzeyine. Her ikisi de görüntülemek **içerik tanımı** iletişim. Bu kutusunun nasıl kullanılacağı hakkında daha fazla bilgi için bkz: [içerik tanımı iletişim kutusunu](../workflow-designer/content-definition-dialog-box.md) konu.|
|<xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A>|False|Belirtir <xref:System.ServiceModel.Activities.CorrelationHandle> uygun iş akışı örneğine ileti yönlendirmek için kullanılır.<br /><br /> Üç nokta düğmesini tıklayın <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A> özelliğini açmak için özellikler kılavuzunda **ifade Düzenleyicisi** iletişim kutusu. Bu iletişim kutusunu kullanma hakkında daha fazla bilgi için bkz [nasıl yapılır: ifade Düzenleyicisi'ni](../workflow-designer/how-to-use-the-expression-editor.md) konu.|
|<xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A>|False|Koleksiyonunu belirtir <xref:System.ServiceModel.Activities.CorrelationInitializer> birden çok başlatma nesneleri <xref:System.ServiceModel.Activities.CorrelationHandle> bu yapılandırma nesneleri <xref:System.ServiceModel.Activities.Send> akışındaki etkinlikler. Yanındaki üç nokta düğmesini tıklayın <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> özelliğini açmak için özellikler kılavuzunda **eklemek bağıntı başlatıcıları** iletişim kutusu. Bu kutu kullanma hakkında daha fazla bilgi için bkz: [CorrelationInitializers iletişim kutusunu](../workflow-designer/add-correlationinitializers-dialog-box.md) konu.|
|<xref:System.ServiceModel.Activities.Send.KnownTypes%2A>|False|Hizmet işlemi bilinen türleri bu tarafından çağrılacak bir koleksiyonunu <xref:System.ServiceModel.Activities.Send> etkinlik. Bu özellik ile birlikte kullanılması gereken <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> özelliğini <xref:System.Runtime.Serialization.DataContractSerializer>. Varsa bu değer yoksayılır <xref:System.Xml.Serialization.XmlSerializer> kullanılır.<br /><br /> Yanındaki üç nokta düğmesini **KnownTypes** görüntülemek için özellik kılavuzunu alanındaki **türü Koleksiyonu Düzenleyicisi** ilgili türleri ile ekleyebileceğiniz iletişim.<br /><br /> Yanındaki üç nokta düğmesini **KnownTypes** görüntülemek için özellik kılavuzunu alanındaki **türü Koleksiyonu Düzenleyicisi** ile ilgili türleri iletişim kutusunu. Bu kutu kullanma hakkında daha fazla bilgi için bkz: [türü koleksiyon Düzenleyicisi iletişim kutusu](../workflow-designer/type-collection-editor-dialog-box.md) konu.|
|<xref:System.ServiceModel.Activities.Send.ProtectionLevel%2A>|Doğru|Belirtir <xref:System.Net.Security.ProtectionLevel> ileti.<br /><br /> 1. <xref:System.Net.Security.ProtectionLevel> yalnızca kimlik doğrulaması anlamına gelir.<br />2. <xref:System.Net.Security.ProtectionLevel> oturum aktarılan veri bütünlüğünü sağlamaya yardımcı olmak için veri anlamına gelir.<br />3. <xref:System.Net.Security.ProtectionLevel> şifrelemek ve oturum gizliliği ve aktarılan veri bütünlüğünü sağlamaya yardımcı olmak için veri anlamına gelir.|
|<xref:System.ServiceModel.Activities.Send.SerializerOption%2A>|Doğru|Çağrılacak hizmet işlemi için kullanılacak serileştirici <xref:System.ServiceModel.Activities.Send> etkinlik. Varsayılan değer <xref:System.Runtime.Serialization.DataContractSerializer>, serileştirir ve bir XML akışı veya sağlanan veri sözleşmesi kullanarak belge türünün bir örneği seri durumdan çıkarır.|
|<xref:System.ServiceModel.Activities.Send.Action%2A>|False|İletinin eylem üstbilgisini belirtir. Değeri açıkça ayarlanmazsa, varsayılan: https://tempuri.org/{service ad alanı sözleşme} / {hizmet sözleşmesi adı} / {işlem adı}. Belirtilen varsa bir <xref:System.ServiceModel.Activities.Send> etkinliği <xref:System.ServiceModel.Activities.Receive> iletiyi alır etkinliği iletisinin doğru şekilde teslim edilmesi aynı değere sahip olmalıdır.|
|<xref:System.ServiceModel.Activities.Send.TokenImpersonationLevel%2A>||<xref:System.Security.Principal.TokenImpersonationLevel> İleti alıcısı için izin verilir. Bir sunucu işlemi istemci işlem adına işlem yapabileceği derece yöneten Güvenlik kimliğe bürünme düzeyleri tanımlar.<xref:System.Security.Principal.TokenImpersonationLevel> Kimliğe bürünme düzeyi atanmamıştır gösterir. <xref:System.Security.Principal.TokenImpersonationLevel> Sunucu işlemi istemci kimlik bilgilerini alamaz ve istemci alamadığı gösterir. <xref:System.Security.Principal.TokenImpersonationLevel> Sunucu işlemi güvenlik tanımlayıcılarını ve öncelikleri gibi istemci hakkında bilgi elde edebilirsiniz, ancak istemci kimliğini belirleyemez gösterir. Bu, örneğin, tabloları ve görünümleri verme veritabanı ürünleri kendi nesneleri dışarı aktarmak sunucuları için faydalıdır. Alınan istemci güvenlik bilgileri kullanarak, sunucu erişimi doğrulaması istemcinin güvenlik bağlamını kullanarak diğer hizmetler kullanabilmeye olmadan kararlarını verebilir. <xref:System.Security.Principal.TokenImpersonationLevel> Sunucu işlemi istemcinin güvenlik bağlamı, yerel sistemde bürünebileceğini gösterir. Sunucu uzak sistemlere istemci kimliğini belirleyemez. <xref:System.Security.Principal.TokenImpersonationLevel> Sunucu işlemi istemcinin güvenlik bağlamı uzak sistemlere bürünebileceğini gösterir.|
|<xref:System.ServiceModel.Activities.Send.Endpoint%2A>||<xref:System.ServiceModel.Endpoint> , <xref:System.ServiceModel.Activities.Send> Etkinlik iletiyi gönderir. Bu özellik ayarlanırsa <xref:System.ServiceModel.Activities.Send.EndpointConfigurationName%2A> özelliği ayarlanmalıdır **null**.|
|<xref:System.ServiceModel.Activities.Send.EndpointAddress%2A>||<xref:System.ServiceModel.EndpointAddress> İletinin gönderildiği için.|
|<xref:System.ServiceModel.Activities.Send.EndpointConfigurationName%2A>||Uç nokta Yapılandırması adı. Bir yapılandırma dosyasında bir uç nokta yapılandırırken bu özelliği ayarlayın. Verilen adı için bu özelliği ayarlayın  **\<uç noktası >** yapılandırma dosyanızda öğesi. Bu özellik ayarlanırsa, <xref:System.ServiceModel.Activities.Send.Endpoint%2A> özelliği ayarlanmalıdır **null**.|

## <a name="see-also"></a>Ayrıca bkz.

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Alma](../workflow-designer/receive-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)