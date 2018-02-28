---
title: "Etkin komut dosyası hata ayıklama genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Active Script Debugging overview
ms.assetid: ce4ec768-d017-4dfa-a7e3-cced3a29e679
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1d9aebdc3f8fa4df0f4386609e632e1a8611c87f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="active-script-debugging-overview"></a>Etkin Komut Dosyası Hata Ayıklamaya Genel Bakış
Etkin komut dosyası hata ayıklama arabirimleri dilden, ana bilgisayar Tarafsız hata ayıklamaya izin verme ve çok çeşitli geliştirme ortamlarını destekler.  
  
 ![Komut dosyası ana bilgisayarı işlemi](../winscript/media/scp56activdbgarchgif.gif "Scp56ActivDbgArchgif")  
Şekil 1  
  
 Bir dilden hata ayıklama ortamında bir programlama dili veya programlama dillerinin, bu dillerden birine belirli bilgisi olmadan karışımını destekler. Hata ayıklama ortamı diller arası atlama ve kesme noktaları da destekler. (Bu genel bakışta öncelikle VBScript gibi dilleri komut desteği odaklanır ve [!INCLUDE[javascript](../javascript/includes/javascript-md.md)].)  
  
 Bir ana bilgisayar Tarafsız hata ayıklayıcı, Internet Explorer veya özel bir ana bilgisayar gibi tüm etkin komut dosyası ana bilgisayarla otomatik olarak kullanılabilir. Konak ne hata ayıklayıcı kullanıcıya, içeriğine belge ağaç yapısını ve hata ayıklama belge sözdizimi renklendirmesi sunar denetler. Bu, ana belge bağlamında gösterilecek hata ayıklaması kaynak kodu sağlar. Örneğin, Internet Explorer bir HTML sayfasında bir komut dosyası gösterebilir.  
  
 Aşağıdaki alt bölümlerde, her anahtar bileşen etkin hata ayıklama ve ilişkili arabirimlerinden ele alınmıştır. Ancak, devam etmeden önce etkin hata ayıklama birkaç temel kavramları tanımlanmış olması gerekir:  
  
 ana bilgisayar uygulaması  
 Komut dosyasını barındıran uygulama motorları ve nesneler (veya "nesne modeli") kodlanabilir kümesi sağlar.  
  
 Dil altyapısı  
 Ayrıştırma, yürütme ve belirli bir dil için soyutlamalar hata ayıklama sağlayan bir bileşendir.  
  
 hata ayıklayıcı IDE  
 Konak uygulama ve dil altyapısı ile iletişim kurarak kullanıcı Arabirimi hata ayıklama sağlayan uygulama.  
  
 Makine Hata Ayıklama Yöneticisi  
 Bir kayıt defteri debuggable uygulama işlemlerinin tutar bileşeni.  
  
 İşlem Hata Ayıklama Yöneticisi  
 Belirli bir uygulama için debuggable belgelerinin ağaç tutan bir bileşen çalışan iş parçacıkları ve benzeri izler.  
  
 Belge bağlamı  
 Bir belge bağlamı, ana belge kaynak kodunu belirli bir aralıkta temsil eden bir soyutlamadır.  
  
 kod bağlamı  
 Kod çalıştırırken belirli bir konumda dil altyapısı (bir "sanal yönerge işaretçisi".) bir kod bağlamını temsil eder  
  
 ifade bağlamı  
 İfadeler bir dil altyapısı tarafından değerlendirilmesi belirli bir içeriğe (örneğin, bir yığın çerçevesi).  
  
 Nesne gözatma  
 Bir nesnenin adı, türü, değer ve alt nesneler, "Gözcü penceresi" uygulamak için uygun yapılandırılmış ve dilden bağımsız gösterimini UI.  
  
 Aşağıda bu arabirimleri ayrıntıları tarafından izlenen karşılık gelen, ilişkili arabirim ve anahtar etkin hata ayıklama bileşenleri her bir genel bakıştır.  
  
