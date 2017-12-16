---
title: "WPF giriş | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8d7cf43-d1f2-4f3d-adb0-4f3a6428edc0
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- csharp
- vb
ms.openlocfilehash: 5dacd44d72e5be7a898ba90c074dedf4b2f2bb4b
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/12/2017
---
# <a name="introduction-to-wpf"></a>WPF'ye Giriş
Windows Presentation Foundation (WPF) masaüstü istemcisi şaşırtıcı kullanıcı deneyimleri ile Windows uygulamaları oluşturmanızı sağlar.  
  
 ![Contoso sağlık UI örnek](../designers/media/wpfintrofigure24.png "WPFIntroFigure24")  
  
 WPF çekirdek modern grafik donanım yararlanmak için yerleşik bir çözüm bağımsız ve vektör tabanlı işleme altyapısıdır. WPF çekirdek Genişletilebilir uygulama biçimlendirme dili (XAML), denetimleri, veri bağlama, düzeni, 2B ve 3B grafikler, animasyon, stiller, şablonları, belgeler, ortam, metin, içeren uygulama geliştirme özellikleri kapsamlı bir kümesini ile genişletir ve Tipografi. .NET Framework sınıf kitaplığı diğer öğeleri dahil uygulamaları oluşturabilmeniz WPF .NET Framework'teki dahil edilir.  
  
 Bu genel bakış yeni gelenlere yöneliktir ve anahtar özellikleri ve WPF kavramlarını kapsar.  
  
##  <a name="Programming_with_WPF"></a>WPF ile programlama  
 WPF mevcut bir alt kümesini çoğunlukla bulunan .NET Framework türleri olarak <xref:System.Windows> ad alanı. Daha önce uygulamaları .NET Framework ile ASP.NET ve Windows Forms gibi yönetilen teknolojileri kullanarak oluşturduysanız, programlama deneyimine temel WPF bilgi sahibi olmanız gerekir; sınıf örneği, özellikleri, yöntemleri çağırabilir ve tüm kullanarak, sık kullanılan .NET dil C# veya Visual Basic gibi programlama tanıtıcı olayları ayarlayın.  
  
 WPF özellikleri ve olayları geliştiren ek programlama yapılarını içerir: [bağımlılık özellikleri](/dotnet/framework/wpf/advanced/dependency-properties-overview) ve [yönlendirilmiş olaylar](/dotnet/framework/wpf/advanced/routed-events-overview).  
  
##  <a name="Markup_And_Codebehind"></a>Biçimlendirme ve arka plan kodu  
 WPF her ikisini de kullanarak bir uygulama geliştirmenize olanak tanır *biçimlendirme* ve *arka plan kodu*, ASP.NET geliştiricilerinin aşina bir deneyim. XAML biçimlendirme genellikle davranışını uygulamak için yönetilen programlama dillerini (arka plan kod) kullanırken bir uygulamanın görünümünü uygulamak için kullanın. Bu ayrım görünümünü ve davranışını aşağıdaki faydaları vardır:  
  
-   Görünüm özgü biçimlendirme davranışı özgü kodu ile sıkı bir şekilde eşleşmediğinden dolayı geliştirme ve Bakım maliyetleri azaltılır.  
  
-   Geliştirme daha verimli çünkü tasarımcıları aynı anda uygulamanın davranışını uygulayan geliştiriciler ile bir uygulamanın görünümünü uygulayabilirsiniz.  
  
-   [Genelleştirme ve Yerelleştirme](/dotnet/framework/wpf/advanced/wpf-globalization-and-localization-overview) büyük uygulamalar WPF için basitleştirilmiştir.  
  
 WPF biçimlendirme ve arka plan kodu kısa bir giriş verilmiştir.  
  
### <a name="markup"></a>Biçimlendirme  
 XAML bir uygulamanın görünümünü bildirimli olarak uygulamak için kullanılan bir XML tabanlı biçimlendirme dilidir. Genellikle, windows, iletişim kutuları, sayfalar ve kullanıcı denetimleri oluşturmak için ve denetimler, şekiller ve grafikler doldurmak için kullanılır.  
  
 Aşağıdaki örnek, tek bir öğe içeren bir pencere görünümünü uygulamak için XAML kullanır.  
  
```xaml  
<Window  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    Title="Window with Button"  
    Width="250" Height="100">  
  
  <!-- Add button to window -->  
  <Button Name="button">Click Me!</Button>  
  
</Window>  
```  
  
 Özellikle, bu XAML bir pencere ve düğme kullanarak tanımlar `Window` ve `Button` öğeleri, sırasıyla. Her öğe gibi özniteliklerle yapılandırılmış `Window` öğenin `Title` özniteliği penceresinin başlık çubuğu metni belirtin. Çalışma zamanında WPF öğeleri ve WPF sınıfların örnekleri biçimlendirmede tanımlanan öznitelikleri dönüştürür. Örneğin, `Window` öğesi örneğine dönüştürülür <xref:System.Windows.Window> sınıfının <xref:System.Windows.Window.Title%2A> özelliktir değerini `Title` özniteliği.  
  
 Aşağıdaki şekilde, önceki örnekte XAML tarafından tanımlanan kullanıcı arabirimini (UI) gösterir.  
  
 ![Bir düğmeyi içeren bir pencere](../designers/media/wpfintrofigure10.png "WPFIntroFigure10")  
  
 XAML XML tabanlı olduğundan, kendisiyle oluşturan kullanıcı Arabirimi olarak bilinen iç içe öğelerin bir hiyerarşideki derlenip bir [öğe ağacı](/dotnet/framework/wpf/advanced/trees-in-wpf). Öğe ağacı oluşturmak ve Uı'lar yönetmek için mantıksal ve sezgisel bir yol sağlar.  
  
### <a name="code-behind"></a>Arka plan kodu  
 Ana uygulamanın (örneğin, bir menü, araç çubuğundaki ya da düğmesini) olayları işleme dahil olmak üzere kullanıcı etkileşimleri yanıtlaması işlevselliği uygulamak için bir davranıştır ve iş mantığı ve verileri erişim mantığı yanıtta çağırma. WPF içinde bu davranış genellikle biçimlendirme ile ilişkili olan kod uygulanır. Bu kod türü, arka plan kodu bilinir. Aşağıdaki örnek, önceki örnekte ve arka plan kodu güncelleştirilmiş biçimlendirmeyi gösterir.  
  
```xaml  
<Window  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    x:Class="SDKSample.AWindow"  
    Title="Window with Button"  
    Width="250" Height="100">  
  
  <!-- Add button to window -->  
  <Button Name="button" Click="button_Click">Click Me!</Button>  
  
</Window>  
```  
  
