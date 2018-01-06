---
title: "Eski iş akışı etkinlikleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
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
ms.openlocfilehash: 756fa86cf892120b0062e2816f146425ac1b4fa3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="legacy-workflow-activities"></a>Eski iş akışı etkinlikleri
[!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]Varsayılan bir işlevsellik denetim akışı, koşullar, olay işleme, durum yönetimi ve iletişim için uygulamaları ve hizmetleri sağlamak etkinlikleri içerir. İş akışları tasarlarken tarafından sağlanan sistem tarafından sağlanan etkinlikler kullanabilirsiniz [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)], veya kendi özel etkinlikler oluşturabilirsiniz.  
  
 Aşağıdaki tabloda [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)] framework out-of-box etkinlik kümesi. Birçok, ancak tüm, bu etkinliklerini erişilebilen etkinlik tasarımcıları tarafından temsil edilen **araç** , [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]. Bir etkinlik oluşturmak için kendi Tasarımcısından sürükleyin **araç** ve tasarım yüzeyine bırakın.  
  
|Etkinlik|Açıklama|  
|--------------|-----------------|  
|[CallExternalMethodActivity](http://go.microsoft.com/fwlink?LinkID=65025)|İle kullanılan **HandleExternalEventActivity** etkinlik giriş ve çıkış yerel bir hizmet ile iletişim için. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak CallExternalMethodActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65060).|  
|[CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050)|Tüm bileşik etkinliğin alt tamamlanmış önce iptal bileşik bir etkinlik için temizleme mantığı kapsamak için kullanılmış yürütülüyor. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak CancellationHandlerActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65061).|  
|[CodeActivity](http://go.microsoft.com/fwlink?LinkID=65026)|Visual Basic veya C# kod akışınıza eklemenize olanak tanır. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak CodeActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65062).|  
|[CompensatableSequenceActivity](http://go.microsoft.com/fwlink?LinkID=65027)|Bir üst öğesi dengelenebilir sürümü [öğeler SequenceActivity](http://go.microsoft.com/fwlink?LinkID=65020). [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak CompensatableSequenceActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65002).|  
|[CompensatableTransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65051)|Bir üst öğesi dengelenebilir sürümü **TransactionScopeActivity**. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak CompensatableTransactionScopeActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65063).|  
|[CompensateActivity](http://go.microsoft.com/fwlink?LinkID=65052)|Geri almak için veya bir hata oluştuğunda zaten iş akışı tarafından gerçekleştirilen işlemler için dengelemek için kodunu çağırmasını sağlar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak CompensateActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65064).|  
|[CompensationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65053)|Tamamlanan TransactionScopeActivity etkinliğinin maaş gerçekleştiren bir veya daha fazla etkinlik için sarmalayıcı [!INCLUDE[crdefault](../test/includes/crdefault_md.md)] [kullanarak CompensationHandlerActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65065).|  
|[ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)|Geçerli bir koşula göre alt etkinlikleri yürütür [ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017) etkinlik kendisi ve ayrı ayrı her bir alt uygulama koşullara bağlı. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][ConditionedActivityGroup etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65066).|  
|[EventDrivenActivity](http://go.microsoft.com/fwlink?LinkID=65028)|Bir zaman aşımı aralığına dayalı gecikmeler iş akışınızda oluşturmanıza olanak sağlar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak EventDrivenActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65067).|  
|[EventDrivenActivity](http://go.microsoft.com/fwlink?LinkID=65029)|Belirtilen bir olay oluştuğunda yürütülen bir veya daha fazla etkinlikleri sarmalar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak EventDrivenActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65068).|  
|[EventHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65018)|Bir etkinlik olayları ilişkilendirme için bir çerçeve sağlar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak EventHandlersActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65069).|  
|[EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030)|Kendi ana alt etkinlikle concurrently yürüten bir [EventHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65018). [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak EventHandlingScopeActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65070).|  
|[FaultHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65054)|Belirttiğiniz bir türünde bir özel durum işleme için kullanılır. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak FaultHandlerActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65071).|  
|[FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055)|Alt etkinlikler türü sıralı bir listesi vardır bileşik bir etkinlik temsil eden [FaultHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65054). [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak FaultHandlersActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65072).|  
|[HandleExternalEventActivity](http://go.microsoft.com/fwlink?LinkID=65031)|İle birlikte kullanılan [CallExternalMethodActivity](http://go.microsoft.com/fwlink?LinkID=65025) etkinlik giriş ve çıkış yerel bir hizmet ile iletişim için. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak HandleExternalEventActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65073).|  
|[IfElseActivity](http://go.microsoft.com/fwlink?LinkID=65033)|Her dal bir koşulu sınar ve etkinlikler için eşittir koşulu ilk dalda gerçekleştirir **doğru**. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][IfElseActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65074).|  
|[Öğeye](http://go.microsoft.com/fwlink?LinkID=65034)|Bir dalı temsil eden bir [IfElseActivity](http://go.microsoft.com/fwlink?LinkID=65033). [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Öğeye etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65075).|  
|[InvokeWebServiceActivity](http://go.microsoft.com/fwlink?LinkID=65035)|Bir Web hizmetini çağırmak, iş akışınızı sağlar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak InvokeWebServiceActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65076).|  
|[InvokeWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65036)|Başka bir iş akışının çağırmak, iş akışınızı sağlar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak InvokeWorkflowActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65077).|  
|[ListenActivity](http://go.microsoft.com/fwlink?LinkID=65037)|Yalnızca içeren bileşik bir etkinlik [EventDrivenActivity](http://go.microsoft.com/fwlink?LinkID=65029) alt etkinlikler. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak ListenActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65078).|  
|[ParallelActivity](http://go.microsoft.com/fwlink?LinkID=65038)|İki veya daha fazla alt zamanlamak için bir yol sağlar **öğeler SequenceActivity** etkinlik dalları aynı anda işleme. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak ParallelActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65079).|  
|[PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019)|Kurallar topluluğu göstermek için kullanın. Bir kural koşulları ve sonuçta elde edilen Eylemler oluşur. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak PolicyActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65004).|  
|[ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)|Tek alt etkinliği birden çok örneğini oluşturur. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak ReplicatorActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65080).|  
|[Öğeler SequenceActivity](http://go.microsoft.com/fwlink?LinkID=65020)|Sıralı yürütme bir araya toplamak için birden çok etkinliği bağlamak için basit bir yol sağlar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Öğeler SequenceActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65081).|  
|[SetStateActivity](http://go.microsoft.com/fwlink?LinkID=65041)|Yeni bir durum geçiş belirtir. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak SetStateActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65082).|  
|[Buraya StateActivity](http://go.microsoft.com/fwlink?LinkID=65042)|Bir iş akışındaki durumu makine durumunu temsil eder. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Buraya StateActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65083).|  
|[StateFinalizationActivity](http://go.microsoft.com/fwlink?LinkID=65043)|Kullanılan bir [buraya StateActivity](http://go.microsoft.com/fwlink?LinkID=65042) etkinlik ayrılırken yürütülen alt etkinlikler için kapsayıcı olarak **buraya StateActivity** etkinlik. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak StateFinalizationActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65008).|  
|[StateInitializationActivity](http://go.microsoft.com/fwlink?LinkID=65044)|Kullanılan bir [buraya StateActivity](http://go.microsoft.com/fwlink?LinkID=65042) etkinlik girerken yürütülen alt etkinlikler için kapsayıcı olarak **buraya StateActivity** etkinlik. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak StateInitializationActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65006).|  
|[SuspendActivity](http://go.microsoft.com/fwlink?LinkID=65056)|Özel dikkat gerektiren bazı hata koşulu durumunda araya etkinleştirmek için iş akışı işlemi askıya alır. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak SuspendActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65084).|  
|[SynchronizationScopeActivity](http://go.microsoft.com/fwlink?LinkID=65057)|İçerilen etkinlikleri eşitlenmiş bir etki alanında sıralı olarak yürütür. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak SynchronizationScopeActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65085).|  
|[TerminateActivity](http://go.microsoft.com/fwlink?LinkID=65058)|İş akışınızı işlemi bir hata koşulu durumunda derhal sona olanak tanır. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak TerminateActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65086).|  
|[ThrowActivity](http://go.microsoft.com/fwlink?LinkID=65059)|İşlem meta verilerinin bir iş akışının bir parçası olarak oluşturulan iş özel durumları yakalamanıza olanak sağlar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak ThrowActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65087).|  
|[TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093)|İşlemler ve özel durum işleme için bir çerçeve sağlar. Daha fazla bilgi için bkz: [TransactionScopeActivity etkinliğinin kullanarak](http://go.microsoft.com/fwlink?LinkID=65088).|  
|[WebServiceFaultActivity](http://go.microsoft.com/fwlink?LinkID=65046)|Bir Web hizmeti hata oluşması modeli sağlar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][WebServiceFaultActivity etkinliği kullanarak](http://go.microsoft.com/fwlink?LinkID=65089).|  
|[WebServiceInputActivity](http://go.microsoft.com/fwlink?LinkID=65047)|Bir Web hizmetinden veri alır. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak WebServiceInputActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65090).|  
|[WebServiceOutputActivity](http://go.microsoft.com/fwlink?LinkID=65048)|Bir iş akışı için yapılan bir Web hizmeti isteğine yanıt verir. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][WebServiceOutputActivity etkinliği kullanarak](http://go.microsoft.com/fwlink?LinkID=65092).|  
|[WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)|Bir koşul yerine getirilene kadar döngü için iş akışınıza sağlar. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kullanarak WhileActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65091).|  
  
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