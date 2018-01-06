---
title: "İzlenecek yol: bir bellek sızıntısı (JavaScript) bulma | Microsoft Docs"
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
helpviewer_keywords: memory leaks, JavaScript example
ms.assetid: f595412f-776b-49a2-8433-ea0062c6904d
caps.latest.revision: "31"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 13d9fd328ffab5c182078e46bbd832cddcba6fd9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-find-a-memory-leak-javascript"></a>İzlenecek yol: Bellek sızıntısını bulma (JavaScript)
![Windows ve Windows Phone için geçerlidir](../debugger/media/windows_and_phone_content.png "windows_and_phone_content")  
  
 Bu kılavuzda ve JavaScript bellek Çözümleyicisi'ni kullanarak basit bellek sorunu düzeltme işleminde size yol gösterir. JavaScript bellek Çözümleyicisi Visual Studio'da JavaScript kullanan Windows için oluşturulmuştur UWP uygulamalar için kullanılabilir. Bu senaryoda, hatalı oluşturulmuş aynı hızda öğelerinin atma yerine bellek DOM öğelerinde koruyan bir uygulama oluşturun.  
  
 Bu uygulamadaki bellek sızıntısı nedenini özgü olsa da, Buradaki adımlarda bellek sızıntısına yol nesneleri yalıtmaya genellikle daha etkilidir bir iş akışı gösterilmektedir.  
  
### <a name="running-the-javascript-memory-analyzer-test-app"></a>JavaScript bellek Çözümleyicisi test uygulaması çalıştırma  
  
1.  Visual Studio'da, **dosya**, **yeni**, **proje**.  
  
2.  Seçin **JavaScript** sol bölmede ve ardından **Windows**, **Windows 8**, sonra da **Evrensel** veya  **Windows Phone uygulamaları**.  
  
    > [!IMPORTANT]
    >  Bu konuda gösterilen bellek kullanımı sonuçlarını bir Windows 8 uygulaması karşı sınanır.  
  
3.  Seçin **boş uygulama** Orta bölmede proje şablonu.  
  
4.  İçinde **adı** kutusunda, gibi bir ad belirtin `JS_Mem_Tester`ve ardından **Tamam**.  
  
5.  İçinde **Çözüm Gezgini**, default.html açın ve aşağıdaki kodu arasında yapıştırın \<gövde > etiketleri:  
  
    ```html  
    <div class="wrapper">  
        <div id="item"></div>  
        <button class="memleak" style="display: block" >Leak Memory</button>  
    </div>  
    ```  
  
    > [!IMPORTANT]
    >  Bir Windows 8.1 Evrensel uygulama şablonu kullanıyorsanız, HTML ve CSS kodu hem de güncelleştirmeniz gerekir. Windows ve. WindowsPhone projeleri.  
  
6.  Default.css açın ve aşağıdaki CSS kodu ekleyin:  
  
    ```css  
    .memleak {  
        position: absolute; top: 100px; left: 100px;  
    }  
    ```  
  
7.  Default.js açın ve tüm kodu bu kod ile değiştirin:  
  
    ```javascript  
    (function () {  
        "use strict";  
  
        var app = WinJS.Application;  
        var activation = Windows.ApplicationModel.Activation;  
  
        var wrapper;  
        var elem;  
  
        app.onactivated = function (args) {  
            if (args.detail.kind === activation.ActivationKind.launch) {  
                if (args.detail.previousExecutionState !== activation.ApplicationExecutionState.terminated) {  
                } else {  
                }  
                args.setPromise(WinJS.UI.processAll());  
  
                elem = document.getElementById("item");  
                wrapper = document.querySelector(".wrapper");  
                var btn = document.querySelector(".memleak");  
                btn.addEventListener("click", btnHandler);  
                run();  
            }  
        };  
  
        app.oncheckpoint = function (args) {  
        };  
  
        app.start();  
  
        function run() {  
            initialize();  
            load();  
        }  
  
        function initialize() {  
  
            if (wrapper != null) {  
                elem.removeNode(true);  
            }  
        }  
  
        function load() {  
  
            var newDiv = document.createElement("div");  
  
            newDiv.style.zIndex = "-1";  
            newDiv.id = "item";  
  
            wrapper.appendChild(newDiv);  
        }  
  
        function btnHandler(args) {  
            run();  
        }  
  
    })();  
    ```  
  
