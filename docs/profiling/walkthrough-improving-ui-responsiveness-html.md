---
title: "İzlenecek yol: UI yanıtlama hızı (HTML) geliştirme | Microsoft Docs"
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
helpviewer_keywords:
- performance tools, JavaScript [UWP apps]
- performance, JavaScript [UWP apps]
- performance, HTML [UWP apps]
- performance tools, HTML [UWP apps]
ms.assetid: 7e5a2524-dbf5-4a40-b5d6-2d1ed7fff3de
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4d1d35049d71ba011516b3bc06316cb46cc61ced
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/14/2017
---
# <a name="walkthrough-improving-ui-responsiveness-html"></a>İzlenecek yol: UI yanıtlama hızı (HTML) artırma
Tanımlama ve kullanarak bir performans sorunu düzeltme sürecinde sizi bu kılavuzda [HTML UI yanıtlama hızı Profil Oluşturucusu](../profiling/html-ui-responsiveness.md). Profil Oluşturucu, JavaScript kullanarak UWP uygulamalar için Visual Studio'da kullanılabilir. Bu senaryoda, DOM öğeleri çok sık güncelleştirmeler bir performans testi uygulaması oluşturma ve tanımlamak ve bu sorunu gidermek için profil oluşturucu kullanın.  
  
### <a name="creating-and-running-the-performance-test-app"></a>Uygulama testi oluşturma ve performans çalıştırma  
  
1.  Visual Studio'da yeni bir Windows Evrensel JavaScript projesi oluşturun. (Seçin **Dosya > Yeni > Proje**. Seçin **JavaScript** sol bölmede ve ardından **Windows**, **Windows 10**, sonra da **Evrensel**, veya  **Windows Phone**.  
  
2.  > [!IMPORTANT]
    >  Bu konuda gösterilen Tanılama sonuçları için Windows 8 uygulaması gösterilir.  
  
3.  Boş proje şablonlarından birini Orta bölmede, aşağıdaki gibi seçin **boş uygulama**.  
  
4.  İçinde **adı** kutusunda, gibi bir ad belirtin `JS_Perf_Tester`ve ardından **Tamam**.  
  
5.  İçinde **Çözüm Gezgini**, default.html açın ve aşağıdaki kodu arasında yapıştırın \<gövde > etiketleri:  
  
    ```html  
    <div class="wrapper">  
        <button id="content">Waiting for values</button>  
    </div>  
    ```  
  
6.  Default.css açın ve aşağıdaki CSS kodu ekleyin:  
  
    ```css  
    #content {  
        margin-left: 100px;  
        margin-top: 100px;  
    }  
    ```  
  
7.  Default.js açın ve tüm kodu bu kod ile değiştirin:  
  
    ```javascript  
    (function () {  
        "use strict";  
  
        var app = WinJS.Application;  
        var activation = Windows.ApplicationModel.Activation;  
  
        var content;  
        var wrapper;  
  
        app.onactivated = function (args) {  
            if (args.detail.kind === activation.ActivationKind.launch) {  
                if (args.detail.previousExecutionState !== activation.ApplicationExecutionState.terminated) {  
  
                    content = document.getElementById("content");  
                    wrapper = document.querySelector(".wrapper");  
  
                    content.addEventListener("click", handler);  
  
                } else {  
                }  
  
                args.setPromise(WinJS.UI.processAll());  
            }  
        };  
  
        app.oncheckpoint = function (args) {  
        };  
  
        app.start();  
  
        var idx = 0;  
        var count = 0;  
        var max = 5000;  
        var text = ["what", "is", "the", "Matrix?"];  
        var color = ["red", "crimson", "maroon", "purple"];  
  
        function increment() {  
  
            setTimeout(function () {  
  
                idx++;  
                count++;  
  
                if (idx > 3) { idx = 0; }  
                if (count < max) { increment(); }  
  
            }, 1000);  
        }  
  
        function setValues() {  
  
            content = document.getElementById("content");  
            content.removeNode(true);  
  
            var newNode = document.createElement("button");  
            newNode.id = "content";  
            newNode.textContent = text[idx];  
            //newNode.textContent = getData();  
            newNode.style.backgroundColor = color[idx];  
            //newNode.style.animationName = "move";  
            //count++;  
  
            wrapper.appendChild(newNode);  
  
        }  
  
        function update() {  
  
            setTimeout(function () {  
  
                setValues();  
                if (count < max) { update(); }  
            });  
        }  
  
        function handler(args) {  
  
            content.textContent = "eenie";  
            increment();  
            update();  
        }  
  
    })();  
  
    ```  
  
