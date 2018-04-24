---
title: Benzetici UWP uygulamaları çalıştırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 81b69bf8-ec87-4bb6-9ad4-1fa7b7802d16
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 99881b657f6d3cb6877c7ce6d1fbf80f4eb1d731
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="run-uwp-apps-in-the-simulator"></a>Benzetici UWP uygulamaları çalıştırma
UWP uygulamalar için Visual Studio simulator, bir UWP uygulaması taklit eden bir masaüstü uygulamasıdır. Genellikle, yerel makine, bağlı bir aygıt veya bir uzak makine hata ayıklama istersiniz. Ancak, bazı senaryolarda, farklı fiziksel ekran boyutu ve çözüm benzetmek için Visual Studio simulator kullanmak isteyebilirsiniz. Ayrıca, ortak dokunma ve döndürme olaylarının benzetimini yapma ve ağ bağlantısı özellikleri benzetimini yapma.
  
 Simulator içinde tasarlama, geliştirme, hata ayıklama ve UWP uygulamaları test kullanabilirsiniz bir ortam sağlar. Ancak, Microsoft Store uygulamanızı yayınlamadan önce uygulamanızı gerçek cihazında test etmeniz gerekir.  
  
 UWP uygulamalar için Visual Studio simulator yalıtılmış bir ortamda yerel makinenizde çalışmaz. Bu nedenle, kurtarılamaz bir sistem genelinde hatası gibi simulator oluşan hataları da tüm makine etkileyebilir.  
  
> [!IMPORTANT]
>  Visual Studio 2015 simulator coğrafi konuma düğmesi içermez. Bu durum, Windows 10 simulator coğrafi konuma benzetimi dahil değildir çünkü.
  
##  <a name="BKMK_Set_the_simulator_as_the_target"></a> Simulator hedef olarak ayarlanmış  
 Benzetici UWP uygulamanızı çalıştırmak için seçin **Simulator** bulunan aşağı açılan listesinde yanına **hata ayıklamayı Başlat** hata ayıklayıcı düğmesinde **standart** araç. Bu seçenek yalnızca kullanılabilir değilse, uygulamanızın **hedef Platform Min. Sürüm** geliştirme makinenizdeki işletim sistemi küçük veya eşit. 
  
 ![Benzetici çalıştıran](../debugger/media/vsrun_f5_simulator.png "VSRUN_F5_Simulator")  
  
##  <a name="BKMK_Choose_an_interaction_mode"></a> Bir etkileşim modu seçin  
 Aşağıdaki etkileşim modlarından birini seçebilirsiniz  
  
-   ![Fare Modu düğmesini](../debugger/media/simulator_mousemodebtn.png "SIMULATOR_MouseModeBtn") fare modu: fare hareketleri etkileşim modunu ayarlar. Fare hareketleri dahil tıklama çift tıklamalar ve drags.  
  
-   ![Başlangıç dokunma öykünme düğmesi](../debugger/media/simulator_starttouchemulationbtn.png "SIMULATOR_StartTouchEmulationBtn") başlangıç dokunma öykünme: etkileşim modunu, tek bir parmak hareketleri touch şekilde ayarlar. Tek parmak olayları dokunarak, sürükleyerek ve geçirmeyi içerir.  
  
     ![Simulator tek bir parmak hedef](../debugger/media/simulator_onefinger.png "SIMULATOR_OneFinger") tek hedef simgesini simulator olayları konumunu belirtir. Fare işaretçisini konumlandırmak için kullanın.  
  
     ![Tek bir parmak dokunma hedef](../debugger/media/simulator_onefingerengaged.png "SIMULATOR_OneFingerEngaged") dokunma modunu etkinleştirmek için sol fare düğmesine basın. Örneğin, bir dokunun benzetimini yapmak veya sürükleyin ya da içeri doğru çekin gibi düğmesini basılı için düğmesini tıklatın.  
  
## <a name="pinch-and-zoom"></a>Çimdik ve Yakınlaştır  
 Çimdik ve iki parmakları hareketleri yakınlaştırmak için etkileşim modunu ayarlar.  
  
-   ![Siimulator iki parmak hedef](../debugger/media/simulator_twofinger.png "SIMULATOR_TwoFinger")  
  
     Çift hedef simgesini aygıt ekranında iki parmakları konumunu belirtir.  
  
    -   Cihaz ekranı nesnesinde üzerinden simgeleri konumlandırmak için fareyi hareket ettirin.  
  
    -   Fare tekerleği geriye dönük veya çimdik veya yakınlaştırma önce iki parmakları benzetimli uzaklığı değiştirmek için İleri döndürün.  
  
-   -   ![Çimdik, yakınlaştırma ve döndürme hedefleri](../debugger/media/simulator_twofingerengaged.png "SIMULATOR_TwoFingerEngaged")  
  
         Sol düğmesine basın ve (tutarak içinde) yakınlaştırmak için (,) geriye dönük tekerleği döndürün.  
  
    -   Sol düğmesine basın ve (uzaklaştırma) yakınlaştırma için fare tekerleğinin (İleri) döndürün.  
  
