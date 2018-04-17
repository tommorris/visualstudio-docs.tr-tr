---
title: Konsolu kullanarak JavaScript hata ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- VS.WebClient.JavaScriptConsole
dev_langs:
- JavaScript
helpviewer_keywords:
- JavaScript Console
- JavaScript debugging
- debugging, JavaScript
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: acdb5d1ff42c43dcfc9f5f0168ad39ee9c277088
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="debug-javascript-using-the-console-in-visual-studio"></a>Visual Studio'da Konsolu kullanarak JavaScript hata ayıklama
  
 JavaScript Konsolu penceresi ile etkileşim ve JavaScript kullanarak oluşturulan UWP uygulamaları hata ayıklamak için kullanabilirsiniz. Bu özellikler, UWP uygulamaları ve Apache Cordova için Visual Studio Araçları kullanılarak oluşturulan uygulamaları için desteklenir. Konsol komut başvurusu için bkz: [JavaScript Konsolu komutları](../debugger/javascript-console-commands.md).  
  
 JavaScript Konsolu penceresi sağlar:  
  
-   Nesneleri, değerler ve iletileri uygulamanızdan konsol penceresine gönderin.  
  
-   Görüntüleyin ve çalışan uygulamanın yerel ve genel değişkenler değerlerini değiştirin.  
  
-   Görünüm nesnesi görselleştiriciler.  
  
-   Geçerli komut dosyası bağlamı içinde yürütür JavaScript kodu çalıştırın.  
  
-   JavaScript hataları ve özel durumları, belge nesne modeli (DOM) ve Windows çalışma zamanı özel durumları ek olarak görüntüleyin.  
  
-   Ekranı temizleme gibi diğer görevleri gerçekleştirin. Bkz: [JavaScript Konsolu komutları](../debugger/javascript-console-commands.md) komutları tam listesi için.  
  
> [!TIP]
>  JavaScript Konsolu penceresi kapatıldığında kaldığınızda **hata ayıklama**> **Windows** > **JavaScript Konsolu** yeniden açın. Betik hata ayıklama oturumunun yalnızca sırasında penceresi görüntülenir.  
  
 JavaScript Konsolu penceresi kullanarak, hata ayıklayıcı durdurup olmadan uygulamanız ile etkileşebilirsiniz. Daha fazla bilgi için bkz: [bir uygulama (JavaScript) yenileme](../debugger/refresh-an-app-javascript.md). DOM Gezgini'ni kullanarak ve kesme noktaları, ayarlama gibi özellikleri, hata ayıklama diğer JavaScript ilişkin bilgi için bkz: [hızlı başlangıç: hata ayıklama HTML ve CSS](../debugger/quickstart-debug-html-and-css.md) ve [Visual Studio uygulamalarında hata ayıklama](../debugger/debug-store-apps-in-visual-studio.md).  
  
##  <a name="InteractiveConsole"></a> JavaScript Konsolu penceresi kullanarak hata ayıklama  
 Aşağıdaki adımları oluşturma bir `FlipView` uygulama ve etkileşimli olarak kodlama hatası JavaScript hata ayıklama gösterilmektedir.  
  
> [!NOTE]
>  Örnek uygulama burada bir UWP uygulaması olur. Ancak, burada açıklanan konsol özellikleri, Apache Cordova için Visual Studio Araçları kullanılarak oluşturulan uygulamalar için de geçerlidir.  
  
#### <a name="to-debug-javascript-code-in-the-flipview-app"></a>JavaScript kodu FlipView uygulamasında hata ayıklamak için  
  
1.  Seçerek Visual Studio'da yeni bir çözüm oluşturmak **dosya** > **yeni proje**.  
  
2.  Seçin **JavaScript** > **Windows Evrensel**ve ardından **WinJS uygulama**.  
  
3.  Proje için bir ad yazın `FlipViewApp`ve seçin **Tamam** uygulama oluşturmak için.  
  
4.  İndex.html gövde öğesinde varolan HTML kodu bu kod ile değiştirin:  
  
    ```html  
    <div id="flipTemplate" data-win-control="WinJS.Binding.Template"  
             style="display:none">  
        <div class="fixedItem" >  
            <img src="#" data-win-bind="src: flipImg" />  
        </div>  
    </div>  
    <div id="fView" data-win-control="WinJS.UI.FlipView" data-win-options="{  
        itemDataSource: Data.items.dataSource, itemTemplate: flipTemplate }">  
    </div>  
    ```  
  
