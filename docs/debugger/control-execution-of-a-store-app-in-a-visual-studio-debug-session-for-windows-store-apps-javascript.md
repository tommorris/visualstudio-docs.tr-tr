---
title: "Denetim bir UWP uygulaması yürütme bir Visual Studio hata ayıklama oturumunda (JavaScript) | Microsoft Docs"
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
ms.assetid: 60159535-61ec-466a-a4a6-115ec72a8af5
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 60b9465677ce033f8b285ce21e2b8332bf88a73a
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2017
---
# <a name="control-execution-of-a-uwp-app-in-a-visual-studio-debug-session-javascript"></a>Bir UWP uygulaması denetim yürütme bir Visual Studio hata ayıklama oturumunda (JavaScript)
Bu Hızlı Başlangıç, Visual Studio Hata Ayıklayıcısı'ndaki gezinmeyi ve bir oturumda Görünüm programın durumunu gösterir.  
  
 Bu Hızlı Başlangıç, Visual Studio ile hata ayıklama için yenidir ve Visual Studio'da gezinme hakkında daha fazla bilgi için isteyen geliştiriciler için oturum hata ayıklama geliştiriciler için olur. Kendisini hata ayıklama resim öğretmek değildir. Örnek kodda işlevleri yalnızca bu konuda açıklanan hata ayıklama yordamları göstermek için tasarlanmıştır. İşlevler en iyi uygulamalar, uygulama veya işlev tasarımının uygulamadığınız değil. Aslında, İşlevler ve uygulama, hiçbir şey çoğunu hiç yapmamanızı hızla keşfeder.  
  
 Bu hızlı başlangıç bölümlerini zaten aşina bilgi içeren herhangi bir bölümü atlayabilirsiniz olabildiğince bağımsız olmak üzere tasarlanmıştır. Örnek bir uygulama oluşturmak için gerekli değildir. Ancak, biz önerilir ve işlem kadar kolay yaptınız.  
  
 **Klavye kısayolları hata ayıklayıcı.** Visual Studio hata ayıklayıcısında gezinti hem fare ve klavye için optimize edilmiştir. Çoğu bu konudaki adımlarda, klavye kısayol tuşu veya kısayol tuşu parantez bir açıklama içerir. Örneğin, (klavye: F5) yazarak F5 başlatır veya hata ayıklayıcısının yürütülmeye anahtarı gösterir.  
  
> [!NOTE]
>  **Modül düzeni**  
>   
>  Sık kullandığınız JavaScript UWP uygulamaları *modülü düzeni* veri ve işlevleri sayfasındaki kapsülleyen. Sayfa işlevselliği genel ad alanından ayrı tutmak için bir tek, otomatik olarak yürütülen ve anonim Kapatılmak üzere modülü desen kullanır. Bu konuda, bu işlev diyoruz *Modülü*.  
  
