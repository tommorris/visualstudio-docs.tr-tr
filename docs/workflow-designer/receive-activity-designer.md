---
title: "Etkinlik Tasarımcısı alıyorsunuz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.Receive.UI
ms.assetid: f58d3c70-944d-4bb4-90a7-e68c103caddc
caps.latest.revision: 
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload:
- multiple
ms.openlocfilehash: 7c02cf726cbf575eae9c389186846855ee1206c4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="receive-activity-designer"></a>Etkinlik Tasarımcısı alma
**Alma** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.ServiceModel.Activities.Receive> etkinlik. A <xref:System.ServiceModel.Activities.Receive> etkinliktir yerleşik bir tür gibi olabilir bir ileti alır bir etkinlik <xref:System.ServiceModel.Channels.Message>, <xref:System.IO.Stream> veya <xref:System.Xml.Linq.XElement>, veya bir uygulama tarafından tanımlanan veri sözleşmesi, ileti sözleşmesi veya seri hale getirilebilir XML sınıfı.  
  
## <a name="the-receive-activity"></a>Etkinlik alma  
 <xref:System.ServiceModel.Activities.Receive> Etkinlik, tek bir öğe alabilir veya birden çok öğe türüne bağlı olarak kullanılan içerik alırsınız. A <xref:System.ServiceModel.Activities.SendReply> etkinlik bağlanabilir bir <xref:System.ServiceModel.Activities.Receive> etkinlik bir istek/yanıt ileti değişim deseni hizmetinin bir parçası olarak bir ileti alır.  
  
### <a name="using-the-receive-activity-designer"></a>Kullanarak etkinlik Tasarımcısı alma  
 **Alma** etkinlik Tasarımcısı bulunabilir **ileti** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç**sekmesi [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)  
  
 **Alma** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir. Bu oluşturur bir <xref:System.ServiceModel.Activities.Receive> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> alma. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **alma** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.  
  
 Oluşturmak için bir <xref:System.ServiceModel.Activities.SendReply> etkinlik ve seçili bağlamak <xref:System.ServiceModel.Activities.Receive> etkinliği sağ tıklatın **alma** etkinlik Tasarımcısı, tıklatın **oluşturma SendReply** bağlam menüsü öğesini ve **SendReplyToReceive** Tasarımcısı görünür aşağıda **alma** Tasarımcısı. <xref:System.ServiceModel.Activities.SendReply> Bir istek/yanıt ileti değişim deseni hizmetinin bir parçası olarak yanıt iletisini gönderir. bir etkinlik bir etkinliktir. İle yapılandırılabilir **SendReplyToReceive** Tasarımcısı.  
  
 Alternatif olarak, **ReceiveAndSendReply** şablonu Tasarımcısı'nda **ileti** kategorisini **araç** önceden yapılandırılmış çiftioluşturmakiçinkullanılan<xref:System.ServiceModel.Activities.Receive>ve <xref:System.ServiceModel.Activities.SendReply> etkinlik. [!INCLUDE[crabout](../test/includes/crabout_md.md)]kullanımını **ReceiveAndSendReply** ve **SendReplyToReceive** şablon bkz [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md) konu.  
  
