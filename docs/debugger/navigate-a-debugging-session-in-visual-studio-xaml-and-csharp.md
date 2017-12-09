---
title: "Visual Studio'da (Xaml ve C#) bir hata ayıklama oturumunda gezinme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 1da33203-333f-4a05-b4e2-8d407c497233
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0c69ff648e2a1ac8c60746f1e7879e80c2063c2a
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2017
---
# <a name="navigate-a-debugging-session-in-visual-studio-xaml-and-c"></a>Visual Studio’da (Xaml ve C#) bir hata ayıklama oturumunda gezinme
Bu Hızlı Başlangıç, Visual Studio hata ayıklama oturumları gidin ve görüntülemek ve bir oturumda program durumu değiştirmek gösterir.  
  
 Bu Hızlı Başlangıç, Visual Studio ile hata ayıklama için yenidir ve Visual Studio'da gezinme hakkında daha fazla bilgi için isteyen geliştiriciler için oturum hata ayıklama geliştiriciler için olur. Kendisini hata ayıklama resim öğretmek değildir. Örnek kodda yöntemleri, yalnızca bu konuda açıklanan hata ayıklama yordamları göstermek için tasarlanmıştır. Yöntemler uygulama veya işlev tasarım en iyi uygulamaları kullanan değil. Aslında, yöntemleri ve uygulama, hiçbir şey çoğunu hiç yapmamanızı hızla keşfeder.  
  
 Bu hızlı başlangıç bölümlerini zaten aşina bilgi içeren herhangi bir bölümü atlayabilirsiniz olabildiğince bağımsız olmak üzere tasarlanmıştır. Örnek bir uygulama oluşturmak için gerekli değildir; Ancak, biz önerilir ve işlem kadar kolay yaptınız.  
  
 **Klavye kısayolları hata ayıklayıcı.** Visual Studio hata ayıklayıcısı gezinti hem fare ve klavye için optimize edilmiştir. Çoğu bu konudaki adımlarda, klavye kısayol tuşu veya kısayol tuşu parantez bir açıklama içerir. Örneğin, (klavye: F5) yazarak F5 başlatır veya hata ayıklayıcısının yürütülmeye anahtarı gösterir.  
  
## <a name="in-this-topic"></a>Bu konuda  
 Bilgi edinebilirsiniz nasıl yapılır:  
  
