---
title: İş Akışı Tasarımcısı - eski iş akışı etkinlikleri
ms.date: 01/18/2017
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- workflows, activities
- activities
- workflow activities
ms.assetid: 4af7a06b-1e82-43c8-aec8-0dc5fb63d08a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 45c24c0be518e58ce87af11a38486818ca4a3ac7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31979483"
---
# <a name="legacy-workflow-activities"></a>Eski iş akışı etkinlikleri

Windows Workflow Foundation (WF) varsayılan bir işlevsellik denetim akışı, koşullar, olay işleme, durum yönetimi ve iletişim için uygulamaları ve hizmetleri sağlamak etkinlikleri içerir. İş akışları tasarlarken, Windows iş akışı tasarımcısı tarafından sağlanan sistem tarafından sağlanan etkinlikler kullanabilir veya kendi özel etkinlikler oluşturabilirsiniz.

Aşağıdaki tabloda, Windows Workflow Foundation framework out-of-box etkinlik kümesi listelenir. Birçok, ancak tüm, bu etkinliklerini erişilebilen etkinlik tasarımcıları tarafından temsil edilen **araç** iş akışı Tasarımcısı'nın. Bir etkinlik oluşturmak için kendi Tasarımcısından sürükleyin **araç** ve tasarım yüzeyine bırakın.

