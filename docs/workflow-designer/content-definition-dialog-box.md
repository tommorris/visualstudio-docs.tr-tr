---
title: İçerik tanımı iletişim kutusunu | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MessageContent.UI
ms.assetid: 7e4237c3-90a1-4149-bd8a-3643d1dde0df
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5b8d79c26413313bc94008d2d221b3ad33f4f334
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="content-definition-dialog-box"></a>İçerik tanımı iletişim kutusu
**İçerik tanımı** iletişim kutusu Windows iş akışı Tasarımcısı'nda yapılandırmak için kullanılan **içerik** özelliklerini <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, ve <xref:System.ServiceModel.Activities.ReceiveReply> etkinlikler. Bu kutuyu etkinlik tasarımcıları hakkında daha fazla bilgi için bkz: [Gönder](../workflow-designer/send-activity-designer.md), [alma](../workflow-designer/receive-activity-designer.md), [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md), ve [SendAndReceiveReply ](../workflow-designer/sendandreceivereply-template-designer.md) Konular.

 Kullanıcı Arabirimi (UI) öğelerini aşağıdaki tabloda açıklanmaktadır **başlatma bağıntı** iletişim kutusu.

|Arabirim Öğesi|Açıklama|
|----------------|-----------------|
|**İleti**|İletinin ile içerik belirtir **ileti veri** ifade metin kutusu ve kullanarak türü **ileti türü** aşağı açılan liste kutusu. Varsayılan olarak, **içerik tanımı** kullanan <xref:System.ServiceModel.Activities.ReceiveMessageContent>, hangi bekliyor bir <xref:System.ServiceModel.Channels.Message> veya sözleşme türü iş akışı hizmeti tanımı içinde bir ileti.|
|**Parametreler**|Tıklatın **parametreleri** kullanmak için radyo düğmesini <xref:System.ServiceModel.Activities.ReceiveParametersContent>, bir veri sözleşmesi bekliyor. Veri Kılavuzu Genel koleksiyonu ayarlamak için kullanın <xref:System.Activities.OutArgument> anahtar/değer çiftleri değerleri, geçerli iş akışı değişken parametreleri atanır.|

 **İçerik tanımı** iletişim kutusu tarafından kullanılan **Gönder**, **alma**, **ReceiveAndSendReply**, ve  **SendAndReceiveReply** tasarımcıları. Her durumda bunları erişme benzer ve alma durumda burada yordamı göstermek için kullanılır.

 **Alma** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir. Bu oluşturur bir <xref:System.ServiceModel.Activities.Receive> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> alma. Seçin **alma** etkinlik Tasarımcısı ve üç nokta düğmesini (içerik) metnini yanındaki tıklatın **içerik** özellik için özellik kılavuzunda **içerik tanımı**iletişim kutusu görünür.

 İçerik içinde belirtilen **ileti** bölümünde bir <xref:System.ServiceModel.Activities.ReceiveMessageContent> etkinlik veya içinde **parametresi** bölümünde bir <xref:System.ServiceModel.Activities.ReceiveParametersContent> etkinlik.

## <a name="see-also"></a>Ayrıca bkz.

- [İş Akışı Tasarımcısı Kullanıcı Arabirimi Yardımı](../workflow-designer/workflow-designer-ui-help.md)