## <a name="in-this-topic"></a>Bu konuda  
 Bilgi edinebilirsiniz nasıl yapılır:  
  
 [Örnek uygulaması oluşturma](#BKMK_Create_the_sample_app)  
  
 [Ayarlama ve bir kesme noktası, bir işlev adımla çalıştırmak ve program verileri inceleyin](#BKMK_Set_and_run_to_a_breakpoint__step_into_a_function__and_examine_program_data)  
  
 [İçine, üzerinden ve işlevleri dışına adım](#BKMK_Step_into__over__and_out_of_functions)  
  
 [Koşullu kesme noktası ayarlayın, imleci çalıştırmak ve bir değişken Görselleştirme](#BKMK_Set_a_conditional_breakpoint__run_to_the_cursor__and_visualize_a_variable)  
  
 [Yerel öğeler penceresi değişken verileri görüntüle](#BKMK_View_variable_data_in_the_Locals_window)  
  
-   [Değişken veri ve bir nesne prototip zincirini görüntüleyin](#BKMK_View_variable_data_and_the_prototype_chain_of_an_object)  
  
-   [Kapsam zinciri verilerini inceleyin](#BKMK_Examine_scope_chain_data)  
  
 [Çağrı yığını penceresini kullanarak kodu gidin](#BKMK_Navigate_to_code_by_using_the_Call_Stack_window)  
  
##  <a name="BKMK_Create_the_sample_app"></a>Örnek uygulaması oluşturma  
 Yalnızca hata ayıklama oturumunda gezinme nasıl çalıştığını ve programın durumunu incelemek nasıl görebilirsiniz kaynak dosyası oluşturmak için örnek uygulama UWP uygulaması çerçevesinin kullanması için hata ayıklama hakkında koddur. Tüm, çağıracağı kod çağrılır `module` default.js dosyası işlevi. Hiçbir denetim eklenir ve hiçbir olay işlenir.  
  
1.  **Boş bir JavaScript UWP uygulaması oluşturursunuz.** Visual Studio'yu açın. Giriş sayfasında, **yeni proje** bağlantı. Üzerinde **yeni proje** iletişim kutusunda, seçin **JavaScript** içinde **yüklü** listeleyin ve ardından **Windows Evrensel**. Proje şablonları listesinden seçip **boş uygulama (Evrensel Windows)**. Visual Studio yeni çözüm ve proje oluşturur ve default.htm dosyasını Kod düzenleyicisinde görüntüler.  
  
     Sayfaya yüklenen komut dosyalarını unutmayın.  
  
    -   `base.js` Ve `ui.js` dosyaları oluşturma **JavaScript için Windows Kitaplığı**. JavaScript için Windows kitaplığı JavaScript kümesidir ve JavaScript kullanarak UWP uygulamaları kolaylaştırmak CSS dosyaları oluşturun. Onu HTML, CSS ve Windows çalışma zamanı ile birlikte uygulamanızı oluşturmak için kullanın.  
  
    -   Kodunuzu başlayacağını `default.js` dosya.  
  
2.  **Default.js kaynak dosyasını açın.** Çözüm Gezgini'nde açık **js** düğümü seçin `default.js`.  
  
3.  **Sayfa içeriğini örnek kod ile değiştirin.** Tüm içeriğini silmek `default.js` dosya. Bu bağlantıyı izleyin: [hata ayıklayıcı, gezinti örnek kod (JavaScript)](https://github.com/MicrosoftDocs/visualstudio-docs/raw/master/docs/debugger/samples/debugger-navigation-sample-code-javascript.js)ve ardından panoya JavaScript bölümünde listelenen kodu kopyalayın. (Seçin **geri** tarayıcı ya da bu hızlı başlangıç sayfasına dönmek için Yardım Görüntüleyicisi.) Visual Studio düzenleyicisinde kodu şimdi boş yapıştırın `default.js`. Seçin **Ctrl + S** dosyayı kaydetmek için.  
  
 Şimdi bu konudaki örnekler birlikte izleyebilirsiniz.  
  
##  <a name="BKMK_Set_and_run_to_a_breakpoint__step_into_a_function__and_examine_program_data"></a>Ayarlama ve bir kesme noktası, bir işlev adımla çalıştırmak ve program verileri inceleyin  
 Hata ayıklama oturumu başlatmak için en yaygın yolu seçmektir **hata ayıklamayı Başlat** gelen **hata ayıklama** menü (klavye: F5). Uygulama başlar ve bir kesme noktası ulaşıldığında, el ile bir özel durum oluştu, yürütme, askıya veya uygulama sona kadar yürütmeye devam eder.  
  
 Yürütme Hata Ayıklayıcısı'ndaki askıya alındığında, değişkeni üzerinde fareyi duraklatarak, etkin bir değişkenin değerini bir veri ipucunda görüntüleyebilirsiniz.  
  
 (Ayıklayıcıya çiğnemekten da adlandırılır) uygulamasını yürütülmesini askıya sonra program kodunu kalan yürütür şeklini denetlemek. Bir işlev çağrısında işlevi kendisini taşıma satır sürdürebilirsiniz veya tek bir adımda çağrılan işlev yürütebilir. Bu yordamları üzerinden uygulama atlama denir. Ayrıca, imlecinizi konumlandırılmış burada ayarladığınız sonraki kesme veya satırına çalışan uygulama, standart yürütülmesi devam edebilirsiniz. Hata ayıklama oturumu herhangi bir zamanda durdurabilirsiniz. Hata ayıklayıcı gerekli temizleme işlemleri gerçekleştirmek ve yürütme çıkmak için tasarlanmıştır.  
  
###  <a name="BKMK_Example_1"></a>Örnek 1  
 Bu örnekte, gövdesinde bir kesme noktası belirleyerek `module` işlevi `default.js` gibi kullanıcı bildirimimizi ilk çağırır. İşlevdeki adım, hata ayıklayıcı veri ipuçlarında değişken değerlerini görüntülemek ve hata ayıklamayı durdurun.  
  
1.  **Bir kesme noktası ayarlayın.** İfadede bir kesme noktası belirleyerek `callTrack = "module function";` çağrısı hemen sonra oluşan `app.start()`. Kaynak Kodu Düzenleyicisi gölgeli cilt payı içinde satır seçin (klavye: İmleç satıra getirin ve seçin **F9** anahtar).  
  
     ![Example1 bir kesme noktası belirleyerek](../debugger/media/dbg_jsnav_example1_breakpoint.png "DBG_JSNAV_example1_breakpoint")  
  
     Kesme noktası simgesi cilt görünür.  
  
2.  **Kesme noktasına Git.** Hata ayıklama oturumu seçerek Başlat **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menü (klavye: F5).  
  
     Uygulama yürütme başlar ve yürütme hemen kesme noktası ayarlama deyimi önce askıya alır. Cilt payını geçerli çizgisi simgesinde konumunuz tanımlar ve geçerli deyimi vurgulanır.  
  
     ![Kesme noktasına Git](../debugger/media/dbg_jsnav_example1_run_to_breakpoint.png "DBG_JSNAV_example1_run_to_breakpoint")  
  
     Uygulamanın yürütülmesini denetiminde sunulmuştur ve program ifadeleri adım gibi programın durumunu inceleyebilirsiniz.  
  
3.  **İşlevdeki adım.** Üzerinde **hata ayıklama** menüsünde seçin **Step Into** (klavye: **F11**).  
  
     ![Bir kod satırı adımla](../debugger/media/dbg_jsnav_example1_step_into.png "DBG_JSNAV_example1_step_into")  
  
     Hata ayıklayıcı bir sonraki satıra taşır Not yapılan bir çağrı olduğu `example1` işlevi. Seçin **Step Into** yeniden. Hata ayıklayıcı için ilk kod satırı taşır `example1` işlevi. Vurgulanan satırı yürütülmedi, ancak işlev çağrı yığınındaki yüklendi ve yerel değişkenler için bellek tahsis edilmiş.  
  
4.  Hata ayıklayıcı kod satırına adım, aşağıdaki eylemlerden birini gerçekleştirir:  
  
    -   Next deyimi çözümünüzdeki işlevi çağrısı değilse, hata ayıklayıcı deyimini yürütür, bir sonraki ifadeye geçer ve yürütme askıya alır.  
  
    -   Deyim, çözümünüzdeki işlevi çağrısı ise, hata ayıklayıcı çağrılan işlev ilk satıra taşır ve yürütme askıya alır.  
  
     Deyime adım devam `example1` kadar çıkış noktası üst sınırına ulaştınız. Hata ayıklayıcı kapanış kuşak işlevinin vurgular.  
  
5.  **Değişken değerleri veri ipuçlarında görüntüleyin.** Deyime adım devam `example1` kadar çıkış noktası üst sınırına ulaştınız. Hata ayıklayıcı kapanış kuşak işlevinin vurgular. Bir değişken adı üzerinde fareyi duraklattığınızda, ad ve değer değişkenin veri ipucunda görüntülenir.  
  
     ![Değişken değerleri veri ipucunda görüntülemek](../debugger/media/dbg_jsnav_data_tip.png "DBG_JSNAV_data_tip")  
  
6.  **CallTrack değişken için bir izleme ekleyin.** `callTrack` Değişkeni bu hızlı başlangıç örneklerde çağrılan işlevler göstermek için kullanılır. Değişkenin değerini görüntülemek kolaylaştırmak için bir Gözcü penceresi ekleyin. Düzenleyicide değişken adını seçin ve ardından **Gözcü Ekle** kısayol menüsünden.  
  
     ![Bir değişken izleme](../debugger/media/dbg_jsnav_watch_window.png "DBG_JSNAV_watch_window")  
  
     Gözcü penceresi birden çok değişkenleri izleyebilirsiniz. Veri ipucu Windows'ta değerleri gibi izlenen değişkenlerin değerleri, her yürütme askıya alındığında güncelleştirilir. İzlenen değişkenlerinizi hata ayıklama oturumları arasında kaydedilir.  
  
7.  **Hata ayıklamayı durdurun.** Üzerinde **hata ayıklama** menüsünde seçin **durdurma hata ayıklama** (klavye: **Shift + F5**). Bu, hata ayıklama oturumu sona erer.  
  
##  <a name="BKMK_Step_into__over__and_out_of_functions"></a>İçine, üzerinden ve işlevleri dışına adım  
 Bir üst işlev tarafından çağrılan işlev içine Adımlama, aksine bir işlev atlama alt işlevi yürütür ve üst sürdürür gibi yürütme arama işlevinde bekletir. İşlevi çalışır ve yürütülmesinin Araştırdığınız sorunun etkilemez emin işlemleriyle öğrendiğinizde işlevi adım.  
  
 Bir işlev çağrısı içermiyor kod hattından atlama satıra atlama gibi satır yürütür.  
  
 Alt işlevi dışına Adımlama işlevinin yürütme devam eder ve işlevi çağıran işleve döndükten sonra çalıştırmayı askıya alır. Rest işlevinin önemli değildir belirlediğinizde uzun işlevi dışında adım.  
  
 Üzerinden atlama hem bir işlev dışına Adımlama işlevi yürütün.  
  
 ![Adım içine, üzerinden ve yöntemleri dışına](../debugger/media/dbg_basics_stepintooverout.png "DBG_Basics_StepIntoOverOut")  
  
###  <a name="BKMK_Example_2"></a>Örnek 2  
 Bu örnekte, içine, üzerinden ve işlevleri dışına adım.  
  
1.  **Modül işlevinde example2 işlevini çağırın.** Düzen `module` işlev ve satır aşağıdaki değiştirin `var callTrack = "module function"` ile `example2();`.  
  
     ![Example2 işlevini çağırın](../debugger/media/dbg_jsnav_example2.png "DBG_JSNAV_example2")  
  
2.  **Kesme noktasına Git.** Hata ayıklama oturumu seçerek Başlat **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menü (klavye: F5). Hata ayıklayıcı yürütme kesme noktasında askıya alır.  
  
3.  **Kod satırının üzerinden adım.** Üzerinde **hata ayıklama** menüsünde seçin **Step Over** (klavye: F10). Hata ayıklayıcı yürütür `var callTrack = "module function"` deyim INTO deyimi atlama olarak aynı şekilde.  
  
4.  **Example2 ve example2_a adım.** Seçin **F11** adımla anahtar `example2` işlevi. Adımla devam `example2` satır ulaşana kadar deyimleri `var x = example2_a();`. Yeniden, adım için giriş noktasını taşımak için bu satırı içine `example2_a`. Her ifadesine adım devam `example2_a` geri kadar `example2`.  
  
     ![Bir işlev Adımlama](../debugger/media/dbg_jsnav_example2_a.png "DBG_JSNAV_example2_a")  
  
5.  **Bir işlev adım.** Sonraki satır Not `example2`, `var y = example2_a();` önceki satıra temelde aynıdır. Bu satırı güvenli bir şekilde geçebilirsiniz. Seçin **F10** sürdürme taşımak için anahtar `example2` bu ikinci çağrısının `example2_a`. Unutmayın `callTrack` dize gösterir `example2_a` işlevi iki kez yürütüldü.  
  
6.  **Bir işlev dışında adım.** Seçin **F11** adımla anahtar `example2_b` işlevi. Unutmayın `example2_b` çok farklı değildir `example2_a`. İşlev dışında adım için tercih **Step Out** üzerinde **hata ayıklama** menü (klavye: **Shift + F11**). Unutmayın `callTrack` değişkeni gösterir `example2_b` yürütüldü ve hata ayıklayıcısı noktasına döndürülen olduğu `example2` sürdürür.  
  
7.  **Hata ayıklamayı durdurun.** Üzerinde **hata ayıklama** menüsünde seçin **durdurma hata ayıklama** (klavye: **Shift + F5**). Bu, hata ayıklama oturumu sona erer.  
  
##  <a name="BKMK_Set_a_conditional_breakpoint__run_to_the_cursor__and_visualize_a_variable"></a>Koşullu kesme noktası ayarlayın, imleci çalıştırmak ve bir değişken Görselleştirme  
 Koşullu kesme noktası yürütme askıya almak hata ayıklayıcı neden olan bir koşulu belirtir. Koşul true veya false sonucu verebilen herhangi bir kod ifade belirtilir. Örneğin, yalnızca bir değişken belirli bir değere ulaştığında sık çağrılan işlev program durumda incelemek için bir koşullu kesme noktası kullanabilirsiniz.  
  
 İmleç çalışıyor tek seferlik bir kesme noktası gibi ayardır. Yürütme askıya alındığında, bir satırı kaynak seçin ve seçili satır ulaşılana kadar yürütme devam. Örneğin, olmaları işlevi bir döngüde doğruluk ve döngü kodda doğru şekilde çalışıp belirleyin. Her döngü tekrarında atlama yerine, döngü yürütüldükten sonra konumlandırılmış imleç çalıştırabilirsiniz.  
  
 Bazı durumlarda, bir veri ipucu veya diğer veri penceresinin satırda bir değişken değerini görüntülemek zordur. Hata ayıklayıcı dizeler, HTML ve XML'de kaydırılabilir penceresindeki Değer biçimlendirilmiş bir görünümünü sunan metin Görselleştirici görüntüleyebilirsiniz.  
  
###  <a name="BKMK_Example_3"></a>Örnek 3  
 Bu örnekte, belirli bir döngü yinelemesinde bölün ve ardından döngüden sonra konumlandırılmış imleci çalıştırmak için bir koşullu kesme noktası ayarlayın. Bir değişkenin değerini de metin görselleştiriciyi görüntüleyin.  
  
1.  **Modül işlevinde Örneği3 işlevini çağırın.** Düzen `module` işlev ve satır aşağıdaki değiştirin `var callTrack = "module function";` satırı ile `example3();`.  
  
     ![Örneği3 çağrısı](../debugger/media/dbg_jsnav_example3.png "DBG_JSNAV_example3")  
  
2.  **Kesme noktasına Git.** Hata ayıklama oturumu seçerek Başlat **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menü (klavye: **F5**). Hata ayıklayıcı kesme noktasındaki durduran `module` işlevi.  
  
3.  **Tabloya Örneği3 işlev adım.** Seçin **Step Into** üzerinde **hata ayıklama** menü (klavye: **F11**) giriş noktası taşımak için `example3` işlevi. Bir veya iki döngüleri yinelendiğinde kadar işlevi Adımlama devam `for` bloğu. Bu, tüm 1000 yineleme adım için uzun sürebilir olduğunu unutmayın.  
  
4.  **Koşullu kesme noktası ayarlayın.** Kod penceresinin sol cilt satıra sağ `s += i.toString() + "\n";` ve ardından **koşulu** kısayol menüsünde.  
  
     Seçin **koşulu** onay kutusunu işaretleyin ve ardından `i == 500;` metin kutusuna. Seçin **doğrudur** seçeneği ve seçin **Tamam**. Kesme noktası 500th yinelemesi değerinde denetlemenizi sağlar `for` döngü. Koşullu kesme noktası simgesi, beyaz bir çarpı tanımlayabilirsiniz.  
  
     ![Koşullu kesme noktası simgesi](../debugger/media/dbg_jsnav_breakpoint_condition_icon.png "DBG_JSNAV_Breakpoint_Condition_icon")  
  
5.  **Kesme noktasına Git.** Üzerinde **hata ayıklama** menüsünde seçin **devam** (klavye: **F5**). Üzerinde duraklatma `i` doğrulamak için geçerli değeri `i` 500'dür. Ayrıca değişkeni `s` tek bir satır olarak temsil edilir ve veriler ipucu penceresinden daha çok uzun.  
  
6.  **Bir dize değişkeni görselleştirin.** Veri ucunu Büyüteç simgesini `s`.  
  
     Metin Görselleştirici penceresi görüntülenir ve dize değeri çok satırlı dize olarak sunulur.  
  
     ![Metin Görselleştirici hata ayıklama](../debugger/media/dbg_jsnav_text_visualizer.png "DBG_JSNAV_Text_Visualizer")  
  
7.  **İmleç çalıştırın.** Satırı seçin `callTrack += "->example3";` ve ardından **çalıştırmak için imleç** kısayol menüsünde (klavye: **Ctrl + F10**). Hata ayıklayıcı döngüsü yinelemeleri tamamlar ve satırında yürütme askıya alır.  
  
8.  **Hata ayıklamayı durdurun.** Üzerinde **hata ayıklama** menüsünde seçin **durdurma hata ayıklama** (klavye: **Shift + F5**). Bu, hata ayıklama oturumu sona erer.  
  
###  <a name="BKMK_Use_Run_to_Cursor_to_return_to_your_code_and_delete_a_breakpoint"></a>İmleç çalışmaya kodunuzu dönün ve bir kesme noktası silmek için kullanın  
 Microsoft'tan kitaplığı koda adım adım ya da üçüncü taraf bir imleç çalışıyor çok kullanışlı olabilir. Kitaplık kodu atlama bilgilendirici olabilirler, ancak genellikle uzun zaman alabilir. Ve genellikle kendi kodunuzu daha ilgilendiğiniz. Bu alıştırmada nasıl yapılacağını gösterir.  
  
1.  **Konumundaki app.start çağrısı bir kesme noktası ayarlayın.** İçinde `module` işlev, satırında bir kesme noktası ayarlama`app.start()`  
  
2.  **Kesme noktasına Git ve kitaplık işlevdeki adım.**  
  
     İçine adım zaman `app.start()`, kodda Düzenleyici görüntüler `base.js`. Birden fazla birkaç satıra adım.  
  
3.  **İçinde ve dışında işlevleri adım.** Üzerinden adım olarak (**F10**) ve işyeri dışında adım (**SHIFT + F11**) kod `base.js`, o karmaşıklığını inceleniyor sonuç gelebilir ve başlangıç işlevinin uzunluğudur yaparak istediğinizi değil.  
  
4.  **İmleç kodunuzu ayarlamak ve kendisine çalıştırın.** Dönmek `default.js` Kod düzenleyicisinde dosya. Koddan sonra ilk satırını seçin `app.start()` (açıklama ya da boş bir satır Çalıştır olamaz). Seçin **çalıştırmak için imleç** kısayol menüsünden. Hata ayıklayıcı app.start işlevinin yürütme devam eder ve yürütme kesme noktasında askıya alır.  
  
##  <a name="BKMK_View_variable_data_in_the_Locals_window"></a>Yerel öğeler penceresi değişken verileri görüntüle  
 Yerel öğeler windows parametreler ve değişkenler şu anda yürütülen işlevinin kapsam zincirinde ağaç görünümünü olur.  
  
###  <a name="BKMK_View_variable_data_and_the_prototype_chain_of_an_object"></a>Değişken veri ve bir nesne prototip zincirini görüntüleyin  
  
1.  **Bir dizi nesnesi modülü işlevi ekleyin.** Düzen `module` işlev ve satır aşağıdaki değiştirin `var callTrack = "module function"` ile`var myArray = new Array(1, 2, 3);`  
  
     ![myArray tanımı](../debugger/media/dbg_jsnav_myarray.png "DBG_JSNAV_myArray")  
  
2.  **Kesme noktasına Git.** Hata ayıklama oturumu seçerek Başlat **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menü (klavye: **F5**). Hata ayıklayıcı yürütme kesme noktasında askıya alır. Satırına adımla.  
  
3.  **Yerel öğeler penceresi açın.** Üzerinde **hata ayıklama** menüsündeki **Windows**ve ardından **Yereller**. (Klavye: Alt + 4).  
  
4.  **Modül işlevi yerel değişkenlerde inceleyin** Yereller windows görüntüler şu anda yürütülen işlevi değişkenleri ( `module` işlevi) ağacının üst düzey düğüm. Bir işlev girdiğinizde, JavaScript tüm değişkenleri oluşturur ve bunları değerini verir `undefined`. İşlev tanımlanan işlevler kendi metin bir değere sahip.  
  
     ![Yerel öğeler penceresi](../debugger/media/dbg_jsnav_locals_window.png "DBG_JSNAV_Locals_window")  
  
5.  **CallTrack ve myArray tanımlarını adım.** CallTrack ve myArray değişkenleri Yereller penceresinde bulabilirsiniz. Atla (**F10**) iki tanımları ve dikkat **değeri** ve **türü** alanları değiştirilir. Yerel öğeler penceresi son sonu beri değiştirilen değişkenlerin değerleri vurgular.  
  
6.  **MyArray nesnesini inceler** genişletme `myArray` değişkeni. Dizideki her öğe listelenen **[prototip]** devralma hiyerarşisini içeren düğümü `Array` nesnesi. Bu düğümü genişletin.  
  
     ![Yerel öğeler penceresi prototip zincirinde](../debugger/media/dbg_jsnav_locals_proto_chain.png "DBG_JSNAV_Locals_proto_chain")  
  
    -   **Yöntemleri** düğümü listeler tüm yöntemleri `Array` nesnesi.  
  
    -   **[Prototip]** düğüm içerir prototipi `Object` nesnesi `Array` türetilir. **[prototip]**  düğümleri özyinelemeli olabilir. Bir nesne hiyerarşideki her üst nesne açıklanan **[prototip]** kendi alt düğümü.  
  
7.  **Hata ayıklamayı durdurun.** Üzerinde **hata ayıklama** menüsünde seçin **durdurma hata ayıklama** (klavye: Shift + F5). Bu, hata ayıklama oturumu sona erer.  
  
##  <a name="BKMK_Examine_scope_chain_data"></a>Kapsam zinciri verilerini inceleyin  
 *Kapsam zinciri* etkin ve işlev tarafından erişilebilir olan tüm değişkenleri işlevi içerir. Şu anda yürütülen işlevi tanımlayan işlev içinde tanımlanan tüm nesnelerin (işlevleri dahil) gibi genel değişkenler kapsam zincirinde bir parçasıdır. Örneğin, `callTrack` tanımlanan değişken `module` işlevinin `default.js` tanımlanan herhangi bir işlev tarafından erişilebilir olduğundan `module` işlevi. Her kapsam ayrı olarak Yereller penceresinde listelenir.  
  
-   Şu anda yürütülen işlevin değişkenleri penceresinin en üstünde listelenmiştir.  
  
-   Kapsam zincirindeki her işlev kapsamı değişkenlerinin altında listelenen bir **[kapsam]** işlevi için düğüm. Kapsam işlevleri zincirindeki zincir en dıştaki işlevi için geçerli işlevi tanımlayan işlevden sıralarına göre listelenir.  
  
-   **[Globals]** düğümü dışında herhangi bir işlev tanımlanan genel nesneleri listeler.  
  
 Kapsam zincirleri kafa karıştırıcı olabilir ve en iyi örnek gösterilmiştir. Aşağıdaki örnekte, gördüğünüz nasıl `module` işlev oluşturur, kendi kapsamı ve başka nasıl oluşturabileceğiniz kapsamını düzeyi bir kapatma oluşturarak.  
  
###  <a name="BKMK_Example_4"></a>Örnek 4  
  
1.  **Example4 işlevi modülü işlevini çağırın.** Düzen `module` işlev ve satır aşağıdaki değiştirin `var callTrack = "module function"` ile `example4()`:  
  
     ![Example4 çağrısı](../debugger/media/dbg_jsnav_example4.png "DBG_JSNAV_example4")  
  
2.  **Kesme noktasına Git.** Hata ayıklama oturumu seçerek Başlat **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menü (klavye: **F5**). Hata ayıklayıcı yürütme kesme noktasında askıya alır.  
  
3.  **Yerel öğeler penceresi açın.** Üzerinde gerekirse, **hata ayıklama** menüsündeki **Windows**ve ardından **Yereller**. (Klavye: **Alt + 4**). Not penceresi tüm değişkenleri listeler ve işlevlerini `module` işlev ve ayrıca içeren bir **[Globals]** düğümü.  
  
4.  **Genel değişkenler inceleyin.** Genişletme **[Globals]** düğümü. Global değişkenler ve nesneleri JavaScript için Windows kitaplığı tarafından ayarlandı. Genel kapsam için kendi değişkenleri ekleyebilirsiniz.  
  
5.  **Adım example4 ve kendi yerel inceleyin ve kapsam değişkenleri** adımla (klavye: **F11**) `example4` işlevi. Çünkü `example4` tanımlanan `module` işlevi, `module` işlevi üst kapsam haline gelir. `example4`işlevlerde hiçbirini çağırabilirsiniz `module` işlev ve değişkenlerini erişebilirsiniz. Genişletme **[kapsam]** düğümünü yerel öğeler penceresi ve aynı ve değişkenleri içeren Not `module` işlevi.  
  
     ![Example4 yöntemi kapsamını](../debugger/media/dbg_jsnav_locals_example4_scope.png "DBG_JSNAV_Locals_example4_scope")  
  
6.  **Adım example4_a ve kendi yerel inceleyin ve kapsam değişkenleri** adımla devam `example4` ve çağrısı halinde `example4_a`. Yerel değişkenler şimdi arasındadır Not `example4_a`ve **[kapsam]** düğümü devam değişkenlerinin tutmak `module` işlevi. Olsa bile değişkenlerinin `example4` bunlar ulaşılamıyor tarafından etkin olan `example4_a` ve artık kapsam zinciri parçasıdır.  
  
7.  **Adım multipyByA ve kendi yerel inceleyin ve kapsam değişkenleri** kalanında adım `example4_a` ve satırına `var x = multilpyByA(b);`.  
  
     İşlev değişkeni `multipyByA` ayarlandığından `multiplyClosure` olan işlevi bir *Kapatılmak üzere*. `multipyClosure`tanımlar ve bir iç işlevi döndürür `mulitplyXby`ve yakalar (üzerinden kapatır), parametre ve değişken. Bir kapatma döndürülen iç işlev dış işlevin veri erişimi ve bu nedenle, kendi düzeyi kapsam oluşturur.  
  
     İçine adım zaman `var x = multilpyByA(b);`, geçmeden `return a * b;` satırından `mulitplyXby` iç işlev.  
  
8.  Yerel öğeler penceresinde, yalnızca parametresini `b` yerel değişken olarak listelenen `multiplyXby`, ancak yeni bir **[kapsam]** düzeyi eklendi. Bu düğümü genişletmek, parametreleri, işlevleri ve değişkenler içerdiğini gördüğünüz `multiplyClosure`dahil `a` değişken olarak adlandırılan ilk satırında `multiplyXby`. İkinci Hızlı Kontrol **[kapsam]** düğümü modülü işlevi değişkenleri ortaya çıkarır hangi `multiplyXby` sonraki satırda erişir.  
  
     ![Yerel öğeler penceresi içinde bir kapatma kapsamını](../debugger/media/dbg_jsnav_scope_mulitplyxby.png "DBG_JSNAV_scope_mulitplyXby")  
  
9. **Hata ayıklamayı durdurun.** Üzerinde **hata ayıklama** menüsünde seçin **durdurma hata ayıklama** (klavye: **Shift + F5**). Bu, hata ayıklama oturumu sona erer.  
  
##  <a name="BKMK_Navigate_to_code_by_using_the_Call_Stack_window"></a>Çağrı yığını penceresini kullanarak kodu gidin  
 Çağrı yığını uygulamanın geçerli iş parçacığında yürütülen işlevler hakkında bilgi içeren bir veri yapısıdır. Bir kesme noktası isabet, çağrı yığını penceresi tüm yığında etkin olan işlevlerin bir listesini görüntüler. Çağrı yığını penceresi listesinin başında şu anda yürütülen işlevdir. İş parçacığı başlatan listesinin altındaki işlevdir. İşlevler arasındaki geçerli işlevi başlatma işlevi çağrısı yolu gösterir.  
  
 Şu anda yürütülen işlevi çağrısı yolunu gösteren ek olarak, çağrı yığını penceresinde Kod düzenleyicisinde kod gitmek için kullanılabilir. Bu işlevselliği birden fazla dosyalarıyla çalışma ve belirli bir işleve hızlıca taşımak istediğinizde yararlı olabilir.  
  
###  <a name="BKMK_Example_5"></a>Örnek 5  
 Bu örnekte, beş kullanıcı tanımlı işlevler içeren bir çağrı yola adım.  
  
1.  **Modül işlevinde Örneği5 işlevini çağırın.** Düzen `module` işlev ve satır aşağıdaki değiştirin `var callTrack = "module function";` satırı ile `example5();`.  
  
     ![Örneği5 çağrısı](../debugger/media/dbg_jsnav_example5.png "DBG_JSNAV_example5")  
  
2.  **Kesme noktasına Git.** Hata ayıklama oturumu seçerek Başlat **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menü (klavye: **F5**). Hata ayıklayıcı modülü işlevinde kesme noktasındaki yürütme askıya alır.  
  
3.  **Çağrı yığını penceresini açın.** Üzerinde **hata ayıklama** menüsünde seçin **Windows**ve ardından **çağrı yığını** (klavye: Alt + 7). Çağrı yığını penceresi iki işlevleri gösterdiğine dikkat edin:  
  
    -   **Global kodu** giriş noktasıdır `module` işlevi alt kısmındaki çağrı yığını.  
  
    -   **Anonim işlevi** satırda gösterir `module` yürütme askıya burada işlevi. Çağrı yığınının tepesindeki budur.  
  
4.  **Example5_d işlevi ulaşması işlevlerini adım.** Seçin **Step Into** üzerinde **hata ayıklama** menü (klavye: **F11**) example5_d işlevinin giriş noktası ulaşana kadar çağrılarında çağrısı yolunda yürütülecek. Her zaman bir işlev bir işlev çağrıları, çağıran işlevi satır sayısı kaydedilir ve çağrılan işlev yığının en üstte yerleştirilir unutmayın. Çağıran işlevi satır sayısı çağıran işlevi yürütme duraklattı noktasıdır. Sarı bir ok şu anda yürütülen işlevi işaret eder.  
  
     ![Çağrı yığını penceresi](../debugger/media/dbg_jsnav_callstack_windows.png "DBG_JSNAV_CallStack_windows")  
  
5.  **Çağrı yığını penceresi example5_a koda gidin ve bir kesme noktası ayarlamak için kullanın.** Çağrı yığını penceresinde seçin `example5_a` liste öğesi ve ardından **kaynağına gidin** kısayol menüsünde. Kod Düzenleyicisi, imleç işlevinin dönüş satırında ayarlar. Bu satırında bir kesme noktası ayarlayın. Geçerli yürütme satır değişmemiş unutmayın. Yalnızca Düzenleyicisi imlecini taşındı.  
  
6.  **İşlevlerini adım ve ardından kesme noktasına çalıştırın.** İçine Adımlama devam `example5_d`. İşlevinden geri döndüğünüzde, çağrı yığını alınır unutmayın. Tuşuna **F5** program yürütme devam etmek için. Önceki adımda oluşturduğunuz kesme noktasındaki durdurun.  
  
7.  **Hata ayıklamayı durdurun.** Üzerinde **hata ayıklama** menüsünde seçin **durdurma hata ayıklama** (klavye: **Shift + F5**). Bu, hata ayıklama oturumu sona erer.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir hata ayıklama oturumu (JavaScript)](../debugger/start-a-debugging-session-for-store-apps-in-visual-studio-javascript.md)   
 [Hızlı Başlangıç: Hata ayıklayıcı Gezinti (JavaScript)](../debugger/control-execution-of-a-store-app-in-a-visual-studio-debug-session-for-windows-store-apps-javascript.md)   
 [Hızlı Başlangıç: HTML ve CSS hata ayıklama](../debugger/quickstart-debug-html-and-css.md)   
 [Tetiklemek askıya alma, sürdürme ve arka plan olaylarını UWP uygulamalar için)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md)   
 [Visual Studio uygulamalarında hata ayıklama](../debugger/debug-store-apps-in-visual-studio.md)