```csharp  
using System.Windows; // Window, RoutedEventArgs, MessageBox   
  
namespace SDKSample  
{  
    public partial class AWindow : Window  
    {  
        public AWindow()  
        {  
            // InitializeComponent call is required to merge the UI   
            // that is defined in markup with this class, including    
            // setting properties and registering event handlers  
            InitializeComponent();  
        }  
  
        void button_Click(object sender, RoutedEventArgs e)  
        {  
            // Show message box when button is clicked  
            MessageBox.Show("Hello, Windows Presentation Foundation!");  
        }  
    }  
}  
```  
  
```vb  
Namespace SDKSample  
  
    Partial Public Class AWindow  
        Inherits System.Windows.Window  
  
        Public Sub New()  
  
            ' InitializeComponent call is required to merge the UI   
            ' that is defined in markup with this class, including    
            ' setting properties and registering event handlers  
            InitializeComponent()  
  
        End Sub   
  
        Private Sub button_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)  
  
            ' Show message box when button is clicked  
            MessageBox.Show("Hello, Windows Presentation Foundation!")  
  
        End Sub   
  
    End Class   
  
End Namespace  
  
```  
  
 Bu örnekte, arka plan kodu türeyen bir sınıf uygulayan <xref:System.Windows.Window> sınıfı. `x:Class` Özniteliği biçimlendirmeyi arka plandaki kod sınıfı ile ilişkilendirmek için kullanılır. `InitializeComponent`arka plandaki kod sınıfı ile biçimlendirmede tanımlanan kullanıcı arabirimini birleştirmek için arka plan kod sınıfının oluşturucusundan çağrılır. (`InitializeComponent` uygulamanız, el ile uygulamanız gerekmez neden olan yapılandırıldığında sizin için oluşturulur.) Birleşimi `x:Class` ve `InitializeComponent` oluşturulduğu zaman, uygulamanız doğru bir şekilde başlatıldığından emin olun. Arka plandaki kod sınıfı ayrıca düğmenin için bir olay işleyicisi uygulayan <xref:System.Windows.Controls.Primitives.ButtonBase.Click> olay. Düğmesine tıklandığında, olay işleyicisi bir ileti kutusu çağırarak gösterir <xref:System.Windows.MessageBox.Show%2A?displayProperty=fullName> yöntemi.  
  
 Düğme tıklatıldığında sonucu aşağıdaki şekilde gösterilmiştir.  
  
 ![Bir MessageBox](../designers/media/wpfintrofigure25.png "WPFIntroFigure25")  
  
##  <a name="Controls"></a>Denetimleri  
 Uygulama modeli tarafından sunulan kullanıcı deneyimleri oluşturulan denetimleridir. WPF, "Denetim" bir aralığı veya bir sayfa içinde barındırılan WPF sınıfları kategorisi için geçerli bir genel bir terimdir, bir kullanıcı arabirimine sahip ve bazı davranışı uygulamak.  
  
 Daha fazla bilgi için bkz: [denetimleri](/dotnet/framework/wpf/controls/index).  
  
### <a name="wpf-controls-by-function"></a>WPF denetimleri işlevi  
 Yerleşik WPF denetimleri burada listelenir.  
  
-   **Düğmeleri**: <xref:System.Windows.Controls.Button> ve <xref:System.Windows.Controls.Primitives.RepeatButton>.  
  
-   **Veri görüntüleme**: <xref:System.Windows.Controls.DataGrid>, <xref:System.Windows.Controls.ListView>, ve <xref:System.Windows.Controls.TreeView>.  
  
-   **Tarih görüntüleme ve seçim**: <xref:System.Windows.Controls.Calendar> ve <xref:System.Windows.Controls.DatePicker>.  
  
-   **İletişim kutuları**: <xref:Microsoft.Win32.OpenFileDialog>, <xref:System.Windows.Controls.PrintDialog>, ve <xref:Microsoft.Win32.SaveFileDialog>.  
  
-   **Dijital Mürekkep**: <xref:System.Windows.Controls.InkCanvas> ve <xref:System.Windows.Controls.InkPresenter>.  
  
-   **Belgeleri**: <xref:System.Windows.Controls.DocumentViewer>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentScrollViewer>, ve <xref:System.Windows.Controls.StickyNoteControl>.  
  
-   **Giriş**: <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, ve <xref:System.Windows.Controls.PasswordBox>.  
  
-   **Düzen**: <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Primitives.BulletDecorator>, <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Expander>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridSplitter>, <xref:System.Windows.Controls.GroupBox>, <xref:System.Windows.Controls.Panel>, <xref:System.Windows.Controls.Primitives.ResizeGrip>, <xref:System.Windows.Controls.Separator>,  <xref:System.Windows.Controls.Primitives.ScrollBar>, <xref:System.Windows.Controls.ScrollViewer>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.Primitives.Thumb>, <xref:System.Windows.Controls.Viewbox>, <xref:System.Windows.Controls.VirtualizingStackPanel>, <xref:System.Windows.Window>, ve <xref:System.Windows.Controls.WrapPanel>.  
  
-   **Medya**: <xref:System.Windows.Controls.Image>, <xref:System.Windows.Controls.MediaElement>, ve <xref:System.Windows.Controls.SoundPlayerAction>.  
  
-   **Menüleri**: <xref:System.Windows.Controls.ContextMenu>, <xref:System.Windows.Controls.Menu>, ve <xref:System.Windows.Controls.ToolBar>.  
  
-   **Gezinti**: <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, ve <xref:System.Windows.Controls.TabControl>.  
  
-   **Seçim**: <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.RadioButton>, ve <xref:System.Windows.Controls.Slider>.  
  
-   **Kullanıcı bilgilerini**: <xref:System.Windows.Controls.AccessText>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.ProgressBar>, <xref:System.Windows.Controls.Primitives.StatusBar>, <xref:System.Windows.Controls.TextBlock>, ve <xref:System.Windows.Controls.ToolTip>.  
  
##  <a name="Input_And_Commanding"></a>Giriş ve komut verme  
 Denetimleri çoğunlukla algılar ve kullanıcı girişine yanıt verir. [WPF giriş sistem](/dotnet/framework/wpf/advanced/input-overview) metin girişi, odak yönetimi ve fare konumlandırmasını desteklemek için doğrudan ve yönlendirilmiş olayların kullanır.  
  
 Uygulamalar genellikle karmaşık giriş gereksinimlerine sahiptir. WPF sağlayan bir [komutu sistem](/dotnet/framework/wpf/advanced/commanding-overview) kullanıcı giriş eylemlerini bu eylemleri yanıt koddan ayırır.  
  
