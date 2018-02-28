---
title: "Paralel Yığınlar penceresini kullanarak iş parçacıklarını görüntülemek | Microsoft Docs"
ms.custom: 
ms.date: 04/25/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.parallelstacks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, parallel tasks window
ms.assetid: f50efb78-5206-4803-bb42-426ef8133f2f
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 72c7c38dece8924f48298c0b7b661f564f9b1afc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="view-threads-and-tasks-using-the-parallel-stacks-window"></a>İş parçacığı ve Paralel Yığınlar penceresini kullanarak görevleri görüntüleme
**Paralel Yığınlar** penceresi, birden çok iş parçacıklı uygulamalar ayıklarken yararlıdır. Kendi **iş parçacıkları görünümü** gösterir, uygulamanızdaki tüm iş parçacıklarının yığın bilgileri çağırın. İş parçacıkları ve bu iş parçacığı üzerinde yığın çerçeveleri arasında gezinmek olanak sağlar. Yönetilen kodda **Görevler görünümü** gösterir çağrı yığını <xref:System.Threading.Tasks.Task?displayProperty=fullName> nesneleri. Yerel kodda **Görevler görünümü** gösterir çağrı yığını [görev grupları](/cpp/parallel/concrt/task-parallelism-concurrency-runtime), [paralel algoritmalar](/cpp/parallel/concrt/parallel-algorithms), [zaman uyumsuz aracılar](/cpp/parallel/concrt/asynchronous-agents)ve [Basit görevler](/cpp/parallel/concrt/task-scheduler-concurrency-runtime).  
  
## <a name="threads-view"></a>İş Parçacıkları Görünümü  
 Aşağıdaki çizimde ana a B ve ardından dış biraz kod oluştu tek bir iş parçacığı gösterir. Diğer iki iş parçacığı bazı dış koddan başlatıldı ve biri B ve ardından dış biraz kod devam iş parçacıkları ve C ve ardından bazı AnonymousMethod devam diğer iş parçacığı dışında bir oluştu.  
  
 ![Paralel Yığınlar penceresini görünümünde iş parçacıkları](../debugger/media/parallel_stacksthread.png "Parallel_StacksThread")  
  
 Çizimde, geçerli iş parçacığının arama yolu mavi renkte vurgulanır ve iş parçacığı geçerli konumunu (etkin yığın çerçevesi) sarı okla belirtilir. Farklı bir yöntem seçerek geçerli yığın çerçevesini değiştirebilirsiniz **Paralel Yığınlar** penceresi. Bu, aynı zamanda seçtiğiniz yöntemi geçerli iş parçacığı zaten veya başka bir iş parçacığı bir parçası olup olmamasına bağlı olarak geçerli iş parçacığı, geçiş de neden olabilir. Aşağıdaki tabloda ana özelliklerini açıklar **Paralel Yığınlar** çizimde gösterildiği gibi penceresi.  
  
|Belirtme çizgisi harf|Öğe adı|Açıklama|  
|--------------------|------------------|-----------------|  
|BİR|Çağrı yığını Segment veya düğümü|Bir dizi yöntem için bir veya daha fazla iş parçacığı içerir. Ardından ona bağlı ok satır düğüm yok, iş parçacıkları için tüm arama yolu temsil eder.|  
|B|Mavi Vurgusu|Geçerli iş parçacığının çağrısı yolunu gösterir.|  
|C|Ok çizgileri|İş parçacıkları için tüm arama yolu oluşturan düğümleri bağlanır.|  
|D|Düğüm başlığındaki araç ipucu|Bu düğüm, arama yolu paylaşır her iş parçacığı kullanıcı tanımlı adını ve kimlik Numarasını gösterir.|  
|E|Yöntem|Bir veya daha fazla yığın çerçeveleri aynı yöntemi temsil eder.|  
|F|Araç İpucu yöntemi|İş Parçacıkları görünümü'nde, tüm iş parçacıkları bir tabloda benzer gösterir **iş parçacığı** penceresi. Görev Görünümü'nde, tüm görevler bir tabloda benzer gösterir **görevleri** penceresi.|  
  
 Ayrıca, Paralel Yığınlar penceresini gösterir bir **Kuşbakışı Görünüm** grafik penceresine sığmayacak kadar büyük olduğunda ana bölmede simgesi. Tüm grafik penceresinde görmek için simgesine tıklayabilirsiniz.  
  
## <a name="stack-frame-icons"></a>Yığın çerçevesi simgeler  
 Aşağıdaki tabloda, etkin ve geçerli yığın çerçeveleri hakkında bilgi sağlayan simgeleri açıklanmaktadır:  
  