### <a name="the-receive-activity-properties"></a>Etkinlik özelliklerini alma  
 Aşağıdaki tabloda <xref:System.ServiceModel.Activities.Receive> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellikleri ızgara veya üzerinde düzenlenebilir [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzeyini. Yalnızca gerekli bir özelliktir <xref:System.ServiceModel.Activities.Receive.OperationName%2A> özelliği.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı belirtir <xref:System.ServiceModel.Activities.Receive> etkinlik. Alma varsayılan değerdir.<br /><br /> Ancak kolay için varsayılan olmayan bir değer kullanımını <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil gibi bir değer kullanmak için en iyi bir uygulamadır.|  
|<xref:System.ServiceModel.Activities.Receive.OperationName%2A>|Doğru|Bu tarafından uygulanan hizmet işlemi adını belirtir <xref:System.ServiceModel.Activities.Receive> etkinlik. Bu özellik için varsayılan değer oluşturmak için kullanılan **eylem** özelliği, **eylem** özelliği açıkça ayarlı değil.|  
|<xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>|False|Hizmet sözleşmesi adını belirtir. Bu özellik, bireysel Hizmet sözleşmeleri içine Grup hizmet işlemleri için kullanılır. Tüm <xref:System.ServiceModel.Activities.Receive> aynı olan etkinlikleri <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A> aynı hizmet sözleşmesine (WSDL bağlantı noktası türü) gruplandırılır. Varsayılan değer tam CLR üst düzey (kök) etkinlik adıdır.|  
|<xref:System.ServiceModel.Activities.Receive.Content%2A>|False|Almak için ileti veya parametre içeriğini belirtir. Ya da olabilir bir <xref:System.ServiceModel.Activities.ReceiveMessageContent> etkinlik veya <xref:System.ServiceModel.Activities.ReceiveParametersContent> etkinlik. Bu özelliğin yanındaki üç nokta düğmesine tıklayarak Düzenle **içerik** özellik kılavuzu veya tıklatarak alanındaki **tanımla...**  yanındaki düğmesini **içerik** üzerinde etiket **alma** etkinlik Tasarımcı yüzeyine. Her ikisi de görüntülemek **içerik tanımı** iletişim. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Bu kutu kullanma hakkında [içerik tanımı iletişim kutusunu](../workflow-designer/content-definition-dialog-box.md) konu.|  
|<xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>|False|Arasındaki bağıntıları belirtir <xref:System.ServiceModel.Activities.Receive> hizmet işlemleri içeren bir iş akışının etkinlikleri bir <xref:System.ServiceModel.MessageQuerySet> nesnesi. Üç nokta düğmesini tıklayın <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> özelliğini açmak için özellikler kılavuzunda **CorrelatesOn tanımı** iletişim kutusu. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Bu iletişim kutusunu kullanımını görmek [içerik tanımı iletişim kutusunu](../workflow-designer/content-definition-dialog-box.md) konu.|  
|<xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A>|False|Belirtir <xref:System.ServiceModel.Activities.CorrelationHandle> uygun iş akışı örneğine ileti yönlendirmek için kullanılır.<br /><br /> Üç nokta düğmesini tıklayın <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> özelliğini açmak için özellikler kılavuzunda **ifade Düzenleyicisi** iletişim kutusu. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Bu iletişim kutusunu kullanımını görmek [nasıl yapılır: ifade Düzenleyicisi'ni](../workflow-designer/how-to-use-the-expression-editor.md) konu.|  
|<xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>|False|Koleksiyonunu belirtir <xref:System.ServiceModel.Activities.CorrelationInitializer> birden çok başlatma nesneleri <xref:System.ServiceModel.Activities.CorrelationHandle> bu yapılandırma nesneleri <xref:System.ServiceModel.Activities.Receive> akışındaki etkinlikler. Yanındaki üç nokta düğmesini tıklayın <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> özelliğini açmak için özellikler kılavuzunda **eklemek bağıntı başlatıcıları** iletişim kutusu. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Bu kutusunu kullanarak bkz [CorrelationInitializers iletişim kutusunu](../workflow-designer/add-correlationinitializers-dialog-box.md) konu.|  
|<xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A>|False|Yeni bir iş akışı örneği ileti var olan bir iş akışı örneğini bağıntılı olmayan, iletiyi işlemek için oluşturulup oluşturulmayacağını belirleyen bir değer belirtir. Değer ayarlanmışsa **doğru**, ileti var olan bir iş akışı örneği ile ilişkili değil, iletiyi işlemek için yeni bir iş akışı örneği oluşturulur.|  
|<xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>|False|Bu tarafından uygulanan hizmet işlemi bilinen türleri koleksiyonunu belirtir <xref:System.ServiceModel.Activities.Receive> etkinlik. Bu özellik ile birlikte kullanılması gereken <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> özelliğini <xref:System.Runtime.Serialization.DataContractSerializer>. Varsa bu değer yoksayılır <xref:System.Xml.Serialization.XmlSerializer> kullanılır.<br /><br /> Yanındaki üç nokta düğmesini **KnownTypes** görüntülemek için özellik kılavuzunu alanındaki **türü Koleksiyonu Düzenleyicisi** ile ilgili türleri iletişim kutusunu. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Bu kutusunu kullanarak bkz [türü koleksiyon Düzenleyicisi iletişim kutusu](../workflow-designer/type-collection-editor-dialog-box.md) konu.|  
|<xref:System.ServiceModel.Activities.Receive.ProtectionLevel%2A>|False|Belirtir <xref:System.Net.Security.ProtectionLevel> ileti.<br /><br /> 1. <xref:System.Net.Security.ProtectionLevel> yalnızca kimlik doğrulaması anlamına gelir.<br />2. <xref:System.Net.Security.ProtectionLevel> oturum aktarılan veri bütünlüğünü sağlamaya yardımcı olmak için veri anlamına gelir.<br />3. <xref:System.Net.Security.ProtectionLevel> şifrelemek ve oturum gizliliği ve aktarılan veri bütünlüğünü sağlamaya yardımcı olmak için veri anlamına gelir.|  
|<xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>|False|Seri hale getirici tarafından uygulanan hizmet işlemi için kullanılacak türünü belirtir <xref:System.ServiceModel.Activities.Receive> etkinlik. Varsayılan değer <xref:System.Runtime.Serialization.DataContractSerializer>, serileştirir ve bir XML akışı veya sağlanan veri sözleşme kullanan belge türünün bir örneği seri durumdan çıkarır. <xref:System.Xml.Serialization.XmlSerializer> Daha fazla denetim gerekliyse, XML de kullanılabilir.|  
|<xref:System.ServiceModel.Activities.Receive.Action%2A>|False|İletinin eylem üstbilgisini belirtir. Değeri açıkça ayarlanmazsa, varsayılan: https://tempuri.org/ {hizmet sözleşmesi ad} / {hizmet sözleşmesi adı} / {işlem adı}.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)   
 [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)   
 [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)   
 [Gönder](../workflow-designer/send-activity-designer.md)   
 [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)   
 [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)