8.  Hata ayıklamayı başlatmak için F5 tuşuna seçin. Doğrulayın **değerlerini bekleyen** düğmesi sayfasında görünür.  
  
9. Seçin **değerlerini bekleyen** ve düğme metni ve renk yaklaşık bir kez saniye başına güncelleştirme olduğunu doğrulayın. Bu tasarım gereğidir.  
  
10. Geri Visual Studio'ya (Alt + Sekme) geçin ve ardından hata ayıklamayı durdurmak için Shift + F5'ı seçin.  
  
     Uygulamanın çalıştığını doğruladıktan, Profil Oluşturucu kullanarak kendi performansını inceleyebilirsiniz.  
  
### <a name="analyzing-performance-data"></a>Performans verilerini çözümleme  
  
1.  Üzerinde **hata ayıklama** araç, **hata ayıklamayı Başlat** listesinde, Windows Phone Öykünücüler birini seçin veya **Simulator**.  
  
2.  Üzerinde **hata ayıklama** menüsünde seçin **performans ve tanılama**.  
  
3.  İçinde **kullanılabilen Araçlar**, seçin **HTML UI yanıtlama hızı**ve ardından **Başlat**.  
  
     Bu öğreticide, Profil Oluşturucu başlangıç projesine ekleniyor. Yüklü bir uygulamaya profil oluşturucu ekleme gibi diğer seçenekleri hakkında bilgi için bkz: [HTML UI yanıtlama hızı](../profiling/html-ui-responsiveness.md).  
  
     Profil Oluşturucu başlattığınızda VsEtwCollector.exe çalıştırmak için izninizi isteyen bir kullanıcı hesabı denetimi görebilirsiniz. Seçin **Evet**.  
  
4.  Çalışan uygulamada seçin **değerlerini bekleyen** ve yaklaşık 10 saniye bekleyin. Düğme metni ve renk yaklaşık bir kez saniye başına güncelleştirme olduğunu doğrulayın.  
  
5.  Çalışan uygulama, Visual Studio'ya (Alt + Sekme) geçin.  
  
6.  Seçin **durdurmak koleksiyonu**.  
  
     Profil Oluşturucu Visual Studio'da yeni bir sekme bilgiler görüntüler. CPU kullanımı ve görsel verimlilik (FPS) verilerini baktığınızda, birkaç eğilimleri kolayca tanımlayabilirsiniz:  
  
    -   CPU kullanımı artırır önemli ölçüde yaklaşık 3 saniye sonra (zaman bastığınız **değerlerini bekleyen** düğmesi) ve bu noktasından (komut dosyası, stil ve işleme olayları tutarlı bir karışımı) olayların Temizle düzeni gösterilir.  
  
    -   Visual verimlilik değil etkilenen ve FPS kalır 60 adresindeki (diğer bir deyişle, bırakılan çerçeve yok).  
  
     CPU kullanım grafiği yüksek etkinlik bu dönemde uygulamanın ne yaptığını bulmak için tipik bir bölümünü bakalım.  
  
7.  CPU kullanım grafiği ortasında bir iki ikinci bölümü seçin (ya da tıklatın-ve-sürükleyin veya sekme ve ok tuşlarını kullanın). Aşağıdaki çizimde, bir seçim yaptıktan sonra CPU kullanım grafiği gösterir. Paylaşılmayan alan seçim değildir.  
  
     ![CPU kullanım grafiği](../profiling/media/js_htmlviz_app_cpu.png "JS_HTMLViz_App_CPU")  
  