8.  Hata ayıklamayı başlatmak için F5 tuşuna seçin. Doğrulayın **sızıntısı bellek** düğmesi sayfasında görünür.  
  
9. Geri Visual Studio'ya (Alt + Sekme) geçin ve ardından hata ayıklamayı durdurmak için Shift + F5'ı seçin.  
  
     Uygulamanın çalıştığını doğruladıktan, bellek kullanımı inceleyebilirsiniz.  
  
### <a name="analyzing-the-memory-usage"></a>Bellek kullanımını analiz etme  
  
1.  Üzerinde **hata ayıklama** araç, **hata ayıklamayı Başlat** listesinde, güncelleştirilen projeyi hata ayıklama hedefi seçin: Windows Phone Öykünücüler birini veya **Simulator**.  
  
    > [!TIP]
    >  Bir UWP uygulaması için de seçebilirsiniz **yerel makine** veya **uzak makine** bu listede. 
  
2.  Üzerinde **hata ayıklama** menüsünde seçin **Performans Profil Oluşturucu...** .  
  
3.  İçinde **kullanılabilen Araçlar**, seçin **JavaScript belleği**ve ardından **Başlat**.  
  
     Bu öğreticide, bellek Çözümleyicisi başlangıç projesine ekleniyor. Bellek Çözümleyicisi yüklü bir uygulamaya ekleme gibi diğer seçenekleri hakkında bilgi için bkz: [JavaScript belleği](../profiling/javascript-memory.md).  
  
     Bellek Çözümleyicisi'ni başlattığınızda VsEtwCollector.exe çalıştırmak için izninizi isteyen bir kullanıcı hesabı denetimi görebilirsiniz. Seçin **Evet**.  
  
4.  Seçin **sızıntısı bellek** dört kez art arda düğmesi.  
  
     Ne zaman olay bir bellek sızıntısı sonuçlanır default.js mu iş kodda işleme düğmesini seçin. Bu tanılama amacıyla kullanacaksınız.  
  
    > [!TIP]
    >  Bellek sızıntısı için test etmek istediğiniz senaryo yinelenen öbek için uygulama başlatma sırasında veya bir sayfa yüklenirken eklenen nesneleri gibi sizi ilgilendirmeyen bilgileri filtrelemek kolaylaştırır.  
  
5.  Çalışan uygulama, Visual Studio'ya (Alt + Sekme) geçin.  
  
     JavaScript bellek Çözümleyicisi Visual Studio'da yeni bir sekme bilgiler görüntüler.  
  
     Bu Özet görünümü gösterir işlem bellek kullanımı zamanla bellek grafik. Görünüm gibi komutlar da sağlar **Al yığın anlık görüntüsü**. Bir anlık görüntü belirli bir zamandaki bellek kullanımı hakkında ayrıntılı bilgiler sağlar. Daha fazla bilgi için bkz: [JavaScript belleği](../profiling/javascript-memory.md).  
  
6.  Seçin **Al yığın anlık görüntüsü**.  
  
7.  Uygulamasına geçin ve seçin **sızıntısı bellek**.  
  
