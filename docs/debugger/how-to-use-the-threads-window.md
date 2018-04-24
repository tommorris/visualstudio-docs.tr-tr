---
title: İş parçacıkları penceresini kullanarak birden çok iş parçacıklı uygulamada hata ayıklama | Microsoft Docs
ms.custom: H1HackMay2017
ms.date: 05/18/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- multithreaded debugging, tutorial
- tutorials, multithreaded debugging
ms.assetid: adfbe002-3d7b-42a9-b42a-5ac0903dfc25
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 09fccc98f52c80a00c2c6a215742ae25b2fc7a4d
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="walkthrough-debug-a-multithreaded-application-in-visual-studio-using-the-threads-window"></a>İzlenecek yol: Visual Studio iş parçacıkları penceresini kullanarak birden çok iş parçacıklı uygulamada hata ayıklama
Visual Studio sağlayan bir **iş parçacığı** penceresini açın ve başka bir kullanıcı arabirimi öğeleri birden çok iş parçacıklı uygulamalarda hata ayıklama yardımcı olacak. Bu öğretici nasıl kullanılacağını gösterir **iş parçacığı** penceresi ve **hata ayıklama konumu** araç. Diğer araçları hakkında daha fazla bilgi için bkz: [çok iş parçacıklı uygulamalarda hata ayıklama başlamak](../debugger/get-started-debugging-multithreaded-apps.md). Bu öğretici yalnızca birkaç dakika sürer ancak tamamlanması, çok iş parçacıklı uygulamalarda hata ayıklama için özelliklerle alışmanızı.   
  
Bu öğreticiye başlamadan birden çok iş parçacıklı uygulama projesi gerekir. Bu projeyi oluşturmak için burada listelenen adımları izleyin.  
  
#### <a name="to-create-the-multithreaded-app-project"></a>Birden çok iş parçacıklı uygulama projesi oluşturmak için  
  
1.  Üzerinde **dosya** menüsünde seçin **yeni** ve ardından **proje**.  
  
     **Yeni proje** iletişim kutusu görüntülenir.  
  
2.  İçinde **proje türü**s kutusunda, tercih ettiğiniz dili seçin: **Visual Basic**, **Visual C#**, veya **Visual C++**.  
  
3.  İçinde **şablonları** kutusunda, seçin **konsol uygulaması**.  
  
4.  İçinde **adı** kutusuna MyThreadWalkthroughApp adı yazın.  
  
5.  **Tamam**'ı tıklatın.  
  
     Yeni bir konsol projesi görüntülenir. Proje oluşturduğunuzda bir kaynak dosya görünür. Seçtiğiniz dil bağlı olarak, kaynak dosya Module1.vb, Program.cs veya MyThreadWalkthroughApp.cpp olarak adlandırılabilir  
  
6.  Kaynak dosyasında görünen kodu silin ve konunun bölümünde "Bir iş parçacığı oluşturulurken" görünür örnek kod ile değiştirin [oluşturma iş parçacıkları ve başlangıç saati veri geçirme](/dotnet/standard/threading/creating-threads-and-passing-data-at-start-time).  
  
7.  Üzerinde **dosya** menüsünde tıklatın **Tümünü Kaydet**.  
  
#### <a name="to-begin-the-tutorial"></a>Öğretici başlatmak için  
  
-   Kaynak Kodu Düzenleyicisi'nde, aşağıdaki kodu bakın:  
  
    ```VB  
    Thread.Sleep(3000)   
    Console.WriteLine()
    ```  
  
    ```csharp  
    Thread.Sleep(3000);  
    Console.WriteLine();  
    ```  
  
    ```C++  
    Thread::Sleep(3000);  
    Console.WriteLine();  
    ```  
  
#### <a name="to-start-debugging"></a>Hata ayıklama başlatılamıyor  
  
1.  Sol cilt payı tıklatın `Console.WriteLine` yeni bir kesme noktası eklemek için deyimi.  
  
     Cilt payını içinde kaynak kod düzenleyicisinde sol tarafında, kırmızı bir daire görünür. Bu, bir kesme noktası bu konumda şimdi ayarlandığını gösterir.  
  
2.  Üzerinde **hata ayıklama** menüsünde tıklatın **hata ayıklamayı Başlat** (**F5**).  
  
     Hata ayıklama başlatır, çalıştırmak için konsol uygulaması başlatıldığında ve kesme sonra durur.  
  
