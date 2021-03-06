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
ms.openlocfilehash: 3578573a2020dbf048e3da4e0bf44a54df07860b
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "35676757"
---
# <a name="analyze-energy-use-in-uwp-apps"></a>UWP uygulamalarında enerji kullanımını analiz etme
Visual Studio **enerji tüketimi** profil oluşturucu, zaman bir kısmını veya tamamını kendi piliyle çalışan düşük güçlü tablet cihazları UWP uygulamaları güç ve enerji tüketimini çözümlemenize yardımcı olur. Enerjisini pilden alan bir aygıtta çok fazla enerji kullanan bir uygulama, çok fazla müşteri memnuniyetsizliğine neden olabilir ve sonunda müşteriler uygulamayı kaldırmaya da karar verebilir. Enerji kullanımını en iyi duruma getirme, uygulamanızın benimsenme oranını artırabilirsiniz ve müşteriler tarafından kullanın.  
  
## <a name="what-the-energy-consumption-profiler-is-how-it-works-and-what-it-measures"></a>Enerji Tüketimi profil oluşturucusu nedir, nasıl çalışır ve neleri ölçer?  
 Enerji Tüketimi profil oluşturucusu, profil oluşturma oturumu sırasında bir cihazın ekran, CPU ve ağ bağlantıları etkinliklerini yakalar. Sonra, bu etkinlikler için kullanılan güçle ilgili ve profil oluşturma oturumunun toplam enerji miktarı için tahminler oluşturur.  
  
> [!NOTE]
>  Enerji profil oluşturucusu, güç ve enerji kullanımını tahmin etmek için, uygulamalarınızın çalıştırılabileceği düşük güçlü tablet cihazları temsil eden standart bir referans cihaz donanımı içeren bir yazılım modeli kullanır. En iyi tahminleri sağlamak için, düşük güç kullanan bir tablet cihazdaki profil verilerini toplamanız önerilir.  
>   
>  Bu model düşük güç tüketen çeşitli cihazlar için iyi tahminler sağlasa da, profilini oluşturduğunuz cihazın gerçek değerleri muhtemelen farklı olur. Diğer kaynaklara göre daha maliyetli ve dolayısıyla optimizasyon için iyi aday olabilecek ekran, CPU ve ağ etkinliklerini bulmak için değerleri kullanın.  
  
 Enerji tüketimi Profil Oluşturucusu bu tanımları kullanır *güç* ve *enerji*:  
  
-   *Güç* ölçüler zorla oranı bir sürede yapılan işi gerçekleştirmek için kullanılır. Elektrik biliminde standart güç birimi olan bir *watt*, hangi iş yapılır zaman oranı tanımlanan bir ampere aracılığıyla voltluk elektriksel potansiyel farkından bir amper, geçerli akış. İçinde **güç kullanımı** grafiğinde birimler Miliwatt **mW** watt'ın bir 214.748,3648 olduğu.  
  
     Güç bir miktar olduğundan, bir yönü (bir zaman dilimi içinde artabilir veya azalabilir) ve bir de hızı (işin artış veya azalış miktarı) olduğu unutulmamalıdır.  
  
-   *Enerji* toplam kapasite veya potansiyel, bir pilin güç kapasitesi olduğu gibi olarak ya da toplam güç miktarı pilin güç bir süre minimuma ölçümleri. Enerji birimi watt-saat olup, bir saat boyunca sürekli olarak uygulanan bir watt'lık güç miktarıdır. İçinde **enerji özeti**, birim watt-saat görüntülenen **mW-h**.  
  
 ![Enerji kapasite, power kullanıldığında, kullanılan toplam enerji](../profiling/media/energyprof_capcitypowerused.png "ENERGYPROF_CapcityPowerUsed")  
  
 Örneğin, bir tabletteki tam şarjlı bir pilde belli miktarda depolanmış enerji vardır. Bir ağ üzerinden iletişim kurma, değerleri hesaplama veya grafikleri görüntüleme gibi görevleri gerçekleştirmek için enerji kullanıldıkça, pilin gücü farklı oranlarda harcanır. Herhangi bir zaman dilimi için, harcanan güç toplamı da enerji ile ölçülür.  
  
