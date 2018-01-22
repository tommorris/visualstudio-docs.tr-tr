---
title: "Eski iş akışı etkinlikleri | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- workflows, activities
- activities
- workflow activities
ms.assetid: 4af7a06b-1e82-43c8-aec8-0dc5fb63d08a
caps.latest.revision: "8"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: ae0cef2943abffe947c179f9cfcd6c2223931337
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2018
---
# <a name="legacy-workflow-activities"></a>Eski iş akışı etkinlikleri
[!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]Varsayılan bir işlevsellik denetim akışı, koşullar, olay işleme, durum yönetimi ve iletişim için uygulamaları ve hizmetleri sağlamak etkinlikleri içerir. İş akışları tasarlarken tarafından sağlanan sistem tarafından sağlanan etkinlikler kullanabilirsiniz [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)], veya kendi özel etkinlikler oluşturabilirsiniz.  
  
 Aşağıdaki tabloda [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)] framework out-of-box etkinlik kümesi. Birçok, ancak tüm, bu etkinliklerini erişilebilen etkinlik tasarımcıları tarafından temsil edilen **araç** , [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]. Bir etkinlik oluşturmak için kendi Tasarımcısından sürükleyin **araç** ve tasarım yüzeyine bırakın.  
  
|Etkinlik|Açıklama|  
|--------------|-----------------|  
|<xref:System.Workflow.Activities.CallExternalMethodActivity>|İle kullanılan **HandleExternalEventActivity** etkinlik giriş ve çıkış yerel bir hizmet ile iletişim için. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak CallExternalMethodActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65060).|  
|**System.Workflow.Activities.CancellationHandlerActivity**|Tüm bileşik etkinliğin alt tamamlanmış önce iptal bileşik bir etkinlik için temizleme mantığı kapsamak için kullanılmış yürütülüyor. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak CancellationHandlerActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65061).|  
|<xref:System.Workflow.Activities.CodeActivity>|Visual Basic veya C# kod akışınıza eklemenize olanak tanır. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak CodeActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65062).|  
|<xref:System.Workflow.Activities.CompensatableSequenceActivity>|Bir üst öğesi dengelenebilir sürümü <xref:System.Workflow.Activities.SequenceActivity>. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak CompensatableSequenceActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65002).|  
|**System.Workflow.Activities.CompensatableTransactionScopeActivity**|Bir üst öğesi dengelenebilir sürümü **TransactionScopeActivity**. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak CompensatableTransactionScopeActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65063).|  
|**System.Workflow.Activities.CompensateActivity**|Geri almak için veya bir hata oluştuğunda zaten iş akışı tarafından gerçekleştirilen işlemler için dengelemek için kodunu çağırmasını sağlar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak CompensateActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65064).|  
|**System.Workflow.Activities.CompensationHandlerActivity**|Tamamlanan TransactionScopeActivity etkinliğinin maaş gerçekleştiren bir veya daha fazla etkinlik için sarmalayıcı [!INCLUDE[crdefault](../test/includes/crdefault_md.md)] [kullanarak CompensationHandlerActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65065).|  
|<xref:System.Workflow.Activities.ConditionedActivityGroup>|Geçerli bir koşula göre alt etkinlikleri yürütür <xref:System.Workflow.Activities.ConditionedActivityGroup> etkinlik kendisi ve ayrı ayrı her bir alt uygulama koşullara bağlı. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][ConditionedActivityGroup etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65066).|  
|<xref:System.Workflow.Activities.DelayActivity>|Bir zaman aşımı aralığına dayalı gecikmeler iş akışınızda oluşturmanıza olanak sağlar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak EventDrivenActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65067).|  
|<xref:System.Workflow.Activities.EventDrivenActivity>|Belirtilen bir olay oluştuğunda yürütülen bir veya daha fazla etkinlikleri sarmalar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak EventDrivenActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65068).|  
|<xref:System.Workflow.Activities.EventHandlersActivity>|Bir etkinlik olayları ilişkilendirme için bir çerçeve sağlar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak EventHandlersActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65069).|  
|<xref:System.Workflow.Activities.EventHandlingScopeActivity>|Kendi ana alt etkinlikle concurrently yürüten bir <xref:System.Workflow.Activities.EventHandlersActivity>. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak EventHandlingScopeActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65070).|  
|**System.Workflow.Activities.FaultHandlerActivity**|Belirttiğiniz bir türünde bir özel durum işleme için kullanılır. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak FaultHandlerActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65071).|  
|**System.Workflow.Activities.FaultHandlersActivity**|Alt etkinlikler türü sıralı bir listesi vardır bileşik bir etkinlik temsil eden **System.Workflow.Activities.FaultHandlerActivity**. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak FaultHandlersActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65072).|  
|<xref:System.Workflow.Activities.HandleExternalEventActivity>|İle birlikte kullanılan <xref:System.Workflow.Activities.CallExternalMethodActivity> etkinlik giriş ve çıkış yerel bir hizmet ile iletişim için. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak HandleExternalEventActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65073).|  
|<xref:System.Workflow.Activities.IfElseActivity>|Her dal bir koşulu sınar ve etkinlikler için eşittir koşulu ilk dalda gerçekleştirir **doğru**. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][IfElseActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65074).|  
|<xref:System.Workflow.Activities.IfElseBranchActivity>|Bir dalı temsil eden bir <xref:System.Workflow.Activities.IfElseActivity>. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Öğeye etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65075).|  
|<xref:System.Workflow.Activities.InvokeWebServiceActivity>|Bir Web hizmetini çağırmak, iş akışınızı sağlar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak InvokeWebServiceActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65076).|  
|<xref:System.Workflow.Activities.InvokeWorkflowActivity>|Başka bir iş akışının çağırmak, iş akışınızı sağlar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak InvokeWorkflowActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65077).|  
|<xref:System.Workflow.Activities.ListenActivity>|Yalnızca içeren bileşik bir etkinlik <xref:System.Workflow.Activities.EventDrivenActivity> alt etkinlikler. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak ListenActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65078).|  
|<xref:System.Workflow.Activities.ParallelActivity>|İki veya daha fazla alt zamanlamak için bir yol sağlar **öğeler SequenceActivity** etkinlik dalları aynı anda işleme. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak ParallelActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65079).|  
|<xref:System.Workflow.Activities.PolicyActivity>|Kurallar topluluğu göstermek için kullanın. Bir kural koşulları ve sonuçta elde edilen Eylemler oluşur. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak PolicyActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65004).|  
|<xref:System.Workflow.Activities.ReplicatorActivity>|Tek alt etkinliği birden çok örneğini oluşturur. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak ReplicatorActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65080).|  
|<xref:System.Workflow.Activities.SequenceActivity>|Sıralı yürütme bir araya toplamak için birden çok etkinliği bağlamak için basit bir yol sağlar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Öğeler SequenceActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65081).|  
|<xref:System.Workflow.Activities.SetStateActivity>|Yeni bir durum geçiş belirtir. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak SetStateActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65082).|  
|<xref:System.Workflow.Activities.StateActivity>|Bir iş akışındaki durumu makine durumunu temsil eder. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Buraya StateActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65083).|  
|<xref:System.Workflow.Activities.StateFinalizationActivity>|Kullanılan bir <xref:System.Workflow.Activities.StateActivity> etkinlik ayrılırken yürütülen alt etkinlikler için kapsayıcı olarak **buraya StateActivity** etkinlik. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak StateFinalizationActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65008).|  
|<xref:System.Workflow.Activities.StateInitializationActivity>|Kullanılan bir <xref:System.Workflow.Activities.StateActivity> etkinlik girerken yürütülen alt etkinlikler için kapsayıcı olarak **buraya StateActivity** etkinlik. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak StateInitializationActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65006).|  
|**System.Workflow.Activities.SuspendActivity**|Özel dikkat gerektiren bazı hata koşulu durumunda araya etkinleştirmek için iş akışı işlemi askıya alır. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak SuspendActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65084).|  
|**System.Workflow.Activities.SynchronizationScopeActivity**|İçerilen etkinlikleri eşitlenmiş bir etki alanında sıralı olarak yürütür. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak SynchronizationScopeActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65085).|  
|**System.Workflow.Activities.TerminateActivity**|İş akışınızı işlemi bir hata koşulu durumunda derhal sona olanak tanır. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak TerminateActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65086).|  
|**System.Workflow.Activities.ThrowActivity**|İşlem meta verilerinin bir iş akışının bir parçası olarak oluşturulan iş özel durumları yakalamanıza olanak sağlar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak ThrowActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65087).|  
|**System.Workflow.Activities.TransactionScopeActivity**|İşlemler ve özel durum işleme için bir çerçeve sağlar. Daha fazla bilgi için bkz: [TransactionScopeActivity etkinliğinin kullanarak](http://go.microsoft.com/fwlink?LinkID=65088).|  
|<xref:System.Workflow.Activities.WebServiceFaultActivity>|Bir Web hizmeti hata oluşması modeli sağlar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][WebServiceFaultActivity etkinliği kullanarak](http://go.microsoft.com/fwlink?LinkID=65089).|  
|<xref:System.Workflow.Activities.WebServiceInputActivity>|Bir Web hizmetinden veri alır. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak WebServiceInputActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65090).|  
|<xref:System.Workflow.Activities.WebServiceOutputActivity>|Bir iş akışı için yapılan bir Web hizmeti isteğine yanıt verir. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][WebServiceOutputActivity etkinliği kullanarak](http://go.microsoft.com/fwlink?LinkID=65092).|  
|<xref:System.Workflow.Activities.WhileActivity>|Bir koşul yerine getirilene kadar döngü için iş akışınıza sağlar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak WhileActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65091).|  
  
 [!INCLUDE[crabout](../test/includes/crabout_md.md)]özel etkinlikler oluşturmak için bkz: nasıl [geliştirme özel etkinlikler](http://go.microsoft.com/fwlink?LinkID=65023) ve [eski etkinlik Tasarımcısı'nı kullanarak](../workflow-designer/using-the-legacy-activity-designer.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Etkinlik Görünümleri (Eski)](../workflow-designer/activity-views-legacy.md)  
 Etkinlikler farklı tasarım görünümlerini açıklar.  
  
 [Nasıl Yapılır: Araç Kutusuna Etkinlik Ekleme (Eski)](../workflow-designer/how-to-add-activities-to-the-toolbox-legacy.md)  
 Araç Kutusu'na etkinlik ekleme gösterir.  
  
 [Nasıl Yapılır: Bildirime Dayanan Kural Koşulu Oluşturma (Eski)](../workflow-designer/how-to-create-a-declarative-rule-condition-legacy.md)  
 Bir bildirim temelli Kural koşulu oluşturmak için aşağıdaki adımları gösterir.  
  
 [Nasıl Yapılır: PolicyActivity Kural Kümesi Oluşturma (Eski)](../workflow-designer/how-to-create-a-policyactivity-rule-set-legacy.md)  
 Bir PolicyActivity kural kümesi oluşturmak için aşağıdaki adımları gösterir.  
  
 [Nasıl yapılır: uygulama bir WCF sözleşmesi işlemi (eski)](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md)  
 Uygulanacak adımlar gösterilmektedir bir [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] sözleşme işlemi.  
  
 [Nasıl yapılır: bir WCF sözleşmesi işlemi (eski) çağırma](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md)  
 Çağrılacak adımlar gösterilmektedir bir [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] sözleşme işlemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Workflow Foundation etkinlikleri](http://go.microsoft.com/fwlink?LinkID=65005)   
 [İş akışları geliştirme](http://go.microsoft.com/fwlink?LinkID=65010)   
 [İş akışı etkinliklerini geliştirme](http://go.microsoft.com/fwlink?LinkID=65023)