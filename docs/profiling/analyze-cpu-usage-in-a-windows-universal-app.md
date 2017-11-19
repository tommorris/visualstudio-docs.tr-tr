---
title: "Bir evrensel Windows uygulamasında CPU kullanımı analiz | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c122b08e-e3bf-43e6-bd6c-e776e178fd9a
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 59669f0430760bb98dd0cb63e05f433cb3a1fe54
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="analyze-cpu-usage-in-a-universal-windows-app-uwp"></a>Evrensel Windows uygulaması (UWP) CPU kullanımının Çözümle
![Windows ve Windows Phone için geçerlidir](../debugger/media/windows_and_phone_content.png "windows_and_phone_content")  
  
 Uygulamanızda performans sorunları araştırmak gerektiğinde başlatmak için uygun bir yerdir nasıl CPU kullandığı anlamaktır. **CPU kullanımı** aracı gösterir, CPU süresi yürütülen kodu yeri harcıyorsa. Belirli senaryolara odaklanmak için CPU kullanımı ile çalıştırılabilir [uygulama zaman çizelgesi](../profiling/application-timeline.md) aracı [enerji tüketimi](../profiling/analyze-energy-use-in-store-apps.md) aracı veya tek bir tanılama oturumunda hem araçları.  
  
> [!NOTE]
>  **CPU kullanımı** aracı Windows Phone Silverlight 8.1 uygulamaları ile kullanılamaz.  
  
 Bu kılavuz, toplama ve basit bir Windows Evrensel XAML uygulama için CPU kullanımını analiz etme aracılığıyla alır.  
  
##  <a name="BKMK_Create_the_CpuUseDemo_project"></a>CpuUseDemo projesi oluşturma  
 **CpuUseDemo** toplamak ve CPU kullanımı verileri çözümlemek nasıl yapılacağını göstermek üzere oluşturulmuş bir uygulamadır. Düğmeleri işlevi için birden fazla çağrı en büyük değer seçer yöntemini çağırarak bir sayı oluşturur. Çağrılan işlev rastgele değerleri çok fazla sayıda oluşturur ve sonra sonuncu döndürür. Verileri bir metin kutusunda görüntülenir.  
  
1.  Adlı yeni bir C# Windows Evrensel uygulama projesi oluşturma **CpuUseDemo** kullanarak **BlankApp** şablonu.  
  
     ![CpuUseDemoProject oluşturma](../profiling/media/cpu_use_newproject.png "CPU_USE_NewProject")  
  