|||  
|-|-|  
|Simge|Açıklama|  
|![Paralel Yığınlar sarı oku](../debugger/media/icon_parallelyellowarrow.gif "Icon_ParallelYellowArrow")|Yöntemi geçerli iş parçacığının geçerli konumunu (etkin yığın çerçevesi) içerdiğini gösterir.|  
|![Paralel Yığınlar İş parçacığı simgesi](../debugger/media/icon_parallelthreads.gif "Icon_ParallelThreads")|Yöntemi, geçerli olmayan bir iş parçacığı geçerli konumunu (etkin yığın çerçevesi) içerdiğini gösterir.|  
|![Paralel Yığınlar yeşil ok](../debugger/media/icon_parallelgreenarrow.gif "Icon_ParallelGreenArrow")|Yöntemi geçerli yığın çerçevesini (geçerli hata ayıklayıcı bağlamını) içerdiğini gösterir. Bu yöntem adı göründüğü tüm düğümlerde kalın.|  
  
## <a name="toolbar-controls"></a>Araç çubuğu denetimleri  
 Aşağıdaki çizimde ve tablo Paralel Yığınlar araç çubuğunda kullanılabilir olan denetimleri açıklar.  
  
 ![Paralel Yığınlar penceresini araç](../debugger/media/parallel_stackstoolbar.png "Parallel_StacksToolbar")  
  
|Belirtme çizgisi harf|Denetim|Açıklama|  
|--------------------|-------------|-----------------|  
|BİR|İş parçacıkları/görevler birleşik giriş kutusu|Görünüm arasında çağrı iş parçacığı yığınları ve çağrı yığınları görevlerin geçiş yapar. Daha fazla bilgi için bkz: Görevler görünümü ve iş parçacıkları görünümü.|  
|B|Yalnızca bayrak Göster|Diğer hata ayıklama pencerelerinde gibi işaretlenmiş yalnızca iş parçacığı için gösterir çağrı yığınları **GPU iş parçacıkları** penceresi ve **paralel Gözcü** penceresi.|  
|C|Yöntem Görünümü Değiştir|Yığın görünümü ve yöntem görünümü arasında geçiş yapar. Daha fazla bilgi için yöntem görünümüne bakın.|  
|D|Geçerli yığın çerçevesini otomatik gidin|Geçerli yığın çerçeve böylece Autoscrolls diyagram görünümünde gösterilir. Bu özellik, geçerli yığın çerçevesini diğer Windows'dan değiştirirken veya yeni bir kesme noktası büyük diyagramlarındaki devreyi zaman yararlıdır.|  
|E|İki durumlu yakınlaştırma denetimi|Gösterir veya yakınlaştırma denetimini gizler. Ayrıca CTRL tuşuna basıp yakınlaştırma denetimi görünürlüğünü bakılmaksızın fare tekerleği kapatma veya CTRL + SHIFT kullanarak yakınlaştırabilirsiniz + yakınlaştırmak için ' +' ve CTRL + SHIFT +'-' uzaklaştırmak için. CTRL + F8 tuşuna basarak, ekran uyacak şekilde yakınlaşır.|  
  
### <a name="context-menu-items"></a>Bağlam menüsü öğeleri  
 Aşağıdaki çizimde ve tablo bir yöntem iş parçacıkları görünümü veya Görevler görünümü sağ tıklattığınızda kullanılabilen kısayol menüsü öğelerini açıklar. Son altı öğeleri doğrudan çağrı yığını penceresinde ödünç ve yeni bir davranış tanıtır.  
  
 ![Paralel Yığınlar penceresini kısayol menüsünde](../debugger/media/parallel_contmenu.png "Parallel_ContMenu")  
  
