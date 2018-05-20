---
title: UWP uygulamalarında enerji kullanımını çözümleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 96d06843-b97e-45a8-8126-07478a40bfc4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 8e7bd65e67af3a76eaf026e79c1153489b9d26a8
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="analyze-energy-use-in-uwp-apps"></a>UWP uygulamalarında enerji kullanımını çözümleme
Visual Studio **enerji tüketimi** profil oluşturucu UWP uygulamaları kendi pille saat bölümünü veya tümünü Çalıştır düşük güç tablet cihazlarda güç ve enerji tüketimi analiz etmenize yardımcı olur. Enerjisini pilden alan bir aygıtta çok fazla enerji kullanan bir uygulama, çok fazla müşteri memnuniyetsizliğine neden olabilir ve sonunda müşteriler uygulamayı kaldırmaya da karar verebilir. Enerji kullanımını en iyi duruma getirme, uygulamanızın benimseme artırmak ve müşteriler tarafından kullanın.  
  
##  <a name="BKMK_What_the_Energy_Consumption_tool_is__how_it_works__and_what_it_measures"></a> Ne ölçer enerji tüketimi profil oluşturucu nedir ve nasıl çalışır?  
 Enerji Tüketimi profil oluşturucusu, profil oluşturma oturumu sırasında bir cihazın ekran, CPU ve ağ bağlantıları etkinliklerini yakalar. Sonra, bu etkinlikler için kullanılan güçle ilgili ve profil oluşturma oturumunun toplam enerji miktarı için tahminler oluşturur.  
  
> [!NOTE]
>  Enerji profil oluşturucusu, güç ve enerji kullanımını tahmin etmek için, uygulamalarınızın çalıştırılabileceği düşük güçlü tablet cihazları temsil eden standart bir referans cihaz donanımı içeren bir yazılım modeli kullanır. En iyi tahminleri sağlamak için, düşük güç kullanan bir tablet cihazdaki profil verilerini toplamanız önerilir.  
>   
>  Bu model düşük güç tüketen çeşitli cihazlar için iyi tahminler sağlasa da, profilini oluşturduğunuz cihazın gerçek değerleri muhtemelen farklı olur. Diğer kaynaklara göre daha maliyetli ve dolayısıyla optimizasyon için iyi aday olabilecek ekran, CPU ve ağ etkinliklerini bulmak için değerleri kullanın.  
  
 Enerji tüketimi profil oluşturucu bu tanımları kullanır *güç* ve *enerji*:  
  
-   *Güç* ölçüleri zorla oranı bir süre içinde yapılır işlerini yapmak için kullanılır. Standart birimidir güç, elektrik Bilim içinde bir *watt*, hangi iş yapılır ne zaman oranı tanımlanan bir volt bir elektrik olası fark aracılığıyla geçerli akışlarının bir ampere. İçinde **güç kullanımı** grafik, birimleri Miliwatt görüntülenen **mW** bir watt bir 214.748,3648 olduğu.  
  
     Güç bir miktar olduğundan, bir yönü (bir zaman dilimi içinde artabilir veya azalabilir) ve bir de hızı (işin artış veya azalış miktarı) olduğu unutulmamalıdır.  
  
-   *Enerji* güç, kapasite ya da bir pil gücü kapasitesini olduğu gibi olası veya olarak toplam toplam miktarı amounted bir süre boyunca tüketim güç ölçümleri. Enerji birimi watt-saat olup, bir saat boyunca sürekli olarak uygulanan bir watt'lık güç miktarıdır. İçinde **enerji Özet**, birimleri Miliwatt-Saat görüntülenen **mW-h**.  
  
 ![Enerji kapasite güç kullanıldığında, kullanılan toplam enerji](../profiling/media/energyprof_capcitypowerused.png "ENERGYPROF_CapcityPowerUsed")  
  
 Örneğin, bir tabletteki tam şarjlı bir pilde belli miktarda depolanmış enerji vardır. Bir ağ üzerinden iletişim kurma, değerleri hesaplama veya grafikleri görüntüleme gibi görevleri gerçekleştirmek için enerji kullanıldıkça, pilin gücü farklı oranlarda harcanır. Herhangi bir zaman dilimi için, harcanan güç toplamı da enerji ile ölçülür.  
  
