---
title: "İçerik tanımı iletişim kutusunu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: MessageContent.UI
ms.assetid: 7e4237c3-90a1-4149-bd8a-3643d1dde0df
caps.latest.revision: "3"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: fa0276e284f84eb6514fc407c9ce9be9cf24d8c4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="content-definition-dialog-box"></a>İçerik tanımı iletişim kutusu
**İçerik tanımı** iletişim kutusu kullanılıyor [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] yapılandırmak için **içerik** özelliklerini <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, ve <xref:System.ServiceModel.Activities.ReceiveReply> etkinlikler. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Bu kutuyu etkinlik tasarımcıları bkz [Gönder](../workflow-designer/send-activity-designer.md), [alma](../workflow-designer/receive-activity-designer.md), [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md), ve [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md) Konular.  
  
 Kullanıcı Arabirimi (UI) öğelerini aşağıdaki tabloda açıklanmaktadır **başlatma bağıntı** iletişim kutusu.  
  
|Arabirim Öğesi|Açıklama|  
|----------------|-----------------|  
|**İleti**|İletinin ile içerik belirtir **ileti veri** ifade metin kutusu ve kullanarak türü **ileti türü** aşağı açılan liste kutusu. Varsayılan olarak, **içerik tanımı** kullanan <xref:System.ServiceModel.Activities.ReceiveMessageContent>, hangi bekliyor bir <xref:System.ServiceModel.Channels.Message> veya sözleşme türü iş akışı hizmeti tanımı içinde bir ileti.|  
|**Parametreleri**|Tıklatın **parametreleri** kullanmak için radyo düğmesini <xref:System.ServiceModel.Activities.ReceiveParametersContent>, bir veri sözleşmesi bekliyor. Veri Kılavuzu Genel koleksiyonu ayarlamak için kullanın <xref:System.Activities.OutArgument> anahtar/değer çiftleri değerleri, geçerli iş akışı değişken parametreleri atanır.|  
  
 **İçerik tanımı** iletişim kutusu tarafından kullanılan **Gönder**, **alma**, **ReceiveAndSendReply**, ve  **SendAndReceiveReply** tasarımcıları. Her durumda bunları erişme benzer ve alma durumda burada yordamı göstermek için kullanılır.  
  
 **Alma** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir. Bu oluşturur bir <xref:System.ServiceModel.Activities.Receive> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> alma. Seçin **alma** etkinlik Tasarımcısı ve üç nokta düğmesini (içerik) metnini yanındaki tıklatın **içerik** özellik için özellik kılavuzunda **içerik tanımı**iletişim kutusu görünür.  
  
 İçerik içinde belirtilen **ileti** bölümünde bir <xref:System.ServiceModel.Activities.ReceiveMessageContent> etkinlik veya içinde **parametresi** bölümünde bir <xref:System.ServiceModel.Activities.ReceiveParametersContent> etkinlik.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş Akışı Tasarımcısı kullanıcı Arabirimi Yardım](../workflow-designer/workflow-designer-ui-help.md)