8.  Seçin **yakınlaştırmak**.  
  
     Seçilen dönem içinde daha fazla ayrıntı göstermek için grafiği değişiklikleri. Aşağıdaki çizimde, yakınlaştırma sonra CPU kullanım grafiği gösterir. (Belirli verileri farklılık gösterebilir, ancak genel düzeni belirgin olacaktır.)  
  
     ![Görünümde uzaklaştırılacağını](../profiling/media/js_htmlviz_app_zoom.png "JS_HTMLViz_App_Zoom")  
  
     Zaman Çizelgesi ayrıntılarını alt bölmede seçili dönem için ayrıntıları örneği gösterir.  
  
     ![Zaman Çizelgesi ayrıntıları](../profiling/media/js_htmlviz_app_details.png "JS_HTMLViz_App_Details")  
  
     Zaman Çizelgesi ayrıntıları olayları CPU kullanım grafiği görünür eğilimler onaylayın: çok kısa sürelerde gerçekleşmesini olayların vardır. Zaman Çizelgesi Ayrıntılar görünümü bu olayları olduğunu gösteren `Timer`, `Layout`, ve `Paint` olaylar.  
  
9. Bağlam menüsünü kullanın (veya sağ tıklayın) birini `Timer` alt bölmedeki olayları ve **olay filtresi**. Aşağıdaki çizimde ayrıntıları örneği biri için gösterilmektedir `Timer` bu test uygulamasında olaylar.  
  
     ![Süreölçer olayı](../profiling/media/js_htmlviz_app_timer.png "JS_HTMLViz_App_Timer")  
  
     Bulguları çeşitli verilerden konusunda. Örneğin:  
  
    -   Her `Timer` olay, bir komut dosyası olay olarak tanımlamak için renkli kodlu bir çağrı içerir `document.createElement`, stil hesaplama ve yapılan bir çağrı tarafından izlenen `style.backgroundColor` ve `appendChild()`.  
  
    -   Seçili kısa süre içinde (yaklaşık iki saniye), çok sayıda vardır `Timer`, `Layout`, ve `Paint` gerçekleşmesini olaylar. `Timer` Olaylarından uygulamayı çalıştırın ve seçin sonra görünür şekilde açıktır saniye başına tek bir güncelleştirme daha sık **değerlerini bekleyen** düğmesi.  
  
10. Araştırmak için aşağıdakilerden birini için anonim işlevi bağlantı seçin `Timer` alt sol bölmedeki olaylar. Aşağıdaki işlevi içinde default.js açar:  
  
    ```javascript  
    function update() {  
  
        setTimeout(function () {  
  
            setValues();  
            if (count < max) { update(); }  
        });  
    }  
    ```  
  
     Bu özyinelemeli işlev çağrıları bir döngü ayarlar `setValues()` düğmesi kullanıcı arabiriminde güncelleştirmeleri işlevi. Profil Oluşturucu farklı Zamanlayıcı olayları inceleyen tarafından en bulmak veya tüm Zamanlayıcı olaylar büyük olasılıkla sorunun burada kaynaklandığı göründüğü şekilde, çok sık çalışıyor bu koddan sonuç.  
  
### <a name="fixing-the-performance-issue"></a>Performans sorunu düzeltme  
  
1.  Değiştir `update()` işlevi aşağıdaki kod ile:  
  
    ```javascript  
    function update() {  
  
        setTimeout(function () {  
  
            setValues();  
            if (count < max) { update(); }  
        }, 1000 );  
    }  
    ```  
  
     Kod sabit bu sürüm, varsayılan gecikme değeri kullanımda kaynaklanan kod, önceki sürümünden unutulmuş bir 1000 milisaniyelik gecikme içerir. Profil Oluşturucu verileri, varsayılan değer neden sıfır milisaniye olduğunu görünür `setValues()` çok sık çalıştırmak için işlevi.  
  
2.  HTML UI yanıtlama hızı Profil Oluşturucusu yeniden çalıştırın ve CPU kullanım grafiği denetleyin. Aşırı olayları kaldırılmıştır ve CPU kullanımı sıfır yakınında bıraktı bulacaksınız. Sabit!  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HTML UI yanıtlama hızı](../profiling/html-ui-responsiveness.md)