##  <a name="BKMK_Identify_scenarios_with_user_marks"></a> Kullanıcı işaretleriyle senaryolarını belirle  
 Ekleyebileceğiniz *kullanıcı işaretleri* zaman çizelgesi cetveli alanlarda tanımlamaya yardımcı olmak üzere profil verilerinize.  
  
 ![Zaman Çizelgesi kullanıcı işaretleri](../profiling/media/profilers_usermarktimeline.png "PROFILERS_UserMarkTimeline")  
  
 İşaret, zaman çizelgesinde yöntemin yürütüldüğü zamanda turuncu bir üçgen olarak görünür. İşaret üzerinde beklediğinizde, ileti ve saat araç ipucu olarak görüntülenir. İki veya daha fazla kullanıcı işareti birbirine yakınsa, işaretler birleştirilir ve araç ipucu verileri birleştirilir. İşaretleri ayırmak için zaman çizelgesinde yakınlaştırma yapabilirsiniz.  
  
 **İşaretleri C#, Visual Basic, C++ kod ekleme**  
  
 Bir kullanıcı işareti C# eklemek için Visual Basic, C++ kodu oluşturun bir [Windows.Foundation.Diagnostics LoggingChannel](http://msdn.microsoft.com/library/windows/apps/windows.foundation.diagnostics.loggingchannel.aspx) nesnesi. Çağrı Ekle [LoggingChannel.LogMessage](http://msdn.microsoft.com/library/windows/apps/dn264210.aspx) kodunuzda işaretlemek istediğiniz noktalarda yöntemleri. Kullanım [LoggingLevel.Information](http://msdn.microsoft.com/library/windows/apps/windows.foundation.diagnostics.logginglevel.aspx) çağrılarında.  
  
 Yöntem yürütüldüğünde, profil oluşturma verilerine bir iletiyle birlikte bir kullanıcı işareti eklenir.  
  