## <a name="identify-scenarios-with-user-marks"></a>Kullanıcı işaretleriyle senaryoları tanımlama  
 Ekleyebileceğiniz *kullanıcı işaretlerini* profil oluşturma verilerinize zaman çizelgesi cetvelindeki alanları tanımlamanıza yardımcı olacak.  
  
 ![Kullanıcı işaretleri zaman çizelgesinde](../profiling/media/profilers_usermarktimeline.png "PROFILERS_UserMarkTimeline")  
  
 İşaret, zaman çizelgesinde yöntemin yürütüldüğü zamanda turuncu bir üçgen olarak görünür. İşaret üzerinde beklediğinizde, ileti ve saat araç ipucu olarak görüntülenir. İki veya daha fazla kullanıcı işareti birbirine yakınsa, işaretler birleştirilir ve araç ipucu verileri birleştirilir. İşaretleri ayırmak için zaman çizelgesinde yakınlaştırma yapabilirsiniz.  
  
 **C#, Visual Basic, C++ kodu işaretler ekleme**  
  
 Bir kullanıcı işareti C# için eklemek için Visual Basic, C++ koduna, oluşturun bir [Windows.Foundation.Diagnostics LoggingChannel](http://msdn.microsoft.com/library/windows/apps/windows.foundation.diagnostics.loggingchannel.aspx) nesne. Ardından çağrıları Ekle [LoggingChannel.LogMessage](http://msdn.microsoft.com/library/windows/apps/dn264210.aspx) kodunuzda işaretlemek istediğiniz noktalarda yöntemleri. Kullanım [LoggingLevel.Information](http://msdn.microsoft.com/library/windows/apps/windows.foundation.diagnostics.logginglevel.aspx) çağrılarda.  
  
 Yöntem yürütüldüğünde, profil oluşturma verilerine bir iletiyle birlikte bir kullanıcı işareti eklenir.  
  
