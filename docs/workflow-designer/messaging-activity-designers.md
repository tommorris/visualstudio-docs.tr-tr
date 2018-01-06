---
title: "Etkinlik tasarımcıları Mesajlaşma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 897e63cf-a42f-4edd-876f-c4ccfffaf6d6
caps.latest.revision: "7"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 481d9e577989b1bd75cea22e0faab6d8a1cc64cf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="messaging-activity-designers"></a>Etkinlik tasarımcıları Mesajlaşma
İleti etkinlik tasarımcıları oluşturmak ve göndermek ve almak Mesajlaşma etkinlikleri yapılandırmak için kullanılan [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] iletileri içinden bir [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] uygulama. [!INCLUDE[netfx40_long](../workflow-designer/includes/netfx40_long_md.md)] Beş Mesajlaşma etkinlikleri tanıtır ve [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] bir iş akışı içinde ileti yönetmenizi sağlayan iki yeni Şablon tasarımcıları sağlar. Bu bölümde yer alan ve aşağıdaki tabloda listelenen konular nasıl kullanılacağı hakkında kılavuzluk [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] etkinliği ve Şablon tasarımcıları.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
|İleti etkinliği|Açıklama|  
|----------------------|-----------------|  
|[CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)|Oluşturur ve yapılandırır bir <xref:System.ServiceModel.Activities.CorrelationScope> etkinliklerle Mesajlaşma alt örtük Yönetimi sağlayan etkinlik bir <xref:System.ServiceModel.Activities.CorrelationHandle> nesnesi.|  
|[InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)|Oluşturur ve yapılandırır bir <xref:System.ServiceModel.Activities.InitializeCorrelation> bağıntı gönderme veya bir ileti alma olmadan başlatmak için kullanılan etkinlik.|  
|[Alma](../workflow-designer/receive-activity-designer.md)|Oluşturur ve yapılandırır bir <xref:System.ServiceModel.Activities.Receive> bir hizmetinden bir ileti alır etkinlik.|  
|[ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)|Önceden yapılandırılmış bir çift oluşturur <xref:System.ServiceModel.Activities.Send> ve <xref:System.ServiceModel.Activities.ReceiveReply> içindeki etkinlikleri bir <xref:System.Activities.Statements.Sequence> etkinlik.|  
|[Gönder](../workflow-designer/send-activity-designer.md)|Oluşturur ve yapılandırır bir <xref:System.ServiceModel.Activities.Send> bir hizmete bir ileti gönderir etkinlik.|  
|[SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)|Önceden yapılandırılmış bir çift oluşturur <xref:System.ServiceModel.Activities.Receive> ve <xref:System.ServiceModel.Activities.SendReply> içindeki etkinlikleri bir <xref:System.Activities.Statements.Sequence> etkinlik.|  
|[TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)|Oluşturur ve yapılandırır bir <xref:System.ServiceModel.Activities.TransactedReceiveScope> bir iş akışı işlemleri akışını sağlayan etkinlik.|  
  
## <a name="reference"></a>Başvuru  
 <xref:System.Activities.Activity>  
  
 <xref:System.ServiceModel.Activities.CorrelationScope>  
  
 <xref:System.ServiceModel.Activities.Receive>  
  
 <xref:System.ServiceModel.Activities.Send>  
  
 <xref:System.ServiceModel.Activities.ReceiveReply>  
  
 <xref:System.ServiceModel.Activities.SendReply>  
  
 <xref:System.ServiceModel.Activities.TransactedReceiveScope>  
  
## <a name="related-sections"></a>İlgili Bölümler  
 Etkinlik tasarımcıları diğer türleri için aşağıdaki konulara bakın.  
  
 [Denetim Akışı](../workflow-designer/control-flow-activity-designers.md)  
  
 [Etkinlik Tasarımcılarını kullanma](../workflow-designer/using-the-activity-designers.md)  
  
 [Akış Çizelgesi](../workflow-designer/flowchart-activity-designers.md)  
  
 [Çalışma Zamanı](../workflow-designer/runtime-activity-designers.md)  
  
 [Temel Türler](../workflow-designer/primitives-activity-designers.md)  
  
 [İşlem](../workflow-designer/transaction-activity-designers.md)  
  
 [Koleksiyon](../workflow-designer/collection-activity-designers.md)  
  
 [Hata İşleme](../workflow-designer/error-handling-activity-designers.md)  
  
## <a name="external-resources"></a>Dış Kaynaklar  
 [Etkinlik Tasarımcılarını kullanma](../workflow-designer/using-the-activity-designers.md)