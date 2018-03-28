---
title: 'İzlenecek yol: paralel uygulamada hata ayıklama | Microsoft Docs'
ms.custom: H1HackMay2017
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, parallel tasks walkthrough
- parallel stacks toolwindow
- parallel tasks toolwindow
- parallel applications, debugging [C++]
- debugging, parallel applications
- parallel applications, debugging [Visual Basic]
- parallel applications, debugging [C#]
ms.assetid: 2820ac4c-c893-4d87-8c62-83981d561493
caps.latest.revision: ''
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: af74685428f15cebdcaf0992ae3ad529f2dd41b8
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2018
---
# <a name="walkthrough-debugging-a-parallel-application-in-visual-studio"></a>İzlenecek yol: Visual Studio paralel uygulamada hata ayıklama
Bu kılavuzda nasıl kullanılacağını gösterir **Paralel Görevler** ve **Paralel Yığınlar** paralel uygulamada hata ayıklamak için windows. Bu windows anlamanıza ve kullanan kodu çalışma zamanı davranışını doğrulayın Yardım [görev paralel kitaplığı (TPL)](/dotnet/standard/parallel-programming/task-parallel-library-tpl) veya [eşzamanlılık çalışma zamanı](/cpp/parallel/concrt/concurrency-runtime). Bu kılavuzda yerleşik kesme noktaları olan örnek kodu sağlıyor. Kod keser sonra izlenecek nasıl kullanılacağını gösterir **Paralel Görevler** ve **Paralel Yığınlar** windows bunu inceleyin.  
  
 Bu kılavuzda, bu görevleri öğretilmektedir:  
  
-   Tüm iş parçacıklarının çağrı yığınları tek bir görünümde görüntülemek nasıl.  
  
-   Listesini görüntülemek nasıl `System.Threading.Tasks.Task` uygulamanızda oluşturulan örnekleri.  
  
-   İş parçacığı yerine görevlerin gerçek çağrı yığınları görüntülemek nasıl.  
  
-   Koddan gitmek nasıl **Paralel Görevler** ve **Paralel Yığınlar** windows.  
  
-   Nasıl windows ölçek gruplandırma, yakınlaştırma ve ilgili diğer özellikleri ile başa çıkacak.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzda varsayar **sadece kendi kodumu** etkin (varsayılan olarak, Visual Studio'nun daha yeni sürümleri etkin). Üzerinde **Araçları** menüsünde tıklatın **seçenekleri**, genişletin **hata ayıklama** düğümü, select **genel**ve ardından **etkinleştir Yalnızca kendi kodum (sadece yönetilen)**. Bu özellik ayarlanmazsa, bu kılavuzda kullanmaya devam edebilirsiniz, ancak sonuçlarınızı çizimler farklı olabilir.  
  
## <a name="c-sample"></a>C# örnek  
 C# örnek kullanırsanız, bu izlenecek yol da harici kod gizli olduğunu varsayar. Harici kod görüntülenip görüntülenmeyeceğini geçiş yapmak için sağ **adı** tablo üstbilgisinin **çağrı yığını** penceresinde ve ardından seçin veya temizleyin **Göster harici kod**. Bu özellik ayarlanmazsa, bu kılavuzda kullanmaya devam edebilirsiniz, ancak sonuçlarınızı çizimler farklı olabilir.  
  
## <a name="c-sample"></a>C++ örnek  
 C++ örnek kullanırsanız, bu konudaki dış koduna başvurular yoksayabilirsiniz. Harici kod yalnızca C# örnek için geçerlidir.  
  
## <a name="illustrations"></a>Çizimler  
 Bu konudaki resimler C# örnek çalıştıran dört çekirdekli bilgisayarda kayıtlı. Bu izlenecek yolu tamamlamak için diğer yapılandırmaları kullanabilmenize karşın, çizimler bilgisayarınızda görüntülenen alanından farklı olabilir.  
  
## <a name="creating-the-sample-project"></a>Örnek Proje oluşturma  
 Bu kılavuzda örnek kod hiçbir şey yapmaz bir uygulamadır. Yalnızca araç pencereleri paralel uygulamada hata ayıklama için nasıl kullanılacağını anlamak için belirtilir.  
  
#### <a name="to-create-the-sample-project"></a>Örnek proje oluşturmak için  
  
1.  Visual Studio'da üzerinde **dosya** menüsündeki **yeni** ve ardından **proje**.  
  
2.  İçinde **yüklü şablonlar** bölmesinde, Visual C#, Visual Basic ya da Visual C++ seçin. Yönetilen diller için emin [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] framework kutusunda görüntülenir.  
  
3.  Seçin **konsol uygulaması** ve ardından **Tamam**. Varsayılan hata ayıklama yapılandırmasını da kalır.  
  
4.  Projede .cpp, .cs veya .vb kod dosyasını açın. Bir boş kod dosyası oluşturmak için içeriğini silin.  
  
5.  Seçilen dil için aşağıdaki kodu boş kod dosyasına yapıştırın.  
  
 [!code-csharp[Debugger#1](../debugger/codesnippet/CSharp/walkthrough-debugging-a-parallel-application_1.cs)]
 [!code-cpp[Debugger#1](../debugger/codesnippet/CPP/walkthrough-debugging-a-parallel-application_1.cpp)]
 [!code-vb[Debugger#1](../debugger/codesnippet/VisualBasic/walkthrough-debugging-a-parallel-application_1.vb)]  
  
1.  Üzerinde **dosya** menüsünde tıklatın **Tümünü Kaydet**.  
  
2.  Üzerinde **yapı** menüsünde tıklatın **çözümü yeniden derle**.  
  
     Dört çağrıları olduğuna dikkat edin `Debugger.Break` (`DebugBreak` C++ örneğinde) bu nedenle, kesme noktaları ekleme gerekmez; yalnızca uygulamayı çalıştıran neden olur, en çok dört kez hata ayıklayıcısı'ndaki ayırmak.  
  
## <a name="using-the-parallel-stacks-window-threads-view"></a>Paralel kullanılarak yığınlar penceresini: iş parçacıkları görünümü  
 Üzerinde **hata ayıklama** menüsünde tıklatın **hata ayıklamayı Başlat**. İlk kesme noktası isabet bekler.  
  
#### <a name="to-view-the-call-stack-of-a-single-thread"></a>Tek bir iş parçacığı çağrı yığınını görüntülemek için  
  
1.  Üzerinde **hata ayıklama** menüsündeki **Windows** ve ardından **iş parçacığı**. Yerleştirme **iş parçacığı** penceresinin alt kısmındaki Visual Studio.  
  
2.  Üzerinde **hata ayıklama** menüsündeki **Windows** ve ardından **çağrı yığını**. Yerleştirme **çağrı yığını** Visual Studio altındaki penceresi.  
  
3.  Bir iş parçacığında çift **iş parçacığı** geçerli hale penceresi. Geçerli iş parçacığı sarı bir ok vardır. Geçerli iş parçacığının değiştirdiğinizde, çağrı yığını görüntülenir **çağrı yığını** penceresi.  
  
#### <a name="to-examine-the-parallel-stacks-window"></a>Paralel Yığınlar penceresini incelemek için  
  
1.  Üzerinde **hata ayıklama** menüsündeki **Windows** ve ardından **Paralel Yığınlar**. Olduğundan emin olun **iş parçacığı** sol üst köşesinde kutusunda seçilir.  
  
     Kullanarak **Paralel Yığınlar** penceresi, tek bir görünümde aynı anda birden fazla çağrı yığınları görüntüleyebilirsiniz. Aşağıdaki çizimde gösterildiği **Paralel Yığınlar** penceresi yukarıdaki **çağrı yığını** penceresi.  
  
     ![Paralel Yığınlar penceresini görünümünde iş parçacıkları](../debugger/media/pdb_walkthrough_1.png "PDB_Walkthrough_1")  
  
     Çağrı yığını ana iş parçacığı bir kutusunda görünür ve diğer dört iş parçacığı çağrı yığınları başka bir kutusunda gruplandırılır. Kendi yığın çerçeveleri aynı yöntemi bağlamları paylaştığından dört iş parçacığı birlikte gruplandırılır; diğer bir deyişle, aynı yöntemleri oldukları: `A`, `B`, ve `C`. İş parçacığı kimlikleri ve adları Paylaş aynı kutusu iş parçacığı üzerine gelerek üstbilgi kutusuyla üzerinden görünümüne (**4 iş parçacığı**). Geçerli iş parçacığının kalın olarak görüntülenir.  
  
     ![İş parçacığı kimlikleri ve adları gösterir araç ipucu](../debugger/media/pdb_walkthrough_1a.png "PDB_Walkthrough_1A")  
  
     Sarı ok geçerli iş parçacığının etkin yığın çerçevesi gösterir.
  
     Yığın çerçevelerini göstermek için ne kadar ayrıntı ayarlayabilirsiniz (**modül adlarını**, **parametre türleri**, **parametre adları**, **parametre değerlerini**, **Satır numaralarını** ve **bayt kaydırır**) içinde sağ tıklanarak **çağrı yığını** penceresi.  
  
     Bir kutu çevresinde mavi Vurgu geçerli iş parçacığının bu kutuya bir parçası olduğunu gösterir. Geçerli iş parçacığının Ayrıca araç ipucunda kalın yığın çerçevesi belirtilir. İş parçacıkları penceresi ana iş parçacığı çift tıklarsanız, inceleyebileceğiniz mavi vurgulama **Paralel Yığınlar** penceresi buna göre hareket eder.  
  
     ![Paralel Yığınlar penceresini ana iş parçacığı vurgulanmış](../debugger/media/pdb_walkthrough_1c.png "PDB_Walkthrough_1C")  
  
#### <a name="to-resume-execution-until-the-second-breakpoint"></a>İkinci kesme noktası kadar yürütme devam etmek için  
  
1.  İkinci kesme noktası, üzerinde ulaşılır kadar yürütme devam etmek için **hata ayıklama** menüsünde tıklatın **devam**. Aşağıdaki çizimde, iş parçacığı ağaç ikinci kesme noktasında gösterir.  
  
     ![Birçok dalları gösteren Paralel Yığınlar penceresini](../debugger/media/pdb_walkthrough_2.png "PDB_Walkthrough_2")  
  
     İlk kesme noktasında S.C yöntemleri için S.B S.A dört iş parçacığı tüm geçti. Bilgi hala görünür olduğunu **Paralel Yığınlar** penceresi ancak dört iş parçacığı progressed daha fazla. Bunlardan birini S.D ve ardından G.D. devam Başka bir S.F, S.G ve S.H. devam İki başkalarının S.I ve S.J ve bunları orada bir devamı S.K için oluştu ve diğer kullanıcı olmayan harici koda devam eder.  
  
     Örneğin, kutusu üstbilgisi getirin **1 iş parçacığı** veya **2 iş parçacığı**, iş parçacığı iş parçacıklarının kimlikleri görmek için. İş parçacığı kimlikleri artı diğer çerçeve ayrıntıları görmek için yığın çerçeveleri gelebilirsiniz. Geçerli iş parçacığının mavi Vurgu gösterir ve geçerli iş parçacığının etkin yığın çerçevesi sarı ok gösterir.  
  
     (Satırları interweaved) havlu iş parçacığı simgesi noncurrent iş parçacıklarının etkin yığın çerçeveleri belirtin. İçinde **çağrı yığını** penceresinde, çerçeve geçiş yapmak için S.B çift tıklayın. **Paralel Yığınlar** penceresi bir eğri gösteren yeşil ok simgesini kullanarak geçerli iş parçacığının geçerli yığın çerçevesini gösterir.  
  
     İçinde **iş parçacığı** penceresinde, iş parçacıkları arasında geçiş yapın ve görüntülendiğini görünümünde **Paralel Yığınlar** penceresi güncelleştirilir.  
  
     Kısayol menüsünü kullanarak başka bir iş parçacığı veya başka bir iş parçacığı, başka bir çerçeve geçebilirsiniz **Paralel Yığınlar** penceresi. Örneğin, S.J sağ tıklayın, fareyle **anahtar çerçevesinin**ve ardından bir komutu.  
  
     ![Paralel Yığınlar yürütme yolu](../debugger/media/pdb_walkthrough_2b.png "PDB_Walkthrough_2B")  
  
     S.C sağ tıklayın ve fareyle **anahtar çerçevesinin**. Komutlarından birini geçerli iş parçacığının yığın çerçevesi belirten bir onay işareti bulunur. (Yalnızca yeşil ok taşınır) iş parçacığı bu çerçeveye geçebilir veya (Mavi Vurgu de taşınır) başka bir iş parçacığı için geçiş yapabilirsiniz. Aşağıdaki çizimde alt gösterir.  
  
     ![J geçerliyken C üzerinde 2 seçenekle Yığınlar menüsü](../debugger/media/pdb_walkthrough_3.png "PDB_Walkthrough_3")  
  
     Bir yöntem bağlamı tek bir yığın çerçevesi ile ilişkili olduğunda kutusu üstbilgisi görüntüler **1 iş parçacığı** ve ona çift tıklayarak geçin. 1'den fazla çerçeve ilişkili olan bir yöntemi bağlamı çift tıklayın, ardından menü otomatik olarak açılır. Yöntemi bağlamları gezinirken sağ siyah üçgen dikkat edin. Bu üçgen tıklatarak kısayol menüsünü görüntüler.  
  
     Birçok iş parçacığı içeren büyük uygulamalar için yalnızca bir alt iş parçacığı üzerinde odaklanmak isteyebilirsiniz. **Paralel Yığınlar** pencere, yalnızca bayraklı iş parçacığı için çağrı yığınları görüntüleyebilir. İş parçacığı bayrak için kısayol menüsü veya bir iş parçacığı ilk hücrenin kullanın. 

     Araç çubuğunda tıklatın **Göster'i yalnızca işaretlenen** liste kutusu yanındaki düğmesi.  

     ![Paralel Yığınlar penceresini ve araç ipucu](../debugger/media/pdb_walkthrough_3a.png "PDB_Walkthrough_3A")  

     Şimdi, yalnızca bayraklı iş parçacığı görünür **Paralel Yığınlar** penceresi.
  
#### <a name="to-resume-execution-until-the-third-breakpoint"></a>Yürütme üçüncü kesme noktası kadar devam etmek için  
  
1.  Üçüncü kesme noktası, üzerinde ulaşılır kadar yürütme devam etmek için **hata ayıklama** menüsünde tıklatın **devam**.  
  
     Birden çok iş parçacığı aynı yöntemdir, ancak yöntemi çağrı yığını başında değildi yöntemi farklı kutularında görünür. Geçerli kesme noktasındaki üç iş parçacığı içerdiği ve üç kutularında görünen S.L örneğidir. R. çift tıklatın  
  
     ![Paralel Yığınlar penceresini yürütme yolunda](../debugger/media/pdb_walkthrough_3b.png "PDB_Walkthrough_3B")  
  
     Else göründüğü görebilmeniz için S.L diğer iki kutularına kalın olduğuna dikkat edin. Görmek istiyorsanız S.L çağrısına çerçeveler ve hangi çerçeve onu çağrıları **yöntemi Görünümü Değiştir** araç çubuğunda. Aşağıdaki çizimde yöntemi görünümünü gösterir **Paralel Yığınlar** penceresi.  
  
     ![Paralel Yığınlar penceresini yöntemi görünümünde](../debugger/media/pdb_walkthrough_4.png "PDW_Walkthrough_4")  
  
     Nasıl diyagram seçili yöntemine özetlenebilir ve kendi kutusunda görünümün ortasında konumlandırılmış dikkat edin. Arayanlar ve callees üst ve alt taraflarına görünür. Tıklatın **yöntemi Görünümü Değiştir** düğmesini yeniden bu modda bırakın.  
  
     Kısayol menüsünde **Paralel Yığınlar** penceresine ayrıca aşağıdaki sahip diğer öğeler.  
  
    -   **Onaltılık görüntü** sayıları ondalık ve onaltılık arasında ipuçlarında değiştirir.  
  
    -   **Simge Ayarları** ilgili iletişim kutusunu açın.  
  
    -   **İş parçacığı kaynağında Göster** kaynak kodda iş parçacığı konumunu gösterir, kaynak kodda iş parçacığı işaretçileri görünümünü değiştirir.
  
    -   **Harici kod Göster** bunlar kullanıcı kodunda olmasa bile tüm çerçeveler görüntüler. Diyagramı (, simgeler kendileri için olmadığından, soluk) ek çerçeveleri uyum sağlayacak şekilde genişlet görmek için deneyin.  

2.  İçinde **Paralel Yığınlar** penceresinde olduğundan emin olun **geçerli yığın çerçevesi için otomatik kaydırma** araç çubuğunda açıktır.  

     Büyük diyagramlarını olan ve sonraki kesme adım, geçerli iş parçacığının etkin yığın çerçevesi için otomatik kaydırma görünümüne isteyebilirsiniz; diğer bir deyişle, ilk kesme noktası isabet iş parçacığı.
  
3.  Buna devam etmeden önce **Paralel Yığınlar** penceresinde, tüm yol sola ve tüm aşağı kaydırın.  
  
#### <a name="to-resume-execution-until-the-fourth-breakpoint"></a>Dördüncü kesme noktası kadar yürütme devam etmek için  
  
1.  Dördüncü kesme noktası, üzerinde ulaşılır kadar yürütme devam etmek için **hata ayıklama** menüsünde tıklatın **devam**.  
  
     Bildirim nasıl yer içine görünüm autoscrolled. İş parçacıklarında geçiş **iş parçacığı** penceresi veya anahtar yığın çerçevelerini **çağrı yığını** penceresini açın ve bildirim nasıl görünümü her zaman doğru çerçeveye autoscrolls. Kapatma **otomatik kaydırma geçerli aracı çerçeveye** seçeneği ve farkı görüntüleyin.  
  
     **Kuşbakışı Görünüm** ayrıca büyük diyagramlarda yardımcı **Paralel Yığınlar** penceresi. Varsayılan olarak, **Kuşbakışı Görünüm** açıktır. Ancak, bunu penceresinin sağ alt köşedeki üzerinde kaydırma çubukları arasında düğmesine tıklayarak aşağıdaki çizimde gösterildiği gibi geçiş yapabilirsiniz.  
  
     ![Kuşbakışı&#45;göz Paralel Yığınlar penceresini görünümünde](../debugger/media/pdb_walkthrough_5.png "PDB_Walkthrough_5")  
  
     Kuşbakışı görünüm içinde hızlı bir şekilde diyagramı kaydırmak için dikdörtgen taşıyabilirsiniz.  
  
     Diyagram herhangi bir yönde taşımak için başka bir diyagram boş bir alana tıklayın ve istediğiniz yere sürükleyin yoldur.  
  
     Diyagram ve yakınlaştırmak için tuşuna basın ve fare tekerleğinin taşırken CTRL basılı tutun. Alternatif olarak, araç çubuğundaki Yakınlaştır düğmesini tıklayın ve ardından Yakınlaştırma aracı kullanın.  
  
     Ayrıca yığınları aşağıdan yukarıya, yerine yukarıdan aşağı yönde tıklayarak görüntüleyebilirsiniz **Araçları** tıklatarak menüsünde **seçenekleri**ve ardından seçin ya da altında seçeneğinin işaretini **hataayıklama** düğümü.  
  
2.  On devam etmeden önce **hata ayıklama** menüsünde tıklatın **durdurma hata ayıklama** son yürütme için.  
  
## <a name="using-the-parallel-tasks-window-and-the-tasks-view-of-the-parallel-stacks-window"></a>Paralel Görevler penceresi ve Paralel Yığınlar penceresini görevleri görünümünü kullanma  
 Devam etmeden önce önceki yordamları tamamlamanız önerilir.  
  
#### <a name="to-restart-the-application-until-the-first-breakpoint-is-hit"></a>İlk kesme kadar uygulamayı yeniden isabet  
  
1.  Üzerinde **hata ayıklama** menüsünde tıklatın **hata ayıklamayı Başlat** ve ilk kesme isabet bekleyin.  
  
2.  Üzerinde **hata ayıklama** menüsündeki **Windows** ve ardından **iş parçacığı**. Yerleştirme **iş parçacığı** penceresinin alt kısmındaki Visual Studio.  
  
3.  Üzerinde **hata ayıklama** menüsündeki **Windows** tıklatıp **çağrı yığını**. Yerleştirme **çağrı yığını** Visual Studio altındaki penceresi.  
  
4.  Bir iş parçacığında çift **iş parçacığı** penceresine kılar geçerli. Geçerli iş parçacığı sarı ok vardır. Geçerli iş parçacığının değiştirdiğinizde, diğer windows güncelleştirilir. Ardından, görevleri inceleyeceğiz.  
  
5.  Üzerinde **hata ayıklama** menüsündeki **Windows**ve ardından **görevleri**. Aşağıdaki çizimde gösterildiği **görevleri** penceresi.  
  
     ![Dört çalışan görevler Görevleri penceresinde](../debugger/media/pdb_walkthrough_6.png "PDW_Walkthrough_6")  
  
     Çalışan her görev için aynı adlı özelliği, kimliği ve adını, konumunu (görüntüleyen tüm çağrı yığınına sahip bir araç ipucu bekleyerek) çalışan iş parçacığı tarafından döndürülen Kimliğini okuyabilir. Ayrıca, altında **görev** sütun göreve geçirilen yöntemi görebilirsiniz; diğer bir deyişle, başlangıç noktası.  
  
     Herhangi bir sütunu sıralayabilirsiniz. Sıralama sütunu ve yönünü gösteren sıralama karakter dikkat edin. Sütunları yeniden sağa veya sola sürükleyerek düzenleyebilirsiniz.  
  
     Sarı ok geçerli görev gösterir. Bir görev çift veya kısayol menüsünü kullanarak görevleri geçiş yapabilirsiniz. Görevler geçiş yaptığınızda, temel alınan iş parçacığı geçerli olur ve diğer windows güncelleştirilir.  
  
     Diğerine el ile bir görevden geçtiğinizde, sarı ok taşır, ancak bir beyaz ok hala ayırmak hata ayıklayıcı neden görev gösterir.  
  
#### <a name="to-resume-execution-until-the-second-breakpoint"></a>İkinci kesme noktası kadar yürütme devam etmek için  
  
1.  İkinci kesme noktası, üzerinde ulaşılır kadar yürütme devam etmek için **hata ayıklama** menüsünde tıklatın **devam**.  
  
     Daha önce **durum** sütun tüm görevler etkin olarak gösterilen, ancak şimdi iki görev engellenir. Görevler, farklı nedenlerle engellenebilir. İçinde **durum** sütun, neden engellendi öğrenmek için bir bekleme görev üzerine getirin. Örneğin, aşağıdaki çizimde, görev 4 görev 3 bekliyor.  
  
     ![İki bekletme görevi Görevler penceresinde](../debugger/media/pdb_walkthrough_7.png "PDB_Walkthrough_7")  
  
     Görev 4, 2 göreve atanan iş parçacığı tarafından sahip olunan bir monitörde sırayla bekliyor. (Başlık satırı sağ tıklatın ve seçin **sütunları** > **iş parçacığı atama** görev 2 iş parçacığı atama değerini görüntülemek için).
  
     ![Görev ve araç ipucu Görevleri penceresinde bekleyen](../debugger/media/pdb_walkthrough_7a.png "PDB_Walkthrough_7A")
  
     İlk sütununda bayrağını tıklayarak görev işaretleyebilirsiniz **görevleri** penceresi.  
  
     Aynı hata ayıklama oturumunda farklı kesme noktaları arasındaki görevleri izlemek için veya, çağrı yığınları gösterilmiştir görevleri filtrelemek için bayrak kullanabilirsiniz **Paralel Yığınlar** penceresi.  
  
     Kullanıldığında, **Paralel Yığınlar** penceresi daha önce uygulama iş parçacığı görüntülenebilir. Görünüm **Paralel Yığınlar** penceresini tekrar, ancak bu kez uygulama görevleri görüntüleyin. Seçerek bunu **görevleri** sol üst kutusunda. Aşağıdaki çizimde Görevler görünümü gösterir.  
  
     ![Paralel Yığınlar penceresini görünümünde görevleri](../debugger/media/pdb_walkthrough_8.png "PDB_Walkthrough_8")  
  
     Görev şu anda yürütülmekte değil iş parçacıkları Görevler görünümünde gösterilmez **Paralel Yığınlar** penceresi. Ayrıca, üst ve alt yığınının'da bazı görevler ilgili olmayan yığın çerçeveleri bir görevleri yürütün, iş parçacığı için filtrelenir.  
  
     Görünüm **görevleri** yeniden penceresi. Sütun için bir kısayol menü görmek için herhangi bir sütun başlığını sağ tıklatın.  
  
     Sütun eklemek veya kaldırmak için kısayol menüsünü kullanabilirsiniz. Örneğin, AppDomain sütun seçilmedi; Bu nedenle, listede görüntülenmez. Tıklatın **üst**. **Üst** dört görevlerden herhangi biri için değer içermeyen sütun görünür.  
  
#### <a name="to-resume-execution-until-the-third-breakpoint"></a>Yürütme üçüncü kesme noktası kadar devam etmek için  
  
1.  Üçüncü kesme noktası, üzerinde ulaşılır kadar yürütme devam etmek için **hata ayıklama** menüsünde tıklatın **devam**.  
  
     Yeni bir görev, görev 5, şu anda çalışıyor ve görev 4 şimdi bekliyor. Bekleme görevde üzerine gelerek veya onları neden tarafından görebilirsiniz **durum** penceresi. İçinde **üst** sütun, bu görev 4 görev 5 üst olduğuna dikkat edin.  
  
     Üst-alt ilişkisi daha iyi görselleştirmek için sütun başlık satırı sağ tıklayın ve ardından **üst alt Görünüm**. Aşağıdaki çizimde görmeniz gerekir.  
  
     ![Üst&#45;alt Görünümü Görevleri penceresinde](../debugger/media/pdb_walkthrough_9.png "PDB_Walkthrough_9")  
  
     Görev 4 ve 5 görevini aynı iş parçacığı üzerinde çalıştığını fark (Göster **iş parçacığı atama** gizli ise sütun). Bu bilgiler görüntülenmez **iş parçacığı** ; burada olmasından başka bir yararı görmesini penceresi **görevleri** penceresi. Bunu doğrulamak için görüntülemek **Paralel Yığınlar** penceresi. Görüntülediğiniz emin olun **görevleri**. Görev 4 ve 5 bunları çift tıklatarak bulun **görevleri** penceresi. Bunu yaptığınızda, mavi Vurgu **Paralel Yığınlar** penceresi güncelleştirilir. Üzerinde araç ipuçları tarayarak görevleri 4 ve 5 bulabilir **Paralel Yığınlar** penceresi.  
  
     ![Görev Paralel Yığınlar penceresini görünümünde](../debugger/media/pdb_walkthrough_9a.png "PDB_Walkthrough_9A")  
  
     İçinde **Paralel Yığınlar** penceresinde S.P sağ tıklayın ve ardından **gitmek için iş parçacığı**. İş Parçacıkları görünümü penceresi geçer ve karşılık gelen görünümünde çerçevedir. Aynı iş parçacığı üzerinde hem görevleri görebilirsiniz.  
  
     ![Vurgulanan iş parçacıkları görünümünde iş parçacığı](../debugger/media/pdb_walkthrough_9b.png "PDB_Walkthrough_9B")  
  
     Bu görevler görünümünde başka bir avantajdır **Paralel Yığınlar** karşılaştırılan penceresinde **iş parçacığı** penceresi.  
  
#### <a name="to-resume-execution-until-the-fourth-breakpoint"></a>Dördüncü kesme noktası kadar yürütme devam etmek için  
  
1.  Üçüncü kesme noktası, üzerinde ulaşılır kadar yürütme devam etmek için **hata ayıklama** menüsünde tıklatın **devam**. Tıklatın **kimliği** kimliğine göre sıralamak için sütun başlığını Aşağıdaki çizimde görmeniz gerekir.  
  
     ![Paralel Yığınlar penceresini Devletleri'nde dört görev](../debugger/media/pdb_walkthrough_10.png "PDB_Walkthrough_10")  
  
     Görev 5 tamamlandığından artık görüntülenir. Bu durum, bilgisayarınızda değil ve kilitlenme gösterilmez, bir kez basarak adım **F11**.  
  
     Görev 3 ve görev 4 bekleyen şimdi birbirine ve engellenir. Görev 2 alt ve şimdi zamanlanmış 5 yeni görevleri de vardır. Zamanlanmış Görevler, kodda başladı, ancak henüz çalıştırmadıysanız görevlerdir. Bu nedenle, kendi **konumu** ve **iş parçacığı atama** sütunları boş.  
  
     Görünüm **Paralel Yığınlar** yeniden penceresi. Her kutu üstbilgisi iş parçacığı kimlikleri ve adları gösteren bir araç ipucu sahiptir. Görevler görünümünde geçin **Paralel Yığınlar** penceresi. Aşağıdaki çizimde gösterildiği gibi görev kimliği ve adını ve görev durumunu görüntülemek için bir başlık gelin.  
  
     ![Paralel Yığınlar penceresini üstbilgi ipucunda](../debugger/media/pdb_walkthrough_11.png "PDB_Walkthrough_11")  
  
     Görevleri sütuna göre gruplandırabilirsiniz. İçinde **görevleri** penceresinde sağ **durum** sütun başlığına tıklayın ve sonra **duruma göre gruplandırın**. Aşağıdaki çizimde gösterildiği **görevleri** penceresi durumuna göre gruplandırılır.  
  
     ![Gruplandırılmış Görevleri penceresinde görevleri](../debugger/media/pdb_walkthrough_12.png "PDB_Walkthrough_12")  
  
     Herhangi bir sütuna göre de gruplandırabilirsiniz. Gruplandırma görevler tarafından görevleri alt kümesinde odaklanabilirsiniz. Daraltılabilir her grubun bir arada gruplandırılmış öğelerin sayısı vardır.
  
     Son özelliğini **görevleri** incelemek için penceredir göreve sağ tıklattığınızda görüntülenen kısayol menüsü.  
  
     Kısayol menüsü görev durumuna bağlı olarak farklı komutları görüntüler. Komutları içerebilir **kopya**, **Tümünü Seç**, **onaltılı görüntü**, **geçiş göreve**, **Dondur atanan İş parçacığı**, **, ancak bu tüm iş parçacıklarını dondurmak**, ve **atanan iş parçacığı çözme**, ve **bayrağı**.  
  
     Temel alınan iş parçacığı bir görevi veya görevleri donmasına veya atanan dışındaki tüm iş parçacıklarını dondurmak. Dondurulmuş bir iş parçacığı temsil edilen **görevleri** şekliyle penceredir içinde **iş parçacığı** pencere mavi tarafından *duraklatma* simgesi.  
  
## <a name="summary"></a>Özet  
 Bu kılavuzda gösterilen **Paralel Görevler** ve **Paralel Yığınlar** windows hata ayıklayıcısı. Bu windows birden çok iş parçacıklı kodu kullanın gerçek projelerde kullanın. C++, C# veya Visual Basic yazılan paralel kod inceleyebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çok iş parçacıklı uygulamalarda hata ayıklama](../debugger/walkthrough-debugging-a-parallel-application.md)   
 [Hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md)   
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)   
 [Paralel Programlama](/dotnet/standard/parallel-programming/index)   
 [Eşzamanlılık Çalışma zamanı](/cpp/parallel/concrt/concurrency-runtime)   
 [Paralel Yığınlar penceresini kullanma](../debugger/using-the-parallel-stacks-window.md)   
 [Görevleri penceresini kullanma](../debugger/using-the-tasks-window.md)