3.  Konsol uygulama penceresi odak bu noktada varsa, tıklayın [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] odağı dönmek için pencereyi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
4.  Kaynak Kodu Düzenleyicisi'nde, aşağıdaki kodu içeren satırı bulun:  
  
    ```VB  
    Thread.Sleep(5000)   
    ```  
  
    ```csharp  
    Thread.Sleep(3000);  
    ```  
  
    ```C++  
    Thread::Sleep(3000);  
    ```
  
#### <a name="to-discover-the-thread-marker"></a>İş parçacığı işaret bulmak için  

1.  Hata ayıklama araç çubuğunda **kaynak iş parçacıkları Göster** düğmesini ![kaynak iş parçacıkları Göster](../debugger/media/dbg-multithreaded-show-threads.png "ThreadMarker"). 
  
2.  Cilt payını penceresinin sol tarafındaki bakın. Bu satırda göreceğiniz bir *iş parçacığı işaret* simgesi ![iş parçacığı işaret](../debugger/media/dbg-thread-marker.png "ThreadMarker") iki havlu iş parçacığı benzer. İş parçacığı işaret bir iş parçacığı bu konumda durdurulduğunu gösterir.  
  
3.  İşaretçinin iş parçacığı işaret gelin. Bir DataTip görünür. DataTip her durdurulan iş parçacığı için adı ve iş parçacığı kimliği numarasını belirtir. Bu durumda, yalnızca bir iş parçacığı adı büyük olasılıkla yok `<noname>`.  

    > [!TIP]
    > Adsız iş parçacığı yeniden adlandırarak tanımlamak daha yararlı olabilir. İş parçacıkları penceresini seçin **yeniden adlandırma** sağ tıklayarak sonra **adı** iş parçacığı satırında sütun.
  
4.  Kısayol menüsünde kullanılabilir seçenekleri görmek için iş parçacığı işaret sağ tıklayın. 
    
  
## <a name="flagging-and-unflagging-threads"></a>Bayrak ekleme ve Unflagging iş parçacıkları  
Özel dikkat vermek istediğiniz iş parçacıklarını bayrakla işaretleyebilirsiniz. İş parçacığı işaretlemesini bir iyi önemli iş parçacığı izlemek için ve önem verdiğiniz olmayan iş parçacıklarının yoksay yoludur.  
  
#### <a name="to-flag-threads"></a>İş parçacığı bayrak atamak için   

1.  Üzerinde **Görünüm** menüsündeki **araç çubukları**.  
  
    Olduğundan emin olun **hata ayıklama konumu** araç seçilidir.

2.  Git **hata ayıklama konumu** araç çubuğu ve tıklatın **iş parçacığı** listesi.  
  
    > [!NOTE]
    >  Bu araç üç belirgin listeleriyle tanıyabilmesi: **işlem**, **iş parçacığı**, ve **yığın çerçevesi**.  
  
3.  Kaç tane iş parçacığı listede dikkat edin.  
  
4.  Kaynak kod düzenleyicisine geri dönün ve iş parçacığı işaretleyicisini sağ ![iş parçacığı işaret](../debugger/media/dbg-thread-marker.png "ThreadMarker") yeniden.  
  
5.  Kısayol menüsünde işaret **bayrağı**, iş parçacığı adı ve kimlik numarasını'ı tıklatın.  
  
6.  Geri dönerek **hata ayıklama konumu** araç ve bulma **Göster yalnızca işaretlenen iş parçacığı** simgesi ![bayrağı iş parçacıkları Göster](../debugger/media/dbg-threads-show-flagged.png "ThreadMarker") için sağ **iş parçacığı** listesi.  
  
    Düğmesine bayrakları simgesi önce soluk. Şimdi, etkin bir düğmeye geldi.  
  
7.  Tıklatın **Göster yalnızca işaretlenen iş parçacığı** simgesi.  
  
    Bayrak eklenmiş iş parçacığı şimdi listede görüntülenir. (Geri geçiş yapmak için tek bayrağı düğmesini tıklatabilirsiniz **tüm iş parçacıkları Göster** modu.)

