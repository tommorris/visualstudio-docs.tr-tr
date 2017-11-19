---
title: "HTML ve CSS (UWP ve Windows 8.1 uygulamaları) hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 07/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.WebClient.DomExplorer
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, CSS
- debugging, HTML
- debugging, JavaScript [UWP apps]
- DOM Explorer [UWP apps]
ms.assetid: 6d156cff-36c6-425a-acf8-e1f02d4f7869
caps.latest.revision: "101"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f1650326711d8d788a7e232df97044c8e896e3b4
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="debug-html-and-css-in-uwp-and-windows-81-apps"></a>HTML ve CSS UWP ve Windows 8.1 uygulamaları hata ayıklama
![Windows ve Windows Phone için geçerlidir](../debugger/media/windows_and_phone_content.png "windows_and_phone_content")  
  
 JavaScript uygulamaları için Visual Studio, Internet Explorer ve Visual Studio geliştiricilerinin aşina özellikleri içeren kapsamlı bir hata ayıklama deneyimi sağlar. Bu özellikler için desteklenen [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)], Windows Phone uygulamaları ve Apache Cordova için Visual Studio Araçları kullanılarak oluşturulan uygulamalar için.  
  
 DOM denetleme araçları tarafından sağlanan etkileşimli hata ayıklama modelini kullanarak görüntüleyebilir ve işlenen HTML ve CSS kodu değiştirebilirsiniz. Tüm hata ayıklayıcı durdurup olmadan bunu yapabilirsiniz.
  
 JavaScript Konsolu penceresi kullanarak ve kesme noktaları, ayarlama gibi özellikleri, hata ayıklama diğer JavaScript ilişkin bilgi için bkz: [hızlı başlangıç: JavaScript hata ayıklama](../debugger/quickstart-debug-javascript-using-the-console.md) ve [Visual Studio uygulamalarında hata ayıklama](../debugger/debug-store-apps-in-visual-studio.md).  
  
##  <a name="InspectingDOM"></a>Canlı DOM inceleniyor  
 DOM Gezgini işlenen sayfa görünümünü gösterir ve değerleri değiştirmek ve hemen sonuçları görmek için DOM Gezgini'ni kullanın. Bu değişiklikleri hata ayıklayıcı durdurup olmadan test etmenizi sağlar. Bu yöntemi kullanarak sayfa ile etkileşim kurarken, projenizi kaynak kodunda değiştirmez istenen kod düzeltmeleri bulduğunuzda, kaynak kodunuzu değişiklik yaparsınız.  
  
> [!TIP]
>  Durdurma ve kaynak kodunuzu değişiklik yaptığınızda hata ayıklayıcı yeniden başlatmayı önlemek için uygulamanızı kullanarak yenileyebilirsiniz **yenileme Windows uygulaması** düğmesi hata ayıklama araç çubuğunda (veya F4 tuşlarına basarak). Daha fazla bilgi için bkz: [bir uygulama (JavaScript) yenileme](../debugger/refresh-an-app-javascript.md).  
  
 DOM Gezgini kullanabilirsiniz:  
  
-   DOM öğesi alt ağacı gidin ve işlenen HTML, CSS ve JavaScript kodu inceleyin.  
  
-   Dinamik olarak öznitelikleri ve CSS stil işlenmiş öğeleri için düzenleyin ve hemen sonuçlarını görebilirsiniz.  
  
-   CSS stilleri sayfa öğelerine nasıl uygulanmış olan inceleyebilir ve uygulanmış olan kurallar izleme.  
  
 Hata ayıklama uygulamaları, genellikle DOM Gezgini'nde öğeleri seçmeniz gerekir. Bir öğe seçtiğinizde, DOM Gezgini'nde sağ tarafındaki sekmelerinde otomatik olarak görünen değerlerin seçili öğenin DOM Gezgini'nde yansıtacak şekilde güncelleştirin. Sekmeleri şunlardır: **stilleri**, **hesaplanan**, **düzeni**. UWP uygulamaları da desteği **olayları** ve **değişiklikleri** sekmeleri. Öğeler seçme hakkında daha fazla bilgi için bkz: [öğeleri seçerek](#SelectingElements).  
  
