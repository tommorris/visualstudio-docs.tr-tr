---
title: "Çekirdek arabirimleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], core interfaces
ms.assetid: 666b9116-8550-4bdd-bc15-55fc57de87df
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 54ecbe034f4fa7054be2725205a013e5899849e7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="core-interfaces"></a>Çekirdek arabirimleri
Hata ayıklayıcı kullanarak genişletmek için çekirdek arabirimleri aşağıdaki arabirimlerdir [!INCLUDE[vsipsdk](../../../extensibility/includes/vsipsdk_md.md)].  
  
## <a name="discussion"></a>Tartışma  
 Bu arabirimleri öncelikle hata ayıklama altyapısı (DE) oluşturmak için kullanılır. Bunlar burada kategorilere göre düzenlenmiştir:  
  
-   [Kesme noktaları](#Breakpoints)  
  
-   [Bağlamlar](#Contexts)  
  
-   [Çekirdek sunucusu](#CoreServer)  
  
-   [Motorları hata ayıklama](#DebugEngines)  
  
-   [Belgeler](#Documents)  
  
-   [Olaylar](#Events)  
  
-   [İfadeler](#Expressions)  
  
-   [Bellek](#Memory)  
  
-   [Modüller](#Modules)  
  
-   [Bağlantı Noktaları](#Ports)  
  
-   [İşlemler](#Processes)  
  
-   [Programlar](#Programs)  
  
-   [Özellikler](#Properties)  
  
-   [Yığın Çerçeveleri](#StackFrames)  
  
-   [İş Parçacıkları](#Threads)  
  
-   [Tür Görselleştiriciler](#TypeVisualizers)  
  
 Arabirimleri uygulayabilir varlıkları şunlardır:  
  
-   Altyapısı (DE) hata ayıklama  
  
-   Bağlantı noktası tedarikçi (PS)  
  
-   İfade değerlendirici (EE)  
  
-   Visual Studio (VS)  
  
##  <a name="Breakpoints"></a>Kesme noktaları  
 Bu arabirimleri ilgili uygulama ve kesme noktaları izleme.  
  
|Arabirim|Tarafından uygulanan|Açıklama|  
|---------------|--------------------|-----------------|  
|[IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)|GİZLE|Bir bellek konumuna bağlı bir kesme noktası temsil eder.|  
|[IDebugBreakpointBoundEvent2](../../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)|GİZLE|Bir kesme noktası bir bellek konumuna bağlı DE gönderilir.|  
|[IDebugBreakpointChecksumRequest2](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2.md)|VS|Bir belge sağlama kesme isteğini temsil eder.|  
|[IDebugBreakpointErrorEvent2](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md)|GİZLE|Bir bellek konumuna bağlanması bir kesme noktası başarısız olduğunda DE tarafından gönderilir.|  
|[IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)|GİZLE|Bir kesme noktası ulaşıldığında DE tarafından gönderilir.|  
|[IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)|VS|Bir kesme noktası için bir istek temsil eder; Bekleyen bir kesme noktası oluşturmak için kullanılan.|  
|[IDebugBreakpointRequest3](../../../extensibility/debugger/reference/idebugbreakpointrequest3.md)|VS|Bir kesme noktası için bir istek temsil eder; Bekleyen bir kesme noktası oluşturmak için kullanılan.|  
|[IDebugBreakpointResolution2](../../../extensibility/debugger/reference/idebugbreakpointresolution2.md)|GİZLE|Bir kesme noktası bağlamak için kullanılan bilgileri temsil eder.|  
|[IDebugBreakpointUnboundEvent2](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2.md)|GİZLE|Bir kesme noktası bir bellek konumundan ilişkisiz olduğunda DE tarafından gönderilir.|  
|[IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)|GİZLE|Geçersiz bir kesme noktası temsil eder (tarafından döndürülen `IDebugBreakpointErrorEvent2`).|  
|[IDebugErrorBreakpointResolution2](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2.md)|GİZLE|Geçersiz bir kesme noktası ilgili çözüm bilgileri temsil eder.|  
|[IDebugFunctionPosition2](../../../extensibility/debugger/reference/idebugfunctionposition2.md)|GİZLE|Bir kesme noktası ayarlandığı bir konumda bir işlevi temsil eder.|  
|[IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)|GİZLE|Bağlanması için bir kesme noktası temsil eder; ilişkili bir kesme noktası oluşturmak için kullanılan.|  
|[IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md)|GİZLE|Numaralandırma bağlı kesme noktaları kümesini temsil eder.|  
|[IEnumDebugErrorBreakpoints2](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md)|GİZLE|Numaralandırma, bir dizi bellek konumundan bağlanamadı kesme noktaları üzerinden temsil eder.|  
  
##  <a name="Contexts"></a>Bağlamları  
 Bu arabirimleri bağlamları ayıklanacak program içinde çeşitli temsil eder.  
  
|Arabirim|Tarafından uygulanan|Açıklama|  
|---------------|--------------------|-----------------|  
|[IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)|GİZLE|Bir kod yönergesi başlangıç konumunu temsil eder.|  
|[IDebugCodeContext3](../../../extensibility/debugger/reference/idebugcodecontext3.md)|GİZLE|Genişletir [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) modülü ve işlem arabirimleri alınmasını etkinleştirmek için arabirim.|  
|[IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)|VS, GİZLE|Belgede bir konumu temsil eder.|  
|[IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md)|GİZLE|İfadenin değerlendirileceği bağlamı temsil eder.|  
|[IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)|GİZLE|Bir koleksiyonun bayt bellek başlangıç konumu temsil eder.|  
|[IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)|GİZLE|Kesme noktası veya özel durum yığın çerçevesi bağlamını temsil eder.|  
|[IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md)|GİZLE|Kesme noktası veya özel durum yığın çerçevesi bağlamını temsil eder.|  
|[IEnumDebugCodeContexts2](../../../extensibility/debugger/reference/ienumdebugcodecontexts2.md)|GİZLE|Numaralandırma kod bağlamları kümesini temsil eder.|  
  
##  <a name="CoreServer"></a>Çekirdek sunucusu  
 Bu arabirimleri bir program ayıklanacak makine temsil eder. Bunlar tarafından uygulanan [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] ancak halinde hata ayıklama motoru tarafından çağrılabilir.  
  
|Arabirim|Tarafından uygulanan|Açıklama|  
|---------------|--------------------|-----------------|  
|[IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)|VS|Bilgisayar hakkında bilgi yanı sıra bağlantı noktası ve bağlantı noktası Üreticiler erişim sağlar.|  
|[IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)|VS|Temsil eden bir [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) uzaktan hata ayıklama destekler.|  
  
##  <a name="DebugEngines"></a>Motorları hata ayıklama  
 Bu arabirimleri hata ayıklama altyapılarını ve bunların ilişkili olaylarını temsil eder.  
  
|Arabirim|Tarafından uygulanan|Açıklama|  
|---------------|--------------------|-----------------|  
|[IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)|GİZLE|Özel hata ayıklama altyapısını temsil eder.|  
|[IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)|GİZLE|Simgeler, JustMyCode ve özel durumları yüklenmesini destekleyen bir özel hata ayıklama altyapısını temsil eder.|  
|[IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)|GİZLE|Hata ayıklama görevleri işlemeye hazır belirtmek için DE yeni her örneği tarafından gönderilir.|  
|[IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)|GİZLE|Başlatma programları destekleyen bir özel hata ayıklama altyapısını temsil eder.|  
|[IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)|DE, PS|Hata ayıklama altyapıları işleyen bir program düğümünü temsil eder.|  
|[IDebugQueryEngine2](../../../extensibility/debugger/reference/idebugqueryengine2.md)|GİZLE|İş parçacığı, program veya yığın çerçevesi için hata ayıklama altyapısını arabirim edinme SDM için bir yol sağlar.|  
  
##  <a name="Documents"></a>Belgeleri  
 Bu arabirimleri belgeleri (kaynak dosyaları) ve bunların ilişkili öğelerini temsil eder.  
  
|Arabirim|Tarafından uygulanan|Açıklama|  
|---------------|--------------------|-----------------|  
|[IDebugActivateDocumentEvent2](../../../extensibility/debugger/reference/idebugactivatedocumentevent2.md)|GİZLE|Açılacak şekilde bir belge istemek için DE tarafından gönderilir.|  
|[IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)|GİZLE|Bir belgeden artık hata ayıklayabildiğinize yönergeleri akışı temsil eder.|  
|[IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)|VS, GİZLE|Bir ad ve bir sınıf kimliği (CLSID) belirterek DE tarafından sağlanan bir belgeyi temsil eder.|  
|[IDebugDocumentChecksum2](../../../extensibility/debugger/reference/idebugdocumentchecksum2.md)|DE, EE|Hata ayıklama belge için bir sağlama toplamı temsil eder ve sağlama toplamı bileşenler arasında geçirme sağlar.|  
|[IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)|VS, GİZLE|Belirli bir ifade ve kod bağlamına karşılık gelen bir belge içinde bir konuma bir belge bağlamını temsil eder.|  
|[IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)|VS, GİZLE|Bir belge içindeki genel bir konumu temsil eder.|  
|[IDebugDocumentPositionOffset2](../../../extensibility/debugger/reference/idebugdocumentpositionoffset2.md)|VS|Bir kaynak dosya konumu olarak bir karakter uygun temsil eder.|  
|[IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)|VS, GİZLE|DE tarafından sağlanan bir metin belgesi temsil eder (türetilmiş [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)), gerçek metin sağlama.|  
|[IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)|GİZLE|Bellekte bir kaynak dosya değişiklikleri belirtmek için DE tarafından gönderilir.|  
  
##  <a name="Events"></a>Olayları  
 Bu arabirimleri DE ve oturum hata ayıklama Yöneticisi'ni (SDM) arasında gönderilen tüm olayları temsil eder.  
  
|Arabirim|Tarafından uygulanan|Açıklama|  
|---------------|--------------------|-----------------|  
|[IDebugActivateDocumentEvent2](../../../extensibility/debugger/reference/idebugactivatedocumentevent2.md)|GİZLE|Açılacak şekilde bir belge istemek için DE tarafından gönderilir.|  
|[IDebugBeforeSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugbeforesymbolsearchevent2.md)|GİZLE|Hata ayıklama altyapısı (DE) Bu arabirim oturum hata ayıklama Yöneticisi durumunu ayarlama (SDM) simgesi yükleri sırasında iletisi gönderir.|  
|[IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)|GİZLE|Programın sonu tamamlandığında DE tarafından gönderilir.|  
|[IDebugBreakpointBoundEvent2](../../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)|GİZLE|Bir kesme noktası bağlandığında DE tarafından gönderilir.|  
|[IDebugBreakpointErrorEvent2](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md)|GİZLE|Bağlanacak bir kesme noktası başarısız olduğunda DE tarafından gönderilir.|  
|[IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)|GİZLE|Bir kesme noktası ulaşıldığında DE tarafından gönderilir.|  
|[IDebugBreakpointUnboundEvent2](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2.md)|GİZLE|Bir kesme noktası ilişkisiz olduğunda DE tarafından gönderilir.|  
|[IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)|GİZLE|Belirli bir konumda durması gerektiğini olup olmadığını belirlemek için DE tarafından gönderilir.|  
|[IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)|GİZLE|Bellekte bir kaynak dosya değişiklikleri belirtmek için DE tarafından gönderilir.|  
|[IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)|GİZLE|Hata ayıklama görevleri işlemeye hazır belirtmek için DE yeni her örneği tarafından gönderilir.|  
|[IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md)|GİZLE|Ayıklanacak program ilk yönergenin yürütmek hazır olduğunu göstermek için DE tarafından gönderilir.|  
|[IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)|GİZLE|Bir hata döndürebilir, diğer olay arabirimleri tarafından okunabilir hata iletileri sağlamak için kullanılan bir arabirim.|  
|[IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)|DE, PS|Temel arabirim hangi tüm diğer olayından arabirimleri türetilir.|  
|[IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)|VS|(Belirli bir olay arabirimini uygulayan nesneler olarak ifade edilir) olayları gönderilme SDM tarafından uygulanan bir arabirimi temsil eder.|  
|[IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)|GİZLE|Ayıklanacak programa bir özel durum oluştu DE tarafından gönderilir.|  
|[IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)|GİZLE|Zaman uyumsuz ifade değerlendirme tamamlandığında DE tarafından gönderilir.|  
|IDebugFindSymbolEvent2||KULLANIMDAN KALKTI. KULLANMAYIN.|  
|[IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md)|GİZLE|Ele geçirilen bir özel durum işleme tamamlandığında DE tarafından gönderilir.|  
|[IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)|GİZLE|Bir programın yüklenmesi tamamlandı DE tarafından gönderilir.|  
|[IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md)|GİZLE|IDE görüntülenmesini sağlamak için DE tarafından kullanıcıya bir bilgilendirme iletisi gönderdi.|  
|[IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md)|GİZLE|Bir modül yüklendiğinde veya kaldırıldığında DE tarafından gönderilir.|  
|[IDebugNoSymbolsEvent2](../../../extensibility/debugger/reference/idebugnosymbolsevent2.md)|GİZLE|Sinyalleri [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] hata ayıklayıcı, simgeler başlatılan yürütülebilir dosyası bulunamadı, kullanıcıyı uyarmak için kullanıcı Arabirimi.|  
|[IDebugOutputStringEvent2](../../../extensibility/debugger/reference/idebugoutputstringevent2.md)|GİZLE|IDE görüntülenmesini sağlamak için DE tarafından rastgele bir dize gönderildi.|  
|[IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md)|VS, GİZLE|Herhangi bir dinleyici bağlantı noktası olayları iletişim kurmak için bir bağlantı tarafından gönderilir.|  
|[IDebugProcessCreateEvent2](../../../extensibility/debugger/reference/idebugprocesscreateevent2.md)|DE, PS|Bir işlem oluştururken DE veya bağlantı noktası tarafından gönderilen.|  
|[IDebugProcessDestroyEvent2](../../../extensibility/debugger/reference/idebugprocessdestroyevent2.md)|DE, PS|Bir işlem yok DE veya bağlantı noktası tarafından gönderilir.|  
|[IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)|DE, PS|Bir program oluşturdu DE veya bağlantı noktası tarafından gönderilir.|  
|[IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)|DE, PS|Bir program yok DE veya bağlantı noktası tarafından gönderilir.|  
|[IDebugProgramDestroyEventFlags2](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2.md)|GİZLE|Varsayılan davranışını geçersiz kılmak hata ayıklama altyapısı sağlar [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] bir hata ayıklama oturumu sonlandırdığınızda, kullanıcı Arabirimi.|  
|[IDebugProgramNameChangedEvent2](../../../extensibility/debugger/reference/idebugprogramnamechangedevent2.md)|GİZLE|Bir programın adını değiştiğinde hata ayıklama altyapısı, (DE) oturum hata ayıklama Yöneticisi (SDM) gönderilir.|  
|[IDebugPropertyCreateEvent2](../../../extensibility/debugger/reference/idebugpropertycreateevent2.md)|GİZLE|Yeni bir özellik zaman DE tarafından gönderilen (tarafından temsil edilen `IDebugProperty2` arabirimi) oluşturuldu.|  
|[IDebugPropertyDestroyEvent2](../../../extensibility/debugger/reference/idebugpropertydestroyevent2.md)|GİZLE|Bir özellik yok DE tarafından gönderilir.|  
|[IDebugReturnValueEvent2](../../../extensibility/debugger/reference/idebugreturnvalueevent2.md)|GİZLE|Dönüş değeri düzgün görüntülenebilmesi dışında veya bir işlev üzerinden atlama DE tarafından gönderilir.|  
|[IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)|VS|Hata ayıklama ölçüm ayarları okumak için motorları etkinleştirir uzaktan.|  
|[IDebugStepCompleteEvent2](../../../extensibility/debugger/reference/idebugstepcompleteevent2.md)|GİZLE|İçinde üzerinden ya da bir yönerge dışında bir adım tamamlandığında DE tarafından gönderilir.|  
|[IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)|GİZLE|Başarı veya başarısızlık simgeleri modülü için yükleme durumunu göstermek için DE tarafından gönderilir.|  
|[IDebugThreadCreateEvent2](../../../extensibility/debugger/reference/idebugthreadcreateevent2.md)|GİZLE|Bir iş parçacığı oluştururken DE tarafından gönderilir.|  
|[IDebugThreadDestroyEvent2](../../../extensibility/debugger/reference/idebugthreaddestroyevent2.md)|GİZLE|Bir iş parçacığı yok DE tarafından gönderilir.|  
|[IDebugThreadNameChangedEvent2](../../../extensibility/debugger/reference/idebugthreadnamechangedevent2.md)|GİZLE|Bir iş parçacığı adı değiştiğinde DE tarafından gönderilir.|  
  
##  <a name="Expressions"></a>İfadeler  
 Bu arabirimleri belirli bir bağlamda değerlendirilecek ifadeleri temsil eder.  
  
|Arabirim|Tarafından uygulanan|Açıklama|  
|---------------|--------------------|-----------------|  
|[IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)|GİZLE|Değerlendirilecek bir ifade temsil eder. Alınan [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md) arabirimi.|  
|[IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md)|GİZLE|Bir ifadenin değerlendirilmesi bağlamını temsil eder. Alınan [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) arabirimi.|  
|[IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)|GİZLE|Zaman uyumsuz ifade değerlendirme tamamlandığında DE tarafından gönderilir.|  
  
##  <a name="Memory"></a>Bellek  
 Bu arabirimleri bellekteki bayt dizisini temsil eder.  
  
|Arabirim|Tarafından uygulanan|Açıklama|  
|---------------|--------------------|-----------------|  
|[IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)|GİZLE|Okuma veya yazma bellek bayt dizisini temsil eder.|  
|[IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)|GİZLE|Bayt dizisinin bellekte bir konumu temsil eder.|  
  
##  <a name="Modules"></a>Modülleri  
 Bu arabirimleri temsil eden bir yürütülebilir dosyaya karşılık gelen bir modül veya. DLL dosyası.  
  
|Arabirim|Tarafından uygulanan|Açıklama|  
|---------------|--------------------|-----------------|  
|[IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)|GİZLE|Bir yürütülebilir dosyayı veya DLL temsil eder.|  
|[IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)|GİZLE|Temsil eden bir [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) simgeleri destekler.|  
|[IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md)|GİZLE|Bir modül yüklendiğinde veya kaldırıldığında DE tarafından gönderilir.|  
|[IDebugSourceServerModule](../../../extensibility/debugger/reference/idebugsourceservermodule.md)|GİZLE|PDB dosyasında yer alan kaynak sunucu bilgileri temsil eder.|  
|[IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)|GİZLE|Tarafından bilinen modüllerin küme üzerinde bir numaralandırma temsil eden bir [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md).|  
  
##  <a name="Ports"></a>Bağlantı noktaları  
 Bu arabirimleri bağlantı noktaları ve bağlantı noktası Üreticiler temsil eder.  
  
|Arabirim|Tarafından uygulanan|Açıklama|  
|---------------|--------------------|-----------------|  
|[IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)|VS, PS|Yerel bilgisayarda varsayılan bağlantı noktası temsil eder.|  
|[IDebugFirewallConfigurationCallback2](../../../extensibility/debugger/reference/idebugfirewallconfigurationcallback2.md)|VS|Sorulacak DCOM kullanan bir hata ayıklama altyapısı sağlar [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] güvenlik duvarı uzaktan hata ayıklama engellemez emin olmak için kullanıcı Arabirimi.|  
|[IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)|VS, PS|Bir bağlantı noktasını temsil eder.|  
|[IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md)|PS|Herhangi bir dinleyici bağlantı noktası olayları iletişim kurmak için bir bağlantı tarafından gönderilir.|  
|[IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)|PS|Başlatma ve sonlandırma işlemleri bir bağlantı noktasını temsil eder.|  
|[IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)|PS|Kaydolun ve bir bağlantı noktası programlarla kaydı için kullanılır. şu anda ayıklanacak programları izlemek bağlantı noktası sağlar.|  
|[IDebugPortPicker](../../../extensibility/debugger/reference/idebugportpicker.md)|PS|Bağlantı noktasını seçmek için özelleştirilmiş bir kullanıcı Arabirimi temsil eder.|  
|[IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)|VS|İçinden yeni bir bağlantı noktası oluşturulan bulunan veya bir bağlantı noktası için bir istek temsil eder.|  
|[IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)|PS|Sağlayıcı bağlantı noktalarının temsil eder.|  
|[IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)|PS|Bir sağlayıcının kalıcı bağlantı noktalarının temsil eden oluşturulduğu (disk Kaydet) bağlantı noktaları hakkında bilgi.|  
|[IDebugPortSupplierDescription2](../../../extensibility/debugger/reference/idebugportsupplierdescription2.md)|PS|Etkinleştirir [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] içindeki metni görüntülemek için kullanıcı Arabirimi **aktarım bilgi** bölümünü **ekleme işlemi için** iletişim kutusu.|  
|[IDebugWindowsComputerPort2](../../../extensibility/debugger/reference/idebugwindowscomputerport2.md)|VS|Hedef bilgisayar hakkında bilgi için sorgulama sağlar.|  
|[IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)|VS, PS|Numaralandırma bir dizi bağlantı noktası temsil eder.|  
|[IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)|VS|Numaralandırma bağlantı noktası Üreticiler kümesini temsil eder.|  
  
##  <a name="Processes"></a>İşlemler  
 Bu arabirimleri işlemleri, bir veya daha fazla program içeren tek bir yürütülebilir dosyayı temsil eder.  
  
|Arabirim|Tarafından uygulanan|Açıklama|  
|---------------|--------------------|-----------------|  
|[IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)|PS, GİZLE|Bir bilgisayarda çalışan bir işlemi temsil eder.|  
|[IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)|PS, GİZLE|Etkin olarak destekleyen bir işlemi temsil eden hata ayıklama (adım değiştirmek için kullanılan, devam etmek ve yöntemleri yürütmek [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) arabirimi).|  
|[IDebugProcessCreateEvent2](../../../extensibility/debugger/reference/idebugprocesscreateevent2.md)|DE, PS|Bir işlem oluştururken DE veya bağlantı noktası tarafından gönderilen.|  
|[IDebugProcessDestroyEvent2](../../../extensibility/debugger/reference/idebugprocessdestroyevent2.md)|DE, PS|Bir işlem yok DE veya bağlantı noktası tarafından gönderilir.|  
|[IDebugProcessEx2](../../../extensibility/debugger/reference/idebugprocessex2.md)|PS|Hangi oturumu ekli olduğu izlemelidir bir işlem temsil eder.|  
|[IEnumDebugProcesses2](../../../extensibility/debugger/reference/ienumdebugprocesses2.md)|PS|Bir bağlantı noktası işlemlerde bir dizi numaralandırması temsil eder.|  
  
##  <a name="Programs"></a>Programlar  
 Bu arabirimleri programları, mutlaka bir fiziksel çalıştırılabilir veya modül benzemez mantıksal birimler yürütme temsil eder.  
  
|Arabirim|Tarafından uygulanan|Açıklama|  
|---------------|--------------------|-----------------|  
|[IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)|GİZLE|Temsil eden bir [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) , aynı anda ayıklanacak diğer programları ile birlikte çalışması gerekir.|  
|[IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)|DE, PS|Bir mantıksal birim yürütme temsil eder.|  
|[IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)|DE, PS|Bir program oluşturdu DE veya bağlantı noktası tarafından gönderilir.|  
|[IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)|DE, PS|Bir program yok DE veya bağlantı noktası tarafından gönderilir.|  
|[IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)|DE, PS|Temsil eden bir [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) birden çok hata ayıklama motoru tarafından işlenebilir.|  
|[IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)|PS|Temsil eden bir [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) , sağlayabilmelidir hangi oturumu ekli olduğu izlemek.|  
|[IDebugProgramHost2](../../../extensibility/debugger/reference/idebugprogramhost2.md)|DE, PS|Temsil eden bir [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) , çalıştığı işlem hakkında bilgi dönebilirsiniz.|  
|[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)|DE, PS|Hata ayıklaması yapılabilir bir programı temsil eder.|  
|[IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)|DE, PS|Program düğümün ilişkili programın bağlama girişimi bildirilmesini sağlar.|  
|[IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)|GİZLE|SDM SE bu DE tarafından denetlenen programlar hakkında sorgulamak bir yol sağlar.|  
|[IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)|VS|Programları ayıklanacak göstermek için SDM ile kaydetmek için DEs tarafından kullanılır.|  
|[IDebugProviderProgramNode2](../../../extensibility/debugger/reference/idebugproviderprogramnode2.md)|DE, PS|Temsil eden bir [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) , sıralama arabirimleri iş parçacığı veya işlem sınırları boyunca.|  
|[IEnumDebugPrograms2](../../../extensibility/debugger/reference/ienumdebugprograms2.md)|DE, PS|Program bir dizi numaralandırması temsil eder.|  
  
##  <a name="Properties"></a>Özellikleri  
 Bu arabirimleri özellikleri, genellikle bir ifade değerlendirme sonucu gibi belirli bir bağlam ile ilişkili bir değeri temsil eder.  
  
|Arabirim|Tarafından uygulanan|Açıklama|  
|---------------|--------------------|-----------------|  
|[IDebugCustomViewer](../../../extensibility/debugger/reference/idebugcustomviewer.md)|EE|Temsil eden bir [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) , görüntüleyebilir değeri özel bir biçimde.|  
|[IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)|GİZLE|Yığın çerçevesi, belge veya bir ifade değerlendirme sonucu değerini temsil eder.|  
|[IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)|GİZLE|Temsil eden bir [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) rasgele uzun dizeleri destekler.|  
|[IDebugPropertyCreateEvent2](../../../extensibility/debugger/reference/idebugpropertycreateevent2.md)|GİZLE|Yeni bir özellik zaman DE tarafından gönderilen (tarafından temsil edilen [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) arabirimi) oluşturuldu.|  
|[IDebugPropertyDestroyEvent2](../../../extensibility/debugger/reference/idebugpropertydestroyevent2.md)|GİZLE|Bir özellik yok DE tarafından gönderilir.|  
|[IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)|GİZLE|Herhangi belirli yığın çerçevesi dışında mevcut bir özellik referansı temsil eder.|  
|[IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)|GİZLE|Numaralandırma kümesini temsil eder [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) yapıları değişkenleri, kayıtları, parametreleri ve ifadeler açıklanmaktadır.|  
|[IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md)|GİZLE|Numaralandırma kümesini temsil eder [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) yapıları.|  
  
##  <a name="StackFrames"></a>Yığın çerçeveleri  
 Bu arabirimleri yığın çerçevesi, bir içeriği temsil eden içinde bir kesme noktası veya özel durum oluştu.  
  
|Arabirim|Tarafından uygulanan|Açıklama|  
|---------------|--------------------|-----------------|  
|[IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)|GİZLE|Bir bağlamı temsil eder, bir kesme noktası veya özel durum oluştu.|  
|[IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md)|GİZLE|Temsil eden bir [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) özel durumlar ele hangi işleyebilir.|  
|[IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md)|GİZLE|Numaralandırma kümesinin üzerine temsil eden [CODE_PATH](../../../extensibility/debugger/reference/code-path.md) işlevi belirtin yapıları çağrısı sırasında belirli yığın çerçevesi ulaşması için kullanılan dizisi.|  
|[IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)|GİZLE|Numaralandırma kümesini temsil eder [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) yığın çerçeveleri açıklamak yapıları.|  
  
##  <a name="Threads"></a>İş parçacıkları  
 Bu arabirimleri iş parçacıkları ve bunların ilişkili olaylarını temsil eder.  
  
|Arabirim|Tarafından uygulanan|Açıklama|  
|---------------|--------------------|-----------------|  
|[IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)|GİZLE|Bir iş parçacığı yürütme temsil eder.|  
|[IDebugThreadCreateEvent2](../../../extensibility/debugger/reference/idebugthreadcreateevent2.md)|GİZLE|Bir iş parçacığı oluştururken DE tarafından gönderilir.|  
|[IDebugThreadDestroyEvent2](../../../extensibility/debugger/reference/idebugthreaddestroyevent2.md)|GİZLE|Bir iş parçacığı yok DE tarafından gönderilir.|  
|[IDebugThreadNameChangedEvent2](../../../extensibility/debugger/reference/idebugthreadnamechangedevent2.md)|GİZLE|Bir iş parçacığı adı değiştiğinde DE tarafından gönderilir.|  
|[IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md)|GİZLE|Numaralandırma iş parçacığı kümesini temsil eder.|  
  
##  <a name="TypeVisualizers"></a>Tür Görselleştiriciler  
 Bu arabirimleri türü görselleştiriciler için destek sağlar. Bu arabirimleri genellikle bir ifade değerlendiricisi tarafından uygulanır.  
  
|Arabirim|Tarafından uygulanan|Açıklama|  
|---------------|--------------------|-----------------|  
|[IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)|EE|Tür görselleştiriciyi sunulacak bir bayt dizisi temsil eder.|  
|[IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)|EE|Tür görselleştiriciyi geçirilecek verilere erişim almak için yöntemleri sağlar.|  
|[IPropertyProxyProvider](../../../extensibility/debugger/reference/ipropertyproxyprovider.md)|EE|Erişim sağlayan bir özelliği temsil [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) uygulamaları.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [API Başvurusu](../../../extensibility/debugger/reference/api-reference-visual-studio-debugging.md)   
 [Özel Hata Ayıklama Altyapısı Oluşturma](../../../extensibility/debugger/creating-a-custom-debug-engine.md)