8. İş parçacıkları penceresini seçerek açın **hata ayıklama > Windows > İş parçacığı**.

    ![İş parçacıkları penceresi](../debugger/media/dbg-threads-window.png "ThreadsWindow")  
  
    İçinde **iş parçacığı** penceresinde bayraklı iş parçacığına sahip bağlı bir belirgin kırmızı bayrak simgesi.

    > [!TIP]
    > Bazı iş parçacıklarını bayrakla zaman bir kod düzenleyicisinde kod satırı sağ tıklatın ve seçin **çalıştırmak işaretlenen iş parçacığı imleç** (tüm iş parçacıklarını bayrakla koda ulaşıp seçtiğinizden emin olun). Bu iş parçacığı tarafından yürütme sırasını daha kolay denetleme kolaylaştırarak kodunun seçili satırındaki duraklatılır [dondurma ve iş parçacıkları çözme](#bkmk_freeze).
  
11. Kaynak Kod düzenleyicisinde iş parçacığı işaret tekrar sağ tıklayın.  
  
     Hangi seçimlere kısayol menüsünde kullanılabilir dikkat edin. Yerine **bayrağı**, bunu şimdi bakın **Unflag**. ' A tıklamayın **Unflag**.  

     İş parçacıklarını bayrakla konusunda bilgi edinmek için sonraki yordama gidin.  
  
#### <a name="to-unflag-threads"></a>İş parçacıklarını bayrakla için  
  
1.  İçinde **iş parçacığı** penceresinde bayraklı iş parçacığına karşılık gelen satırını sağ tıklayın.  
  
     Bir kısayol menüsü görüntülenir. Seçeneklerine sahip **Unflag** ve **tüm iş parçacıklarını bayrakla**.  
  
2.  İş parçacığı bayrakla için tıklatın **Unflag**.  

    Bakmak **hata ayıklama konumu** yeniden araç. **Göster yalnızca işaretlenen iş parçacığı** düğmesini yeniden görünüyorsa. Yalnızca bayraklı iş parçacığı işareti kaldırıldı. Bayrak eklenmiş iş parçacığı olduğundan, araç için geri geçti **tüm iş parçacıkları Göster** modu. Tıklatın **iş parçacığı** listelemek ve tüm iş parçacıklarının görebildiğini doğrulayın.  
  
5.  Geri dönerek **iş parçacığı** penceresi ve bilgi sütunu inceleyin.  
  
    İlk sütunda, iş parçacığı listesinin her satırda bir bayrak anahat simgesi fark edeceksiniz. (Anahattı iş parçacığı bayrak yok anlamına gelir.)  
  
6.  İki iş parçacığı, ikinci ve üçüncü listenin en üstündeki bayrağı Anahat simgeleri tıklatın. 

    Bayrağı simgeleri boş anahatları yerine düz kırmızı olur.  
  
7.  Bayrak sütunu üstündeki düğmesini tıklatın.  
  
    Düğme tıklatıldığında değiştirilen iş parçacığı listesi sırası. İş parçacığı listesi şimdi üstte bayraklı iş parçacığı ile sıralanır.  
  
8.  Yeniden Bayrak sütunu üstündeki düğmesini tıklatın.  
  
    Sıralama düzenini yeniden değiştirildi.  
  
## <a name="more-about-the-threads-window"></a>İş parçacıkları penceresi hakkında daha fazla bilgi  
  
#### <a name="to-learn-more-about-the-threads-window"></a>İş parçacıkları penceresi hakkında daha fazla bilgi için  
  
1.  İçinde **iş parçacığı** penceresinde soldan üçüncü sütununu inceleyin. Bu sütunun üstündeki düğmesi diyor **kimliği**.  
  
2.  Tıklatın **kimliği**.  
  
     İş parçacığı listesi şimdi iş parçacığı kimliği numarasına göre sıralanır.  
  
3.  Listedeki herhangi bir iş parçacığı sağ tıklayın. Kısayol menüsünde **onaltılı görüntü**.  
  
     İş parçacığı kimliği sayıların biçimini değiştirilir.  
  
4.  Fare işaretçisini üzerine gelerek **konumu** listesindeki herhangi bir iş parçacığı için sütun.  
  
     Kısa süreli bir gecikmeden sonra bir DataTip görünür. İş parçacığı için kısmi çağrı yığını gösterir.

     > [!TIP]
     > Çağrı yığınları iş parçacığı için grafik görünümü için açık [Paralel Yığınlar](../debugger/using-the-parallel-stacks-window.md) penceresi (hata ayıklama sırasında seçin **hata ayıklama / Windows / Paralel Yığınlar**).  
  
5.  Etiketli soldan dördüncü sütununa bakın **kategori**. İş parçacığı kategoride sınıflandırılır.  
  
     Bir işlemde oluşturulan ilk iş parçacığı ana iş parçacığı olarak adlandırılır. İş parçacığı listesinde bulun.  
  
6.  Ana iş parçacığı sağ tıklayın ve ardından **geçiş iş parçacığına**.  
  
     A **kesme modu** penceresi görüntülenir. Hata ayıklayıcı (ana iş parçacığı olduğundan) görüntülemek herhangi bir kod gerçekleştirmektedir olduğunu bildirir.   
  
7.  Bakmak **çağrı yığını** penceresi ve **hata ayıklama konumu** araç.  
  
     İçeriğini **çağrı yığını** penceresi değişti. 

## <a name="bkmk_freeze"></a> Dondurma ve iş parçacığı yürütmeyi çözme 

Dondurma ve çözme (askıya alma ve sürdürme) iş parçacıklarının iş gerçekleştirmek sırasını denetlemek için iş parçacığı sayısı. Bu, kilitlenmeleri gibi eşzamanlılık sorunları çözün ve koşullar durumunu yardımcı olabilir.

> [!TIP]
> (Ayrıca genel bir hata ayıklama senaryosu) diğer iş parçacıklarını dondurmak olmadan tek bir iş parçacığı izleyin istiyorsanız bkz [çok iş parçacıklı uygulamalarda hata ayıklama başlamak](../debugger/get-started-debugging-multithreaded-apps.md#bkmk_follow_a_thread).
  
#### <a name="to-freeze-and-unfreeze-threads"></a>Freeze ve iş parçacıkları Çöz  
  
1.  İçinde **iş parçacığı** penceresinde herhangi bir iş parçacığı sağ tıklayın ve ardından **Dondur**.  
  
2.  İkinci sütununa (geçerli iş parçacığı sütun) bakın. Duraklatma simgesinin şimdi var gibi görünüyor. Bu duraklatma simgesinin iş parçacığı donuk olduğunu gösterir.  
  
3.  Göster **askıya sayısı** içinde seçerek sütun **sütunları** listesi.

    İş parçacığı için askıya alma sayısı 1 sunulmuştur.  
  
4.  Dondurulmuş iş parçacığı sağ tıklayın ve ardından **çözme**.  
  
     Geçerli iş parçacığı sütun ve **askıya sayısı** sütun Değiştir. 
  
## <a name="switching-the-to-another-thread"></a>Geçiş için başka bir iş parçacığı 
  
#### <a name="to-switch-threads"></a>Geçiş yapmak için iş parçacıkları  
  
1.  İçinde **iş parçacığı** penceresinde, soldaki (geçerli iş parçacığı sütun) ikinci sütundaki inceleyin. Bu sütunun üstündeki düğmesi metin veya simgesi vardır.
  
2.  Geçerli iş parçacığı sütununa bakın ve bir iş parçacığı sarı bir ok olduğuna dikkat edin. Sarı ok bu iş parçacığı (yürütme işaretçi geçerli konumunu budur) geçerli iş parçacığının olduğunu gösterir.
  
    Geçerli iş parçacığı simgesi gördüğünüz iş parçacığı kimliği numarasını not edin. Başka bir iş parçacığı için geçerli iş parçacığı simgesi taşınır, ancak geri tamamladığınızda koymak gerekir. 
  
3.  Başka bir iş parçacığı sağ tıklayın ve ardından **geçiş iş parçacığına**.  
  
4.  Bakmak **çağrı yığını** Kaynak Kod Düzenleyicisi penceresinde. İçeriği değişmiş.  
  
5.  Bakmak **hata ayıklama konumu** araç. Geçerli iş parçacığı simgesi vardır, çok değişti.  
  
6.  Git **hata ayıklama konumu** araç. Farklı bir iş parçacığından seçin **iş parçacığı** listesi.  
  
7.  Bakmak **iş parçacığı** penceresi. Geçerli iş parçacığı simgesi değişti.  
  
8. Kaynak Kod düzenleyicisinde iş parçacığı işaret sağ tıklayın. Kısayol menüsünde işaret **geçiş iş parçacığına** ve bir iş parçacığı adı/kimlik numarası'ı tıklatın.  
  
     Geçerli iş parçacığı simgesi başka bir iş parçacığına değiştirme üç şekilde şimdi gördünüz: kullanarak **iş parçacığı** penceresinde **iş parçacığı** listesinde **hata ayıklama konumu** araç ve Kaynak Kod düzenleyicisinde iş parçacığı işaretçisi.  
  
     İş parçacığı işaretçisi ile belirli o konumda durdurulan iş parçacıklarını geçiş yapabilirsiniz. Kullanarak **iş parçacığı** penceresi ve **hata ayıklama konumu** araç, tüm iş parçacığına geçiş.   
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birden çok iş parçacıklı uygulamalarda hata ayıklama](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Nasıl yapılır: hata ayıklarken başka bir iş parçacığı için geçiş](../debugger/how-to-switch-to-another-thread-while-debugging.md)
