---
title: "Windows Phone 8.1 uygulamaları öykünücüde çalıştırma | Microsoft Docs"
ms.custom: 
ms.date: 07/18/2017
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
ms.assetid: c7590788-beb3-403c-a7dd-18472a9e585e
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: fc458bddfe354f43afd15176d0283cad4875234d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="run-windows-phone-81-apps-in-the-emulator"></a>Windows Phone 8.1 uygulamaları öykünücüsünde çalıştırın
Windows Phone öykünücüsü hata ayıklama ve bir fiziksel aygıt olmadan bilgisayarınızdaki Windows Phone uygulamalarını test sanallaştırılmış bir ortam sağlar. Ortak dokunma ve döndürme olaylarının benzetimini yapma ve fiziksel ekran boyutu ve taklit etmek istediğiniz çözümü seçin. Ayrıca, konum, ağ, bildirimler, algılayıcılar, accelerometer ve isteğe bağlı SD kart gibi birçok yaygın olarak kullanılan özellik test edebilirsiniz.  

Windows 10 Mobile öykünücüde çalıştırma hakkında daha fazla bilgi için bkz: [Microsoft Emulator ile Test](/windows/uwp/debug-test-perf/test-with-the-emulator).
  
Windows Phone 8.1 öykünücüde test edebilirsiniz özellikler hakkında daha fazla bilgi için bkz: [uygulama özelliklerini Windows Phone Öykünücüde Test](http://msdn.microsoft.com/en-us/c1b2b0ec-b8cc-4a98-84c1-701428e45cb1).  
  
Visual Studio ile birlikte öykünücü içinde tasarlayabilir, geliştirme, hata ayıklama ve Windows Phone uygulamalarını test tam bir ortam sağlar.  
  
##  <a name="BKMK_run"></a>Windows Phone Uygulama öykünücüsünde çalıştırın  
 Windows Phone Uygulama geliştirirken olsa da, Windows Phone öykünücüsü dağıtmak ve hızlı bir şekilde uygulamanızı test etmek için kullanabilirsiniz. Windows Phone Mağazası'nda uygulamanızı yayınlamadan önce uygulamanızı gerçek bir Windows Phone cihazında ancak sınamanızı öneririz. Bu, kullanıcıların bu yaşar gibi uygulamanızı deneyimi sağlar.  
  
 Bir Windows Phone uygulamasını Windows Phone öykünücüsü ilk kez çalıştırdığınızda, aşağıdaki olaylar gerçekleşir:  
  
1.  Öykünücü başlatır.  
  
2.  Öykünücü Windows Phone işletim sistemi yükler.  
  
3.  Öykünücü Windows Phone başlangıç ekranı görüntüler.  
  
4.  Uygulamanızı öykünücü dağıtılır.  
  
5.  Uygulamanızı öykünücü üzerinde çalışır.  
  
 Seçili öykünücüsü zaten çalışıyorsa, uygulamanızı dağıtılan ve çalışan öykünücüsünde başlatıldı. Her öykünücüsü yalnızca bir örneği aynı anda çalıştırabilirsiniz.  
  
> [!TIP]
>  Öykünücü uygulamanızı yeniden hızlı bir şekilde çalıştırabilmeniz için oturumları hata ayıklama arasında uygulamanızı öykünücü üzerinde test ederken açık bırakın.  
  
###  <a name="BKMK_vs"></a>Visual Studio'dan bir uygulamayı çalıştırma  
  
##### <a name="to-deploy-and-run-an-app-from-visual-studio"></a>Dağıtma ve uygulama Visual Studio'dan çalıştırma  
  
1.  Visual Studio'da bir Windows Phone projesini açın.  
  
2.  Üzerinde **standart** araç, öykünücüsü seçeneklerden birini belirleyin.  
  
     ![Windows Phone öykünücüsü görüntülerin listesi](../debugger/media/wp_emulator_list.png "WP_Emulator_list")  
  
3.  Dağıtmak ve hata ayıklama ile uygulamanızın üzerinde çalıştırmak için **hata ayıklama** menüsünde tıklatın **hata ayıklamayı Başlat**, veya F5 tuşuna basın.  
  
     Dağıtmak ve hata ayıklama olmadan, uygulamanızın üzerinde çalıştırmak için **hata ayıklama** menüsünde tıklatın **Başlat hata ayıklama olmadan**, veya Ctrl + F5 tuşuna basın.  
  
     Uygulamanızı dağıtılan ve başlatıldı.  
  
     On çalıştırmadan uygulamanızı dağıtmak için **yapı** menüsünde tıklatın **çözümü Dağıt**.  
  
##### <a name="to-stop-a-running-app"></a>Çalışan bir uygulamanın durdurmak için  
  
-   Çalışan bir uygulamanın durdurmak için aşağıdakilerden birini yapın:  
  
    -   Visual Studio'da üzerinde **hata ayıklama** menüsünde tıklatın **durdurma hata ayıklama**, veya Shift + F5 tuşuna basın.  
  
    -   Öykünücüde basın **geri** uygulaması'ndan çıkmak için düğmesi. Etkin sayfa uygulamanın uygulamanın başlangıç sayfasını olduysa, basmanız gerekebilir **geri** birden çok kez düğmesine tıklayın.  
  
     Uygulama çıkar ve başlangıç ekranı açılır. Bu, geçerli hata ayıklama oturumu sona erer.  
  
##### <a name="to-restart-an-app-without-debugging"></a>Hata ayıklama olmadan bir uygulamayı yeniden başlatmak için  
  
1.  Öykünücüsünde başlangıç ekranında uygulama listesini görüntülemek için sağdan sola.  
  
2.  Uygulama listesinde uygulama simgesine dokunun. Uygulama hata ayıklama olmadan yeniden başlatır.  
  
##### <a name="to-deactivate-a-running-app"></a>Çalışan bir uygulamanın devre dışı bırakmak için  
  
1.  Uygulamanızı çalıştırmadan önce Visual Studio'daki Çözüm Gezgini'nde projeye sağ tıklayın ve ardından **özellikleri** açmak için **Proje Tasarımcısı**.  
  
2.  İçinde **Proje Tasarımcısı**, **hata ayıklama** sayfasında, bırakın **silinmiş öğe işareti hata ayıklama devre dışı bırakma işlemi sırasında** etkinliği olmayan gitmek için uygulama istiyorsanız onay kutusunu işaretli duruma devre dışı bırakıldı. Uygulama devre dışı olduğunda kaldırıldı olmasını istiyorsanız onay kutusunu işaretleyin.  
  
3.  Üzerinde **hata ayıklama** menüsünde tıklatın **hata ayıklamayı Başlat**, veya uygulamayı çalıştırmak için F5 tuşuna basın.  
  
4.  Öykünücüde basın **Başlat** düğmesi. Başlangıç ekranı görüntülenir ve uygulama devre dışı bırakılır. Uygulama ya da etkinliği olmayan bir duruma girer veya bağlı olarak ayarı kaldırıldı **silinmiş öğe işareti hata ayıklama devre dışı bırakma işlemi sırasında** onay kutusu.  
  
##### <a name="to-reactivate-a-dormant-or-tombstoned-app"></a>Bir etkinliği olmayan veya kaldırıldı uygulama yeniden etkinleştirmek için  
  
-   Öykünücüde basın **geri** düğmesi uygulamaya geri dönün. Diğer sayfalara gittiğinizde veya başka bir uygulama açıldığında, basmanız gerekebilir **geri** uygulamayı yeniden etkinleştirmek için birden çok kez düğmesine tıklayın.  
  
     Hata ayıklama oturumu sürdürür. Hata ayıklayıcı uygulamadan ayrılmış, hata ayıklama oturumu sürdürmek için F5 tuşuna basarak gerekebilir.  
  
###  <a name="BKMK_depltool"></a>Bir uygulama uygulama dağıtımı aracı ile çalıştırma  
 Windows Phone uygulama dağıtımı aracı da kullanabilirsiniz (**AppDeploy.exe**) uygulamanızı öykünücüde çalıştırmak için. Bu araç, Windows Phone geliştirme araçları yüklediğinizde, yüklü olduğu tek başına bir uygulamadır.  
  
 Daha fazla bilgi için bkz: [dağıtmak Windows Phone 8.1 uygulamaları uygulama dağıtımı aracı ile](http://msdn.microsoft.com/Library/23700f82-1399-44d9-bc0c-714be4a48ee6).  
  
##  <a name="BKMK_toolbar"></a>Windows Phone öykünücüsü öykünücüsü araç ile yapılandırma  
 Bu tablo öykünücüsü araç çubuğunda kullanılabilir yapılandırma düğmeleri gösterir.  
  
|Araç çubuğu düğmeleri|Yapılandırma seçenekleri|  
|---------------------|---------------------------|  
|![Windows Phone öykünücüsü araç çubuğundaki seçenekleri giriş](../debugger/media/wp_emulator_.png "WP_Emulator_")|**Giriş noktası tek veya çok noktası yapılandırın**<br /><br /> Giriş çok noktayı etkinleştirdiğinizde, ekran dokunmadan dokunma noktaları taşımak için sağ tıklayabilirsiniz. Ardından, her iki dokunma noktaları aynı anda taşımak için sol.|  
|![Windows Phone öykünücüsü araç çubuğunda yönlendirmesini](../debugger/media/wp_emulator_rotation.png "WP_Emulator_rotation")|**Öykünücü yönlendirmesini yapılandırma**<br /><br /> Windows Phone öykünücüsü yönde üç yönler birine değiştirebilirsiniz: dikey, yatay sola veya sağa yatay. Yönlendirmeyi değiştirdiğinizde öykünücü boyutunu değiştirmez.<br /><br /> Yönünü değiştirmek için tıklatın. **Sola Döndür** düğmesini veya **Sağa Döndür** düğmesi.|  
|![Windows Phone öykünücüsü araç çubuğundaki seçenekleri boyut](../debugger/media/wp_emulator_size.png "WP_Emulator_size")|**Öykünücü boyutunu yapılandırın**<br /><br /> Ana bilgisayar ekranında öykünücüsü boyutunu değiştirebilirsiniz. Nokta / inç (DPI) öykünücüsü yakınlaştırma değerini bağımsız olarak ana bilgisayar İzleyici DPI dayanır.<br /><br /> -Ekrana öykünücüsü sığacak şekilde tıklatın **ekrana Sığdır** düğmesi.<br />-Yakınlaştırma ayarını değiştirmek için tıklatın **yakınlaştırma** düğmesi. **Yakınlaştırma** iletişim kutusu açılır. İçinde **yakınlaştırma** iletişim kutusunda, 33 ile 100 arasında bir yakınlaştırma değeri girin.|  
  
##  <a name="BKMK_buttons"></a>Öykünücüsünde benzetimli donanım düğmelerini kullanın  
 Bir telefon donanım düğmelerinin kullanımını öykünücüsü ekranın sağ tarafta sanal donanım düğmeleri kullanarak benzetimi.  
  
-   Tıklatın **güç** görüntü kapatıp açmayı benzetimini yapmak için düğmesi. ' I tıklatın ve telefon kapatma benzetimini yapmak için basılı tutun.  
  
-   Tıklatın **birim yukarı** veya **birim aşağı** telefon aramaları ve bildirimler için telefonun Konuşmacı hacmi değiştirme benzetimini yapmak için düğmesi.  
  
-   **Kamera** düğmesi kamera uygulamayı başlatır. Bir fotoğraf veya bir video kamera uygulamasındaki denetimleri kullanarak alma benzetimini yapabilirsiniz.  
  
 Aşağıdaki ekran görüntüsü sanal donanım düğmeleri gösterir.  
  
1.  Sol görüntü öykünücüsünde başlangıç ekranı görüntüler.  
  
2.  Ortadaki görüntü öykünücü sonra dokunma görüntüler **güç** görüntülenmesini devre dışı bırakma düğmesi.  
  
3.  Sağ görüntü öykünücüsü ekran sonra dokunma görüntüler **birim yukarı** birim artırmak için düğmesini.  
  
 ![Windows Phone öykünücüsü düğmeleri](../debugger/media/wp_emulator_buttons.png "WP_Emulator_buttons")  
  
##  <a name="BKMK_tasks_kbd"></a>Öykünücü ile bilgisayar klavyeyi kullanma  
 Öykünücü donanım klavye eşleme geliştirme bilgisayarınızda bir Windows Phone klavyede destekler. Anahtarların davranış bir Windows Phone aygıtta aynıdır.  
  
 Varsayılan olarak, donanım klavye etkin değil. Bu uygulamayla kullanabilmeniz için önce dağıtılması gereken kayan bir klavye eşdeğerdir. Klavye donanımı etkinleştirmeden önce öykünücü anahtar girdisinden yalnızca denetim tuşları kabul eder.  
  
 Bir Windows geliştirme bilgisayarın yerelleştirilmiş bir sürümün klavyede özel karakterler öykünücü tarafından desteklenmez. Yerelleştirilmiş klavyede bulunan özel karakterleri girmek için yazılım giriş paneli (SIP) kullanın.  
  
 Bilgisayarınızın klavye öykünücüsünde kullanmak için anahtar veya PAUSE/BREAK anahtarı (Windows 8/8.1 öykünücüsü) PAGEUP veya F4 basın (Windows 10 öykünücüsü).  
  
 Öykünücüde, bilgisayarınızın klavyeyi kullanarak durdurmak için PAGE DOWN tuşuna veya PAUSE/BREAK tuşuna (Windows 8/8.1 öykünücüsü) veya F4 basın (Windows 10 öykünücüsü).  
  
 Aşağıdaki tabloda tuşlarını düğmeleri benzetmek için kullanabileceğiniz bir donanım ve Windows Phone diğer denetimlere listeler.  
  
|Bilgisayarın donanım anahtarı|Windows Phone donanım düğmesi|Notlar|  
|---------------------------|-----------------------------------|-----------|  
|F1|GERİ|Uzun basarsa beklendiği gibi çalışmayabilir.|  
|F2|BAŞLAT|Uzun basarsa beklendiği gibi çalışmayabilir.|  
|F3|ARAMA||  
|F4|Windows 10 öykünücüsünde yerel bilgisayarın Klavyesi kullanılmadan değil ve yerel bilgisayarın Klavyesi kullanılmadan arasında geçiş yapar.|Windows 8/8.1 öykünücüsü içinde geçerli değil.|  
|F5|Yok.||  
|F6|KAMERA YARIM|Yarısı basıldığında ayrılmış kamera düğmesi.|  
|F7|KAMERA TAM|Ayrılmış kamera düğme.|  
|F8|Yok.||  
|F9|BİRİMİ||  
|F10|AŞAĞI BİRİM||  
|F11|Yok.||  
|F12|GÜÇ|İki kez kilit ekranı etkinleştirmek için F12 tuşuna basın.<br /><br /> Uzun basarsa beklendiği gibi çalışmayabilir.|  
|ESC|GERİ|Uzun basarsa beklendiği gibi çalışmayabilir.|  
|DURAKLAT/SONU|İki durumlu klavye (yalnızca windows 8/8.1 öykünücüsü).|Windows 10 öykünücüsü için geçerli değildir.|  
|PAGE UP|Donanım klavye (yalnızca Windows 8/8.1 öykünücüsü) sağlar.|Windows 10 öykünücüsü için geçerli değildir.|  
|PAGE DOWN|(Yalnızca Windows 8/8.1 öykünücüsü) klavye donanımı devre dışı bırakır.|Windows 10 öykünücüsü için geçerli değildir.|  
  
##  <a name="BKMK_checkpoints"></a>Kaydetme ve özel denetim noktaları yükleme  
 Öykünücü'nın durumunun anlık görüntüsü kullanarak kaydetme **kontrol noktaları** öykünücüsü'nın sekmesinde **ek araçlar**. Bu özellik, sık sık aynı verileri ve ayarları ile uygulamanızı test yararlıdır.  
  
 Örneğin, uygulamanızı birkaç kişi gerektiriyorsa, bir kez kişi kayıtlarını oluşturun ve anlık görüntü öykünücüsünü kaydedin. Aksi takdirde öykünücü her başlattığınızda kişi kayıtları oluşturmanız gerekebilir.  
  
-   Tıklatın **yeni bir kontrol noktası** öykünücü verileri ve daha sonra yeniden uygulamanızı test etmek için gerekli ayarları ile durumunun yeni bir anlık görüntü yakalamak için. Yeni bir kontrol noktası eklenen **kontrol noktaları** listesi.  
  
     Hata ayıklayıcı öykünücüsünü eklenirken bir denetim noktası yakalama yapılamaz.  
  
-   Bir denetim noktasını seçin **kontrol noktaları** denetim noktası hakkında bilgi görüntülemek için liste.  
  
-   Radyo düğmesini seçin **varsayılan** kaydedilmiş bir denetim noktası için etkin öykünücüsü varsayılan denetim noktası yapmak için sütun.  
  
-   Tıklatın **geri** öykünücüsü Windows Phone işletim sisteminde yeniden başlatmak ve seçilen anlık görüntü yüklemek için.  
  
-   Tıklatın **silmek** artık ihtiyaç duymadığınız bir anlık görüntüyü silmek için.  
  
 Özgün öykünücü görüntünüzün her zaman listedeki ilk öğe olarak görünür **kontrol noktaları** listelemek ve silinmiş veya değiştirilemez. Ancak varsayılan öykünücü görüntü olarak farklı bir anlık görüntü seçebilirsiniz.  
  
 ![Windows Phone öykünücüsü kontrol noktaları sekmesinde](../debugger/media/wp_emulator_checkpoints.png "WP_Emulator_checkpoints")  
  
##  <a name="BKMK_tasks_shot"></a>Öykünücü ekran yakalama  
 Windows Phone uygulamalarınızı ekran görüntüleri ek araçlar penceresinden ekran aracını kullanarak oluşturabilirsiniz. Araç çalışan öykünücünüze çözümleme eşleşen PNG dosyaları oluşturur.  
  
 ![Windows Phone gelen ekran görüntüleri öykünücüsü](../debugger/media/wp_emulator_screenshots.png "WP_Emulator_screenshots")  
  
#### <a name="to-create-an-app-screenshot-by-using-the-built-in-emulator-screenshot-tool"></a>Yerleşik öykünücüsü ekran Aracı'nı kullanarak bir uygulama ekran görüntüsü oluşturmak için  
  
1.  Ekran görüntüleri kalitesini iyileştirmek için yüzde 100 olarak öykünücü yakınlaştırma düzeyini ayarlayın. Daha yüksek ekran kalitesini daha iyi yakınlaştırma düzeyini ayarlayın.  
  
2.  Uygulamanızı öykünücüsünde başlatın.  
  
3.  Öykünücü araç çubuğunda, açmak için Genişlet düğmesini **ek araçlar** penceresi.  
  
4.  Tıklatın **ekran** sekmesi.  
  
5.  Uygulamanızı hazır olduğunda tıklatın **yakalama** düğmesi.  
  
     Ekran görüntüsü çalışma alanında görüntülenir.  
  
6.  Tıklatın **kaydetmek** açmak için düğmeye **Kaydet** iletişim kutusu.  
  
7.  Konum seçin ve **dosya adı** ve ardından **kaydetmek**.  
  
8.  İsteğe bağlı olarak, uygulamanızın diğer sayfalar gidin ve ek ekran görüntüleri yakalama.  
  
9. Farklı ekran çözünürlüğü farklı çözünürlükte aynı ekran görüntülerini yakalamak için bir öykünücü başlatın. Hata ayıklama ile uygulamanızı çalıştırdıysanız, başka bir öykünücü üzerinde yeniden çalıştırmadan önce hata ayıklamayı durdurmak zorunda.  
  
 Windows Phone Mağazası'na gönderilen ekran görüntüleri yakalamadan önce öykünücüsü ekranında kare hızı sayaçları devre dışı bırakın.  
  
#### <a name="to-disable-frame-rate-counters-in-the-emulator-before-capturing-screenshots"></a>Ekran görüntüleri yakalama önce öykünücü kare hızı sayaçları devre dışı bırakmak için  
  
-   Yayın derlemesi Visual Studio'da belirtin. Yayın derlemesi belirttikten sonra uygulamanızı seçerek başlatma **dağıtma *[uygulama adı]***  bağlantı **yapı** menüsü.  
  
-   Alternatif olarak, çıkış kodu değerini ayarlar app.xaml.cs veya app.xaml.vb dosyasındaki satır yorum yapabileceği `EnableFrameRateCounter` için `true`.