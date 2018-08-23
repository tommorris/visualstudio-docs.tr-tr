---
title: CorrelationScope etkinlik Tasarımcısı | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.CorrelationScope.UI
ms.assetid: 75f20664-9042-464d-8e2b-148d365a2286
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 61ce707f0a26a11d7e8c81899d5c2d65a7dc3f22
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42680941"
---
# <a name="correlationscope-activity-designer"></a>CorrelationScope Etkinlik Tasarımcısı
**CorrelationScope** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.ServiceModel.Activities.CorrelationScope> alt Mesajlaşma etkinlikleri kullanarak örtük yönetimini sağlayan etkinlik bir <xref:System.ServiceModel.Activities.CorrelationHandle> nesne.  
  
## <a name="the-correlationscope-activity"></a>CorrelationScope etkinlik  
 <xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A> Özellik belirtir <xref:System.ServiceModel.Activities.CorrelationHandle> alt Mesajlaşma etkinlikleri yönetmek için kullanılır. <xref:System.ServiceModel.Activities.Send> Ve <xref:System.ServiceModel.Activities.Receive> yer alan etkinlikleri <xref:System.ServiceModel.Activities.CorrelationScope.Body%2A> kullanmak üzere yapılandırılmış <xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A> içeren özellik <xref:System.ServiceModel.Activities.CorrelationScope> bağıntısı yapmak için etkinlik.  
  
### <a name="using-the-correlationscope-activity-designer"></a>CorrelationScope etkinlik Tasarımcısı kullanma  
 **CorrelationScope** etkinlik Tasarımcısı bulunabilir **Mesajlaşma** kategorisi **araç kutusu**, hangi erişilen tıklayarak **araçkutusu** sol tarafındaki sekmesinde [!INCLUDE[wfd2](../includes/wfd2-md.md)] (Alternatif olarak, seçin **araç** gelen **görünümü** menüsünü veya CTRL + ALT + X.)  
  
 **CorrelationScope** etkinlik Tasarımcısı, gelen sürüklenebilir **araç kutusu** ve oturum bırakılan [!INCLUDE[wfd2](../includes/wfd2-md.md)] yüzeyi. Bu, oluşturur bir <xref:System.ServiceModel.Activities.CorrelationScope> etkinliği ile bir varsayılan **DisplayName** CorrelationScope biri. <xref:System.Activities.Activity.DisplayName%2A> Üst bilgisinde düzenlenebilir **CorrelationScope** etkinlik Tasarımcısı veya **DisplayName** kutusunun **özellikleri** penceresi.  
  
 Belirtmek için <xref:System.ServiceModel.Activities.CorrelationHandle> Mesajlaşma etkinlikleriyle alt tarafından kullanılan, yanında bulunan üç nokta düğmesini tıklatın **CorrelatesWith** alanındaki **özellikleri** penceresini görüntülemek için **ifade Düzenleyicisi**  iletişim kutusu. Bu özellik, etkinlik Tasarımcı yüzeyinde de ayarlanabilir.  
  
 İçinde tasarımcılar bırakarak içinde bağıntı kapsamlı etkinlikleri belirtilen **gövdesi** içinde kutusunda **CorrelationScope** Tasarımcısı.  
  
### <a name="the-correlationscope-properties"></a>CorrelationScope özellikleri  
 Aşağıdaki tabloda <xref:System.ServiceModel.Activities.CorrelationScope> özellikleri Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikler olabilir ya da düzenlenebilir **özellikleri** penceresi veya [!INCLUDE[wfd2](../includes/wfd2-md.md)] Tasarımcı yüzeyi ve çoğunlukla her ikisinde de.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adı <xref:System.ServiceModel.Activities.InitializeCorrelation> etkinlik.|  
|<xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A>|False|Belirtir <xref:System.ServiceModel.Activities.CorrelationHandle> alt Mesajlaşma etkinlikleri yönetmek için kullanılır. Bu özelliği ayarlamazsanız <xref:System.ServiceModel.Activities.CorrelationScope> örtük oluşturur <xref:System.ServiceModel.Activities.CorrelationHandle> otomatik olarak.|  
|<xref:System.ServiceModel.Activities.CorrelationScope.Body%2A>|False|Bağıntı kapsamı içindeki belirtir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Initializecorrelation](../workflow-designer/initializecorrelation-activity-designer.md)   
 [Alma](../workflow-designer/receive-activity-designer.md)   
 [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)   
 [Gönder](../workflow-designer/send-activity-designer.md)   
 [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)   
 [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)