2.  MainPage.xaml ile Değiştir [bu kodu](#BKMK_MainPage_xaml).  
  
3.  MainPage.xaml.cs ile Değiştir [bu kodu](#BKMK_MainPage_xaml_cs).  
  
4.  Uygulamayı oluşturun ve deneyin. Uygulama, CPU kullanım verilerini analiz sık karşılaşılan bazı durumlarda göstermek basit bir işlemdir.  
  
##  <a name="BKMK_Collect_CPU_usage_data"></a>CPU kullanım verilerini toplama  
 ![Yayın derlemesi uygulamanın benzeticisinde çalıştırmak](../profiling/media/cpu_use_wt_setsimulatorandretail.png "CPU_USE_WT_SetSimulatorAndRetail")  
  
1.  Visual Studio'da dağıtım hedefini ayarlamak **Simulator** ve çözüm yapılandırması **sürüm**.  
  
    -   Uygulamayı benzetici çalıştıran uygulama ile Visual Studio IDE arasında kolayca geçiş olanak sağlar.  
  
    -   Bu uygulamayı çalışır durumda **sürüm** modu gerçek uygulamanızın performansı ile daha iyi bir görünümünü sağlar.  
  
2.  Üzerinde **hata ayıklama** menüsünde seçin **Performans Profil Oluşturucu...** .  
  
3.  Performans ve tanılama hub'ı seçin **CPU kullanımı** ve ardından **Başlat**.  
  
     ![CpuUsage Tanılama oturumu başlatmak](../profiling/media/cpu_use_wt_perfdiaghub.png "CPU_USE_WT_PerfDiagHub")  
  
4.  Uygulama başlatıldığında tıklatın **almak en çok sayı**. Çıktı görüntülendikten sonra ikinci bir hakkında bekleyin ve ardından **en büyük sayı zaman uyumsuz Al**. Düğme tıklamaları yapar bekleyen düğmesi yalıtmak daha kolay tıklatın Tanılama raporu yordamları.  
  
5.  İkinci çıkış satır göründükten sonra seçin **koleksiyonunu Durdur** performans ve tanılama hub'ında.  
  
 ![CpuUsage veri toplamayı durdurmayı](../profiling/media/cpu_use_wt_stopcollection.png "CPU_USE_WT_StopCollection")  
  
 CPU kullanımı aracı verileri analiz eder ve rapor görüntüler.  
  
 ![CpuUsage rapor](../profiling/media/cpu_use_wt_report.png "CPU_USE_WT_Report")  
  
##  <a name="BKMK_Analyze_the_CPU_Usage_report"></a>CPU kullanım raporu Çözümle  
  
###  <a name="BKMK_CPU_utilization_timeline_graph"></a>CPU kullanım zaman çizelgesi grafiği  
 ![CpuUtilization &#40; % &#41; Zaman Çizelgesi grafik](../profiling/media/cpu_use_wt_timelinegraph.png "CPU_USE_WT_TimelineGraph")  
  
 CPU kullanım grafiği cihazda uygulama CPU etkinlik tüm işlemci çekirdeği gelen tüm CPU süresi bir yüzdesi olarak gösterir. Bu rapor veri çift çekirdekli makine üzerinde toplanmıştır. İki büyük depoları iki düğme tıklama CPU etkinliği temsil eder. `GetMaxNumberButton_Click`Böylece yöntemin grafik yüksekliği hiçbir zaman % 50 aştığını mantıklıdır tek bir çekirdek üzerinde eşzamanlı olarak gerçekleştirir. `GetMaxNumberAsycButton_Click`Bunu yeniden sağa, görünüyor şekilde kendi depo iki çekirdek CPU kaynaklarının tümü yararlanarak daha yakından alır zaman uyumsuz olarak iki çekirdek arasında çalışır, böylece.  
  
####  <a name="BKMK_Select_timeline_segments_to_view_details"></a>Ayrıntılarını görüntülemek için zaman çizelgesi kesimleri seçin  
 Seçim çubuklarını kullanın **Tanılama oturumu** GetMaxNumberButton_Click verileri odaklanmak için zaman çizelgesi:  
  
 ![GetMaxNumberButton &#95; Seçili tıklatın](../profiling/media/cpu_use_wt_getmaxnumberreport.png "CPU_USE_WT_GetMaxNumberReport")  
  
 **Tanılama oturumu** zaman çizelgesi şimdi (biraz 2 saniyeden fazla Bu raporda) seçili kesimdeki harcanan süreyi görüntüler ve seçim çalıştıran bu yöntem çağrısı ağacına filtreler.  
  
 Şimdi seçin `GetMaxNumberAsyncButton_Click` kesimi.  
  
 ![GetMaxNumberAsyncButton &#95; Rapor seçimi tıklatın](../profiling/media/cpu_use_wt_getmaxnumberasync_selected.png "CPU_USE_WT_GetMaxNumberAsync_Selected")  
  
 Bu yöntem hakkında ikinci tamamlar daha hızlı bir şekilde `GetMaxNumberButton_Click`, ancak çağrı ağacı girişleri anlamını kadar belirgin.  
  
###  <a name="BKMK_The_CPU_Usage_call_tree"></a>CPU kullanımı çağrı ağacı  
 Çağrı ağacı bilgileri anlama başlamak için yeniden `GetMaxNumberButton_Click` segmentlere ayırmak ve çağrı ağacı ayrıntılarını inceleyin.  
  
####  <a name="BKMK_Call_tree_structure"></a>Çağrı ağaç yapısı  
 ![GetMaxNumberButton &#95; Çağrı ağacı tıklatın](../profiling/media/cpu_use_wt_getmaxnumbercalltree_annotated.png "CPU_USE_WT_GetMaxNumberCallTree_annotated")  
  
|||  
|-|-|  
|![1. adım](../profiling/media/procguid_1.png "ProcGuid_1")|CPU kullanımı çağrısı ağaçları en üst düzey düğümünde sahte bir düğümdür|  
|![2. adım](../profiling/media/procguid_2.png "ProcGuid_2")|Çoğu uygulamalardaki zaman **Göster harici kod** seçeneği devre dışıdır, ikinci düzey düğüm bir **[dış kodu]** başlayan ve uygulama durdurur sistem ve framework kodu içeren düğümü çizer kullanıcı Arabirimi iş parçacığı zamanlama denetler ve diğer alt düzey uygulama hizmetleri sağlar.|  
|![3. adım](../profiling/media/procguid_3.png "ProcGuid_3")|Düğümün alt öğelerinin ikinci düzey adlı ya da framework kod ve ikinci düzey sistem oluşturduğunuz zaman uyumsuz yordamları ve kullanıcı kodu yöntemler ' dir.|  
|![Adım 4](../profiling/media/procguid_4.png "ProcGuid_4")|Bir yöntemin alt düğümleri yalnızca üst yöntemi çağrıları verilerini içerir. Zaman **Göster harici kod** olan devre dışı, uygulama yöntemlerini de içerebilir bir **[dış kodu]** düğümü.|  
  
####  <a name="BKMK_External_Code"></a>Harici kod  
 Dış kodu yazdığınız kodu tarafından gerçekleştirilen sistem ve framework bileşenleri işlevlerde oluşur. Dış kodu başlatın ve uygulamayı durdurun, UI çizin, iş parçacığı oluşturma denetleyen ve diğer alt düzey uygulama hizmetleri sağlamak işlevler içerir. Çoğu durumda, dış kodda ilgilenen olmayacak ve bu nedenle CPU kullanımı çağırın ağaç toplar kullanıcı yönteminin dış işlevler birine **[dış kodu]** düğümü.  
  
 Harici kod çağrısı yollarını görüntülemek istediğinizde, belirleyin **Göster harici kod** gelen **filtre görünümü** listeleyin ve ardından **Uygula**.  
  
 ![Filtre görünümü seçin, ardından Göster harici kod](../profiling/media/cpu_use_wt_filterview.png "CPU_USE_WT_FilterView")  
  
 İşlev adı sütunun genişliği tüm ancak bilgisayar monitörü en büyük görüntü genişliğini aşabilir böylece birçok harici kod çağrısı zincirleri derine yerleştirilir unutmayın. Bu gerçekleştiğinde, işlev adları olarak gösterilen **[...]** :  
  
 ![Çağrı ağacı dış kodda iç içe geçmiş](../profiling/media/cpu_use_wt_showexternalcodetoowide.png "CPU_USE_WT_ShowExternalCodeTooWide")  
  
 Aradığınız bir düğüm bulmak için arama kutusunu kullanın, sonra verileri görünüme getirmek için yatay kaydırma çubuğu kullanın:  
  
 ![İç içe geçmiş harici kod arama](../profiling/media/cpu_use_wt_showexternalcodetoowide_found.png "CPU_USE_WT_ShowExternalCodeTooWide_Found")  
  
###  <a name="BKMK_Call_tree_data_columns"></a>Çağrı ağacı veri sütunları  
  
|||  
|-|-|  
|**Toplam CPU (%)**|![Toplam % veri eşitlik](../profiling/media/cpu_use_wt_totalpercentequation.png "CPU_USE_WT_TotalPercentEquation")<br /><br /> Uygulamanın CPU etkinlik işlev ve işlev tarafından çağrılan işlev çağrıları tarafından kullanılan seçili zaman aralığı içinde yüzdesi. Bu farklı olduğuna dikkat edin **CPU kullanımı** bir zaman aralığı için toplam kullanılabilir CPU kapasitesini uygulamada yapılan toplam etkinliği karşılaştırır zaman çizelgesi grafik.|  
|**Kendi kendini CPU (%)**|![Kendi kendine % eşitlik](../profiling/media/cpu_use_wt_selflpercentequation.png "CPU_USE_WT_SelflPercentEquation")<br /><br /> İşlev çağrıları tarafından kullanılan seçili zaman aralığı uygulamanın CPU etkinliğinde yüzdesi, işlevleri etkinliğini hariç işlev tarafından çağrılır.|  
|**Toplam CPU (ms)**|Seçili zaman aralığı içinde işlev ve işlev tarafından adı veriliyordu işlev çağrılarında milisaniye sayısını harcanan.|  
|**Kendi kendini CPU (ms)**|Seçili zaman aralığı içinde işlev ve işlev tarafından adı veriliyordu işlev çağrılarında milisaniye sayısını harcanan.|  
|**Modülü**|İşlev veya işlevleri [dış kodu] düğümünde içeren modüllerin sayısını içeren modülü adı.|  
  
###  <a name="BKMK_Asynchronous_functions_in_the_CPU_Usage_call_tree"></a>CPU kullanımı zaman uyumsuz işlevlerde çağrı ağacı  
 Derleyici zaman uyumsuz bir yöntem karşılaştığında yöntemin yürütme denetlemek için gizli bir sınıf oluşturur. Kavramsal olarak, özgün metodun işlemlerini zaman uyumsuz olarak çağırma derleyicinin ürettiği işlevleri ve geri aramalar, Zamanlayıcı ve bunları doğru gerekli yineleyiciler listesini içeren bir durum makinesinin sınıftır. Özgün yöntemi üst yöntemi tarafından çağrıldığında, çalışma zamanı üst yürütme bağlamından yöntemi kaldırır ve gizli sınıfı yöntemlerinin uygulamanın yürütme denetlemek sistem ve framework kodu bağlamında çalıştırılır. Zaman uyumsuz yöntemleri genellikle, ancak her zaman, bir veya daha fazla farklı iş parçacıklarında yürütülür. Bu kod CPU kullanımı çağrısı ağacında alt olarak gösterilen **[dış kodu]** hemen üst Ağaç düğümünün altında düğüm.  
  
 Bu örneğimizde görmek için yeniden seçin `GetMaxNumberAsyncButton_Click` zaman çizelgesi segmenti.  
  
 ![GetMaxNumberAsyncButton &#95; Rapor seçimi tıklatın](../profiling/media/cpu_use_wt_getmaxnumberasync_selected.png "CPU_USE_WT_GetMaxNumberAsync_Selected")  
  
 İlk iki düğüm altında **[dış kodu]** durumu makine sınıfının derleyicinin ürettiği yöntemleridir. Üçüncü özgün yöntem çağrısı var. Oluşturulan yöntemleri genişletme neler olduğunu gösterir.  
  
 ![Genişletilmiş GetMaxNumberAsyncButton &#95; Çağrı ağacı tıklatın](../profiling/media/cpu_use_wt_getmaxnumberasync_expandedcalltree.png "CPU_USE_WT_GetMaxNumberAsync_ExpandedCallTree")  
  
-   `MainPage::GetMaxNumberAsyncButton_Click`çok az yapar; görev değerlerinin bir listesini yönetir, sonuçları maksimum hesaplar ve çıktısını görüntüler.  
  
-   `MainPage+<GetMaxNumberAsyncButton_Click>d__3::MoveNext`zamanlama ve çağrısı sarmalamak 48 görevleri başlatmak için gerekli etkinliğini gösterir `GetNumberAsync`.  
  
-   `MainPage::<GetNumberAsync>b__b`Çağrı görevleri etkinliğini gösterir `GetNumber`.  
  
##  <a name="BKMK_Next_steps"></a>Sonraki adımlar  
 CpuUseDemo uygulama uygulamalar üstün en değildir, ancak zaman uyumsuz işlemi ve diğer araçları performans ve tanılama hub'ında deneme kullanarak kendi yardımcı programı genişletebilirsiniz.  
  
-   Unutmayın `MainPage::<GetNumberAsync>b__b` harcadığı [dış kodu] GetNumber yöntemini yürütmenin mu daha uzun. Bu süre çoğunu zaman uyumsuz işlemleri yükü var. Görevlerin sayısını artırmayı deneyin (kümesinde `NUM_TASKS` MainPage.xaml.cs, sabit) ve yinelemelerini sayısının azaltılması `GetNumber` (değiştirme `MIN_ITERATIONS` değeri). Koleksiyon senaryo çalıştırmak ve CPU etkinliğini karşılaştırmak `MainPage::<GetNumberAsync>b__b`, özgün CPU kullanımı tanılama oturumunda. Deneyin görevleri azaltarak ve yinelemeleri artırma.  
  
-   Kullanıcıları, genellikle gerçek uygulamanızın performansı ile önemli değil; Algılanan performans ve uygulama yanıt hızını hakkında bunlar dikkat edin. XAML kullanıcı Arabirimi yanıt aracı etkisi yanıtlama algılanan kullanıcı Arabirimi iş parçacığı etkinliği ayrıntılarını gösterir.  
  
     Tanılama ve performans hub'ı yeni bir oturum oluşturun ve XAML UI esnek aracı ve CPU kullanımı aracı ekleyin. Koleksiyon senaryosu çalıştırabilirsiniz. Bu okuduğunuz varsa şu ana kadar rapor büyük olasılıkla, size zaten çıkışı, ancak farklılıkları dahil edilir henüz herhangi bir şey bildirmez **kullanıcı Arabirimi iş parçacığı kullanımı** iki yöntem için zaman çizelgesi grafik çarpıcı. Karmaşık, gerçek uygulamalarda araçları birleşimi çok yararlı olabilir.  
  
##  <a name="BKMK_MainPage_xaml"></a>MainPage.xaml  
  
```xaml  
<Page  
    x:Class="CpuUseDemo.MainPage"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:local="using:CpuUseDemo"  
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    mc:Ignorable="d">  
  
    <Page.Resources>  
        <Style TargetType="TextBox">  
            <Setter Property="FontFamily"  Value="Lucida Console" />  
        </Style>  
    </Page.Resources>  
    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">  
        <Grid.RowDefinitions>  
            <RowDefinition Height="Auto" />  
            <RowDefinition Height="*" />  
        </Grid.RowDefinitions>  
        <StackPanel Grid.Row="0" Orientation="Horizontal"  Margin="0,40,0,0">  
            <Button Name="GetMaxNumberButton" Click="GetMaxNumberButton_Click"  Content="Get Max Number" />  
            <Button Name="GetMaxNumberAsyncButton" Click="GetMaxNumberAsyncButton_Click"  Content="Get Max Number Async" />  
        </StackPanel>  
        <StackPanel Grid.Row="1">  
            <TextBox Name="TextBox1" AcceptsReturn="True" />  
        </StackPanel>  
    </Grid>  
  
</Page>  
  
```  
  
##  <a name="BKMK_MainPage_xaml_cs"></a>MainPage.xaml.cs  
  
```CSharp  
using System;  
using System.Collections.Generic;  
using System.IO;  
using System.Linq;  
using System.Runtime.InteropServices.WindowsRuntime;  
using Windows.Foundation;  
using Windows.Foundation.Collections;  
using Windows.UI.Xaml;  
using Windows.UI.Xaml.Controls;  
using Windows.UI.Xaml.Controls.Primitives;  
using Windows.UI.Xaml.Data;  
using Windows.UI.Xaml.Input;  
using Windows.UI.Xaml.Media;  
using Windows.UI.Xaml.Navigation;  
using Windows.Foundation.Diagnostics;  
using System.Threading;  
using System.Threading.Tasks;  
using System.Collections.Concurrent;  
  
// The Blank Page item template is documented at http://go.microsoft.com/fwlink/?LinkId=234238  
  
namespace CpuUseDemo  
{  
    /// <summary>  
    /// An empty page that can be used on its own or navigated to within a Frame.  
    /// </summary>  
    public sealed partial class MainPage : Page  
    {  
        public MainPage()  
        {  
            this.InitializeComponent();  
        }  
  
        const int NUM_TASKS = 48;  
        const int MIN_ITERATIONS = int.MaxValue / 1000;  
        const int MAX_ITERATIONS = MIN_ITERATIONS + 10000;  
  
        long m_totalIterations = 0;  
        readonly object m_totalItersLock = new object();  
  
        private void GetMaxNumberButton_Click(object sender, RoutedEventArgs e)  
        {  
            GetMaxNumberAsyncButton.IsEnabled = false;  
            lock (m_totalItersLock)  
            {  
                m_totalIterations = 0;  
            }  
            List<int> tasks = new List<int>();  
            for (var i = 0; i < NUM_TASKS; i++)  
            {  
                var result = 0;  
                result = GetNumber();  
                tasks.Add(result);  
            }  
            var max = tasks.Max();  
            var s = GetOutputString("GetMaxNumberButton_Click", NUM_TASKS, max, m_totalIterations);  
            TextBox1.Text += s;  
            GetMaxNumberAsyncButton.IsEnabled = true;  
        }  
  
        private async void GetMaxNumberAsyncButton_Click(object sender, RoutedEventArgs e)  
        {  
            GetMaxNumberButton.IsEnabled = false;  
            GetMaxNumberAsyncButton.IsEnabled = false;  
            lock (m_totalItersLock)  
            {  
                m_totalIterations = 0;  
            }  
            var tasks = new ConcurrentBag<Task<int>>();  
            for (var i = 0; i < NUM_TASKS; i++)  
            {  
                tasks.Add(GetNumberAsync());  
            }  
            await Task.WhenAll(tasks.ToArray());  
            var max = 0;  
            foreach (var task in tasks)  
            {  
                max = Math.Max(max, task.Result);  
            }  
            var func = "GetMaxNumberAsyncButton_Click";  
            var outputText = GetOutputString(func, NUM_TASKS, max, m_totalIterations);  
            TextBox1.Text += outputText;  
            this.GetMaxNumberButton.IsEnabled = true;  
            GetMaxNumberAsyncButton.IsEnabled = true;  
        }  
  
        private int GetNumber()  
        {  
            var rand = new Random();  
            var iters = rand.Next(MIN_ITERATIONS, MAX_ITERATIONS);  
            var result = 0;  
            lock (m_totalItersLock)  
            {  
                m_totalIterations += iters;  
            }  
            // we're just spinning here  
            // and using Random to frustrate compiler optimizations  
            for (var i = 0; i < iters; i++)  
            {  
                result = rand.Next();  
            }  
            return result;  
        }  
  
        private Task<int> GetNumberAsync()  
        {  
            return Task<int>.Run(() =>  
            {  
                return GetNumber();  
            });  
        }  
  
        string GetOutputString(string func, int cycles, int max, long totalIters)  
        {  
            var fmt = "{0,-35}Tasks:{1,3}    Maximum:{2, 12}    Iterations:{3,12}\n";  
            return String.Format(fmt, func, cycles, max, totalIters);  
        }  
  
    }  
}  
  
```
## <a name="see-also"></a>Ayrıca Bkz.
 [Visual Studio'da profil oluşturma](../profiling/index.md)  
 [Özellik turu profil oluşturma](../profiling/profiling-feature-tour.md)