## <a name="object-rotation"></a>Nesne döndürme  
 **Dokunma öykünme döndürme** düğmesi iki parmakları kullanarak döndürme hareketleri etkileşim modunu ayarlar.  
  
-   -   Cihaz ekranı nesnesinde üzerinden simgeleri konumlandırmak için fareyi hareket ettirin.  
  
    -   Fare tekerleği geriye dönük veya nesneyi döndürmek önce iki parmakları benzetimli yönünü değiştirmek için İleri döndürün.  
  
-   -   Sol düğmesine basın ve yönünün nesneyi döndürmek için (,) geriye dönük tekerleği döndürün. Fare tekerleği döndürürken iki hedef simgelerinden birini diğer döndürme göreli boyutunu belirtmek için döndürür.  
  
    -   Sol düğmesine basın ve nesneyi saat yönünde döndürmek için fare tekerleğinin (İleri) döndürün.  
  
##  <a name="BKMK_Enable_or_disable_Always_on_top_mode"></a> Etkinleştirmek veya her zaman üst modunu devre dışı  
 Simulator penceresini her zaman diğer windows en üstünde olacak şekilde ayarlayabilirsiniz. **En üstteki pencere geçişi** düğmesini etkinleştirir veya devre dışı bırakır **her zaman üstte** simulator penceresinin modu.  
  
##  <a name="BKMK_Change_the_device_orientation"></a> Cihaz yönlendirmesini değiştirme  
 Herhangi bir yönde 90 derece simulator döndürerek cihaz yönlendirmesini dikey ve yatay arasında geçiş yapabilirsiniz.  
  
