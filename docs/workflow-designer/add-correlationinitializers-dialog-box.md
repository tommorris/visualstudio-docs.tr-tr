---
title: "CorrelationInitializers iletişim kutusu ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- AddCorrelationInitializers.UI
ms.assetid: c0517467-d54a-4ee6-aef0-c19b96b6f395
caps.latest.revision: 
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload:
- multiple
ms.openlocfilehash: 4c4d8e07aa172aef524b4d85bda5ad8efdfb509f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="add-correlationinitializers-dialog-box"></a>Ekle CorrelationInitializers iletişim kutusu
**Eklemek bağıntı başlatıcıları** iletişim kutusu kullanılıyor [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] yapılandırmak için **CorrelationInitializers** özelliklerini <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, ve <xref:System.ServiceModel.Activities.ReceiveReply> etkinlikler. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Bu kutuyu etkinlik tasarımcıları bkz [Gönder](../workflow-designer/send-activity-designer.md), [alma](../workflow-designer/receive-activity-designer.md), [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md), ve [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md) Konular.  
  
 Bu iletişim kutusundaki belirlenmiş koleksiyonunda bağıntı başlatıcıları sorgu tabanlı başlatabilir bağlamı, geri çağırma bağlamı veya istek-yanıt bağıntıları Mesajlaşma etkinlikleri arasındaki.  
  
 Kullanıcı Arabirimi (UI) öğelerini aşağıdaki tabloda açıklanmaktadır **eklemek bağıntı başlatıcıları** iletişim kutusu.  
  
|Arabirim Öğesi|Açıklama|  
|----------------|-----------------|  
|**Başlatıcı ekleme**|Tıklatın **Ekle Initialize** kutusunu ek bir başlatıcı koleksiyona eklemek için.|  
|**Bağıntı türü**|Bağıntı başlatıcı türünü belirtir. Aralarından seçim yapabileceğiniz dört tür vardır:<br /><br /> 1.  Belirtmek için bir geri çağırma bağıntı başlatıcı bir <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer>.<br />2.  Belirtmek için bir bağlam bağıntı başlatıcı bir <xref:System.ServiceModel.Activities.CorrelationInitializer>.<br />3.  Belirtmek için bir istek-yanıt bağıntısı Başlatıcı bir <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>.<br />4.  Belirtmek için bir sorgu bağıntı başlatıcı bir <xref:System.ServiceModel.Activities.QueryCorrelationInitializer>.<br /><br /> Düzenlenecek **CorrelationType**<br /><br /> 1.  Belirli satırda sekmesine **eklemek Başlatıcı** DataGrid.<br />2.  Odak ayarlamak için CTRL + SEKME tuşuna basın **CorrelationTypeComboBox**<br />3.  Pop için alt + aşağı ok tuşlarına basın **ComboBox** ve düzenleyin.|  
|**XPath sorguları**|Gelen ve giden iletilerden bağıntı veri ayıklamak için kullanılan sorgu içeren bir anahtar/değer çifti. Bu liste yalnızca geçerli kullanıldığında <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> türleri.|  
  
## <a name="to-launch-the-add-correlation-initializers-dialog-box"></a>Bağıntı başlatıcıları Ekle iletişim kutusunu başlatmak için  
 **Eklemek bağıntı başlatıcıları** iletişim kutusu tarafından kullanılan **Gönder**, **alma**, **ReceiveAndSendReply**, ve  **SendAndReceiveReply** tasarımcıları. Erişmesini benzer her durumda ve içerir durumda **alma** Tasarımcısı kullanıldığı burada yordamı göstermek için.  
  
 **Alma** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir. Bu oluşturur bir <xref:System.ServiceModel.Activities.Receive> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> alma. Seçin **alma** etkinlik Tasarımcısı ve üç nokta düğmesini (toplama) metnini yanındaki tıklatın **CorrelationInitializers** özellik için özellik kılavuzunda **Ekle Bağıntı başlatıcıları** iletişim kutusu görünür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağıntı iletişim kutusu ekleme](http://msdn.microsoft.com/en-us/9e41a149-e8ab-41b1-8886-ea06a63041b6)   
 [Bağıntıyı Başlat İletişim Kutusu](../workflow-designer/initialize-correlation-dialog-box.md)