> [!TIP]
>  DOM Gezgini penceresi kapattıysanız, seçin **hata ayıklama**>**Windows** > **DOM Gezgini** yeniden açın. Pencere, yalnızca bir komut dosyası hata ayıklama oturumu sırasında görüntülenir.  
  
 Aşağıdaki yordamda, biz etkileşimli olarak DOM Gezgini'ni kullanarak bir uygulama hata ayıklama işlemi gidersiniz. Kullanan bir uygulama oluşturacağız bir `FlipView` denetlemek ve ardından hata ayıklama. Uygulama çeşitli hatalar içeriyor.  
  
> [!WARNING]
>  Aşağıdaki örnek bir UWP uygulaması uygulamasıdır. Cordova için aynı özellikleri desteklenir, ancak uygulama farklı olacaktır.  
  
#### <a name="to-debug-by-inspecting-the-live-dom"></a>Canlı DOM inceleyerek hata ayıklamak için  
  
1.  Seçerek Visual Studio'da yeni bir çözüm oluşturmak **dosya** > **yeni proje**.  
  
2.  Seçin **JavaScript** > **deposu**, ya da seçin **Windows uygulamalarını** veya **Windows Phone uygulamaları**ve ardından seçin **Boş uygulama**.  
  
3.  Proje için bir ad yazın `FlipViewApp`ve seçin **Tamam** uygulama oluşturmak için.  
  
4.  Default.html gövde öğesine bu kodu ekleyin:  
  
    ```html  
    <div id="flipTemplate" data-win-control="WinJS.Binding.Template"  
             style="display:none">  
        <div class="fixedItem" >  
            <img src="#" data-win-bind="src: flipImg" />  
        </div>  
    </div>  
    <div id="fView" style="width:100px;height:100px"  
        data-win-control="WinJS.UI.FlipView" data-win-options="{  
        itemDataSource: Data.items.dataSource, itemTemplate: flipTemplate }">  
    </div>  
    ```  
  
5.  Default.css açın ve aşağıdaki CSS ekleyin:  
  
    ```css  
    #fView {  
        background-color:#0094ff;  
        height: 100%;  
        width: 100%;  
        margin: 25%;  
    }  
    ```  
  