## <a name="language-engine"></a>Dil altyapısı  
 Dil altyapısı sağlar:  
  
-   Dil ayrıştırma ve yürütme.  
  
-   Hata ayıklama desteği (kesme noktaları ve benzeri).  
  
-   İfade değerlendirme.  
  
-   Sözdizimi renklendirmesi.  
  
-   Gözatma nesne.  
  
-   Yığın numaralandırması ve ayrıştırma.  
  
 Bir komut dosyası motoru hata ayıklama sağlamak üzere desteklemesi gerekir arabirimleri, ifade değerlendirmesi ve nesne gözatma altındadır. Bu arabirimleri belge bağlamını ve altyapının kod bağlamları arasında eşleme ve ayrıca numaralandırması debugger ifade değerlendirme yapmak için kullanıcı Arabirimi tarafından yığın ve tarama nesne için konak uygulama tarafından kullanılır.  
  
 [Iactivescriptdebug arabirimi](../winscript/reference/iactivescriptdebug-interface.md)  
 Sözdizimi renklendirmesi ve kod bağlam numaralandırması sağlar.  
  
 [Iactivescripterrordebug arabirimi](../winscript/reference/iactivescripterrordebug-interface.md)  
 Belge bağlamları ve hatalar için yığın çerçeveleri döndürür.  
  
 [Iactivescriptsitedebug arabirimi](../winscript/reference/iactivescriptsitedebug-interface.md)  
 Hata ayıklayıcı betiği altyapısından sağlanan bağlantıyı barındırır.  
  
 [Idebugcodecontext arabirimi](../winscript/reference/idebugcodecontext-interface.md)  
 Bir sanal sağlayan bir iş parçacığında "yönerge işaretçisi".  
  
 [Ienumdebugcodecontexts arabirimi](../winscript/reference/ienumdebugcodecontexts-interface.md)  
 Bir belge bağlamına karşılık gelen kod bağlamları numaralandırır.  
  
 [Idebugstackframe arabirimi](../winscript/reference/idebugstackframe-interface.md)  
 İş parçacığı yığında mantıksal yığın çerçevesi temsil eder.  
  
 [Idebugexpressioncontext arabirimi](../winscript/reference/idebugexpressioncontext-interface.md)  
 İfadeler değerlendirilebilir bağlamı sağlar.  
  
 [Idebugstackframesniffer arabirimi](../winscript/reference/idebugstackframesniffer-interface.md)  
 Mantıksal yığın çerçeveleri numaralandırmak için bir yol sağlar.  
  
 [Idebugexpression arabirimi](../winscript/reference/idebugexpression-interface.md)  
 Zaman uyumsuz olarak değerlendirilen bir ifade temsil eder.  
  
 [Idebugsyncoperation arabirimi](../winscript/reference/idebugsyncoperation-interface.md)  
 Belirli bir engellenmiş iş parçacığı, iç içe geçmiş sırada gerçekleştirilmesi gerekir bir işlem soyut için bir komut dosyası altyapısı sağlar.  
  
 [Idebugasyncoperation arabirimi](../winscript/reference/idebugasyncoperation-interface.md)  
 Zaman uyumlu hata ayıklama işlemi zaman uyumsuz erişim sağlar.  
  
 [Idebugasyncoperationcallback arabirimi](../winscript/reference/idebugasyncoperationcallback-interface.md)  
 İlerleme durumunu ilgili durum olaylarını sağlayan bir `IDebugAsyncOperation` arabirim değerlendirme.  
  
 [Ienumdebugexpressioncontexts arabirimi](../winscript/reference/ienumdebugexpressioncontexts-interface.md)  
 Bir koleksiyonu numaralandırır `IDebugExpressionContexts` nesneleri.  
  
 [Iprovideexpressioncontexts arabirimi](../winscript/reference/iprovideexpressioncontexts-interface.md)  
 Belirli bir bileşen tarafından bilinen ifade bağlamları numaralandırmak için bir yol sağlar.  
  
 [Idebugformatter arabirimi](../winscript/reference/idebugformatter-interface.md)  
 Bir dil veya değişken değerleri veya VARTYPE türler ile dizeler arasındaki dönüştürme özelleştirmek için IDE'yi sağlar.  
  
 [Idebugstackframesnifferex arabirimi](../winscript/reference/idebugstackframesnifferex-interface.md)  
 Mantıksal yığın çerçeveleri için PDM numaralandırır.  
  