> [!NOTE]
>  Simulator saygı [DisplayProperties.AutoRotationPreferences](http://go.microsoft.com/fwlink/?LinkId=249460) projenin özelliği. Örneğin, projenizin yönlendirmesini olarak ayarlar, `Landscape`ve ardından dikey yönlendirmeye simulator döndürme, simulator ekran görüntüsü de döndürülmüş ve yeniden boyutlandırılabilir. Bu ayarları gerçek cihazında sınayın.  
  
> [!NOTE]
>  Bir simulator kenarına görüntülendiği ekran daha büyük şekilde simulator döndürme olursa simulator içinde ekran sığması için otomatik olarak boyutlandırılır. Yeniden döndürme olursa simulator özgün boyutuna boyutlandırılır değil.  
  
##  <a name="BKMK_Change_the_simulated_screen_size_and_resolution"></a> Çözümleme ve sanal ekran boyutu değiştirme  
 Benzetimli ekran boyutu ve çözünürlüğü değiştirmek için tercih **değiştirmek çözümleme** paletini temel düğmesine tıklayın ve yeni boyutunu ve çözüm listeden seçin.  
  
 Ekran boyutu ve çözüm olarak listelenen *ekran genişliği inç, piksel genişlik X piksel yükseklik*. Ekran boyutu ve çözümleme benzetilir unutmayın. Seçilen aygıt boyutu ve çözümleme ortak ordinates için konum ortak ordinates simulator üzerinde çevrilir.  
  
> [!NOTE]
>  Bit eşlem görüntülerinin ölçeklendirilmiş sürümleri uygulamanızda kaydedebilir ve Windows geçerli ölçek için doğru görüntüyü yükler. Daha fazla bilgi için bkz: [tasarım ve kullanıcı Arabirimi giriş](/windows/uwp/layout/design-and-ui-intro). Ancak, Windows çözümleme sığması için farklı bir resim Çekmeleri şekilde simulator çözümleme değiştirirseniz, durdurmak ve yeni görüntüyü görüntülemek için hata ayıklama oturumu yeniden başlatması.  
  
##  <a name="BKMK_Capture_a_screenshot_of_your_app_for_submission_to_the_Microsoft_Store"></a> Microsoft Store göndermelerini, uygulamanızın bir ekran görüntüsü alma  
 Bir uygulamaya Microsoft Store gönderdiğinizde, uygulama ekran görüntüleri eklemeniz gerekir.  
  
> [!NOTE]
>  Ekran simulator geçerli çözünürlükte kaydedilir. Çözümleme değiştirmek için tercih **değiştirmek çözümleme** düğmesi.  
  
-   Ekran görüntüleri, uygulamanızın simulator oluşturmak için seçtiğiniz **panoya ekran yakalama** düğmesi.  
  
-   Ekran görüntüleri bulunduğu konumun ayarlamak için seçin **ekran ayarları** düğmesine tıklayın ve kısayol menüsünden konumu seçin.  
  
     ![Ekran ayarları bağlam menüsü](../debugger/media/simulator_screenshotsettingscntxmnu.png "SIMULATOR_ScreenShotSettingsCntxMnu")  
  
##  <a name="BKMK_Simulate_network_connection_properties"></a> Ağ bağlantısı özellikleri benzetimi  
 Uygulamanızın kullanıcıları ağ bağlantı maliyeti veya veri planı durum değişikliklerini tanıma koruma ve dolaşım veya aşan ek maliyetlerin oluşmasını önlemek için bu bilgileri kullanmak uygulamanızı etkinleştirme tarafından tarifeli ağ bağlantılarında maliyetini Yönet yardımcı olabilecek bir Belirtilen veri aktarımı sınırı. [Windows.Networking.Connectivity](/uwp/api/windows.networking.connectivity) API'ler sağlar, yanıt [NetworkStatusChanged](/uwp/api/windows.networking.connectivity.networkinformation) ve [TriggerType](/uwp/api/windows.applicationmodel.background.systemtrigger) oturum olayları. Bkz: [hızlı başlangıç: tarifeli ağ yönetme maliyet kısıtlamaları](http://msdn.microsoft.com/library/windows/apps/Hh750310.aspx).  
  
 Hata ayıklama veya ağ maliyet uyumlu kodunuzu test etmek için simulator aracılığıyla sunulan bir ağ özelliklerini taklit edebilirsiniz [ConnectionProfile](/uwp/api/windows.networking.connectivity.connectionprofile) tarafından döndürülen nesne [GetInternetConnectionProfile](/uwp/api/windows.networking.connectivity.networkinformation).
  
 Ağ özellikleri benzetimini yapmak için:  
  
1.  Simulator araç çubuğunda seçin **değiştirmek ağ özellikleri** düğmesi.  
  
2.  Üzerinde **ağ özelliklerini ayarla** iletişim kutusunda **kullanım benzetimli ağ özellikleri**.  
  
     Benzetim kaldırın ve şu anda bağlı arabirimi ağ özelliklerine dönmek için bu onay kutusunu temizleyin.  
  
3.  Girin bir **profil adı** sanal ağ için. Benzetim tanımlamak için kullanabileceğiniz benzersiz bir ad kullanmanızı öneririz [ProfileName](/uwp/api/windows.networking.connectivity.connectionprofile) özelliği [ConnectionProfile](/uwp/api/windows.networking.connectivity.connectionprofile) nesnesi.  
  
4.  Seçin [NetworkCostType](/uwp/api/windows.networking.connectivity.networkcosttype) profilinden değeri **ağ maliyet türü** listesi.  
  
5.  Gelen **veri sınırı durum bayrağı** ayarlayabileceğiniz listesinde [ApproachingDataLimit](/uwp/api/windows.networking.connectivity.connectioncost) özelliği veya [OverDataLimit](/uwp/api/windows.networking.connectivity.connectioncost) özelliği true olarak veya seçebilirsiniz  **Veri sınırı altında** her iki değeri false olarak ayarlamak üzere.  
  
6.  Gelen **gezici durumu** listesinde, ayarlamak [gezici](/uwp/api/windows.networking.connectivity.connectioncost) özelliği.  
  
7.  Seçin **özelliklerini ayarla** ön plan tetikleme tarafından ağ özellikleri benzetimini yapmak için [NetworkStatusChanged](/uwp/api/windows.networking.connectivity.networkinformation) olay ve arka plan [SystemTrigger](/uwp/api/windows.applicationmodel.background.systemtrigger) türü **NetworkStateChange**.  
  
 **Ağ bağlantılarını yönetme hakkında daha fazla bilgi**  
  
 [Hızlı Başlangıç: Tarifeli ağ maliyet kısıtlamaları yönetme](http://msdn.microsoft.com/library/windows/apps/Hh750310.aspx)  
  
 [Ağ bilgi örnek](http://code.msdn.microsoft.com/windowsapps/Network-Information-Sample-63aaa201)  
  
 [Enerji kullanımını çözümleme](../profiling/analyze-energy-use-in-store-apps.md)  
  
 [Windows.Networking.Connectivity](/uwp/api/windows.networking.connectivity)  
  
 [Arka plan görevleri ile sistem olaylarına tepki vermek nasıl](http://msdn.microsoft.com/en-us/f7c86e86-a7ae-4abb-a923-76b03337a80a)  
  
 [UWP uygulamalarında askıya alma, sürdürme ve arka plan olayları tetikleme](http://msdn.microsoft.com/library/windows/apps/hh974425.aspx)  
  
##  <a name="BKMK_Navigate_the_simulator_with_the_keyboard"></a> Klavye ile simulator gidin  
 Simulator araç çubuğu tuşlarına basarak gezinebilirsiniz **CTRL + ALT + YUKARI OK** odak simulator penceresinden simulator araç çubuğuna geçiş yapmak için. Kullanım **yukarı ok** ve **aşağı ok** araç çubuğu düğmeleri arasında taşımak için.  
  
 Simulator tuşlarına basarak kapatabilirsiniz **CTRL + ALT + F4**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'dan uygulamaları çalıştırma](../debugger/run-store-apps-from-visual-studio.md)