6.  Default.js kodda bu kod ile değiştirin:  
  
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
  
            pages.setAt(0, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223195" });  
            pages.setAt(1, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223196" });  
            pages.setAt(2, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223197" });  
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
  
     Aşağıdaki çizimde, biz Phone öykünücüsü (Benzeticisinde benzer görünür), bu uygulama çalıştırırsanız görmeyi istiyoruz gösterir. Ancak, uygulama bu duruma getirmek için biz hataların sayısını ilk düzeltme gerekecektir.  
  
     ![Beklenen sonuçları gösteren FlipView uygulama](../debugger/media/js_dom_appfixed.png "JS_DOM_AppFixed")  
  
7.  Ya da seçin **Simulator** veya **öykünücüsü 8.1 WVGA 4 inç 512MB** bulunan aşağı açılan listesinde yanına **hata ayıklamayı Başlat** düğmesini **hataayıklama**araç çubuğu:  
  
     ![Select hata ayıklama hedef listesi](../debugger/media/js_select_target.png "JS_Select_Target")  
  
8.  Seçin **hata ayıklama** > **hata ayıklamayı Başlat**, ya da uygulamanızı hata ayıklama modunda çalıştırmak için F5 tuşuna basın.  
  
     Bu uygulamayı benzetici veya telefon öykünücü çalışır, ancak stil birkaç hataların olmadığı için çoğunlukla boş bir ekran görürsünüz. İlk `FlipView` ekranın Orta yanında küçük bir kare görüntü görünür.  
  
9. Benzetici uygulama çalıştırıyorsanız, seçin **değiştirmek çözümleme** 1280 x 800 ekran çözünürlüğü yapılandırmak için Simulator sağındaki araç komutu. Bu, aşağıdaki adımlarda gösterilen değerleri Benzeticisinde gördükleri eşleşen güvence altına alır.  
  
10. Geçiş için Visual Studio ve seçin **DOM Gezgini** sekmesi.  
  
    > [!TIP]
    >  Visual Studio ve çalışan uygulamanın arasında geçiş yapmak için Alt + sekme veya F12 tuşuna basabilirsiniz.  
  
11. DOM Gezgini penceresi Kimliğine sahip bölüm DIV öğesinin seçin `"fView"`. Görüntülemek ve doğru DIV öğesinin seçmek için ok tuşlarını kullanın. (Sağ ok tuşuna bir öğenin alt öğelerini görüntülemenize izin verir.)  
  
     ![DOM Gezgini](../debugger/media/js_dom_explorer.png "JS_DOM_Explorer")  
  
    > [!TIP]
    >  Yazarak JavaScript konsol penceresinin sol alt köşesinde DIV öğesinin seçebilirsiniz `select(fView)` adresindeki >> giriş istem ve sonra Enter tuşuna basın.  
  
     DOM Gezgini penceresinin sağ tarafında sekmelerde otomatik olarak görünür değerlerini, geçerli öğenin DOM Gezgini'nde yansıtacak şekilde güncelleştirin.  
  
12. Seçin **hesaplanan** sağa sekmesinde.  
  
     Bu sekme seçilen DOM öğesinin her bir özellik için hesaplanan ya da son değerini gösterir.  
  
13. Yükseklik CSS kuralı açın. Yükseklik değeri ayarlamak için % 100 ile tutarsız görünür 100px bir satır içi stil kümesine fark `#fView` CSS Seçici. Üstü çizili metni `#fView` seçiciyi gösterir içi stil bu stili önceliği sürüyor.  
  
     Aşağıdaki çizimde gösterildiği **hesaplanan** sekmesi.  
  
     ![DOM Gezgini hesaplanan sekmesini](../debugger/media/js_dom_explorer_computed.png "JS_DOM_Explorer_Computed")  
  
14. Satır içi stili genişliği ve yüksekliği için ana DOM Gezgini penceresinde, çift `fView` DIV öğesinin. Şimdi buraya değerler düzenleyebilirsiniz. Bu senaryoda, tamamen kaldırmak istiyoruz.  
  
15. Seçin `width: 100px;height: 100px;`Delete tuşuna basın ve ardından Enter tuşuna basın. Enter tuşuna bastıktan sonra hata ayıklama oturumu durduruldu henüz karşın yeni değerleri hemen benzeticisi veya Phone öykünücüsü yansıtılır.  
  
    > [!IMPORTANT]
    >  DOM Gezgini penceresi öznitelikleri güncelleştirebilir gibi görünür değerleri da güncelleştirebilirsiniz **stilleri**, **hesaplanan**, ve **düzeni** sekmeleri. Daha fazla bilgi için bkz: [DOM Gezgini'ni kullanarak hata ayıklama CSS stilleri](../debugger/debug-css-styles-using-dom-explorer.md) ve [DOM Gezgini'ni kullanarak hata ayıklama Düzen](../debugger/debug-layout-using-dom-explorer.md).  
  
16. Uygulamaya benzeticisi veya Phone öykünücüsü seçerek veya Alt + sekme kullanarak geçiş yapın.  
  
     Şimdi `FlipView` denetim Simulator'ın veya Phone öykünücüsü'nın ekran boyutundan daha büyük görünür. Bu amaçlanan sonucu değildir. Araştırmak için Visual Studio'ya geri geçin.  
  
17. DOM Gezgini'nde seçin **hesaplanan** yeniden sekmesinde ve yüksekliği kuralı açın. FView öğesi hala CSS'den beklendiği gibi % 100 değerini gösterir, ancak ne bu uygulama için istiyoruz değil olan Simulator'ın ekran yüksekliğe (örneğin, 800 piksel veya 667.67px), hesaplanan değeri eşittir. Araştırmak için yüksekliğini ve genişliğini kaldırabilirsiniz `fView` DIV öğesinin.  
  
18. İçinde **stilleri** sekmesinde, yükseklik ve genişlik özelliklerini işaretini `#fView` CSS Seçici.  
  
     **Hesaplanan** sekmesi şimdi 400px yüksekliğini gösterir. Bu değer UI-platform CSS dosyası olan dark.css içinde belirtilen .win flipview Seçici'den gelen bilgileri gösterir.  
  
19. Uygulamaya tekrar geçin.  
  
     Şeyler iyileştirilmiştir. Ancak, yine düzeltmek için bir daha fazla sorun olduğunu: kenar boşluklarını çok büyük görünür.  
  
20. Araştırmak için geçiş için Visual Studio ve seçin **düzeni** öğenin kutusunun modeli aramak için sekmesi.  
  
     İçinde **düzeni** sekmesinde, aşağıdaki değerleri görürsünüz:  
  
    -   Simulator için: 320px (uzaklık) ve 320px (kenar boşluğu).  
  
    -   Phone öykünücüsü: 100px (uzaklık) ve 100px (kenar boşluğu).  
  
     Aşağıdaki çizimde gösterildiği nasıl **düzeni** sekmesi görünür Phone öykünücüsü (100px uzaklık ve kenar boşluğu) kullanıyorsanız.  
  
     ![DOM Gezgini Düzen sekmesini](../debugger/media/js_dom_explorer_layout.png "JS_DOM_Explorer_Layout")  
  
     Bu doğru olmadığı görülüyor. **Hesaplanan** sekmesi ayrıca aynı kenar boşluğu değerlerini gösterir.  
  
21. Seçin **stilleri** sekmesinde ve bulun `#fView` CSS Seçici. % 25'için değeri burada gördüğünüz **kenar boşluğu** özelliği.  
  
22. % 25'i seçin ve 25px için değiştirin ve Enter tuşuna basın.  
  
23. Ayrıca, **stilleri** sekmesinde, .win flipview Seçici yüksekliği kuralı seçin ve 500px için 400px değiştirin ve Enter tuşuna basın.  
  
24. Geçiş uygulamaya tekrar ve öğeleri yerleşimini doğru göründüğünü görebilirsiniz. Kaynak düzeltmeleri yapın ve uygulama hata ayıklayıcı durdurup olmadan yenilemek için aşağıdaki yordama bakın.  
  
#### <a name="to-refresh-your-app-while-debugging"></a>Hata ayıklama sırasında uygulamanızı yenilemek için  
  
1.  Uygulama çalışmaya devam ederken, Visual Studio'ya geçin.  
  
2.  Default.HTML açın ve kaynak kodunuzu yüksekliğini ve genişliğini değiştirerek değişiklik `"fView"` DIV öğesinin % 100.  
  
3.  Seçin **yenileme Windows uygulaması** Debug araç çubuğunda düğmesini (veya F4 tuşuna basın). Düğme şöyle görünür: ![yenileme Windows Uygulama düğmesi](../debugger/media/js_refresh.png "JS_Refresh").  
  
     Uygulama sayfaları yeniden ve benzeticisi veya Phone öykünücüsü ön plana döndürür.  
  
     Yenileme özelliği hakkında daha fazla bilgi için bkz: [bir uygulama (JavaScript) yenileme](../debugger/refresh-an-app-javascript.md).  
  
##  <a name="SelectingElements"></a>Öğeler seçme  
 Bir uygulama hata ayıklama sırasında üç yolla DOM öğeleri seçebilirsiniz:  
  
-   Öğeleri doğrudan DOM Gezgini penceresi (veya ok tuşlarını kullanarak) tıklayarak.  
  
-   Kullanarak **seçin öğesi** düğmesini (Ctrl + B).  
  
-   Kullanarak `select` biridir komutu, [JavaScript Konsolu komutları](../debugger/javascript-console-commands.md).  
  
 DOM Gezgini penceresi öğeleri seçin ve bir öğede fare işaretçisini kullandığınızda, karşılık gelen öğe çalışan uygulamada vurgulanır. DOM Gezgini seçmek için öğesinde tıklatmalısınız veya vurgulayın ve öğelerini seçmek için ok tuşlarını kullanın. Kullanarak DOM Gezgini'nde öğeleri seçebilirsiniz **Select öğesi** düğmesi. Aşağıdaki çizimde gösterildiği **seçin öğesi** düğmesi.  
  
 ![DOM Gezgini'nde öğe düğmesini seçin](../debugger/media/js_dom_select_element_button.png "JS_DOM_Select_Element_Button")  
  
 Tıkladığınızda **Select öğesi** (veya Ctrl + B tuşuna basın), çalışan uygulamaya tıklayarak öğeyi DOM Gezgini'nde seçebilir böylece bu seçim modunu değiştirir. Modunu tek tıklattıktan sonra normal seçim moduna geri değiştirir. Tıkladığınızda **Select öğesi**, uygulamanın ön plana gelir ve imleci değişikliklerini yeni seçim modu yansıtır. Anahatları belirlenmiş öğesi tıkladığınızda, DOM Gezgini ön plana seçili belirtilen öğeyi döndürür.  
  
 Seçtiğiniz önce **öğesi seçin**, çalışan uygulamanın öğelerinde değiştirerek vurgulamak belirtebilirsiniz **görüntülemek web sayfası vurgular** düğmesi. Bu düğme aşağıda gösterilmektedir. Öne çıkan özellikleri varsayılan olarak görüntülenir.  
  
 ![Web Sayfa Görüntüle düğmesi vurgular](../debugger/media/js_dom_display_highlights_button.png "JS_DOM_Display_Highlights_Button")  
  
 Öğeleri vurgulamak seçtiğinizde Benzeticisinde üzerine öğeler vurgulanır. Vurgulanan öğeleri görünür kutu modeli eşleştirmek için renkleri **düzeni** DOM Gezgini sekmesinde.  
  
> [!NOTE]
>  Üzerine gelerek öğeleri vurgulama, Windows Phone öykünücüsünde yalnızca kısmen desteklenir.  
  
 Kullanarak öğelerini seçmek nasıl oluşturulduğunu gösteren bir örnek **Select öğesi** düğmesini bkz [DOM Gezgini'ni kullanarak hata ayıklama CSS stilleri](../debugger/debug-css-styles-using-dom-explorer.md).  
  
##  <a name="BrowserSupport"></a>Tarayıcı ve Platform desteği  
 JavaScript, DOM Gezgini ve JavaScript Konsolu penceresi için Visual Studio Araçları aşağıdaki platformlarda desteklenir:  
  
-   [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)]ve JavaScript ve HTML kullanarak Windows Phone uygulamaları  
  
-   Internet Explorer 11 üzerinde çalışan[!INCLUDE[win81](../debugger/includes/win81_md.md)]  
  
-   Internet Explorer 10 üzerinde çalışan[!INCLUDE[win8](../debugger/includes/win8_md.md)]  
  
 Git [burada](http://go.microsoft.com/fwlink/?LinkID=232448) indirmek için [!INCLUDE[win8](../debugger/includes/win8_md.md)] ve Visual Studio.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio uygulamalarında hata ayıklama](../debugger/debug-store-apps-in-visual-studio.md)   
 [DOM Gezgini'ni kullanarak CSS stillerinde hata ayıklama](../debugger/debug-css-styles-using-dom-explorer.md)   
 [DOM Gezgini'ni kullanarak Düzen hatalarını ayıklama](../debugger/debug-layout-using-dom-explorer.md)   
 [DOM olayı dinleyicilerini görüntüleme](../debugger/view-dom-event-listeners.md)   
 [Bir uygulama (JavaScript) Yenile](../debugger/refresh-an-app-javascript.md)   
 [Bir Web Görünümü denetimi hata ayıklama](../debugger/debug-a-webview-control.md)   
 [Klavye kısayolları](../debugger/keyboard-shortcuts-html-and-javascript.md)   
 [JavaScript Konsolu komutları](../debugger/javascript-console-commands.md)   
 [HTML, CSS ve JavaScript örnek kodda hata ayıklama](../debugger/debug-html-css-and-javascript-sample-code.md)   
 [Ürün desteği ve erişilebilirlik](http://msdn.microsoft.com/library/tzbxw1af\(VS.120\).aspx)