5.  Default.css açın ve CSS için ekleyin `#fView` Seçici:  
  
    ```css  
    #fView {  
        background-color:#0094ff;  
        height: 500px;  
        margin: 25px;  
    }  
    ```  
  
6.  Default.js açın ve kodu aşağıdaki JavaScript kod ile değiştirin:  
  
    ```javascript  
    (function () {  
        "use strict";  
  
        var app = WinJS.Application;  
        var activation = Windows.ApplicationModel.Activation;  
  
        var myData = [];  
        for (var x = 0; x < 4; x++) {  
            myData[x] = { flipImg: "/images/logo.png" }  
        };  
  
        var pages = new WinJS.Binding.List(myData, { proxy: true });  
  
        app.onactivated = function (args) {  
            if (args.detail.kind === activation.ActivationKind.launch) {  
                if (args.detail.previousExecutionState !==  
                activation.ApplicationExecutionState.terminated) {  
                    // TODO: . . .  
                } else {  
                    // TODO: . . .  
                }  
                args.setPromise(WinJS.UI.processAll());  
  
                updateImages();  
            }  
        };  
  
        function updateImages() {  
  
            pages.push(0, { flipImg: "http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-76.jpg" });  
            pages.push(1, { flipImg: "http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-77.jpg" });  
            pages.push(2, { flipImg: "http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-78.jpg" });  
  
        };  
  
        app.oncheckpoint = function (args) {  
        };  
  
        app.start();  
  
        var publicMembers = {  
            items: pages  
        };  
  
        WinJS.Namespace.define("Data", publicMembers);  
  
    })();  
    ```  
  
7.  Hata ayıklama hedefi seçili değilse, seçin **yerel makine** bulunan aşağı açılan listesinde yanına **aygıt** düğmesini **hata ayıklama** araç çubuğu:  
  
     ![Select hata ayıklama hedef listesi](../debugger/media/js_select_target.png "JS_Select_Target")  
  
8.  Hata ayıklayıcı başlatmak için F5 tuşuna basın.  
  
     Uygulama çalışır ancak görüntüleri eksik. JavaScript konsol penceresinde APPHOST hatalarını görüntüler eksik olduğunu gösterir.  
  
9. İle `FlipView` çalışan, uygulama türü `Data.items` giriş penceresi istemi konsolunda (yanındaki ">>" simgesi) ve Enter tuşuna basın.  
  
     Görselleştirici için `items` nesne konsol penceresinde görünür. Bu belirten `items` nesne örneği ve geçerli betik bağlamda kullanılamıyor. Konsol penceresinde özellik değerlerini görüntülemek (veya ok tuşlarını kullanın) için bir nesne düğümleri arasında tıklatabilirsiniz. Aşağı uygulamasına tıklarsanız `items._data` nesnesi resimde gördüğünüz gibi kendi görüntü kaynağı başvuruları beklendiği gibi yanlış olduğunu göreceksiniz. Varsayılan görüntü (logo.png) nesnesinde hala mevcut olduğunda ve beklenen görüntülerle interspersed eksik görüntüler.  
  
     ![JavaScript Konsolu penceresi](../debugger/media/js_console_window.png "JS_Console_Window")  
  
     Ayrıca, çok daha fazla öğe olduğunu unutmayın `items._data` , beklediğinizden nesne.  
  
10. İsteminde `Data.items.push` ve Enter tuşuna basın. Görselleştirici için konsol penceresi gösterilir `push` uygulanan işlevi bir [!INCLUDE[winjs_long](../debugger/includes/winjs_long_md.md)] proje dosyası. Bu uygulamada kullanıyoruz `push` doğru öğeleri eklemek için. IntelliSense kullanma küçük bir araştırma ile biz biz kullanması gerektiğini olduğunu öğrenmek `setAt` varsayılan görüntülerini değiştirmek için.  
  