> [!NOTE]
>  -   Windows.Foundation.Diagnostics LoggingChannel uygulayan [Windows.Foundation.IClosable](/uwp/api/windows.foundation.iclosable) arabirimi (tahmini olarak [System.IDisposable](/dotnet/api/system.idisposable) C# ve VB). İşletim sistemi kaynaklarını sızmasını önlemek için arama [LoggingChannel.Close](/uwp/api/Windows.Foundation.Diagnostics.LoggingChannel) ([Windows.Foundation.Diagnostics.LoggingChannel.Dispose](/uwp/api/Windows.Foundation.Diagnostics.LoggingChannel) C# ve VB) işiniz bittiğinde günlüğe kaydetme ile kanalı.  
> -   Her açık günlük kanalının benzersiz bir adı olması gerekir. Elde kalan bir kanal ile aynı adda yeni bir günlük kanalı oluşturmaya çalışmak özel duruma neden olur.  
  
 Windows SDK'sı örneği bkz [LoggingSession örnek](http://code.msdn.microsoft.com/windowsapps/LoggingSession-Sample-ccd52336) örnekleri için.  
  
 **JavaScript kodu işaretleri ekleyin**  
  
 Kullanıcı işaretleri eklemek için, kodunuzda işaretlemek istediğiniz noktalarda aşağıdaki kodu ekleyin:  
  
```JavaScript  
if (performance && performance.mark) {  
    performance.mark(markDescription);  
}  
```  
  
 *markDescription* kullanıcı işareti İpucunda görüntülenecek iletiyi içeren bir dizedir.  
  
##  <a name="BKMK_Configure_your_environment_for_profiling"></a> Profil oluşturma için ortamınızı yapılandırma  
 İyi tahminleri elde etmek için uygulama tarafından pil gücü düşük destekli bir aygıtta enerji kullanımını profil istersiniz. Visual Studio bu çoğu cihazında çalıştırmadığı aygıtına Visual Studio uzak araçlar kullanarak Visual Studio bilgisayarınızı bağlamanız gerekir. Uzaktaki bir cihaza bağlanmak için, hem Visual Studio projesini hem de uzak cihazı yapılandırmanız gerekir. Bkz: [uzaktaki bir makinede çalıştırın UWP uygulamaları](../debugger/run-windows-store-apps-on-a-remote-machine.md) daha fazla bilgi için.  
  
> [!TIP]
>  -   UWP simulator veya Visual Studio bilgisayara enerji profil öneririz yok. Gerçek cihazda profil oluşturmak çok daha gerçekçi veriler sağlar.  
> -   Hedef cihazda profil oluşturmayı, kendi pilleriyle çalışırken gerçekleştirin.  
> -   Aynı kaynakları (ağ, CPU veya ekran) kullanabilecek diğer uygulamaları kapatın.  
  
##  <a name="BKMK_Collect_energy_profile_data_for_your_app"></a> Uygulamanız için enerji profil verilerini topla  
  
1.  Üzerinde **hata ayıklama** menüsünde seçin **tanılama olmadan hata ayıklamayı Başlat**.  
  
     ![Enerji tüketimi tanılama hub'ı seçin](../profiling/media/energyprof_diagnosticshub.png "ENERGYPROF_DiagnosticsHub")  
  
2.  Seçin **enerji tüketimi** ve ardından **Başlat**.  
  
    > [!NOTE]
    >  Başlattığınızda **enerji tüketimi** profil oluşturucu, görebileceği bir **kullanıcı hesabı denetimi** VsEtwCollector.exe çalıştırmak için izninizi isteyen penceresi. Seçin **Evet**.  
  
3.  Veri toplamak için uygulamanızda alıştırma yapın.  
  
4.  Profil oluşturmayı durdurmak için geri Visual Studio'ya (Alt + Sekme) geçip seçin **durdurmak koleksiyonu** tanılama hub'ı sayfasında.  
  
     ![Veri toplamayı durdurmak](../profiling/media/xamlprof_stopcollection.png "XAMLProf_StopCollection")  
  
     Visual Studio toplanan verileri analiz eder ve sonuçları görüntüler.  
  
##  <a name="BKMK_Collect_energy_profile_data_for_an_installed_app"></a> Yüklü bir uygulama için enerji profil verilerini topla  
 Enerji tüketimi aracı yalnızca, bir Visual Studio çözümü başlatıldığında veya Microsoft Store yüklü UWP uygulamaları çalıştırılabilir. Bir çözümü Visual Studio'da açıkken, varsayılan hedef olduğu **başlangıç projesi**. Yüklü bir uygulamayı hedeflemek için:  
  
1.  Seçin **değişiklik hedef** ve ardından **yüklü App**.  
  
2.  Gelen **yüklü uygulama paketi seçin** listesinde, bir hedef seçin.  
  
3.  Seçin **enerji tüketimi** tanılama hub'ı sayfasında.  
  
4.  Seçin **Başlat** profil oluşturmayı başlatmak için.  
  
 Profil oluşturmayı durdurmak için geri Visual Studio'ya (Alt + Sekme) geçip seçin **durdurmak koleksiyonu** tanılama hub'ı sayfasında.  
  
##  <a name="BKMK_Analyze_energy_profile_data"></a> Enerji profil verileri analiz etme  
 Enerji profili verileri Visual Studio belge penceresinde görüntülenir:  
  
 ![Enerji Profil Oluşturucusu rapor sayfasının](../profiling/media/energyprof_all.png "ENERGYPROF_All")  
  
|||  
|-|-|  
|![1. adım](../profiling/media/procguid_1.png "ProcGuid_1")|Rapor dosyası rapor adlı*YYYYAAGG SSDD*.diagsession. Raporu kaydetmeye karar verirseniz adını değiştirebilirsiniz.|  
|![2. adım](../profiling/media/procguid_2.png "ProcGuid_2")|Zaman çizelgesi profil oluşturma oturumunun uzunluğunu, uygulama yaşam döngüsü etkinleştirme olaylarını ve kullanıcı işaretlerini gösterir.|  
|![3. adım](../profiling/media/procguid_3.png "ProcGuid_3")|Mavi çubukları sürükleyip zaman çizelgesinde bir bölgeyi seçerek, raporu zaman çizelgesinin bir bölümüyle sınırlandırabilirsiniz.|  
|![Adım 4](../profiling/media/procguid_4.png "ProcGuid_4")|**Güç kullanımı** grafiktir değişikliği aygıt kaynak tarafından profil oluşturma oturumu sırasında neden güç çıktı görüntüler çok çizgi grafiği. Enerji Tüketimi profil oluşturucusu CPU, ağ etkinliği ve ekran görüntüsü tarafından kullanılan gücü izler.|  
|![5. adım](../profiling/media/procguid_6.png "ProcGuid_6")|**Kaynakları (açık/kapalı)** grafiği enerji maliyeti ağ ayrıntılarını sağlar. **Ağ** çubuk ağ bağlantısı açık olduğu zamanı temsil eder. **Veri aktarımı** alt çubuğu, uygulama alma veya ağ üzerinden veri gönderme olduğunu süre.|  
|![Adım 6](../profiling/media/procguid_6a.png "ProcGuid_6a")|**Enerji Kullanım Özeti** seçili zaman çizelgesi CPU, ağ etkinliği ve ekran görüntüsü tarafından kullanılan toplam enerji orantılı miktarını gösterir.|  
  
 **Enerji profil verileri çözümlemek için**  
  
 Kaynağın gücünün tepe noktasına vardığı bir alan bulun. Tepe noktası alanını, uygulamanızın işlevselliğiyle ilişkilendirin. Sonra zaman çizelgesindeki denetim çubuklarını kullanarak, zaman çizelgesinde alanı yakınlaştırın. Ağ kullanımı odaklanmış durumdaysa genişletin **ağ** düğümünde **kaynakları (açık/kapalı)** uygulama alma veya aktarma süreye açık olan ağ bağlantısı zaman karşılaştırmak için grafik veri bağlantısı üzerinden. Ağın gereksiz yere açık kaldığı süreyi azaltmak çok etkili bir optimizasyondur.  
  
##  <a name="BKMK_Optimize_energy_use"></a> Enerji kullanımını en iyi duruma getirme  
 Ağ bağlantılarında veri aktarmaktan başka, bağlantı başlatma, sürdürme ve kapatma ile ilgili enerji maliyetleri de vardır. Bazı ağlar veri gönderildikten veya alındıktan sonra, tek bağlantı üzerinden daha fazla veri iletimine olanak sağlamak için bağlantıyı bir süre daha sürdürür. Kullanabileceğiniz **kaynakları (açık/kapalı)** bölmesinde uygulamanızı bağlantı ile etkileşim şeklini inceleyin.  
  
 ![Kaynakları &#40;üzerinde&#47;kapalı&#41; bölmesinde](../profiling/media/energyprof_resources.png "ENERGYPROF_Resources")  
  
 Varsa **ağ** ve **veri aktarımı** çubukları bağlantı zaman zaman bir dizi küçük veri paketlerini iletmek uzun süre boyunca açık olduğunda, bir iletim gönderilecek veri toplu ağ açık olan süreyi azaltmak ve bu nedenle enerji maliyeti kaydedin.  
  
 ![Enerji tüketimi özeti bölmesinde](../profiling/media/energyprof_summary.png "ENERGYPROF_Summary")  
  
 Ekranın enerji giderleri üzerinde daha az denetiminiz vardır. Çoğu ekranlar açık renkleri görüntülemek için koyu renklere göre daha fazla enerji harcar ve dolayısıyla koyu renk arka plan kullanmak giderleri azaltmanın bir yoludur.  
  
##  <a name="BKMK_Other_resources"></a> Diğer kaynaklar  
  
-   **Bağlantı durumunu ve maliyet Yönetim** için bölümler [C# / VB/C++ ve XAML](http://msdn.microsoft.com/en-us/0ee0b706-8432-4d49-9801-306ed90764e1) ve [JavaScript ve HTML](http://msdn.microsoft.com/en-us/372afa6a-1c7c-4657-967d-03a77cd8e933) Windows geliştirme Merkezi'nde sağlayan Windows API'larını açıklar ağ trafiği maliyetini en aza indirmek için uygulamanızı kullanabilirsiniz ağ bağlantı bilgileri.  
  
     UWP uygulamalar için Visual Studio simulator ağ bilgilerini API'leri veri bağlantısı özelliklerini benzetimini sağlar. Bkz: [simulator çalıştırmak UWP uygulamaları](../debugger/run-windows-store-apps-in-the-simulator.md)  
  
-   **JavaScript işlevi zamanlama** ve **CPU kullanımı** araçları verimsiz işlevleri tarafından nedeni CPU yükünü azaltmanıza yardımcı olabilir. Bkz: [CPU kullanımı analiz](../profiling/analyze-cpu-usage-in-a-windows-universal-app.md).

## <a name="see-also"></a>Ayrıca bkz.
 [Visual Studio'da profil oluşturma](../profiling/index.md)  
 [Özellik turu profil oluşturma](../profiling/profiling-feature-tour.md)