|Menü Öğesi|Açıklama|  
|---------------|-----------------|  
|Bayrağı|Seçili öğeyi işaretler.|  
|Bayrakla|Seçili öğeyi unflags.|  
|Dondurma|Seçili öğeyi donuyor.|  
|Çözme|Seçili öğeyi thaws.|  
|Göreve (iş parçacığı) Git|Araç çubuğundaki açılan kutu aynı işlevi görür ancak vurgulanmış aynı yığın çerçevesi tutar.|  
|Kaynak koduna Git|Kullanıcı sağ yığın çerçevesi karşılık gelen kaynak kodu konumda gider.|  
|Çerçeve için geçiş|Çağrı yığını penceresinde karşılık gelen menü komutu ile aynıdır. Ancak, Paralel Yığınlar ile birden çok çerçeve bir yönteme karşılık gelebilir. Bu nedenle, her biri belirli yığın çerçevesi temsil eden alt menüler, menü öğesi vardır. Yığın çerçeveleri geçerli iş parçacığı üzerinde ise, o yığın çerçevesi karşılık gelen menü seçilir.|  
|Çözüme Git|Kullanıcı sağ yığın çerçevesi karşılık gelen Ayrıştırılmış kod penceresini konumda gider.|  
|Harici kod Göster|Gösterir veya gizler harici kod.|  
|Onaltılık görüntüleme|Ondalık ve onaltılık görüntü arasında geçiş yapar.|  
|Sembol Yükleme Bilgisi|Karşılık gelen iletişim kutusunu görüntüler.|  
|Simge Ayarları|Karşılık gelen iletişim kutusunu görüntüler.|  
  
## <a name="tasks-view"></a>Görevler görünümü  
 Uygulamanızı kullanıyorsanız <xref:System.Threading.Tasks.Task?displayProperty=fullName> nesneleri (yönetilen kod) veya `task_handle` paralellik ifade etmek için (yerel kod) nesneleri, geçiş yapmak için Paralel Yığınlar penceresini araç açılan kutuda kullanabilir *Görevler görünümü*. Görevler, görev iş parçacıkları yerine çağrı yığınları görüntüler. Görevler görünümü gibi iş parçacıkları Görünümü'ndeki farklılık gösterir:  
  
-   Çağrı yığınları görevleri çalışan iş parçacığı gösterilmez.  
  
-   Çağrı yığınları görevleri çalışan iş parçacığı, üst ve alt görevler ilgilidir en uygun çerçeveleri göstermek için görsel olarak atılır.  
  
-   Birden çok görev bir iş parçacığı üzerinde olduğunda, bu görevlerin çağrı yığınları ayrı düğümlerin içine bölünür.  
  
 Aşağıdaki çizimde, Paralel Yığınlar Görevler görünümü sağ ve sol karşılık gelen iş parçacıkları görünümü gösterir.  
  
 ![Paralel Yığınlar penceresini görünümünde görevleri](../debugger/media/parallel_tasksview.png "Parallel_TasksView")  
  
 Tüm çağrı yığını görmek için yalnızca geri iş parçacığı yığın çerçevesi sağ tıklayarak ve ardından görünümüne **iş parçacığına Git**.  
  
 Bir yöntem gelerek önceki tabloda açıklandığı gibi ek bilgileri görebilirsiniz. Aşağıdaki görüntü iş parçacıkları görünümü ve Görevler görünümü için araç ipucunda bilgileri gösterir.  
  
 ![Paralel Yığınlar penceresini ipuçlarında](../debugger/media/parallel_stack_tooltips.png "Parallel_Stack_Tooltips")  
  
## <a name="method-view"></a>Yöntem görünümü  
 İş Parçacıkları görünümü ya da Görevler görünümü, araç çubuğundaki yöntemi görünümü simgesini tıklatarak geçerli yöntemi grafikte Özet. Yöntem görünümü bir bakışta çağıran veya geçerli yöntemi tarafından çağrılır tüm iş parçacıklarının tüm yöntemleri gösterir. Aşağıdaki çizimde, iş parçacıkları görünümü ve aynı zamanda aynı bilgileri yöntemi görünümünde nasıl göründüğünü gösterir.  
  
 ![Paralel Yığınlar penceresini yöntemi görünümünde](../debugger/media/parallel_methodview.png "Parallel_MethodView")  
  
 Yeni bir yığın çerçevesine geçme tarafından bu yöntem geçerli yöntemi olun ve tüm arayanlar ve yeni yöntemi için callees göstermek yol. Bu, bazı iş parçacığı görünür veya bu yöntem, çağrı yığınları görüntülenip bağlı olarak bu görünümden kayboluyor neden olabilir. Yığın görünümüne dönmek için yeniden yöntemi görünümü araç çubuğu düğmesini tıklatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birden çok iş parçacıklı uygulaması hata ayıklama kullanmaya başlama](../debugger/get-started-debugging-multithreaded-apps.md)   
 [İzlenecek yol: paralel uygulamada hata ayıklama](../debugger/walkthrough-debugging-a-parallel-application.md)   
 [Hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md)   
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)   
 [Paralel Programlama](/dotnet/standard/parallel-programming/index)   
 [Görevleri penceresini kullanma](../debugger/using-the-tasks-window.md)   
 [Task sınıfı](../extensibility/debugger/task-class-internal-members.md)