> [!NOTE]
>  -   Windows.Foundation.Diagnostics LoggingChannel uygulayan [Windows.Foundation.ıclosable](/uwp/api/windows.foundation.iclosable) arabirimi (tahmini olarak [System.IDisposable](/dotnet/api/system.idisposable) C# ve VB). İşletim sistemi kaynaklarını sızdırılmasını önlemek için çağrı [LoggingChannel.Close](/uwp/api/Windows.Foundation.Diagnostics.LoggingChannel) ([Windows.Foundation.Diagnostics.LoggingChannel.Dispose](/uwp/api/Windows.Foundation.Diagnostics.LoggingChannel) C# ve VB) işiniz bittiğinde günlük kaydı ile Kanal.  
> -   Her açık günlük kanalının benzersiz bir adı olması gerekir. Elde kalan bir kanal ile aynı adda yeni bir günlük kanalı oluşturmaya çalışmak özel duruma neden olur.  
  
 Bkz. Windows SDK'sı örneği [LoggingSession örneğine](http://code.msdn.microsoft.com/windowsapps/LoggingSession-Sample-ccd52336) örnekler.  
  
 **İşaretleri JavaScript kodunu ekleyin**  
  
 Kullanıcı işaretleri eklemek için, kodunuzda işaretlemek istediğiniz noktalarda aşağıdaki kodu ekleyin:  
  
```JavaScript  
if (performance && performance.mark) {  
    performance.mark(markDescription);  
}  
```  
  
 *markDescription* kullanıcı işareti İpucunda görüntülenecek iletiyi içeren bir dizedir.  
  
## <a name="configure-your-environment-for-profiling"></a>Profil oluşturma için ortamınızı yapılandırma  
 İyi tahminler elde etmek için pilden güç alan düşük güç tüketimli bir cihazda uygulamanın enerji kullanımının profilini oluşturmak istersiniz. Visual Studio bu cihazların çoğunda çalışmadığından, Visual Studio bilgisayarınızı cihaza Visual Studio uzak araçlarını kullanarak bağlanmak gerekir. Uzaktaki bir cihaza bağlanmak için, hem Visual Studio projesini hem de uzak cihazı yapılandırmanız gerekir. Bkz: [uzak bir makinede çalıştırmak UWP uygulamaları](../debugger/run-windows-store-apps-on-a-remote-machine.md) daha fazla bilgi için.  
  
> [!TIP]
>  -   UWP simülatör'ü veya Visual Studio bilgisayarında enerji profili oluşturma önerilmemektedir. Gerçek cihazda profil oluşturmak çok daha gerçekçi veriler sağlar.  
> -   Hedef cihazda profil oluşturmayı, kendi pilleriyle çalışırken gerçekleştirin.  
> -   Aynı kaynakları (ağ, CPU veya ekran) kullanabilecek diğer uygulamaları kapatın.  
  
## <a name="collect-energy-profile-data-for-your-app"></a>Uygulamanız için enerji profili verilerini toplama  
  
1.  Üzerinde **hata ayıklama** menüsünde seçin **tanılama hata ayıklama olmadan Başlat**.  
  
     ![Enerji tüketimi tanılama hub'ı seçin.](../profiling/media/energyprof_diagnosticshub.png "ENERGYPROF_DiagnosticsHub")  
  
2.  Seçin **enerji tüketimi** seçip **Başlat**.  
  
    > [!NOTE]
    >  Başladığınızda **enerji tüketimi** profil, bir **kullanıcı hesabı denetimi** çalıştırmak için izninizi isteyen bir pencere *Vsetwcollector.exe'yi*. Seçin **Evet**.  
  
3.  Veri toplamak için uygulamanızda alıştırma yapın.  
  
4.  Profil oluşturmayı durdurmak için Visual Studio'ya dönün (Alt + Sekme) ve seçin **koleksiyonu Durdur** tanılama hub'ı sayfasında.  
  
     ![Veri toplamayı durdurmak](../profiling/media/xamlprof_stopcollection.png "XAMLProf_StopCollection")  
  
     Visual Studio toplanan verileri analiz eder ve sonuçları görüntüler.  
  
## <a name="collect-energy-profile-data-for-an-installed-app"></a>Yüklü bir uygulama için enerji profili verilerini toplama  
 Enerji tüketimi aracı yalnızca, Visual Studio çözümünden başlatılan veya Microsoft Store yüklü UWP uygulamalarında çalıştırılabilir. Visual Studio'da bir çözümü açtığınızda, varsayılan hedef olduğunu **başlangıç projesi**. Yüklü bir uygulamayı hedeflemek için:  
  
1.  Seçin **hedefi Değiştir** seçip **uygulamasının yüklü**.  
  
2.  Gelen **yüklü uygulama paketi seçin** listesinde, bir hedef seçin.  
  
3.  Seçin **enerji tüketimi** tanılama hub'ı sayfasında.  
  
4.  Seçin **Başlat** profili oluşturmaya başlamak için.  
  
 Profil oluşturmayı durdurmak için Visual Studio'ya dönün (Alt + Sekme) ve seçin **koleksiyonu Durdur** tanılama hub'ı sayfasında.  
  
## <a name="analyze-energy-profile-data"></a>Enerji profili verilerini analiz etme  
 Enerji profili verileri Visual Studio belge penceresinde görüntülenir:  
  
 ![Enerji Profil Oluşturucusu rapor sayfası](../profiling/media/energyprof_all.png "ENERGYPROF_All")  
  
|||  
|-|-|  
|![1. adım](../profiling/media/procguid_1.png "ProcGuid_1")|Rapor dosyası, rapor adlı*YYYYMMDD-HHMM*.diagsession. Raporu kaydetmeye karar verirseniz adını değiştirebilirsiniz.|  
|![2. adım](../profiling/media/procguid_2.png "ProcGuid_2")|Zaman çizelgesi profil oluşturma oturumunun uzunluğunu, uygulama yaşam döngüsü etkinleştirme olaylarını ve kullanıcı işaretlerini gösterir.|  
|![3. adım](../profiling/media/procguid_3.png "ProcGuid_3")|Mavi çubukları sürükleyip zaman çizelgesinde bir bölgeyi seçerek, raporu zaman çizelgesinin bir bölümüyle sınırlandırabilirsiniz.|  
|![4. adım](../profiling/media/procguid_4.png "ProcGuid_4")|**Güç kullanımı** grafiğidir bir profil oluşturma oturumu sırasında bir aygıt kaynağının neden olduğu güç çıkışı değişikliğini gösteren çok satırlı bir grafiktir. Enerji Tüketimi profil oluşturucusu CPU, ağ etkinliği ve ekran görüntüsü tarafından kullanılan gücü izler.|  
|![5. adım](../profiling/media/procguid_6.png "ProcGuid_6")|**Kaynaklar (açık/kapalı)** grafiği ile ilgili enerji maliyetleri ağ ayrıntılarını sağlar. **Ağ** çubuğu ağ bağlantısının açık olduğu zamanı temsil eder. **Veri aktarımı** alt çubuğudur uygulama alma veya ağ üzerinden veri gönderme zamanı.|  
|![6. adım](../profiling/media/procguid_6a.png "ProcGuid_6a")|**Enerji Kullanım Özeti** CPU, ağ etkinliği ve ekran görüntüsünü seçili zaman çizelgesinde kullanılan toplam enerjinin orantılı miktarını gösterir.|  
  
 **Enerji profili verilerini analiz etmek için**  
  
 Kaynağın gücünün tepe noktasına vardığı bir alan bulun. Tepe noktası alanını, uygulamanızın işlevselliğiyle ilişkilendirin. Sonra zaman çizelgesindeki denetim çubuklarını kullanarak, zaman çizelgesinde alanı yakınlaştırın. Ağ kullanımına odaklanıyorsanız genişletin **ağ** düğümünde **kaynaklar (açık/kapalı)** ağ bağlantısı uygulama alma ya da aktarma zaman açık olduğu zamanı karşılaştırmak için grafiği verileri bağlantı üzerinden. Ağın gereksiz yere açık kaldığı süreyi azaltmak çok etkili bir optimizasyondur.  
  
## <a name="optimize-energy-use"></a>Enerji kullanımını en iyi duruma getirme  
 Ağ bağlantılarında veri aktarmaktan başka, bağlantı başlatma, sürdürme ve kapatma ile ilgili enerji maliyetleri de vardır. Bazı ağlar veri gönderildikten veya alındıktan sonra, tek bağlantı üzerinden daha fazla veri iletimine olanak sağlamak için bağlantıyı bir süre daha sürdürür. Kullanabileceğiniz **kaynaklar (açık/kapalı)** uygulamanızı bağlantıyla etkileşim şeklini incelemek için bölmesi.  
  
 ![Kaynakları &#40;üzerinde&#47;kapalı&#41; bölmesinde](../profiling/media/energyprof_resources.png "ENERGYPROF_Resources")  
  
 Varsa **ağ** ve **veri aktarımı** çubukları bağlantının aralıklı olarak birtakım küçük veri paketleri iletmek üzere uzun süreler boyu açık olduğundan, bir iletim gönderilecek verileri toplu iş ağın açık kaldığı süreyi azaltmak ve böylece enerji tasarrufu.  
  
 ![Enerji tüketimi özeti bölmesinde](../profiling/media/energyprof_summary.png "ENERGYPROF_Summary")  
  
 Ekranın enerji giderleri üzerinde daha az denetiminiz vardır. Çoğu ekranlar açık renkleri görüntülemek için koyu renklere göre daha fazla enerji harcar ve dolayısıyla koyu renk arka plan kullanmak giderleri azaltmanın bir yoludur.  
  
## <a name="other-resources"></a>Diğer kaynaklar  
  
-   **Bağlantı durumu ve maliyet Yönetimi** bölümlerinde [C# / VB/C++ ve XAML](http://msdn.microsoft.com/en-us/0ee0b706-8432-4d49-9801-306ed90764e1) ve [JavaScript ve HTML](http://msdn.microsoft.com/en-us/372afa6a-1c7c-4657-967d-03a77cd8e933) Windows geliştirme Merkezi'nde sağlayan Windows API'leri açıklama Uygulamanızı ağ trafiği maliyetini en aza indirmek için kullanabileceğiniz ağ bağlantı bilgileri.  
  
     UWP uygulamaları için Visual Studio simulator, ağ bilgi API'lerinin veri bağlantısı özelliklerinin benzetimini yapmak sağlar. Bkz: [simulator'da çalıştırmak UWP uygulamaları](../debugger/run-windows-store-apps-in-the-simulator.md)  
  
-   **JavaScript işlev zamanlaması** ve **CPU kullanımı** araçları, yetersiz işlevlerin neden olduğu CPU yükünü azaltmanıza yardımcı olabilir. Bkz: [analiz CPU kullanımı](../profiling/analyze-cpu-usage-in-a-windows-universal-app.md).

## <a name="see-also"></a>Ayrıca bkz.
 [Visual Studio profil oluşturma](../profiling/index.md)  
 [Araçlar profil oluşturmaya ilk bakış](../profiling/profiling-feature-tour.md)