##  <a name="Layout"></a>Düzen  
 Bir kullanıcı arabirimi oluşturduğunuzda, konum ve boyut bir düzen oluşturmak için denetimlerinizin düzenleyin. Pencere boyutu değişikliklere uyum ve ayarlarını görüntülemek için herhangi bir düzeni, anahtar gerekli değildir. Bu durumlarda bir düzen uyarlamak için kod yazmak için zorlama yerine WPF birinci sınıf, Genişletilebilir düzen sistemi sizin için sağlar.  
  
 Düzen sisteminin dönüm hangi penceresi değişen uyum ve koşullar görüntüleme olanağı artırır göreli konumlandırma, ' dir. Ayrıca, düzen sistemi düzenini belirlemek için denetimler arasındaki anlaşma yönetir. Anlaşma iki adımlı bir işlemdir: ilk olarak, bir denetim hangi konum ve boyut gerektiriyor; üst bildirir İkinci olarak, üst denetim sağlayabilirsiniz hangi alanı söyler.  
  
 Düzen sistemi temel WPF sınıfları aracılığıyla alt denetimlere açıktır. Yığınlama ve takma kılavuzları gibi ortak düzenler için çeşitli düzen denetimleri WPF içerir:  
  
-   <xref:System.Windows.Controls.Canvas>: Alt denetimler kendi düzenini sağlar.  
  
-   <xref:System.Windows.Controls.DockPanel>: Alt denetimler panel kenarlarına hizalanır.  
  
-   <xref:System.Windows.Controls.Grid>: Alt denetimler, satırları ve sütunları tarafından konumlandırılır.  
  
-   <xref:System.Windows.Controls.StackPanel>: Alt denetimler dikey veya yatay olarak Yığılmış.  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>: Alt denetimler sanallaştırılır ve yatay veya dikey olarak yönlendirilmiş tek bir satırda düzenlenir.  
  