11. Hata ayıklama oturumu durdurmadan etkileşimli olarak bu sorunu gidermek için default.js açın ve bu koddan seçin `updateImages` işlevi:  
  
    ```javascript  
    pages.push(0, { flipImg: "http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-76.jpg" });  
    pages.push(1, { flipImg: "http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-77.jpg" });  
    pages.push(2, { flipImg: "http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-78.jpg" });  
    ```  
  
     Bu kodu kopyalayıp giriş JavaScript Konsolu komut isteminde yapıştırın.  
  
    > [!TIP]
    >  Birden fazla satır kod içine yapıştırdığınız zaman istemi JavaScript konsoluna giriş, giriş Konsolu komut isteminde otomatik olarak çok satırlı moda geçer. Çok satırlı modunu açma ve kapatma için Ctrl + Alt + M tuşlarına basabilirsiniz. Çok satırlı modunda bir komut dosyasını çalıştırmak için Ctrl + Enter tuşuna basın veya penceresinin sağ alt köşesinde ok simgesini seçin. Daha fazla bilgi için bkz: [tek satırlı moda ve JavaScript konsol penceresinde çok satırlı moda](#SinglelineMultilineMode).  
  
12. Düzeltmek `push` işlevi çağırır isteminde değiştirme `pages.push` ile `Data.items.setAt`. Düzeltilmiş kod gibi görünmelidir:  
  
    ```javascript  
    Data.items.setAt(0, { flipImg: "http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-76.jpg" });  
    Data.items.setAt(1, { flipImg: "http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-77.jpg" });  
    Data.items.setAt(2, { flipImg: "http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-78.jpg" });  
    ```  
  
    > [!TIP]
    >  Kullanmak istiyorsanız, `pages` yerine nesne `Data.items`, tutmak için kodunuzda bir kesme noktası belirleyerek gerek `pages` kapsamındaki nesne.  
  
13. Komut dosyasını çalıştırmak için yeşil ok simgesini seçin.  
  
14. Tek satırlı moda giriş Konsolu komut isteminde, ve ardından Ctrl + Alt + M basın **temizleyin giriş** (giriş isteminden kodunu silmek için kırmızı "X").  
  
15. Tür `Data.items.length = 3` istemi ve ENTER tuşuna basın. Bu, verileri yabancı öğeleri kaldırır.  
  
16. Uygulamayı yeniden denetleyin ve doğru görüntüleri doğru olduğunu görürsünüz `FlipView` sayfaları.  
  
17. DOM Gezgini'nde, güncelleştirilmiş DIV öğesinin görebilir ve beklenen IMG öğeleri bulmak için alt ağacı gidin.  
  
18. Seçerek hata ayıklamayı durdurun **hata ayıklama** > **durdurma hata ayıklama** veya göre Shift + F5'e basarak ve kaynak kodu düzeltin.  
  
     Tam default.html sayfayı içeren örnek kod düzeltildi için bkz: [hata ayıklama HTML, CSS ve JavaScript örnek kod](../debugger/debug-html-css-and-javascript-sample-code.md).  
  
##  <a name="InteractiveDebuggingBreakMode"></a> Etkileşimli hata ayıklama ve kesme modu  
 Kesme noktaları ve JavaScript hata ayıklama araçları JavaScript Konsolu penceresi gibi kullanırken koda adım kullanabilirsiniz. Hata ayıklayıcıda çalıştırılan bir program bir kesme noktası karşılaştığında, hata ayıklayıcı programın yürütülmesi geçici olarak askıya alır. Yürütme askıya alındığında, programınızı kesme modu için çalışma modunda geçer. Herhangi bir zamanda yürütme devam edebilirsiniz.  
  
 Bir program kesme modunda olduğunda, komut dosyaları ve geçerli komut dosyası yürütme bağlam için geçerli olan komutları çalıştırmak için JavaScript Konsolu penceresi kullanabilirsiniz. Bu yordamda, sabit sürümü kullanacağınız `FlipView` kesme modu kullanımını göstermek için daha önce oluşturduğunuz uygulama.  
  
#### <a name="to-set-a-breakpoint-and-debug-the-app"></a>Bir kesme noktası ayarlama ve uygulama hatalarını ayıklamak için  
  
1.  Default.html dosyasındaki `FlipView` , daha önce oluşturulmuş kısayol menüsünü açın uygulama `updateImages()` işlev ve ardından **kesme noktası** > **kesme noktası Ekle**.  
  
2.  Seçin **yerel makine** açılan liste yanına **hata ayıklamayı Başlat** düğmesini **hata ayıklama** araç.  
  
3.  Seçin **hata ayıklama** > **hata ayıklamayı Başlat**, veya F5 tuşuna basın.  
  
     Yürütme ulaştığında uygulamayı Kesme moduna girer `updateImages()` işlevi ve program yürütme geçerli satırının sarı olarak vurgulanır.  
  
     ![Kesme modu ile JavaScript konsolu kullanılarak](../debugger/media/js_breakmode.png "JS_BreakMode")  
  
     Hemen geçerli hata ayıklama oturumu sona erdirmeden programın durumunu etkileyen değişkenlerin değerleri değiştirebilirsiniz.  
  
4.  Tür `updateImages` istemi yazıp Enter tuşuna basın. Görselleştirici işlevi için konsol penceresinde görünür.  
  
5.  İşlev uygulama göstermek için konsol penceresinde işlevi seçin.  
  
     Aşağıdaki çizimde, bu noktada konsol penceresi gösterir.  
  
     ![JavaScript Konsolu penceresi Görselleştirici gösteren](../debugger/media/js_console_function_visualizer.png "JS_Console_Function_Visualizer")  
  
6.  Tek bir çizgi işlevinin giriş sorusu çıktı penceresinden kopyalayın ve dizin değeri 3 olarak değiştirin:  
  
    ```javascript  
    pages.setAt(3, { flipImg: "http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-76.jpg" });  
    ```  
  
7.  Kod satırını çalıştırmak için Enter tuşuna basın.  
  
     Satır kod üzerinden adım istiyorsanız, F11 tuşuna basın veya program yürütme devam etmek için F5 tuşuna basın.  
  
8.  Program yürütme devam etmek için F5 tuşuna basın. `FlipView` Uygulama görünür ve şimdi tüm dört sayfalar varsayılan olmayan görüntülerden birini gösterir.  
  
     Visual Studio'ya geri dönmek için F12 veya Alt + Sekme tuşuna basın.  
  
##  <a name="SinglelineMultilineMode"></a> Tek satırlı modu ve JavaScript konsol penceresinde çok satırlı modu  
 JavaScript Konsolu penceresi giriş sor tek satırlı moda ve çok satırlı moda destekler. Bu konudaki etkileşimli hata ayıklama yordamı her iki modu kullanarak bir örnek sağlar. Modlar arasında geçiş yapmak için Ctrl + Alt + M tuşlarına basabilirsiniz.  
  
 Tek satırlı moda giriş geçmişini sağlar. Yukarı ve aşağı ok tuşlarını kullanarak giriş geçmişinde gidebilirsiniz. Komut dosyalarını çalıştırdığınızda tek satırlı moda giriş istemi temizler. Tek satırlı modunda bir komut dosyasını çalıştırmak için Enter tuşuna basın.  
  
 Komut dosyalarını çalıştırdığınızda, çok satırlı moda giriş istemi temizlemez. Çok satırlı modundan tek satırlı moda geçiş yaptığınızda tuşlarına basarak giriş satır temizleyebilirsiniz **temizleyin giriş** (kırmızı "X"). Çok satırlı modunda bir komut dosyasını çalıştırmak için Ctrl + Enter tuşuna basın veya penceresinin sağ alt köşesinde ok simgesini seçin.  
  
##  <a name="Switching"></a> Komut dosyası yürütme bağlamı değiştirme  
 JavaScript Konsolu penceresi aynı anda tek bir web platformu ana bilgisayar (WWAHost.exe) örneğini temsil eder, tek yürütme bağlamı ile etkileşim sağlar. Bazı senaryolarda, uygulamanızın başka bir örneği kullandığınızda konağının başlayabilir bir `iframe`, paylaşım sözleşme, bir web çalışanı veya `WebView` denetim. Başka bir ana bilgisayar örneği çalışıyorsa, yürütme bağlamı seçerek uygulama çalıştırılırken farklı yürütme bağlamı seçebilirsiniz **hedef** listesi.  
  
 Aşağıdaki çizimde JavaScript konsol penceresinde hedef listesini gösterir.  
  
 ![Hedef seçimi JavaScript konsol penceresinde](../debugger/media/js_console_target.png "JS_Console_Target")  
  
 Yürütme bağlamı kullanarak da geçiş yapabilirsiniz `cd` komutu, ancak diğer yürütme bağlamı adını bilmeniz gerekir ve kullandığınız başvuru kapsamında olması gerekir. **Hedef** listesi diğer yürütme bağlamı daha iyi erişim sağlar.   
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio uygulamalarında hata ayıklama](../debugger/debug-store-apps-in-visual-studio.md)   
 [JavaScript Konsolu komutları](../debugger/javascript-console-commands.md)   
 [Bir uygulama (JavaScript) Yenile](../debugger/refresh-an-app-javascript.md)   
 [Klavye kısayolları](../debugger/keyboard-shortcuts-html-and-javascript.md)   
 [HTML, CSS ve JavaScript örnek kodda hata ayıklama](../debugger/debug-html-css-and-javascript-sample-code.md)   
 [Hızlı Başlangıç: HTML ve CSS hata ayıklama](../debugger/quickstart-debug-html-and-css.md)   
 [Bir Web Görünümü denetimi hata ayıklama](../debugger/debug-a-webview-control.md)   
 [Ürün desteği ve erişilebilirlik](http://msdn.microsoft.com/library/tzbxw1af\(VS.120\).aspx)