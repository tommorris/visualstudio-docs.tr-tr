---
title: "SendAndReceiveReply şablonu Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.SendAndReceiveReply.UI
- System.ServiceModel.Activities.ReceiveReply.UI
ms.assetid: 818a8c84-6593-416d-b016-1d91b85ffb68
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: be208d526fdc9f1d6f434425e3931b0f0a6510f5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="sendandreceivereply-template-designer"></a>SendAndReceiveReply şablonu Tasarımcısı
**SendAndReceiveReply** şablonu çifti oluşturmak için kullanılan önceden yapılandırılmış <xref:System.ServiceModel.Activities.Send> ve <xref:System.ServiceModel.Activities.ReceiveReply> içindeki etkinlikleri bir <xref:System.Activities.Statements.Sequence> istek/yanıt iletisi exchange bir parçası olarak bağıntılı etkinliği istemci üzerinde deseni.  
  
## <a name="the-sendandreceivereply-template"></a>SendAndReceiveReply şablonu  
 Ekleme **SendAndReceiveReply** şablonu oluşturma yanı sıra üç şey yapar <xref:System.ServiceModel.Activities.Send> ve <xref:System.ServiceModel.Activities.ReceiveReply> içindeki etkinlikleri bir <xref:System.Activities.Statements.Sequence> etkinlik:  
  
1.  Yapılandırır <xref:System.ServiceModel.Activities.Send.OperationName%2A>, <xref:System.ServiceModel.Activities.Send.ServiceContractName%2A> özelliklerini <xref:System.ServiceModel.Activities.Send> etkinlik.  
  
2.  Bağlar <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A> özelliği <xref:System.ServiceModel.Activities.ReceiveReply> etkinliğe <xref:System.ServiceModel.Activities.Send> etkinlik.  
  
3.  Oluşturur bir <xref:System.ServiceModel.Activities.CorrelationHandle> bir değişken üst etkinlik olarak.  
  
### <a name="using-the-sendandreceivereply-template-designer"></a>SendAndReceiveReply şablonu Tasarımcısı'nı kullanarak  
 **SendAndReceiveReply** etkinlik Tasarımcısı bulunabilir **ileti** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç kutusu**  sekmesi [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)  
  
 **SendAndReceiveReply** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir. Bu oluşturur bir <xref:System.ServiceModel.Activities.Send> ile yapılandırılmış etkinlik **Gönder** etkinlik Tasarımcısı ve bir ilişkili <xref:System.ServiceModel.Activities.ReceiveReply> ile yapılandırılabilir **ReceiveReplyForSend** Tasarımcısı.  
  
 [!INCLUDE[crabout](../test/includes/crabout_md.md)]kullanarak **Gönder** yapılandırmak için tasarımcı <xref:System.ServiceModel.Activities.Send> etkinliği bkz [Gönder](../workflow-designer/send-activity-designer.md) konu.  
  
 [!INCLUDE[crabout](../test/includes/crabout_md.md)]kullanarak **ReceiveReplyForSend** yapılandırmak için tasarımcı <xref:System.ServiceModel.Activities.ReceiveReply> etkinlik, aşağıdaki bölüme bakın.  
  
### <a name="properties-of-receivereply"></a>ReceiveReply özellikleri  
 Aşağıdaki tabloda <xref:System.ServiceModel.Activities.ReceiveReply> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellikleri kılavuzunda düzenlenebilir ve bazı üzerinde düzenlenebilir [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]Tasarımcı yüzeyine.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adını <xref:System.ServiceModel.Activities.ReceiveReply> etkinlik. ReceiveReplyForSend varsayılandır.<br /><br /> Ancak kolay için varsayılan olmayan bir değer kullanımını <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil gibi bir değer kullanmak için en iyi bir uygulamadır.|  
|<xref:System.ServiceModel.Activities.ReceiveReply.Request%2A>|Doğru|Başvuru <xref:System.ServiceModel.Activities.Send> etkinlik bu ile eşleştirilmiş <xref:System.ServiceModel.Activities.ReceiveReply> etkinlik. Bu özellik olmamalıdır **null**. <xref:System.ServiceModel.Activities.Send>ve <xref:System.ServiceModel.Activities.ReceiveReply> etkinlikleri birlikte istemcide bir istek/yanıt Mesajlaşma düzeni modellemek için kullanılır. Bu özellik belirten <xref:System.ServiceModel.Activities.Send> etkinlik eşleştirilmiş. Tasarımcıda için otomatik olarak bağlı olduğundan, bu özellik düzenlenemiyor <xref:System.ServiceModel.Activities.Send> , oluşturulduğu etkinlik <xref:System.ServiceModel.Activities.ReceiveReply> etkinlik.|  
|<xref:System.ServiceModel.Activities.ReceiveReply.Content%2A>|False|Almak için ileti veya parametre içeriğini belirtir. Ya da olabilir bir <xref:System.ServiceModel.Activities.ReceiveMessageContent> etkinlik veya <xref:System.ServiceModel.Activities.ReceiveParametersContent> etkinlik. Bu özelliğin yanındaki üç nokta düğmesine tıklayarak Düzenle **içerik** özellik kılavuzu veya tıklatarak alanındaki **tanımla...**  yanındaki düğmesini **içerik** üzerinde etiket **alma** etkinlik Tasarımcı yüzeyine. Her ikisi de görüntülemek **içerik tanımı** iletişim. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Bu kutu kullanma hakkında [içerik tanımı iletişim kutusunu](../workflow-designer/content-definition-dialog-box.md) konu.|  
|<xref:System.ServiceModel.Activities.ReceiveReply.CorrelationInitializers%2A>|False|Koleksiyonunu belirtir <xref:System.ServiceModel.Activities.CorrelationInitializer> birden çok başlatma nesneleri <xref:System.ServiceModel.Activities.CorrelationHandle> bu yapılandırma nesneleri <xref:System.ServiceModel.Activities.Receive> akışındaki etkinlikler. Yanındaki üç nokta düğmesini tıklayın <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> özelliğini açmak için özellikler kılavuzunda **eklemek bağıntı başlatıcıları** iletişim kutusu. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Bu kutusunu kullanarak bkz [CorrelationInitializers iletişim kutusunu](../workflow-designer/add-correlationinitializers-dialog-box.md) konu.|  
|<xref:System.ServiceModel.Activities.ReceiveReply.Action%2A>|False|İletinin eylem üstbilgisini belirtir. Açıkça ayarlanmazsa değerini varsayılan olarak:<br /><br /> **https://tempuri.org/ {hizmet sözleşmesi ad} / {hizmet sözleşmesi adı} / {işlem adı}.**|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)   
 [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)   
 [Alma](../workflow-designer/receive-activity-designer.md)   
 [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)   
 [Gönder](../workflow-designer/send-activity-designer.md)   
 [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)