8.  Geçiş için Visual Studio ve seçin **Al yığın anlık görüntüsü** yeniden.  
  
     Bu örnekte temel anlık görüntü (#1) ve anlık görüntü #2 gösterilmiştir.  
  
     ![Taban çizgisi anlık görüntü ve anlık görüntü 2](../profiling/media/js_mem_app_snapshot2.png "JS_Mem_App_Snapshot2")  
  
    > [!NOTE]
    >  Windows Phone öykünücüsü bir uygulamasının ekran görüntüsü, anlık görüntünün alındığı anda göstermez.  
  
9. Uygulamasına geçin ve seçin **sızıntısı bellek** yeniden düğmesine tıklayın.  
  
10. Geçiş için Visual Studio ve seçin **Al yığın anlık görüntüsü** üçüncü süre.  
  
    > [!TIP]
    >  Bu iş akışındaki üçüncü bir anlık görüntü uygulayarak bellek sızıntıları ile ilişkili olmayan taban çizgisi anlık görüntü Değişikliklerden ikinci bir anlık görüntüye çıkışı filtre uygulayabilirsiniz. Örneğin, üstbilgiler ve altbilgiler bazı değişiklikler bellek kullanımında oluşturur ama bellek sızıntıları ilişkisiz bir sayfada güncelleştirme gibi beklenen değişiklikler olabilir.  
  
     Bu örnekte, anlık görüntü #2 ve anlık görüntü #3 gösterilmiştir.  
  
     ![Anlık görüntü 2 ve 3 anlık görüntü](../profiling/media/js_mem_app_snapshot3.png "JS_Mem_App_Snapshot3")  
  
11. Visual Studio'da, **durdurmak** profil oluşturmayı durdurmak için.  
  
12. Visual Studio'da anlık görüntüleri karşılaştırın. Anlık görüntü #2 aşağıda gösterilmiştir:  
  
    -   Anlık görüntü # 1'e göre birkaç KB (kırmızı yukarı ok sol tarafından gösterilen) yığın boyutu artar.  
  
        > [!IMPORTANT]
        >  Tam bellek kullanım değerlerini yığın boyutu için hata ayıklama hedef bağlıdır.  
  
    -   (Yukarı ok sağda kırmızı tarafından gösterilen) yığında nesne sayısı anlık görüntü #1 karşılaştırıldığında artar. Bir nesne (+ 1) eklendi ve herhangi bir nesnenin kaldırılmış (-0).  
  
     Anlık görüntü #3 aşağıda gösterilmiştir:  
  
    -   Anlık görüntü # 2'ye kıyasla birkaç yüz bayt olarak yeniden yığın boyutu artar.  
  
    -   Yeniden anlık görüntü # 2'ye kıyasla yığında nesne sayısı artar. Bir nesne (+ 1) eklendi ve herhangi bir nesnenin kaldırılmış (-0).  
  
13. Anlık görüntü # 3'te, bağlantı metnini + 1 değerini gösterir sağdaki seçin / - 0 yukarı ok kırmızı yanındaki.  
  
     ![Yığın nesnelerin farklı görünümünü bağlantı](../profiling/media/js_mem_app_link.png "JS_Mem_App_Link")  
  
     Bu nesneleri yığında adlı bir fark görünümü açılır **anlık görüntü #3 - Snapshot #2**, varsayılan olarak gösteren türleri görünümü. Varsayılan olarak, anlık görüntü #2 ve anlık görüntü #3 arasında öbek eklenen nesnelerin bir listesini görürsünüz.  
  
14. İçinde **kapsam** seçin, filtre **nesneleri kalan anlık görüntü # 2'den**.  
  
15. Nesne ağacına üstündeki HTMLDivElement nesnesini aşağıda gösterildiği gibi açın.  
  
     ![Fark görünümü nesnesinin saymak öbek üzerinde](../profiling/media/js_mem_app_typesdiff.png "JS_Mem_App_TypesDiff")  
  
     Bu görünüm aşağıdaki gibi bellek sızıntısı hakkında yararlı bilgiler gösterir:  
  
    -   Bu görünüm DIV öğesinin kimliği gösterir `item`, ve tutulan boyut nesnesi için (tam değeri değişir) birkaç yüz bayttır.  
  
    -   Bu nesne, anlık görüntü # 2 girişiminden kalmış bir nesnedir ve olası bellek sızıntısı temsil eder.  
  
     Uygulamanın bazı bilgi bu noktada yardımcı olur: seçme **sızıntısı bellek** düğmesi DIV öğesinin kaldırın ve kod sağ çalışma görünmemektedir bir öğe ekleyin (diğer bir deyişle, bellek sızıntılarını). Sonraki bölümde, düzeltme açıklanmaktadır.  
  
    > [!TIP]
    >  Bazı durumlarda yazılımla ilişkili olarak bir nesne bulma `Global` nesne söz konusu nesne tanımlamaya yardımcı olabilir. Bunu yapmak için tanımlayıcısı için kısayol menüsünü açın ve ardından **Göster kökleri görünümünde**.  
  
##  <a name="FixingMemory"></a>Bellek sorunu düzeltme  
  
1.  Profil Oluşturucu tarafından açığa verileri kullanarak "öğesi" kimliği ile DOM öğeleri kaldırmak için sorumlu kodu inceleyin. Bu gerçekleşirse `initialize()` işlevi.  
  
    ```javascript  
    function initialize() {  
  
        if (wrapper != null) {  
            elem.removeNode(true);  
        }  
    }  
    ```  
  
     `elem.removeNode(true)`belki de düzgün çalışmıyor olabilir. Kod DOM öğesi nasıl önbelleğe alma inceleyin ve bir sorun bulunamadı; önbelleğe alınan öğe referansı güncelleştirilmiyor.  
  
2.  Default.js içinde yük işlevi yalnızca çağırmadan önce aşağıdaki kod satırını ekleyin `appendChild`:  
  
    ```javascript  
    elem = newDiv;  
    ```  
  
     Bu kod önbelleğe alınan öğe referansı güncelleştirir seçtiğinizde öğesi doğru kaldırılır **sızıntısı bellek** düğmesi. Tam kod yük işlevi için şimdi şöyle görünür:  
  
    ```javascript  
    function load() {  
  
        wrapper = document.querySelector(".wrapper");  
  
        var newDiv = document.createElement("div");  
  
        newDiv.style.zIndex = "-1";  
        newDiv.id = "item";  
        elem = newDiv;  
  
        wrapper.appendChild(newDiv);  
    }  
    ```  
  
3.  Üzerinde **hata ayıklama** menüsünde seçin **performans ve tanılama**.  
  
4.  İçinde **kullanılabilen Araçlar**, seçin **JavaScript belleği**ve ardından **Başlat**.  
  
5.  Üç anlık görüntülerini almak için önce yordamın aynısını izleyin. Adımlar burada özetlenmektedir:  
  
    1.  Uygulamada, seçin **sızıntısı bellek** dört kez art arda düğmesi.  
  
    2.  Geçiş için Visual Studio ve seçin **Al yığın anlık görüntüsü** temel anlık görüntü için.  
  
    3.  Uygulamada, seçin **sızıntısı bellek** düğmesi.  
  
    4.  Geçiş için Visual Studio ve seçin **Al yığın anlık görüntüsü** ikinci anlık görüntü için.  
  
    5.  Uygulamada, seçin **sızıntısı bellek** düğmesi.  
  
    6.  Geçiş için Visual Studio ve seçin **Al yığın anlık görüntüsü** üçüncü anlık görüntü için.  
  
     Anlık görüntü #3 şimdi yığın boyutu olarak gösterir **hiçbir artış** anlık görüntü #2 ve nesne sayısı + 1 / -1, bir nesneleri belirten eklendi ve bir nesne kaldırılmıştır. İstenen davranış budur.  
  
     Aşağıdaki çizimde, anlık görüntü #2 ve anlık görüntü #3 gösterir.  
  
     ![Sabit bellek sızıntısı gösteren anlık görüntüleri](../profiling/media/js_mem_app_fixed_snapshot3.png "JS_Mem_App_Fixed_Snapshot3")  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JavaScript belleği](../profiling/javascript-memory.md)