## <a name="hosts"></a>Ana bilgisayarlar  
 Ana bilgisayar:  
  
-   Dil motorları barındırır.  
  
-   Bir nesne modeli (betiği yazılabilir nesneleri kümesi) sağlar.  
  
-   Hata ayıklaması yapılabilir belgeleri ağacının ve içerikleri tanımlar.  
  
-   Komut dosyaları, sanal uygulamaları düzenler.  
  
 Konaklar iki tür vardır:  
  
-   Dumb bir ana bilgisayar yalnızca temel etkin komut dosyası arabirimleri destekler. Belge yapısı veya kuruluşlar üzerinde denetimi yoktur; Bu, tamamen dil altyapısına sağlanan komut dosyaları tarafından belirlenir.  
  
-   Bir akıllı ana bilgisayar, belge ağacı, belge içeriklerini ve sözdizimi renklendirmesi tanımlamanızı sağlayan daha büyük bir arabirimleri destekler. Bir akıllı ana bilgisayar olacak şekilde bir ana bilgisayar için çok daha kolay yapan sonraki alt bölümde açıklanan yardımcı arabirimleri, bir dizi yoktur.  
  
### <a name="smart-host-helper-interfaces"></a>Akıllı konak yardımcı arabirimleri  
 `IDebugDocumentHelper` Yöntemleri sunar arabirimleri oldukça basitleştirilmiş bir dizi ana bilgisayar tam karmaşıklığı (gücü) tam ana bilgisayar arabirimlerin işleme ve olmadan akıllı barındırma avantajları elde için kullanabilirsiniz.  
  
 Bir ana bilgisayar bu arabirimleri Elbette kullanmak için gerekli değildir. Ancak bu arabirimleri kullanarak, uygulama veya çok sayıda daha karmaşık arabirimleri kullanarak önleyebilirsiniz.  
  
 [Idebugdocumenthelper arabirimi](../winscript/reference/idebugdocumenthelper-interface.md)  
 PDM tarafından uygulanan ve uygulamaları için akıllı barındırmak için gereken birçok arabirimler sağlar.  
  
 [Idebugdocumenthost arabirimi](../winscript/reference/idebugdocumenthost-interface.md)  
 (İsteğe bağlı) sözdizimi, hata ayıklayıcı için renklendirme gibi ana bilgisayara özgü işlevselliği kullanıma sunmak için ana bilgisayar tarafından uygulanır.  
  
 Daha fazla bilgi için bkz: [akıllı konak yardımcı arabirimleri uygulama](../winscript/implementing-smart-host-helper-interfaces.md).  
  
### <a name="full-smart-host-interfaces"></a>Tam akıllı konak arabirimleri  
 Aşağıda tam bir akıllı ana bilgisayar uygulamak veya yardımcı arabirimleri kullanmıyorsa kullanmak arabirimleri ayarlanır.  
  
 Ana bilgisayar tarafından uygulanan arabirimler:  
  
 [Idebugdocumentınfo arabirimi](../winscript/reference/idebugdocumentinfo-interface.md)  
 Bilgi olabilir veya değil örneği bir belge üzerinde sağlar.  
  
 [Idebugdocumentprovider arabirimi](../winscript/reference/idebugdocumentprovider-interface.md)  
 İsteğe bağlı bir belge başlatmasını sağlar.  
  
 [Idebugdocument arabirimi](../winscript/reference/idebugdocument-interface.md)  
 Tüm hata ayıklama belgeler için temel arabirim.  
  
 [Idebugdocumenttext arabirimi](../winscript/reference/idebugdocumenttext-interface.md)  
 Hata ayıklama belge salt metin sürümü erişim sağlar.  
  
 [Idebugdocumenttextauthor arabirimi](../winscript/reference/idebugdocumenttextauthor-interface.md)  
 Hata ayıklama belge salt metin sürümünü düzenlemeyi sağlar.  
  
 [Idebugdocumentcontext arabirimi](../winscript/reference/idebugdocumentcontext-interface.md)  
 Ayıklanacak belgenin bir bölümünü soyut bir gösterimini sağlar.  
  
 Ana bilgisayar adına göre PDM uygulanan arabirimler:  
  
 [Idebugapplicationnode arabirimi](../winscript/reference/idebugapplicationnode-interface.md)  
 İşlevselliğini genişleten `IDebugDocumentProvider` proje ağacı bağlamında sağlayarak arabirimi.  
  