-   [Örnek uygulaması oluşturma](#BKMK_CreateTheApplication)  
  
-   [Ayarlama ve bir kesme noktası, bir yöntem adımla çalıştırmak ve program verileri inceleyin](#BKMK_StepInto)  
  
-   [İçine, üzerinden ve yöntemleri dışına adım](#BKMK_StepIntoOverOut)  
  
-   [Koşullu kesme noktası ayarlayın, imleci çalıştırmak ve bir değişken Görselleştirme](#BKMK_ConditionCursorVisualize)  
  
-   [Düzenle ve devam etmek için bir özel durumundan Kurtar](#BKMK_EditContinueRecoverExceptions)  
  
##  <a name="BKMK_CreateTheApplication"></a>Örnek uygulaması oluşturma  
 Yalnızca hata ayıklama oturumunda gezinme nasıl çalıştığını ve incelemek ve programın durumunu değiştirmek nasıl görebilirsiniz kaynak dosyası oluşturmak için örnek uygulama UWP uygulaması çerçevesinin kullanması için hata ayıklama hakkında koddur. Tüm, çağıracağı kod ana sayfasında oluşturucusundan çağrılır; Hiçbir denetim eklenir ve hiçbir olay işlenir.  
  
 **Bir varsayılan C# UWP uygulaması oluşturursunuz.** Visual Studio'yu açın. Giriş sayfasında, **yeni proje** bağlantı. Yeni Proje iletişim kutusunda seçin **Visual C#** içinde **yüklü** listeleyin ve ardından **Windows Evrensel**. Proje şablonları listesinden seçip **boş uygulama (Evrensel Windows)**. Visual Studio yeni çözüm ve proje oluşturur ve MainPage.xaml Tasarımcısı ve XAML Kod düzenleyicisinde görüntüler.  
  
 **MainPage.xaml.cs kaynak dosyasını açın.** XAML Düzenleyicisi'nde herhangi bir yere sağ tıklatın ve seçin **görünümü kodu**. MainPage.xaml.cs arka plan kod dosyası görüntülenir. Bu yalnızca bir yöntem Not `MainPage()` oluşturucusu, dosyada listelenen.  
  
 **MainPage Oluşturucusu örnek kod ile değiştirin.** MainPage() yöntemi silin. Bu bağlantıyı izleyin: [hata ayıklayıcı, gezinti örnek kod (Xaml ve C#)](https://github.com/MicrosoftDocs/visualstudio-docs/raw/master/docs/debugger/samples/debugger-navigation-sample-code-xaml-and-csharp.cs)ve ardından panoya C# bölümünde listelenen kodu kopyalayın. (Seçin **geri** tarayıcı ya da bu hızlı başlangıç sayfasına dönmek için Yardım Görüntüleyicisi.) Visual Studio düzenleyicisinde kodda Yapıştır `partial class MainPage` bloğu. Dosyayı kaydetmek için CTRL + s seçin.  
  
 Şimdi bu konudaki örnekler birlikte izleyebilirsiniz.  
  
##  <a name="BKMK_StepInto"></a>Ayarlama ve bir kesme noktası, bir yöntem adımla çalıştırmak ve program verileri inceleyin  
 Hata ayıklama oturumu başlatabilirsiniz en yaygın yolu seçmektir **hata ayıklamayı Başlat** gelen **hata ayıklama** menü (klavye: F5). Yürütme başlar ve bir kesme noktası ulaşıldığında, el ile bir özel durum oluştu, yürütme, askıya veya uygulama sona kadar devam eder.  
  
 Yürütme Hata Ayıklayıcısı'ndaki askıya alındığında, fare değişkeni gelerek, etkin bir değişkenin değerini bir veri ipucunda görüntüleyebilirsiniz. Etkin değişkenler ve geçerli değerleri listesini görmek için yerel ve otomatik değişkenler pencerelerini da açabilirsiniz. Bir veya daha fazla değişken uygulama yürütme devam ettikçe değişkenlerin değerini odaklanmak Gözcü penceresi imkan ekleniyor.  
  
 (Ayıklayıcıya çiğnemekten da adlandırılır) uygulamasını yürütülmesini askıya sonra program kodunu kalan yürütülen şekilde denetler. Yöntemin kendisi, yöntem çağrısından taşıma satır sürdürebilirsiniz veya tek bir adımda çağrılan yöntemi yürütebilir. Bu yordamları üzerinden uygulama atlama denir. Ayrıca, imlecinizi konumlandırılmış burada ayarladığınız sonraki kesme veya satırına çalışan uygulama, standart yürütülmesi devam edebilirsiniz. Hata ayıklama oturumu herhangi bir zamanda durdurabilirsiniz. Hata ayıklayıcı gerekli temizleme işlemleri gerçekleştirmek ve yürütme çıkmak için tasarlanmıştır.  
  
### <a name="example-1"></a>Örnek 1  
 Bu örnekte, MainPage.xaml.cs dosya MainPage oluşturucuda bir kesme noktası belirleyerek, ilk yöntemin içine, değişken değerlerini görüntülemek ve hata ayıklamayı durdurun.  
  
 **Bir kesme noktası ayarlayın.** İfadede bir kesme noktası belirleyerek `methodTrack = "Main Page";` MainPage oluşturucuda. Kaynak Kodu Düzenleyicisi gölgeli cilt payı içinde satır seçin (klavye: İmleç satıra getirin ve F9 anahtarı seçin).  
  
 ![Adımla](../debugger/media/dbg_basics_stepinto.png "DBG_Basics_StepInto")  
  
 Kesme noktası simgesi cilt görünür.  
  
 **Kesme noktasına Git.** Hata ayıklama oturumu seçerek Başlat **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menü (klavye: F5).  
  
 Uygulama yürütme başlar ve yürütme hemen kesme noktası ayarlama deyimi önce askıya alır. Cilt payını geçerli çizgisi simgesinde konumunuz tanımlar ve geçerli deyimi vurgulanır.  
  
 ![Bir kesme noktası belirleyerek](../debugger/media/dbg_basics_setbreakpoint.png "DBG_Basics_SetBreakpoint")  
  
 Uygulamanın yürütülmesini denetiminde sunulmuştur ve program ifadeleri adım gibi programın durumunu inceleyebilirsiniz.  
  
 **Yönteme adım.** Üzerinde **hata ayıklama** menüsünde seçin **Step Into** (klavye: F11).  
  
 ![Geçerli satır](../debugger/media/dbg_basics_currentline.png "DBG_Basics_CurrentLine")  
  
 Hata ayıklayıcı Example1 yöntemine bir çağrı sonraki satıra taşır unutmayın. Step Into yeniden seçin. Hata ayıklayıcı Example1 yöntemi Giriş noktasına taşır. Bu yöntem çağrı yığınındaki yüklendi ve yerel değişkenler için bellek tahsis gösterir.  
  
 Hata ayıklayıcı kod satırına adım, aşağıdaki eylemlerden birini gerçekleştirir:  
  
-   Next deyimi çözümünüzdeki işlevi çağrısı değilse, hata ayıklayıcı deyimini yürütür, bir sonraki ifadeye geçer ve yürütme askıya alır.  
  
-   Deyim, çözümünüzdeki işlevi çağrısı ise, hata ayıklayıcı çağrılan işlev giriş noktası taşır ve yürütme askıya alır.  
  
 Çıkış noktası ulaştınız kadar Example1 deyime adım devam edin. Hata ayıklayıcı kapanış kuşak yönteminin vurgular.  
  
 **Veri ipuçları değişken değerleri inceleyin.** Bir değişken adı fare geldiğinizde, bir veri ipucunda adını, değeri ve değişken türü görüntülenir.  
  
 ![Hata ayıklayıcı veri İpucu](../debugger/media/dbg_basics_datatip.png "DBG_Basics_DataTip")  
  
 Fare değişkeninden vurgulu `a`. Ad, değer ve veri türü unutmayın. Fare değişkeninden vurgulu `methodTrack`. Yeniden ada, değere ve veri türü unutmayın.  
  
 **Yerel öğeler penceresi değişken değerleri inceleyin.** Üzerinde **hata ayıklama** menüsündeki **Windows**ve ardından **Yereller**. (Klavye: Alt + 4).  
  
 ![Yerel öğeler penceresi](../debugger/media/dbg_basics_localswindow.png "DBG_Basics_LocalsWindow")  
  
 Yerel öğeler windows parametreleri ağaç görünümünü ve işlevini değişkenleri olur. Bir nesne değişkeni nesnenin alt düğümleri özelliklerdir. `this` Değişkeni, gizli bir parametreye her nesne yönteminde nesneyi temsil ediyor. Bu durumda, MainPage sınıfı temsil eder. Çünkü `methodTrack` MainPage sınıfı, değeri ve veri türünün bir üyesi bir satırda altında listelenen `this`. Genişletme `this` görüntülemek için düğümü `methodTrack` bilgi.  
  
 **MethodTrack değişken için bir izleme ekleyin.** `methodWatch` Değişkeni bu hızlı başlangıç örneklerde çağrılan yöntemler göstermek için kullanılır. Değişkenin değerini görüntülemek kolaylaştırmak için bir Gözcü penceresi ekleyin. Yerel öğeler penceresi, değişken adına sağ tıklayın ve ardından **Gözcü Ekle**.  
  
 ![Gözcü penceresi](../debugger/media/dbg_basics_watchwindow.png "DBG_Basics_WatchWindow")  
  
 Gözcü penceresi birden çok değişkenleri izleyebilirsiniz. Yereller ve veri ipucu windows değerler gibi izlenen değişkenlerin değerleri, her yürütme askıya alındığında güncelleştirilir. Kod Düzenleyicisi'nden Gözcü penceresi değişkenleri de ekleyebilirsiniz. İzlemek üzere değişken seçin, sağ tıklatın ve ardından **Gözcü Ekle**.  
  
##  <a name="BKMK_StepIntoOverOut"></a>İçine, üzerinden ve yöntemleri dışına adım  
 Bir üst yöntemi tarafından adlı bir yöntem içine Adımlama, aksine bir yöntem atlama alt yöntemini yürütür ve üst sürdürür gibi yürütme arama yönteminde bekletir. Yol yöntemi çalışır ve yürütülmesinin Araştırdığınız sorunun etkilemez eminseniz öğrendiğinizde yöntemi adım.  
  
 Yöntem çağrısı içermiyor kod hattından atlama satıra atlama gibi satır yürütür.  
  
 Alt yöntemi dışına Adımlama yönteminin yürütülmesi devam eder ve yöntemini çağıran yönteme döndükten sonra çalıştırmayı askıya alır. Rest işlevinin önemli değildir belirlediğinizde uzun işlevi dışında adım.  
  
 Üzerinden atlama hem bir işlev dışına Adımlama işlevi yürütün.  
  
 ![Adım içine, üzerinden ve yöntemleri dışına](../debugger/media/dbg_basics_stepintooverout.png "DBG_Basics_StepIntoOverOut")  
  
### <a name="example-2"></a>Örnek 2  
 Bu örnekte, içine, üzerinden ve yöntemleri dışına adım.  
  
 **MainPage oluşturucuda Example2 yöntemini çağırın.** MainPage Oluşturucusu düzenleyin ve satır aşağıdaki değiştirin `methodTrack = String.Empty;` ile `Example2();`.  
  
 ![Tanıtım yönteminden Example2 yöntemini çağırın](../debugger/media/dbg_basics_callexample2.png "DBG_Basics_CallExample2")  
  
 **Kesme noktasına Git.** Hata ayıklama oturumu seçerek Başlat **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menü (klavye: F5). Hata ayıklayıcı yürütme kesme noktasında askıya alır.  
  
 **Kod satırının üzerinden adım.** Üzerinde **hata ayıklama** menüsünde seçin **Step Over** (klavye: F10). Hata ayıklayıcı yürütür `methodTrack = "MainPage";` deyim INTO deyimi atlama olarak aynı şekilde.  
  
 **Example2 ve Example2_A adımla.** Örnek 2 yöntemin içine F11 anahtarı seçin. Satır ulaşana kadar Example2 deyime adım devam `int x = Example2_A();`. Yeniden adımla, giriş noktası Example2_A taşımak için bu satırı. Example2 için dönüş kadar her Example2_A ifadesine adım devam edin.  
  
 ![Example2](../debugger/media/dbg_basics_example2.png "DBG_Basics_Example2")  
  
 **Bir işlev adım.** Sonraki satır Example2 içinde Not `int y = Example2_A();` önceki satıra temelde aynıdır. Bu satırı güvenli bir şekilde geçebilirsiniz. Bu ikinci çağrı Example2_A Example2 sürdürme taşımak için F10 anahtarı seçin. Bu yöntem adım F10 seçin. Unutmayın `methodTrack` dize gösterir Example2_A yöntemi iki kez yürütüldü. Ayrıca, hata ayıklayıcı hemen bir sonraki satıra taşır fark edeceksiniz. Bu yürütme sırasında noktası Example2 sürdürür askıya almaz.  
  
 **Bir işlev dışında adım.** Example2_B yöntemin içine F11 anahtarı seçin. Not Example2_B Example2_A çok farklı değildir. Yöntemin dışında adım tercih **Step Out** üzerinde **hata ayıklama** menü (klavye: Shift + F11). Unutmayın `methodTrack` değişkeni Example2_B yürütüldü ve hata ayıklayıcısı burada Example2 sürdürür noktasına döndürdüğünü gösterir.  
  
 **Hata ayıklamayı durdurun.** Durdurma hata ayıklamayı Debug menüsünden seçin (klavye: Shift + F5). Bu, hata ayıklama oturumu sona erer.  
  
##  <a name="BKMK_ConditionCursorVisualize"></a>Koşullu kesme noktası ayarlayın, imleci çalıştırmak ve bir değişken Görselleştirme  
 Koşullu kesme noktası yürütme askıya almak hata ayıklayıcı neden olan bir koşulu belirtir. Koşul true veya false sonucu verebilen herhangi bir kod ifade belirtilir. Örneğin, yalnızca bir değişken belirli bir değere ulaştığında sık çağrılan yöntemin program durumda incelemek için koşullu bir kesme noktası kullanabilirsiniz.  
  
 İmleç çalışıyor tek seferlik bir kesme noktası gibi ayardır. Yürütme askıya alındığında, bir satırı kaynak seçin ve seçili satır ulaşılana kadar yürütme devam. Örneğin, olmaları bir yöntem bir döngüde doğruluk ve döngü kodda doğru şekilde çalışıp belirleyin. Her döngü tekrarında atlama yerine, döngü yürütüldükten sonra konumlandırılmış imleç çalıştırabilirsiniz.  
  
 Bazı durumlarda, veri ipucu veya değişken penceresinde satırda bir değişken değerini görüntülemek zordur. Hata ayıklayıcı dizeler, HTML ve XML'de kaydırılabilir penceresindeki Değer biçimlendirilmiş bir görünümünü sunan metin Görselleştirici görüntüleyebilirsiniz.  
  
### <a name="example-3"></a>Örnek 3  
 Bu örnekte, belirli bir döngü yinelemesinde bölün ve ardından döngüden sonra konumlandırılmış imleci çalıştırmak için bir koşullu kesme noktası ayarlayın. Bir değişkenin değerini de metin görselleştiriciyi görüntüleyin.  
  
 **MainPage oluşturucuda Örneği3 yöntemini çağırın.** MainPage Oluşturucusu düzenleyin ve satır aşağıdaki değiştirin `methodTrack = String.Empty;` satırı ile `Example3();`.  
  
 ![Örneği3 Demo yöntemi çağırın](../debugger/media/dbg_basics_callexample3.png "DBG_Basics_CallExample3")  
  
 **Kesme noktasına Git.** Hata ayıklama oturumu seçerek Başlat **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menü (klavye: F5). Hata ayıklayıcı MainPage yönteminde kesme noktasındaki yürütme askıya alır.  
  
 **Örneği3 yöntemi adımla.** Seçin **Step Into** üzerinde **hata ayıklama** menü (klavye: F11) Örneği3 yöntemi Giriş noktasına taşımak için. Bir veya iki döngüleri yinelendiğinde kadar yöntemin içine Adımlama devam `for` bloğu. Bu, tüm 1000 yineleme adım için uzun sürebilir olduğunu unutmayın.  
  
 **Koşullu kesme noktası ayarlayın.** Kod penceresinin sol cilt satıra sağ `x += i;` ve ardından **koşul**. Seçin **koşulu** onay kutusunu işaretleyin ve ardından `i == 500;` metin kutusuna. Seçin **doğrudur** seçeneği ve seçin **Tamam**. Kesme noktası 500th yinelemesi değerinde denetlemenizi sağlar `for` döngü.  
  
 ![Kesme noktası durumu iletişim kutusu](../debugger/media/dbg_basics_breakpointcondition.png "DBG_Basics_BreakpointCondition")  
  
 Koşullu kesme noktası simgesi, beyaz bir çarpı tanımlayabilirsiniz.  
  
 ![Koşullu kesme noktası](../debugger/media/dbg_basics_conditionalbreakpoint.png "DBG_Basics_ConditionalBreakpoint")  
  
 **Kesme noktasına Git.** Hata Ayıklama menüsünde devam seçin (klavye: F5). Yerel öğeler penceresi onaylayın geçerli değeri `i` 500'dür. Unutmayın değişkeni `s` tek bir satır olarak temsil edilir ve penceresinden daha çok uzun.  
  
 **Visual bir dize değişkeni.** Büyüteç simgesini **değeri** sütunu `s`.  
  
 Metin Görselleştirici penceresi görüntülenir ve dize değeri çok satırlı dize olarak sunulur.  
  
 **İmleç çalıştırın.** Satırın sağ `methodTrack += "->Example3";` ve ardından **çalıştırmak için imleç** (klavye: satır; imleç taşıma CTRL + F10). Hata ayıklayıcı döngüsü yinelemeleri tamamlar ve satırında yürütme askıya alır.  
  
 **Hata ayıklamayı durdurun.** Durdurma hata ayıklamayı Debug menüsünden seçin (klavye: Shift + F5). Bu, hata ayıklama oturumu sona erer.  
  
##  <a name="BKMK_EditContinueRecoverExceptions"></a>Düzenle ve devam etmek için bir özel durumundan Kurtar  
 Visual Studio hata ayıklayıcısında koda bölün bazı durumlarda, değişkenlerin değerini ve hatta deyimleri logics değiştirme olanağı vardır. Bu işlev düzenleme olarak adlandırılır ve devam edin.  
  
 Düzenle ve devam et bir özel durum böldüğünüzde özellikle yararlı olabilir. Durdurmak ve özel durum önlemek için uzun ve ilgili bir yordam hata ayıklaması yeniden başlatmak zorunda yerine, "yürütme hemen bir özel durum oluştu önce noktasına taşımak için özel durum bırakma" ve kullanabilirsiniz sorunlu değişkenini veya deyimi değiştirin ve Geçerli hata ayıklama oturum bir özel durum oluşturmadığını durumunda devam edin.  
  
 Düzenleme kullanın ve çok çeşitli durumlarda devam edebilirsiniz ancak yoksa düzenleme desteği ve devam belirli koşullar koşulları program yığın geçerli durumunu programlama dili bağımlı olduğundan belirtmek zordur ve işlem bozulmasını olmadan durumunu değiştirmek için hata ayıklayıcı yeteneği. Yalnızca denemek için bir düzen değişikliği desteklenip desteklenmediğini belirlemek için en iyi yolu olan; hata ayıklayıcı, değişikliği desteklenmiyor, hemen bilmenizi sağlar.  
  
### <a name="example-4"></a>Örnek 4  
 Bu örnekte, bir özel durum hata ayıklayıcıda çalıştırmak, özel durum geri sar, yöntemi mantığı düzeltin ve yöntemini yürütmenin devam edebilmeniz için bir değişken değerini değiştirin.  
  
 **MainPage oluşturucuda Example4 yöntemini çağırın.** MainPage() Oluşturucusu düzenleyin ve satır aşağıdaki değiştirin `methodTrack = String.Empty;` satırı ile `Example4();`.  
  
 ![Example4 Demo yöntemi çağırın](../debugger/media/dbg_basics_callexample4.png "DBG_Basics_CallExample4")  
  
 **Özel durumu çalıştırın.** Hata ayıklama oturumu seçerek Başlat **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menü (klavye: F5). Yeniden yürütme devam etmek için F5 tuşuna basın. Hata ayıklayıcı yürütme Example4 yöntemi özel durum sırasında askıya alır ve bir özel durum iletişim kutusu görüntüler.  
  
 ![Özel durum iletişim kutusu](../debugger/media/dbg_basics_exceptiondlg.png "DBG_Basics_ExceptionDlg")  
  
 **Program mantığını değiştirin.** Hata olduğunu açıktır `if` koşul: değerini `x` ne zaman değiştirilmelidir `x` 0'a eşit; değil, `x` sıfıra eşit değil. Seçin **bölün** yöntemi mantığı düzeltmek için. Satır düzenlemeye çalıştığınızda, başka bir iletişim kutusu görüntülenir.  
  
 ![Düzenle ve devam et iletişim kutusu](../debugger/media/dbg_basics_editandcontinuedlg.png "DBG_Basics_EditAndContinueDlg")  
  
 Seçin **Düzenle** ve satır değiştirme `if (x != 0)` için `if (x == 0)`. Hata ayıklayıcı kaynak dosyasına program mantığı değişiklikler devam ettirir.  
  
 **Değişken değeri değiştirin.** Değerini inceleyin `x` veri ipucu veya yerel öğeler penceresi. Hala 0 (sıfır). Özgün özel duruma neden deyimi çalıştırmayı denerseniz, yalnızca yeniden atar. Değerini değiştirebilir `x`. Yerel öğeler penceresi çift **değeri** sütunu **x** satır. Değer 0'dan 1 olarak değiştirin.  
  
 ![Yerel öğeler penceresi değerinde Düzenle](../debugger/media/dbg_basics_editandcontinuefix.png "DBG_Basics_EditAndContinueFix")  
  
 Daha önce bir özel durum oluşturdu ifadesine adım için F11 anahtarı seçin. Satır bir hata çalışacağını unutmayın. F11 yeniden seçin.  
  
 **Hata ayıklamayı durdurun.** Üzerinde **hata ayıklama** menüsünde seçin **durdurma hata ayıklama** (klavye: Shift + F5). Bu, hata ayıklama oturumu sona erer.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama oturumu (VB, C#, C++ ve XAML) Başlat](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)   
 [Tetiklemek askıya alma, sürdürme ve arka plan olaylarını UWP uygulamalar için)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md)   
 [Visual Studio uygulamalarında hata ayıklama](../debugger/debug-store-apps-in-visual-studio.md)