|Etkinlik|Açıklama|
|--------------|-----------------|
|<xref:System.Workflow.Activities.CallExternalMethodActivity>|İle kullanılan **HandleExternalEventActivity** etkinlik giriş ve çıkış yerel bir hizmet ile iletişim için. Daha fazla bilgi için bkz: [CallExternalMethodActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65060).|
|**System.Workflow.Activities.CancellationHandlerActivity**|Tüm bileşik etkinliğin alt tamamlanmış önce iptal bileşik bir etkinlik için temizleme mantığı kapsamak için kullanılmış yürütülüyor. Daha fazla bilgi için bkz: [kullanarak CancellationHandlerActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65061).|
|<xref:System.Workflow.Activities.CodeActivity>|Visual Basic veya C# kod akışınıza eklemenize olanak tanır. Daha fazla bilgi için bkz: [CodeActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65062).|
|<xref:System.Workflow.Activities.CompensatableSequenceActivity>|Bir üst öğesi dengelenebilir sürümü <xref:System.Workflow.Activities.SequenceActivity>. Daha fazla bilgi için bkz: [CompensatableSequenceActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65002).|
|**System.Workflow.Activities.CompensatableTransactionScopeActivity**|Bir üst öğesi dengelenebilir sürümü **TransactionScopeActivity**. Daha fazla bilgi için bkz: [CompensatableTransactionScopeActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65063).|
|**System.Workflow.Activities.CompensateActivity**|Geri almak için veya bir hata oluştuğunda zaten iş akışı tarafından gerçekleştirilen işlemler için dengelemek için kodunu çağırmasını sağlar. Daha fazla bilgi için bkz: [CompensateActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65064).|
|**System.Workflow.Activities.CompensationHandlerActivity**|Daha fazla bilgi için tamamlanmış bir TransactionScopeActivity etkinliğinin maaş gerçekleştiren bir veya daha fazla etkinlik için sarmalayıcı bkz [kullanarak CompensationHandlerActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65065).|
|<xref:System.Workflow.Activities.ConditionedActivityGroup>|Geçerli bir koşula göre alt etkinlikleri yürütür <xref:System.Workflow.Activities.ConditionedActivityGroup> etkinlik kendisi ve ayrı ayrı her bir alt uygulama koşullara bağlı. Daha fazla bilgi için bkz: [kullanarak ConditionedActivityGroup etkinliğini](http://go.microsoft.com/fwlink?LinkID=65066).|
|<xref:System.Workflow.Activities.DelayActivity>|Bir zaman aşımı aralığına dayalı gecikmeler iş akışınızda oluşturmanıza olanak sağlar. Daha fazla bilgi için bkz: [kullanarak EventDrivenActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65067).|
|<xref:System.Workflow.Activities.EventDrivenActivity>|Belirtilen bir olay oluştuğunda yürütülen bir veya daha fazla etkinlikleri sarmalar. Daha fazla bilgi için bkz: [kullanarak EventDrivenActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65068).|
|<xref:System.Workflow.Activities.EventHandlersActivity>|Bir etkinlik olayları ilişkilendirme için bir çerçeve sağlar. Daha fazla bilgi için bkz: [kullanarak EventHandlersActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65069).|
|<xref:System.Workflow.Activities.EventHandlingScopeActivity>|Kendi ana alt etkinlikle concurrently yürüten bir <xref:System.Workflow.Activities.EventHandlersActivity>. Daha fazla bilgi için bkz: [kullanarak EventHandlingScopeActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65070).|
|**System.Workflow.Activities.FaultHandlerActivity**|Belirttiğiniz bir türünde bir özel durum işleme için kullanılır. Daha fazla bilgi için bkz: [kullanarak FaultHandlerActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65071).|
|**System.Workflow.Activities.FaultHandlersActivity**|Alt etkinlikler türü sıralı bir listesi vardır bileşik bir etkinlik temsil eden **System.Workflow.Activities.FaultHandlerActivity**. Daha fazla bilgi için bkz: [kullanarak FaultHandlersActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65072).|
|<xref:System.Workflow.Activities.HandleExternalEventActivity>|İle birlikte kullanılan <xref:System.Workflow.Activities.CallExternalMethodActivity> etkinlik giriş ve çıkış yerel bir hizmet ile iletişim için. Daha fazla bilgi için bkz: [kullanarak HandleExternalEventActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65073).|
|<xref:System.Workflow.Activities.IfElseActivity>|Her dal bir koşulu sınar ve etkinlikler için eşittir koşulu ilk dalda gerçekleştirir **doğru**. Daha fazla bilgi için bkz: [kullanarak IfElseActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65074).|
|<xref:System.Workflow.Activities.IfElseBranchActivity>|Bir dalı temsil eden bir <xref:System.Workflow.Activities.IfElseActivity>. Daha fazla bilgi için bkz: [kullanarak öğeye etkinliğini](http://go.microsoft.com/fwlink?LinkID=65075).|
|<xref:System.Workflow.Activities.InvokeWebServiceActivity>|Bir Web hizmetini çağırmak, iş akışınızı sağlar. Daha fazla bilgi için bkz: [InvokeWebServiceActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65076).|
|<xref:System.Workflow.Activities.InvokeWorkflowActivity>|Başka bir iş akışının çağırmak, iş akışınızı sağlar. Daha fazla bilgi için bkz: [InvokeWorkflowActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65077).|
|<xref:System.Workflow.Activities.ListenActivity>|Yalnızca içeren bileşik bir etkinlik <xref:System.Workflow.Activities.EventDrivenActivity> alt etkinlikler. Daha fazla bilgi için bkz: [ListenActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65078).|
|<xref:System.Workflow.Activities.ParallelActivity>|İki veya daha fazla alt zamanlamak için bir yol sağlar **öğeler SequenceActivity** etkinlik dalları aynı anda işleme. Daha fazla bilgi için bkz: [kullanarak ParallelActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65079).|
|<xref:System.Workflow.Activities.PolicyActivity>|Kurallar topluluğu göstermek için kullanın. Bir kural koşulları ve sonuçta elde edilen Eylemler oluşur. Daha fazla bilgi için bkz: [PolicyActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65004).|
|<xref:System.Workflow.Activities.ReplicatorActivity>|Tek alt etkinliği birden çok örneğini oluşturur. Daha fazla bilgi için bkz: [kullanarak ReplicatorActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65080).|
|<xref:System.Workflow.Activities.SequenceActivity>|Sıralı yürütme bir araya toplamak için birden çok etkinliği bağlamak için basit bir yol sağlar. Daha fazla bilgi için bkz: [kullanarak öğeler SequenceActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65081).|
|<xref:System.Workflow.Activities.SetStateActivity>|Yeni bir durum geçiş belirtir. Daha fazla bilgi için bkz: [SetStateActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65082).|
|<xref:System.Workflow.Activities.StateActivity>|Bir iş akışındaki durumu makine durumunu temsil eder. Daha fazla bilgi için bkz: [kullanarak buraya StateActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65083).|
|<xref:System.Workflow.Activities.StateFinalizationActivity>|Kullanılan bir <xref:System.Workflow.Activities.StateActivity> etkinlik ayrılırken yürütülen alt etkinlikler için kapsayıcı olarak **buraya StateActivity** etkinlik. Daha fazla bilgi için bkz: [StateFinalizationActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65008).|
|<xref:System.Workflow.Activities.StateInitializationActivity>|Kullanılan bir <xref:System.Workflow.Activities.StateActivity> etkinlik girerken yürütülen alt etkinlikler için kapsayıcı olarak **buraya StateActivity** etkinlik. Daha fazla bilgi için bkz: [StateInitializationActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65006).|
|**System.Workflow.Activities.SuspendActivity**|Özel dikkat gerektiren bazı hata koşulu durumunda araya etkinleştirmek için iş akışı işlemi askıya alır. Daha fazla bilgi için bkz: [SuspendActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65084).|
|**System.Workflow.Activities.SynchronizationScopeActivity**|İçerilen etkinlikleri eşitlenmiş bir etki alanında sıralı olarak yürütür. Daha fazla bilgi için bkz: [SynchronizationScopeActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65085).|
|**System.Workflow.Activities.TerminateActivity**|İş akışınızı işlemi bir hata koşulu durumunda derhal sona olanak tanır. Daha fazla bilgi için bkz: [TerminateActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65086).|
|**System.Workflow.Activities.ThrowActivity**|İşlem meta verilerinin bir iş akışının bir parçası olarak oluşturulan iş özel durumları yakalamanıza olanak sağlar. Daha fazla bilgi için bkz: [ThrowActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65087).|
|**System.Workflow.Activities.TransactionScopeActivity**|İşlemler ve özel durum işleme için bir çerçeve sağlar. Daha fazla bilgi için bkz: [TransactionScopeActivity etkinliğinin kullanarak](http://go.microsoft.com/fwlink?LinkID=65088).|
|<xref:System.Workflow.Activities.WebServiceFaultActivity>|Bir Web hizmeti hata oluşması modeli sağlar. Daha fazla bilgi için bkz: [WebServiceFaultActivity etkinliği kullanarak](http://go.microsoft.com/fwlink?LinkID=65089).|
|<xref:System.Workflow.Activities.WebServiceInputActivity>|Bir Web hizmetinden veri alır. Daha fazla bilgi için bkz: [kullanarak WebServiceInputActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65090).|
|<xref:System.Workflow.Activities.WebServiceOutputActivity>|Bir iş akışı için yapılan bir Web hizmeti isteğine yanıt verir. Daha fazla bilgi için bkz: [kullanarak WebServiceOutputActivity etkinliğini](http://go.microsoft.com/fwlink?LinkID=65092).|
|<xref:System.Workflow.Activities.WhileActivity>|Bir koşul yerine getirilene kadar döngü için iş akışınıza sağlar. Daha fazla bilgi için bkz: [WhileActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65091).|

Özel etkinlikler oluşturma hakkında daha fazla bilgi için bkz: [geliştirme özel etkinlikler](http://go.microsoft.com/fwlink?LinkID=65023) ve [eski etkinlik Tasarımcısı'nı kullanarak](../workflow-designer/using-the-legacy-activity-designer.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Windows Workflow Foundation etkinlikleri](http://go.microsoft.com/fwlink?LinkID=65005)
- [İş akışları geliştirme](http://go.microsoft.com/fwlink?LinkID=65010)
- [İş akışı etkinliklerini geliştirme](http://go.microsoft.com/fwlink?LinkID=65023)