## <a name="debugger-ide"></a>hata ayıklayıcı IDE  
 IDE bir dilden bağımsız hata ayıklama UI'dır. Şu olanakları sunar:  
  
-   Belge görüntüleyiciler/düzenleyiciler.  
  
-   Kesme yönetimi.  
  
-   İfade değerlendirme ve Gözcü pencerelerini.  
  
-   Çerçeve gözatma yığın.  
  
-   Nesne/sınıfı tarama.  
  
-   Sanal uygulama yapısı tarama.  
  
 Hata ayıklayıcı tarafından uygulanan arabirimler:  
  
 [Iapplicationdebugger arabirimi](../winscript/reference/iapplicationdebugger-interface.md)  
 Hata ayıklayıcı IDE oturumu tarafından kullanıma sunulan birincil arabirimdir.  
  
 [Iapplicationdebuggeruı arabirimi](../winscript/reference/iapplicationdebuggerui-interface.md)  
 Dış bileşen hata ayıklayıcı kullanıcı arabirimini (UI) üzerinde daha fazla denetim sağlar.  
  
 [Idebugexpressioncallback arabirimi](../winscript/reference/idebugexpressioncallback-interface.md)  
 Durum olayları için sağlar `IDebugExpression` değerlendirme devam ediyor.  
  
 [Idebugdocumenttextevents arabirimi](../winscript/reference/idebugdocumenttextevents-interface.md)  
 İlişkili metin belgesi değişiklikleri belirten olaylar sağlar.  
  
 [Idebugapplicationnodeevents arabirimi](../winscript/reference/idebugapplicationnodeevents-interface.md)  
 Olay arabirimi sağlar `IDebugApplicationNode` arabirimi.  
  
### <a name="machine-debug-manager"></a>Makine Hata Ayıklama Yöneticisi  
 Makine Hata Ayıklama Yöneticisi, koruma ve etkin sanal uygulamaların bir listesini numaralandırma sanal uygulamaları ve hata ayıklayıcıları arasında bağlantı noktası sağlar.  
  
 [Idebugsessionprovider arabirimi](../winscript/reference/idebugsessionprovider-interface.md)  
 Hata ayıklama oturumu için çalışan bir uygulama oluşturur.  
  
 [Imachinedebugmanager arabirimi](../winscript/reference/imachinedebugmanager-interface.md)  
 Makine Hata Ayıklama Yöneticisi birincil arabirim.  
  
 [Imachinedebugmanagercookie arabirimi](../winscript/reference/imachinedebugmanagercookie-interface.md)  
 Benzer şekilde `IMachineDebugManager` arabirimi, ancak bu destekler hata ayıklama tanımlama bilgilerini arabirim.  
  
 [Imachinedebugmanagerevents arabirimi](../winscript/reference/imachinedebugmanagerevents-interface.md)  
 Sinyalleri çalışmasını değişiklikleri Makine Hata Ayıklama Yöneticisi tarafından tutulan uygulama listesi.  
  
 [Ienumremotedebugapplications arabirimi](../winscript/reference/ienumremotedebugapplications-interface.md)  
 Bir makine üzerinde çalışan uygulamaları numaralandırır.  
  