-   <xref:System.Windows.Controls.WrapPanel>: Alt denetimler soldan sağa düzeninde konumlandırılır ve geçerli satır üzerinde alan izin verdiğinden daha fazla denetim olduğunda sonraki satıra kaydırılmış.  
  
 Aşağıdaki örnek kullanan bir <xref:System.Windows.Controls.DockPanel> birkaç düzenlemek için <xref:System.Windows.Controls.TextBox> kontrol eder.  
  
 [!code-xaml[IntroToWPFSnippets#LayoutMARKUP](../designers/codesnippet/Xaml/introduction-to-wpf_1.xaml)]  
  
 <xref:System.Windows.Controls.DockPanel> Alt verir <xref:System.Windows.Controls.TextBox> yerleştirmek üzere nasıl bildirmek için kontrol eder. Bunu yapmak için <xref:System.Windows.Controls.DockPanel> uygulayan bir `Dock` her birinin yerleştirme stilini belirlemek için izin vermek için alt denetimleri sunulan özelliği eklenmiş.  
  
> [!NOTE]
>  Alt denetimler tarafından kullanılacak bir WPF yapısı için bir üst denetimi tarafından uygulanan bir özellik olarak adlandırılan bir [özelliği eklenmiş](/dotnet/framework/wpf/advanced/attached-properties-overview).  
  
 Aşağıdaki şekilde, önceki örnekte XAML biçimlendirme sonucunu gösterir.  
  
 ![DockPanel sayfası](../designers/media/wpfintrofigure11.png "WPFIntroFigure11")  
  
##  <a name="Data_Binding"></a>Veri bağlama  
 Çoğu uygulamayı kullanıcılara görüntülemek ve veri düzenlemesi bulunmasını sağlamak için oluşturulur. WPF uygulamaları için depolama ve veri erişim iş zaten için SQL Server ve ADO .NET gibi teknolojileri tarafından sağlanır. Veri erişilen ve bir uygulamanın yönetilen nesneleri içine yüklendikten sonra WPF uygulamaları için asıl zor iş başlar. Esas olarak, bu iki şeyi içerir:  
  
1.  Verilerin yönetilen nesnelerden verileri nerede görüntülenir ve düzenlenebilir denetimlere kopyalanıyor.  
  
2.  Denetimleri kullanarak verilerde yapılan değişiklikleri yönetilen nesnelerin kopyalandığından emin olma.  
  
 Uygulama geliştirmeyi kolaylaştırmak için WPF otomatik olarak bu adımları gerçekleştirmek için bir veri bağlama altyapısı sağlar. Veri bağlama altyapısı çekirdek birimidir <xref:System.Windows.Data.Binding> , iş denetimi (bağlama hedefi) bağlamak için bir veri nesnesine (bağlama kaynağı) sınıfı. Bu ilişki aşağıdaki şekilde gösterilmiştir.  
  
 ![Basit veri bağlama diyagramı](../designers/media/databindingmostbasic.png "DataBindingMostBasic")  
  
 Aşağıdaki örnekte nasıl bağlanacağını gösterir bir <xref:System.Windows.Controls.TextBox> özel bir örneğine `Person` nesnesi. `Person` Uygulaması, aşağıdaki kodda gösterilir.  
  
 [!code-vb[SimpleDataBindingSnippets#PersonClassCODE](../designers/codesnippet/VisualBasic/introduction-to-wpf_2.vb)]
 [!code-csharp[SimpleDataBindingSnippets#PersonClassCODE](../designers/codesnippet/CSharp/introduction-to-wpf_2.cs)]  
  
 Aşağıdaki biçimlendirmede bağlar <xref:System.Windows.Controls.TextBox> özel bir örneğine `Person` nesnesi.  

 ```xaml  
 <Window
     xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
     xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
     x:Class="SDKSample.DataBindingWindow">  

   <!-- Bind the TextBox to the data source (TextBox.Text to Person.Name) -->
   <TextBox Name="personNameTextBox" Text="{Binding Path=Name}" />  

 </Window>
 ```
  
 [!code-vb[SimpleDataBindingSnippets#DataBindingCODEBEHIND](../designers/codesnippet/VisualBasic/introduction-to-wpf_6.vb)]
 [!code-csharp[SimpleDataBindingSnippets#DataBindingCODEBEHIND](../designers/codesnippet/CSharp/introduction-to-wpf_6.cs)]  
  
 Bu örnekte, `Person` sınıf kod arkasında örneği ve veri bağlamı olarak ayarlanmış olan `DataBindingWindow`. Biçimlendirme içinde <xref:System.Windows.Controls.TextBox.Text%2A> özelliği <xref:System.Windows.Controls.TextBox> bağlı `Person.Name` özelliği (kullanarak "`{Binding ... }`" XAML sözdizimi). WPF bağlamak için bu XAML söyler <xref:System.Windows.Controls.TextBox> denetimini `Person` depolanan nesne <xref:System.Windows.FrameworkElement.DataContext%2A> penceresinin özelliği.  
  
 WPF veri bağlama altyapısı doğrulama, sıralama, filtreleme ve gruplandırma içeren ek destek sağlar. Ayrıca, veri bağlama standart WPF denetimleri tarafından görüntülenen kullanıcı arabirimi uygun değilse, bağlı veri için özel kullanıcı arabirimi oluşturmak üzere veri şablonları kullanımını destekler.  
  
 Daha fazla bilgi için bkz: [veri bağlama genel bakış](/dotnet/framework/wpf/data/data-binding-overview).  
  
##  <a name="Graphics"></a>Grafik  
 WPF kapsamlı, ölçeklenebilir ve esnek bir aşağıdaki avantajlara sahiptir grafik özellikler kümesi sunar:  
  
-   **Çözümleme ve cihaz bağımsız grafik**. 1. aygıttan bağımsız piksel temel WPF Grafik sistemi ölçüm birimidir/96 inç, gerçek bağımsız olarak ekran çözünürlüğü ve çözümleme ve cihaz bağımsız işleme için temeli sağlar. Her aygıttan bağımsız piksel üzerinde işlediği sistemin nokta / inç (dpi) ayarını eşleşecek şekilde otomatik olarak ölçeklendirir.  
  
-   **Geliştirilmiş duyarlık**. WPF koordinat sistemi tek duyarlıklı yerine çift duyarlıklı kayan nokta sayıları ile ölçülür. Dönüşümler ve saydamlık değerleri de çift duyarlıklı ifade edilir. WPF da geniş bir renk skalasını (scRGB) destekler ve girişleri farklı renk alanlarını yönetmek için tümleşik destek sağlar.  
  
-   **Gelişmiş grafikler ve animasyon desteği**. WPF animasyon planda yöneterek grafik programlamasını basitleştiren; Sahne işleme, işleme döngüler ve çift doğrusal ilişkilendirme hakkında endişelenmeye gerek yoktur. Buna ek olarak, WPF vuruş sınaması desteği ve tam alfa birleştirme desteği sağlar.  
  
-   **Donanım hızlandırma**. WPF Grafik sistemi CPU kullanımını en aza indirmek için grafik donanım yararlanır.  
  
### <a name="2-d-shapes"></a>2B şekiller  
 WPF ortak vektör çizilmiş 2B şekiller, aşağıdaki çizimde gösterilen elipsler ve dikdörtgenler gibi kitaplığını sağlar.  
  
 ![Elipsler ve dikdörtgenler](../designers/media/wpfintrofigure4.PNG "WPFIntroFigure4")  
  
 Bir ilginç şekillerin değil yalnızca görüntü için oldukları bir özelliktir; Şekilleri klavye ve fare girişini içeren denetimlerden beklediğiniz özelliklerin çoğunu uygular. Aşağıdaki örnekte gösterildiği <xref:System.Windows.UIElement.MouseUp> olayı bir <xref:System.Windows.Shapes.Ellipse> işlenen.  
  
 [!code-xaml[IntroToWPFSnippets#HandleEllipseMouseUpEventMARKUP](../designers/codesnippet/Xaml/introduction-to-wpf_7.xaml)]  
  
 [!code-vb[IntroToWPFSnippets#HandleEllipseMouseUpEventCODEBEHIND](../designers/codesnippet/VisualBasic/introduction-to-wpf_8.vb)]
 [!code-csharp[IntroToWPFSnippets#HandleEllipseMouseUpEventCODEBEHIND](../designers/codesnippet/CSharp/introduction-to-wpf_8.cs)]  
  
 Aşağıdaki şekilde önceki kod tarafından üretilen gösterilmektedir.  
  
 ![Metinle "elips &#33; tıkladığınız" penceresi ] (../designers/media/wpfintrofigure12.png "WPFIntroFigure12")  
  
 Daha fazla bilgi için bkz: [şekilleri ve WPF genel bakış temel çizim](/dotnet/framework/wpf/data/data-binding-overview).  
  
### <a name="2-d-geometries"></a>2-D geometri  
 WPF tarafından sağlanan 2B şekiller temel şekillerin standart kümesini kapsar. Ancak, özelleştirilmiş kullanıcı arabirimi tasarımını kolaylaştırmak için özel şekiller oluşturmanız gerekebilir. Bu amaçla WPF geometri sağlar. Aşağıdaki şekil doğrudan çizilmiş, fırça olarak kullanılan veya küçük diğer şekiller ve denetimler için kullanılan özel bir şekil oluşturmak için geometri kullanımını göstermektedir.  
  
 <xref:System.Windows.Shapes.Path>nesneleri, kapalı veya açık şekiller, birden çok şekil ve hatta eğri şekiller çizmek için kullanılabilir.  
  
 <xref:System.Windows.Media.Geometry>nesneleri kırpma, isabet testi ve 2B grafik verilerini işleme için kullanılabilir.  
  
 ![Bir yol çeşitli kullanımları](../designers/media/wpfintrofigure5.PNG "WPFIntroFigure5")  
  
 Daha fazla bilgi için bkz: [geometrisi](/dotnet/framework/wpf/graphics-multimedia/geometry-overview).  
  
### <a name="2-d-effects"></a>2B efektler  
 WPF 2B yeteneklerinin bir alt kümesini gradyan, bit eşlemler, çizimler, videoları, döndürme, ölçekleme ve eğriltme boyama gibi görsel efektler içerir. Bunların tümü fırçalar ile elde edilir; Aşağıdaki şekilde bazı örnekler gösterilmektedir.  
  
 ![Farklı fırçalar çizimi](../designers/media/wpfintrofigure6.PNG "WPFIntroFigure6")  
  
 Daha fazla bilgi için bkz: [WPF Fırçaları Genel Bakış](/dotnet/framework/wpf/graphics-multimedia/wpf-brushes-overview).  
  
### <a name="3-d-rendering"></a>3B işleme  
 WPF 2B grafik daha heyecan verici ve ilginç kullanıcı arabirimleri oluşturulmasına izin ile tümleştirmek 3B işleme özelliklerini de içerir. Örneğin, aşağıdaki şekilde 3-b şekilleri üzerinde işlenen 2B görüntüleri gösterilmektedir.  
  
 ![Visual3D örnek ekran görüntüsü](../designers/media/wpfintrofigure13.png "WPFIntroFigure13")  
  
 Daha fazla bilgi için bkz: [3-b grafiklere genel bakış](/dotnet/framework/wpf/graphics-multimedia/3-d-graphics-overview).  
  
##  <a name="Animation"></a>Animasyon  
 Arttıkça, sallama denetimlerini yapın, WPF animasyon desteği sağlar döndürme ve ilginç oluşturmak için yavaşça geçişleri ve daha fazla sayfa. Çoğu WPF sınıfları animasyon, özel sınıflar bile. Aşağıdaki şekilde basit bir animasyon eylemde gösterilmektedir.  
  
 ![Animasyonlu bir küpü görüntülerini](../designers/media/wpfintrofigure7.png "WPFIntroFigure7")  
  
 Daha fazla bilgi için bkz: [animasyon genel bakış](/dotnet/framework/wpf/graphics-multimedia/animation-overview).  
  
##  <a name="Media"></a>Medya  
 Zengin içerik iletmek için bir görsel ve işitsel ortam kullanımı ile yoludur. WPF, görüntü, video ve ses için özel destek sağlar.  
  
### <a name="images"></a>Görüntüler  
 Görüntüleri çoğu uygulamaları için ortak ve WPF bunları kullanmak için çeşitli yöntemler sağlar. Aşağıdaki şekil küçük resimlerini içeren bir liste kutusu ile bir kullanıcı arabirimi gösterir. Küçük resim seçili olduğunda, görüntü tam boyutlu gösterilir.  
  
 ![Küçük resimler ve tam &#45; resim boyutu](../designers/media/wpfintrofigure8.PNG "WPFIntroFigure8")  
  
 Daha fazla bilgi için bkz: [Imaging genel bakış](/dotnet/framework/wpf/graphics-multimedia/imaging-overview).  
  
### <a name="video-and-audio"></a>Video ve ses  
 <xref:System.Windows.Controls.MediaElement> Denetimidir video ve ses çalma yeteneğine sahiptir ve özel media player için temel olarak yeterince esnektir. Aşağıdaki XAML biçimlendirme media player uygular.  
  
 [!code-xaml[IntroToWPFSnippets#MediaElementMARKUP](../designers/codesnippet/Xaml/introduction-to-wpf_9.xaml)]  
  
 Aşağıdaki şekil gösterdiği penceresinde <xref:System.Windows.Controls.MediaElement> eylem denetiminde.  
  
 ![Ses ve video MediaElement denetimi](../designers/media/wpfintrofigure1.png "WPFIntroFigure1")  
  
 Daha fazla bilgi için bkz: [grafik ve çoklu ortam](/dotnet/framework/wpf/graphics-multimedia).  
  
##  <a name="Text_and_Typography"></a>Metin ve tipografi  
 Yüksek kaliteli metin işlemesini kolaylaştırmak için WPF aşağıdaki özellikleri sunar:  
  
-   OpenType yazı tipi desteği.  
  
-   ClearType geliştirmeleri.  
  
-   Donanım hızlandırma yararlanan yüksek performans.  
  
-   Metni ortam, grafik ve animasyon ile tümleştirilmesi.  
  
-   Uluslararası yazı tipi desteği ve geri dönüş mekanizmaları.  
  
 Metin tümleştirme grafik gösterimi, aşağıdaki şekilde metin düzenlemelerinin uygulaması gösterilmektedir.  
  
 ![Çeşitli metin düzenlemelerinin metinle](../designers/media/wpfintrofigure23.png "WPFIntroFigure23")  
  
 Daha fazla bilgi için bkz: [Windows Presentation Foundation'da tipografi](/dotnet/framework/wpf/advanced/typography-in-wpf).  
  
##  <a name="WPF_Customization"></a>WPF uygulamalarını özelleştirme  
 Bu noktaya kadar uygulamaları geliştirmek için çekirdek WPF yapı taşlarını gördünüz. Ana bilgisayar ve çoğunlukla denetimlerden oluşan uygulama içerik dağıtımı için uygulama modeli kullanın. Bir kullanıcı arabirimi denetimlerini düzenlemesini basitleştirmek ve düzenlemeyi pencere boyutu değişiklikler karşısında korunduğundan emin olmak ve ayarlarını görüntülemek için WPF düzeni sistemi kullanın. Çoğu uygulama verilerle etkileşime girmesine izin için kullanıcı arabirimi ile veri tümleştirme işini azaltmak için veri bağlama kullanın. Uygulamanızı görsel görünümünü geliştirmek için WPF tarafından sağlanan kapsamlı grafikler, animasyon ve medya kullanın.  
  
 Genellikle, yine de temellerini oluşturma ve gerçekten farklı yönetmek ve görsel olarak şaşırtıcı bir kullanıcı deneyimi için yeterli değildir. Standart WPF denetimleri, uygulamanızın istenen görünümüyle tümleştirin değil. Veri en etkili şekilde görüntülenmeyebilir. Uygulamanızın genel kullanıcı deneyimi, varsayılan görünüm ve yapısını için Windows temaları uygun olmayabilir. Birçok yolla sunu teknolojisi visual genişletilebilirlik genişletilebilirlik kadar herhangi bir diğer tür gerekiyor.  
  
 Bu nedenle, WPF denetimleri, Tetikleyiciler, Denetim ve veri şablonları, stiller, kullanıcı arabirimi kaynakları ve temalar ve kaplamaları için zengin bir içerik modeli içeren benzersiz kullanıcı deneyimleri oluşturmak için mekanizmaları çeşitli sağlar.  
  
### <a name="content-model"></a>İçerik modeli  
 WPF denetimleri çoğunu ana amacı, içeriği görüntülemektir. WPF içinde denetimin içeriğini oluşturan öğelerin sayısını ve türünü adlandırılır denetimin *içerik modeli*. Bazı denetimler tek öğe ve içerik türünü içerebilir; Örneğin, içeriği bir <xref:System.Windows.Controls.TextBox> atanan bir dize değeridir <xref:System.Windows.Controls.TextBox.Text%2A> özelliği. Aşağıdaki örnek, içeriği ayarlar bir <xref:System.Windows.Controls.TextBox>.  

```xaml  
<Window 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.TextBoxContentWindow"
    Title="TextBox Content">  

    <TextBox Text="This is the content of a TextBox." />  
</Window>  
```
  
 Aşağıdaki şekil sonucu gösterir.  
  
 ![Metin içeren bir metin kutusu denetimi](../designers/media/wpfintrofigure21.png "WPFIntroFigure21")  
  
 Diğer denetimler, ancak içerik farklı türlerde birden çok öğe içerebilir; içeriği bir <xref:System.Windows.Controls.Button>tarafından belirtilen <xref:System.Windows.Controls.ContentControl.Content%2A> özelliği, öğeleri düzen denetimleri, metin, görüntüler ve şekiller de dahil olmak üzere çeşitli içerebilir. Aşağıdaki örnekte gösterildiği bir <xref:System.Windows.Controls.Button> içeren içerik ile bir <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Border>ve bir <xref:System.Windows.Controls.MediaElement>.  
  
```xaml
<Window 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.ButtonContentWindow"
    Title="Button Content">  

  <Button Margin="20">
    <!-- Button Content -->
    <DockPanel Width="200" Height="180">
      <Label DockPanel.Dock="Top" HorizontalAlignment="Center">Click Me!</Label>
      <Border Background="Black" BorderBrush="Yellow" BorderThickness="2" 
        CornerRadius="2" Margin="5">
        <MediaElement Source="media/wpf.wmv" Stretch="Fill" />
      </Border>
    </DockPanel>
  </Button>  
</Window>  
```
  
 Aşağıdaki şekilde bu düğme içeriğini gösterir.  
  
 ![Birden çok içerik türlerini içeren bir düğme](../designers/media/wpfintrofigure22.png "WPFIntroFigure22")  
  
 Çeşitli denetimler tarafından desteklenen içerik türleri hakkında daha fazla bilgi için bkz: [WPF içeriği modeli](/dotnet/framework/wpf/controls/wpf-content-model).  
  
### <a name="triggers"></a>Tetikleyiciler  
 XAML biçimlendirme ana amacı bir uygulamanın görünümünü uygulamak için olsa da, bir uygulamanın davranışını bazı yönlerini uygulamak için XAML de kullanabilirsiniz. Kullanıcı etkileşimlerine dayalı bir uygulamanın görünümünü değiştirmek için Tetikleyiciler kullanımını bir örnektir. Daha fazla bilgi için bkz: [stil ve şablon](/dotnet/framework/wpf/controls/styling-and-templating).  
  
### <a name="control-templates"></a>Denetim şablonları  
 WPF denetimleri için varsayılan kullanıcı arabirimleri genellikle diğer denetim ve şekillerden oluşturulur. Örneğin, bir <xref:System.Windows.Controls.Button> her ikisi de oluşan <xref:Microsoft.Windows.Themes.ButtonChrome> ve <xref:System.Windows.Controls.ContentPresenter> kontrol eder. <xref:Microsoft.Windows.Themes.ButtonChrome> Standart düğme görünümünü sağlar ancak <xref:System.Windows.Controls.ContentPresenter> tarafından belirtilen düğmenin içeriğini görüntüler <xref:System.Windows.Controls.ContentControl.Content%2A> özelliği.  
  
 Bazen bir denetimin varsayılan görünümünü bir uygulamanın genel görünümünü incongruent olabilir. Bu durumda, kullanabileceğiniz bir <xref:System.Windows.Controls.ControlTemplate> içeriği ve davranışını değiştirmeden denetimin kullanıcı arabiriminin görünümünü değiştirmek için.  
  
 Örneğin, aşağıdaki örnek görünümünü değiştirme gösterilmektedir bir <xref:System.Windows.Controls.Button> kullanarak bir <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xaml[IntroToWPFSnippets#ButtonControlTemplateWindowMARKUP](../designers/codesnippet/Xaml/introduction-to-wpf_16.xaml)]  
  
 [!code-csharp[IntroToWPFSnippets#ButtonControlTemplateWindowCODEBEHIND](../designers/codesnippet/CSharp/introduction-to-wpf_17.cs)]
 [!code-vb[IntroToWPFSnippets#ButtonControlTemplateWindowCODEBEHIND](../designers/codesnippet/VisualBasic/introduction-to-wpf_17.vb)]  
  
 Bu örnekte, varsayılan düğme kullanıcı arabirimi ile değiştirilmiştir bir <xref:System.Windows.Shapes.Ellipse> , koyu mavi kenarlığı olan ve kullanılarak doldurulan bir <xref:System.Windows.Media.RadialGradientBrush>. <xref:System.Windows.Controls.ContentPresenter> Denetimi içeriğini görüntüler <xref:System.Windows.Controls.Button>, "Beni tıklayın!" Zaman <xref:System.Windows.Controls.Button> tıklandığında, <xref:System.Windows.Controls.Primitives.ButtonBase.Click> hala olayı parçası olarak <xref:System.Windows.Controls.Button> denetimin varsayılan davranışı. Sonuç aşağıdaki çizimde gösterilmiştir.  
  
 ![Elips düğme ve ikinci bir pencere](../designers/media/wpfintrofigure2.png "WPFIntroFigure2")  
  
### <a name="data-templates"></a>Veri şablonları  
 Bir denetim şablonu denetiminin görünümünü belirtmenize olanak tanır ancak veri şablonu denetim içeriğinin görünümünü belirtmenize olanak sağlar. Veri şablonları nasıl bağlı veri geliştirmek için kullanılan sık görüntülenir. Varsayılan görünüm için aşağıdaki şekilde gösterilmiştir bir <xref:System.Windows.Controls.ListBox> bir koleksiyona bağlı `Task` nesneleri, her görevin sahip olduğu bir ad, açıklama ve öncelik.  
  
 ![Varsayılan görünüm içeren bir liste kutusu](../designers/media/wpfintrofigure18.png "WPFIntroFigure18")  
  
 Varsayılan görünüm gelen beklediğiniz olan bir <xref:System.Windows.Controls.ListBox>. Bununla birlikte, her görevin varsayılan görünümünü yalnızca görev adını içerir. Görev adı, açıklama ve öncelik, varsayılan görünümünü göstermek için <xref:System.Windows.Controls.ListBox> denetimin ilişkili liste öğelerini kullanarak değiştirilmelidir bir <xref:System.Windows.DataTemplate>. Aşağıdaki XAML gibi tanımlayan bir <xref:System.Windows.DataTemplate>, uygulandığı her görev için kullanarak <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> özniteliği.  
  
```xaml
<Window
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  x:Class="SDKSample.DataTemplateWindow"
  Title="With a Data Template">
  <Window.Resources>
    <!-- Data Template (applied to each bound task item in the task collection) -->
    <DataTemplate x:Key="myTaskTemplate">
      <Border Name="border" BorderBrush="DarkSlateBlue" BorderThickness="2" 
        CornerRadius="2" Padding="5" Margin="5">
        <Grid>
          <Grid.RowDefinitions>
            <RowDefinition/>
            <RowDefinition/>
            <RowDefinition/>
          </Grid.RowDefinitions>
          <Grid.ColumnDefinitions>
            <ColumnDefinition Width="Auto" />
            <ColumnDefinition />
          </Grid.ColumnDefinitions>
          <TextBlock Grid.Row="0" Grid.Column="0" Padding="0,0,5,0" Text="Task Name:"/>
          <TextBlock Grid.Row="0" Grid.Column="1" Text="{Binding Path=TaskName}"/>
          <TextBlock Grid.Row="1" Grid.Column="0" Padding="0,0,5,0" Text="Description:"/>
          <TextBlock Grid.Row="1" Grid.Column="1" Text="{Binding Path=Description}"/>
          <TextBlock Grid.Row="2" Grid.Column="0" Padding="0,0,5,0" Text="Priority:"/>
          <TextBlock Grid.Row="2" Grid.Column="1" Text="{Binding Path=Priority}"/>
        </Grid>
      </Border>  
    </DataTemplate>
  </Window.Resources>

  <!-- UI -->
  <DockPanel>
    <!-- Title -->
    <Label DockPanel.Dock="Top" FontSize="18" Margin="5" Content="My Task List:"/>
  
    <!-- Data template is specified by the ItemTemplate attribute -->
    <ListBox 
      ItemsSource="{Binding}" 
      ItemTemplate="{StaticResource myTaskTemplate}" 
      HorizontalContentAlignment="Stretch" 
      IsSynchronizedWithCurrentItem="True" 
      Margin="5,0,5,5" />

 </DockPanel>
</Window>
```  
  
 Aşağıdaki şekil bu kodun etkisini gösterir.  
  
 ![Veri şablonunu kullanan simgesiz liste kutusunu](../designers/media/wpfintrofigure19.png "WPFIntroFigure19")  
  
 Unutmayın <xref:System.Windows.Controls.ListBox> kendi davranış ve genel görünümünü; koruduğunu yalnızca liste kutusu tarafından görüntülenmekte olan içeriğin görünümünü değişti.  
  
 Daha fazla bilgi için bkz: [veri şablonu özeti](/dotnet/framework/wpf/data/data-templating-overview).  
  
### <a name="styles"></a>Stilleri  
 Stiller, geliştiricilerin ve tasarımcıların kendi ürün için belirli bir görünümünü standartlaştırmak olanak sağlar. WPF sağlar temeli olan güçlü bir stil modeli, <xref:System.Windows.Style> öğesi. Aşağıdaki örnek, arka plan rengini ayarlayan bir stil oluşturur her <xref:System.Windows.Controls.Button> pencere üzerindeki `Orange`.  
  
```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.StyleWindow"
    Title="Styles">  
  <!-- Style that will be applied to all buttons -->
  <Style TargetType="{x:Type Button}">
    <Setter Property="Background" Value="Orange" />
    <Setter Property="BorderBrush" Value="Crimson" />
    <Setter Property="FontSize" Value="20" />
    <Setter Property="FontWeight" Value="Bold" />
    <Setter Property="Margin" Value="5" />
  </Style>  
  <!-- This button will have the style applied to it -->
  <Button>Click Me!</Button>

  <!-- This label will not have the style applied to it -->
  <Label>Don't Click Me!</Label>

  <!-- This button will have the style applied to it -->
  <Button>Click Me!</Button>  
</Window>
```  
  
 Bu stili tüm hedeflediğinden <xref:System.Windows.Controls.Button> aşağıdaki resimde gösterildiği gibi pencere içindeki tüm düğmelere denetimleri, stil otomatik olarak uygulanır.  
  
 ![İki turuncu düğmeleri](../designers/media/wpfintrofigure20.png "WPFIntroFigure20")  
  
 Daha fazla bilgi için bkz: [stil ve şablon](/dotnet/framework/wpf/controls/styling-and-templating).  
  
### <a name="resources"></a>Kaynaklar  
 Bir uygulama denetimlerinde herhangi bir şey şablonları, veri şablonları ve stiller denetlemek için yazı tipi ve arka plan renklerini içerebilir aynı görünüme paylaşması gerekir. Bu kaynakları yeniden kullanım için tek bir konumda için kullanıcı arabirimi kaynakları WPF'in desteğini kullanabilirsiniz.  
  
 Aşağıdaki örnek tarafından paylaşılan ortak bir arka plan rengini tanımlayan bir <xref:System.Windows.Controls.Button> ve <xref:System.Windows.Controls.Label>.  
  
```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.ResourcesWindow"
    Title="Resources Window">
  
  <!-- Define window-scoped background color resource -->
  <Window.Resources>
    <SolidColorBrush x:Key="defaultBackground" Color="Red" />
  </Window.Resources>  

  <!-- Button background is defined by window-scoped resource -->
  <Button Background="{StaticResource defaultBackground}">One Button</Button>

  <!-- Label background is defined by window-scoped resource -->
  <Label Background="{StaticResource defaultBackground}">One Label</Label>  
</Window>
``` 
  
 Bu örnek bir arka plan rengi kaynağı kullanarak uygulayan `Window.Resources` özellik öğesi. Bu kaynağın tüm alt öğeleri için kullanılabilir durumda <xref:System.Windows.Window>. Çeşitli kaynak vardır kapsamlar, aşağıdakiler de dahil, bunlar çözümlenmiş sırayla listelenen:  
  
1.  Tek bir denetim (devralınan kullanarak <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> özelliği).  
  
2.  A <xref:System.Windows.Window> veya <xref:System.Windows.Controls.Page> (Ayrıca devralınan kullanarak <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> özelliği).  
  
3.  Bir <xref:System.Windows.Application> (kullanarak <xref:System.Windows.Application.Resources%2A?displayProperty=fullName> özelliği).  
  
 Çeşitli kapsamlar içinde tanımlamak ve kaynaklarınızı paylaşma yolu göre esnekliği sağlar.  
  
 Belirli bir kapsamla kaynaklarınızı doğrudan ilişkilendirmeye alternatif olarak, ayrı bir kullanarak bir veya daha fazla kaynak paketleyebilirsiniz <xref:System.Windows.ResourceDictionary> uygulamanın diğer bölümlerinde başvurulabilir. Örneğin, aşağıdaki örnek, bir kaynak sözlüğü varsayılan arka plan rengi tanımlar.  
  
```xaml
<ResourceDictionary 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

  <!-- Define background color resource -->
  <SolidColorBrush x:Key="defaultBackground" Color="Red" />

  <!-- Define other resources -->
</ResourceDictionary>
```  
  
 Aşağıdaki örnek bir uygulama arasında paylaşılacak şekilde, önceki örnekte tanımlanan kaynak sözlüğüne başvurur.  
  
```xaml
<Application
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.App">
  
  <Application.Resources>
    <ResourceDictionary>
      <ResourceDictionary.MergedDictionaries>
        <ResourceDictionary Source="BackgroundColorResources.xaml"/>
      </ResourceDictionary.MergedDictionaries>
    </ResourceDictionary>
  </Application.Resources>
</Application>
```  
  
 Kaynak ve kaynak sözlükleri desteğinin WPF temalar ve dış görünümler temelidir.  
  
 Daha fazla bilgi için bkz: [kaynaklarına genel bakış](/dotnet/framework/wpf/advanced/xaml-resources).  
  
### <a name="custom-controls"></a>Özel denetimler  
 WPF özelleştirme desteği ana bilgisayarını sağlasa da, burada mevcut WPF denetimleri uygulamanızı veya kullanıcılarına gereksinimlerini karşılamayan durumlarla karşılaşabilirsiniz. Bu durum ortaya çıkabilir zaman:  
  
-   İhtiyaç duyduğunuz kullanıcı arabirimi, varolan WPF uygulamalarında Görünüm ve yapısını özelleştirerek oluşturulamıyor.  
  
-   İhtiyaç duyduğunuz davranışı desteklenmiyor (veya kolayca desteklenmez) mevcut WPF uygulamaları tarafından.  
  
 Bu noktada, Bununla birlikte, yeni bir denetim oluşturmak için üç WPF modeli birinin yararlanabilirsiniz. Her model belirli bir senaryoyu hedefler ve bir belirli WPF temel sınıfından türetilen özel denetim gerektirir. Üç modeli aşağıda listelenmiştir:  
  
-   **Kullanıcı denetim modeli**. Özel bir denetim türetilen <xref:System.Windows.Controls.UserControl> ve bir veya daha fazla denetimden oluşur.  
  
-   **Denetim modeli**. Özel bir denetim türetilen <xref:System.Windows.Controls.Control> ve WPF denetimleri çoğunluğu gibi şablonları kullanarak görünümlerini davranışlarını ayırmak uygulamaları oluşturmak için kullanılır. Türetme <xref:System.Windows.Controls.Control> kullanıcı denetimleri, ancak daha fazla çaba gerektirebilir özel kullanıcı arabirimi oluşturmak için özgürlüğü sağlar.  
  
-   **Çerçeve Öğe modeli**. Özel bir denetim türetilen <xref:System.Windows.FrameworkElement> görünümünü (şablon yok) özel işleme mantığı tarafından tanımlanan zaman.  
  
 Aşağıdaki örnek özel bir sayısal gösterir yukarı/aşağı türetilen denetim <xref:System.Windows.Controls.UserControl>.  
  
 [!code-xaml[IntroToWPFSnippets#UserControlMARKUP](../designers/codesnippet/Xaml/introduction-to-wpf_33.xaml)]  
  
 [!code-csharp[IntroToWPFSnippets#UserControlCODEBEHIND1](../designers/codesnippet/CSharp/introduction-to-wpf_34.cs)]
 [!code-vb[IntroToWPFSnippets#UserControlCODEBEHIND1](../designers/codesnippet/VisualBasic/introduction-to-wpf_34.vb)]  
  
 İçinde kullanıcı denetimini eklemek için gereken XAML sonraki örnek gösterilmektedir bir <xref:System.Windows.Window>.  
  
 [!code-xaml[IntroToWPFSnippets#UserControlWindowMARKUP1](../designers/codesnippet/Xaml/introduction-to-wpf_37.xaml)]  
  
 Aşağıdaki şekil gösterir `NumericUpDown` denetiminde barındırılan bir <xref:System.Windows.Window>.  
  
 ![Özel bir UserControl](../designers/media/wpfintrofigure3.png "WPFIntroFigure3")  
  
 Özel denetimler hakkında daha fazla bilgi için bkz: [denetimine genel bakış yazma](/dotnet/framework/wpf/controls/control-authoring-overview).  
  
##  <a name="WPF_Best_Practices"></a>WPF en iyi yöntemler  
 Tüm geliştirme platformunda olduğu gibi WPF bir çeşitli şekillerde istenen sonucu elde etmek için kullanılabilir. WPF sağlamaya bir yolu olarak uygulamaları gerekli bir kullanıcı deneyimi sağlar ve genel kitlenin taleplerini karşılamak, önerilen erişilebilirlik, Genelleştirme ve yerelleştirme ve performans için en iyi uygulamalar. Daha fazla bilgi için aşağıdakilere bakın:  
  
-   [En iyi erişilebilirlik uygulamaları](/dotnet/framework/ui-automation/accessibility-best-practices)en iyi erişilebilirlik uygulamaları  
  
-   [WPF Genelleştirmesi ve Yerelleştirmesine Genel Bakış](/dotnet/framework/wpf/advanced/wpf-globalization-and-localization-overview)  
  
-   [WPF Uygulama Performansını İyileştirme](/dotnet/framework/wpf/advanced/optimizing-wpf-application-performance)  
  
-   [Windows Presentation Foundation güvenliği](/dotnet/framework/wpf/security-wpf)  
  
##  <a name="Summary"></a>Özet  
 WPF görsel olarak şaşırtıcı istemci uygulamaları çeşitli oluşturmaya yönelik bir kapsamlı sunu teknolojisidir. Bu giriş, WPF anahtar özelliklerini göz sağlamıştır.  
  
 WPF uygulamaları oluşturmak için sonraki adımdır bakın!  
  
 Onları oluşturduğunuz gibi geri Yenileyici bu giriş için anahtar özellikler ve bu bölümde ele alınan özelliklerin daha ayrıntılı kapsam başvuruları bulmak için gelebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WPF ile çalışmaya başlama](../designers/getting-started-with-wpf.md)   
 [Windows Presentation Foundation ile modern masaüstü uygulamaları oluşturma](../designers/create-modern-desktop-applications-with-windows-presentation-foundation.md)   
 [Windows Presentation Foundation](/dotnet/framework/wpf/index)