### <a name="process-debug-manager"></a>İşlem Hata Ayıklama Yöneticisi  
 PDM şunları yapar:  
  
-   Birden çok dil motorları, hata ayıklama eşitler.  
  
-   Debuggable belgeleri ağacının tutar.  
  
-   Birleştirmeler çerçeveler yığın.  
  
-   Kesme noktaları ve dil motorları arasında adımlama düzenler.  
  
-   İş parçacığı izler.  
  
-   Zaman uyumsuz işleme için hata ayıklayıcı iş parçacığı tutar.  
  
-   Makine Hata Ayıklama Yöneticisi ve IDE hata ayıklayıcısı ile iletişim kurar.  
  
 İşlem Hata Ayıklama Yöneticisi tarafından sağlanan arabirimleri aşağıda verilmiştir.  
  
 [Iprocessdebugmanager arabirimi](../winscript/reference/iprocessdebugmanager-interface.md)  
 İşlem Hata Ayıklama Yöneticisi'ni birincil arabirim. Bu arabirim oluşturmak, eklemek veya bir sanal uygulamayı bir işlemden kaldırın.  
  
 [Iremotedebugapplication arabirimi](../winscript/reference/iremotedebugapplication-interface.md)  
 Çalışan bir uygulama temsil eder.  
  
 [Idebugapplication arabirimi](../winscript/reference/idebugapplication-interface.md)  
 Uzaktan erişilebilir olmayan hata ayıklama yöntemlerini kullanmak için dil motorları ve ana bilgisayar tarafından gösterir.  
  
 [Iremotedebugapplicationthread arabirimi](../winscript/reference/iremotedebugapplicationthread-interface.md)  
 Belirli bir uygulama içinde yürütme iş parçacığı temsil eder.  
  
 [Idebugapplicationthread arabirimi](../winscript/reference/idebugapplicationthread-interface.md)  
 Dil motorları ve ana iş parçacığı eşitleme sağlamak ve iş parçacığına özgü, hata ayıklama durum bilgileri korumak için sağlar.  
  
 [Ienumremotedebugapplicationthreads arabirimi](../winscript/reference/ienumremotedebugapplicationthreads-interface.md)  
 Bir uygulama içinde çalışan iş parçacıkları numaralandırır.  
  
 [Idebugthreadcall arabirimi](../winscript/reference/idebugthreadcall-interface.md)  
 Dağıtımları sıralanmış çağırır.  
  
 [Idebugapplicationnode arabirimi](../winscript/reference/idebugapplicationnode-interface.md)  
 Hiyerarşideki bir belge için bir konum tutar.  
  
 [Ienumdebugapplicationnodes arabirimi](../winscript/reference/ienumdebugapplicationnodes-interface.md)  
 Bir uygulama ile ilişkili bir düğümün alt öğelerinin numaralandırır.  
  
 [Ienumdebugstackframes arabirimi](../winscript/reference/ienumdebugstackframes-interface.md)  
 Yığın çerçeveleri motorlarından birleştirilmiş bir iş parçacığı, karşılık gelen sıralar.  
  
 [Idebugcookie arabirimi](../winscript/reference/idebugcookie-interface.md)  
 Komut dosyası hata ayıklayıcıları ayarlanması hata ayıklama tanımlama bilgisi sağlar.  
  
 [Idebughelper arabirimi](../winscript/reference/idebughelper-interface.md)  
 Nesne tarayıcılar için bir üreteci ve komut dosyası motorları için basit bağlantı noktaları olarak görev yapar.  
  
 [Isimpleconnectionpoint arabirimi](../winscript/reference/isimpleconnectionpoint-interface.md)  
 Açıklayan ve komut dosyası motorları için belirli bağlantı noktasında tetiklenen olayları numaralandırma için basit bir yol sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etkin komut dosyası hata ayıklayıcı arabirimleri](../winscript/reference/active-script-debugger-interfaces.md)