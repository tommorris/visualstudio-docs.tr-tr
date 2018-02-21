---
title: "İzlenecek yol: İlk WPF Masaüstü Uygulamam | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- csharp
- vb
ms.workload:
- multiple
ms.openlocfilehash: c668d454cb4584cbaaa345c0ca00e286526c6aae
ms.sourcegitcommit: bfa26fd7426af0d065cb2eef3d6827b5d6f7986c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2018
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a>İzlenecek yol: İlk WPF Masaüstü Uygulamam

Bu kılavuzda Windows Presentation Foundation (WPF) geliştirme tanıtılmaktadır. Çoğu WPF Masaüstü uygulamaları için ortak olan öğeleri içeren temel bir uygulama oluşturacaksınız: XAML biçimlendirme, arka plan kodu, uygulama tanımları, denetimler, düzeni, veri bağlama ve stiller.

## <a name="creating-the-application-project"></a>Uygulama projesi oluşturma

Bu bölümde, proje ve bir ana penceresi veya form içeren uygulama altyapısı oluşturacaksınız.

### <a name="to-create-the-project"></a>Proje oluşturmak için

1. Menü çubuğunda seçin **dosya** > **yeni** > **proje**.

1. İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic** düğümü seçin **Windows** düğümünü genişletin ve ardından **Windows** düğümü seçin **Klasik Masaüstü** düğümü.

1. Şablon listesinde seçim **WPF uygulaması** şablonu.

1. İçinde **adı** metin kutusuna girin `ExpenseIt`ve ardından **Tamam** düğmesi.

    Proje oluşturulur ve proje dosyaları eklenir **Çözüm Gezgini**ve adlı varsayılan uygulama penceresi Tasarımcı **MainWindow.xaml** görüntülenir.

### <a name="to-modify-the-main-window"></a>Ana pencereyi değiştirmek için

1. Tasarımcıda seçin **MainWindow.xaml** etkin Tasarımcı sekmesi değilse sekmesinde.

1. C# kullanıyorsanız satırı bulun `<Window x:Class="ExpenseIt.MainWindow"` ve bunların yerine `<NavigationWindow x:Class="ExpenseIt.MainWindow"`.
  
     Visual Basic kullanıyorsanız satırı bulun `<Window x:Class=" MainWindow"` ve bunların yerine `<NavigationWindow x:Class="MainWindow"`.
  
     Değiştirdiğinizde dikkat `<Window` etiketini `<NavigationWindow`, IntelliSense otomatik olarak kapanış etiketi değiştirir `</NavigationWindow>` de.
  
    > [!NOTE]
    >  Etiket, değiştirdikten sonra **hata listesi** penceresi açık çeşitli hatalar görebilirsiniz. Endişelenmeyin, sonraki birkaç adımda yaptığınız değişiklikler bu Git hemen hale getirir.

1. Seçin `<Grid>` ve `</Grid>` etiketleri ve silebilirsiniz.
  
     A **NavigationWindow** diğer kullanıcı Arabirimi öğeleri gibi bulunamaz bir **kılavuz**.

1. İçinde **özellikleri** penceresinde genişletin **ortak** Kategori düğümü ve seçin **başlık** özelliği ve enter `ExpenseIt` ve tuşuna basın **girin**  anahtarı.
  
     Dikkat **başlık** özniteliği XAML penceresinde değiştirir yeni değer ile eşleşmelidir. XAML penceresinde XAML özelliklerini değiştirebilirsiniz veya **özellikleri** penceresi ve değişiklikleri eşitlenir.

1. XAML penceresinde değerini **yükseklik** öğesine `375`ve değeri ayarlayın **genişliği** özelliğine `500`.
  
     Bu öğeler karşılık **yükseklik** ve **genişliği** bulunan özellikler, **düzeni** kategorisinde **özellikleri** penceresi.
  
     **MainWindow.xaml** dosya şimdi şöyle görünmelidir C#:  
  
    ```xaml  
    <NavigationWindow x:Class="ExpenseIt.MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
            xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
            xmlns:local="clr-namespace:ExpenseIt"  
            mc:Ignorable="d"  
            Title="ExpenseIt" Height="375" Width="500">
    </NavigationWindow>  
    ```

    Ya da böyle Visual Basic'te:

    ```xaml  
    <NavigationWindow x:Class="MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
            xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
            xmlns:local="clr-namespace:ExpenseIt"  
            mc:Ignorable="d"  
            Title="ExpenseIt" Height="375" Width="500">    
    </NavigationWindow>  
    ```  

### <a name="to-modify-the-code-behind-file-c"></a>Arka plan kodu dosyasını (C#) değiştirmek için

1. İçinde **Çözüm Gezgini**, genişletin **MainWindow.xaml** düğümü ve açık **MainWindow.xaml.cs** dosya.

1. Satırı bulun `public partial class MainWindow : Window` ve bunların yerine `public partial class MainWindow : NavigationWindow`.

    Bu değişiklikler `MainWindow` öğesinden türetilen sınıf `NavigationWindow`. Kod değişiklikleri gerekli; bu nedenle XAML penceresinde değiştirdiğinizde, Visual Basic'te, bu otomatik olarak gerçekleşir.

## <a name="adding-files-to-the-application"></a>Dosyalar için uygulama ekleme

Bu bölümde, uygulama için iki sayfaları ve görüntü ekleyeceksiniz.

### <a name="to-add-a-home-screen"></a>Giriş ekranı eklemek için

1. İçinde **Çözüm Gezgini**, kısayol menüsünü açın **ExpenseIt** düğümü seçin **Ekle** > **sayfa**.

1. İçinde **Yeni Öğe Ekle** iletişim kutusunda, seçin **adı** metin kutusunda ve girin `ExpenseItHome`ve ardından **Ekle** düğmesi.
  
     Bu sayfa uygulama başlatıldığında görüntülenen ilk penceredir.

1. Tasarımcıda seçin **ExpenseItHome.XAML** etkin Tasarımcı sekmesi değilse sekmesinde.

1. Seçin `Title` özniteliği ve onun değerine değiştirin **ExpenseIt - giriş**.
  
     **ExpenseItHome.XAML** dosya şimdi şöyle görünmelidir C#:  
  
    ```xaml  
    <Page x:Class="ExpenseIt.ExpenseItHome"  
          xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
          xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"   
          xmlns:d="http://schemas.microsoft.com/expression/blend/2008"   
          xmlns:local="clr-namespace:ExpenseIt"  
          mc:Ignorable="d"   
          d:DesignHeight="300" d:DesignWidth="300"  
          Title="ExpenseIt - Home">    
        <Grid>  
  
        </Grid>  
    </Page>  
    ```  
  
    Visual Basic'te tarafından ilk satırı olacak biraz farklı:  
  
    ```xaml  
    <Page x:Class="ExpenseItHome"  
    ```  

1. Tasarımcıda seçin **MainWindow.xaml** sekmesi.

1. Satırı bulun `Title="ExpenseIt" Height="375" Width="500">` öğesi ekleyin bir `Source="ExpenseItHome.xaml"` özelliği.
  
     Bu ayarlar **ExpenseItHome.XAML** ilk sayfa olarak uygulama başladığında açılır. **MainWindow.xaml** dosya şimdi şöyle görünmelidir C#:  
  
    ```xaml  
    <NavigationWindow x:Class="ExpenseIt.MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
            xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
            xmlns:local="clr-namespace:ExpenseIt"  
            mc:Ignorable="d"  
            Title="ExpenseIt" Height="375" Width="500" Source="ExpenseItHome.xaml">    
    </NavigationWindow>  
    ```  
  
    Visual Basic'te tarafından ilk satırı olacak biraz farklı:  
  
    ```xaml  
    <NavigationWindow x:Class="MainWindow"
    ```  
  
     Daha önce belirlediğiniz özelliklerle şu ayarlamış olduğunuz gibi `Source` özelliğinde **çeşitli** kategorisini **özellikleri** penceresi.
  
### <a name="to-add-a-details-window"></a>Ayrıntılar pencere eklemek için

1. İçinde **Çözüm Gezgini**, kısayol menüsünü açın **ExpenseIt** düğümü seçin **Ekle** > **sayfa**.

1. İçinde **Yeni Öğe Ekle** iletişim kutusunda, seçin **adı** metin kutusunda ve girin `ExpenseReportPage`ve ardından **Ekle** düğmesi.
  
     Bu pencere tek bir gider raporunu görüntüler.

1. Tasarımcıda seçin **ExpenseReportPage.xaml** etkin Tasarımcı sekmesi değilse sekmesinde.

1. Seçin `Title` özniteliği ve onun değerine değiştirin **ExpenseIt - görünüm gider**.
  
     ExpenseReportPage.xaml dosyanızı gibi C# ' ta görünmelidir:  
  
    ```xaml  
    <Page x:Class="ExpenseIt.ExpenseReportPage"  
          xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
          xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"   
          xmlns:d="http://schemas.microsoft.com/expression/blend/2008"   
          xmlns:local="clr-namespace:ExpenseIt"  
          mc:Ignorable="d"   
          d:DesignHeight="300" d:DesignWidth="300"  
          Title="ExpenseIt - View Expense">    
        <Grid>  
  
        </Grid>  
    </Page>  
    ```  
  
    Visual Basic'te ilk satırı farklılık gösterir:  
  
    ```xaml  
    <Page x:Class="ExpenseReportPage"  
    ```  

1. Menü çubuğunda seçin **hata ayıklama** > **hata ayıklamayı Başlat** (veya basın **F5**) uygulamayı çalıştırın.
  
     Aşağıdaki çizimde Gezinti penceresi düğmeleri ile uygulamayı gösterir.
  
     ![ExpenseIt örnek ekran görüntüsü](../designers/media/gettingstartedfigure1.png "GettingStartedFigure1")

1. Tasarım moduna dönerseniz uygulamayı kapatın.

## <a name="creating-the-user-interface"></a>Kullanıcı arabirimi oluşturma

Düzeni öğeleri yerleştirmek için sıralı bir yol sağlar ve formu yeniden boyutlandırıldığında boyutunu ve konumunu bu öğelerin da yönetir. Bu bölümde, üç satır tek sütunlu kılavuz oluşturacaksınız. İki sayfalara denetimleri ekleme, biraz kod eklemek ve son olarak denetimler için yeniden kullanılabilir stiller tanımlamak.

### <a name="to-create-the-layout"></a>Bir düzen oluşturmak için

1. Açık **ExpenseItHome.XAML** ve `<Grid>` öğesi.

1. İçinde **özellikleri** penceresinde genişletin **düzeni** Kategori düğümü ve kümesi **kenar boşluğu** değerler `10`, `10`, `0`ve `10`, sol, sağ, üst ve alt kenar boşluklarına karşılık gelir.

     Öğe `Margin="10,0,10,10"` eklenen `<Grid>` XAML'de öğesi. Bir kez daha, bu değerleri doğrudan de yerine XAML kodu girdiğiniz **özellikleri** aynı sonucu penceresiyle.

1. Aşağıdaki XAML kodu eklemek `Grid` öğesinde satır ve sütun tanımları oluşturmak için:

    ```xaml  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
    <Grid.RowDefinitions>  
        <RowDefinition Height="Auto"/>  
        <RowDefinition />  
        <RowDefinition Height="Auto"/>  
    </Grid.RowDefinitions>  
    ```

### <a name="to-add-controls"></a>Denetim eklemek için

1. Açık **ExpenseItHome.XAML**.

1. Aşağıdaki XAML kodu eklemek yukarıdaki `</Grid>` oluşturmak için etiket `Border`, `ListBox` ve `Button` denetimleri:  

    ```xaml  
    <!-- People list -->  
      <Border Grid.Column="0" Grid.Row="0" Height="35" Padding="5" Background="#4E87D4">  
          <Label VerticalAlignment="Center" Foreground="White">Names</Label>  
      </Border>  
      <ListBox Name="peopleListBox" Grid.Column="0" Grid.Row="1">  
          <ListBoxItem>Mike</ListBoxItem>  
          <ListBoxItem>Lisa</ListBoxItem>  
          <ListBoxItem>John</ListBoxItem>  
          <ListBoxItem>Mary</ListBoxItem>  
      </ListBox>

      <!-- View report button -->
      <Button Grid.Column="0" Grid.Row="2" Margin="0,10,0,0" Width="125"
    Height="25" HorizontalAlignment="Right">View</Button>
    ```

     Denetimleri tasarım penceresinde görüntülendiğine dikkat edin. Ayrıca denetimleri sürükleyerek oluşturmuş olabileceğiniz **araç** tasarım penceresini ve bunların özelliklerini ayarlama penceresinden **özellikleri** penceresi.

1. Derleme ve uygulamayı çalıştırın. Aşağıdaki çizimde, bu yordamdaki XAML tarafından oluşturulan denetimlerin çalışma zamanı görünümünü gösterir.

     ![ExpenseIt örnek ekran görüntüsü](../designers/media/gettingstartedfigure2.png "GettingStartedFigure2")  

1. Tasarım moduna dönerseniz uygulamayı kapatın.

### <a name="to-add-a-background-image"></a>Arka plan görüntüsü eklemek için

1. Aşağıdaki görüntü olarak kaydedin seçip `watermark.png`.

     ![Filigran resminin kılavuz](../designers/media/wpf_watermark.png "Filigran")  

    > [!NOTE]
    >  Alternatif olarak kendi görüntünüzü oluşturabilir ve kaydedileceği `watermark.png`.

1. İçinde **Çözüm Gezgini**, kısayol menüsünü açın **ExpenseIt** düğümü seçin **Ekle** > **varolan öğeyi**.

1. İçinde **varolan öğeyi Ekle** iletişim kutusunda, Bul **watermark.png** eklediğiniz, onu seçin ve ardından görüntü **Ekle** düğmesi.

    > [!NOTE]
    >  Genişletmeniz gerekebilir **dosya türlerini** listesinde ve seçin **görüntü dosyaları**.

1. Açık **ExpenseItHome.XAML** dosya ve aşağıdaki XAML kodu ekleyin yukarıdaki `</Grid>` etiketi arka plan görüntüsü oluşturmak için:

    ```xaml
    <Grid.Background>
        <ImageBrush ImageSource="watermark.png"/>
    </Grid.Background>
    ```

### <a name="to-add-a-title"></a>Başlık eklemek için

1. Açık **ExpenseItHome.XAML**.

1. Satırı bulun `<Grid.ColumnDefinitions>` ve aşağıdaki yalnızca altına ekleyin:

    ```xaml
    <ColumnDefinition Width="230" />
    ```

    Bu, sabit bir 230 piksel genişlik ile diğer sütunların solundaki ek bir sütun oluşturur.

1. Satırı bulun `<Grid.RowDefinitions>` ve aşağıdaki yalnızca altına ekleyin:  

    ```xaml
    <RowDefinition />
    ```

    Bu kılavuz üst kısmına bir satır ekler.

1. Denetimleri ayarlayarak ikinci sütun taşımak `Grid.Column` değerini 1. Her denetim her artırarak bir satır aşağı taşı `Grid.Row` değeri 1.

    1. Satırı bulun `<Border Grid.Column="0" Grid.Row="0" Height="35" Padding="5" Background="#4E87D4">`. Değiştirme `Grid.Column="0"` için `Grid.Column="1"` değiştirip `Grid.Row="0"` için `Grid.Row="1"`.

    1. Satırı bulun `<ListBox Name="peopleListBox" Grid.Column="0" Grid.Row="1"`. Değiştirme `Grid.Column="0"` için `Grid.Column="1"` değiştirip `Grid.Row="1"` için `Grid.Row="2"`.

    1. Satırı bulun `<Button Grid.Column="0" Grid.Row="2" Margin="0,10,0,0" Width="125"`. Değiştirme `Grid.Column="0"` için `Grid.Column="1"` değiştirip `Grid.Row="2"` için `Grid.Row="3"`.

1. Hemen önce `<Border` öğesi başlık görüntülemek için aşağıdaki XAML kodu ekleyin:

    ```xaml
    <Label Grid.Column="1" VerticalAlignment="Center" FontFamily="Trebuchet MS"
            FontWeight="Bold" FontSize="18" Foreground="#0066cc">
        View Expense Report
    </Label>
    ```

     İçeriğini **ExpenseItHome.XAML** gibi C# ' ta görünmelidir:

    ```xaml
    <Page x:Class="ExpenseIt.ExpenseItHome"  
          xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
          xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"   
          xmlns:d="http://schemas.microsoft.com/expression/blend/2008"   
          xmlns:local="clr-namespace:ExpenseIt"  
          mc:Ignorable="d"   
          d:DesignHeight="300" d:DesignWidth="300"  
          Title="ExpenseIt - Home">  
        <Grid Margin="10,0,10,10">  
            <Grid.ColumnDefinitions>  
                <ColumnDefinition Width="230" />  
                <ColumnDefinition />  
            </Grid.ColumnDefinitions>  
            <Grid.RowDefinitions>  
                <RowDefinition />  
                <RowDefinition Height="Auto"/>  
                <RowDefinition />  
                <RowDefinition Height="Auto"/>  
            </Grid.RowDefinitions>  
            <Border Grid.Column="1" Grid.Row="1" Height="35" Padding="5" Background="#4E87D4">  
                <Label VerticalAlignment="Center" Foreground="White">Names</Label>  
            </Border>  
            <!-- People list -->  
            <Label Grid.Column="1" VerticalAlignment="Center" FontFamily="Trebuchet MS"   
            FontWeight="Bold" FontSize="18" Foreground="#0066cc">  
                View Expense Report  
            </Label>  
            <ListBox Name="peopleListBox" Grid.Column="1" Grid.Row="2">  
                <ListBoxItem>Mike</ListBoxItem>  
                <ListBoxItem>Lisa</ListBoxItem>  
                <ListBoxItem>John</ListBoxItem>  
                <ListBoxItem>Mary</ListBoxItem>  
            </ListBox>  
  
            <!-- View report button -->  
            <Button Grid.Column="1" Grid.Row="3" Margin="0,10,0,0" Width="125"  
    Height="25" HorizontalAlignment="Right">View</Button>  
            <Grid.Background>  
                <ImageBrush ImageSource="watermark.png"/>  
            </Grid.Background>  
        </Grid>  
    </Page>  
    ```  
  
    Visual Basic'te ilk satırı farklılık gösterir:  
  
    ```xaml  
    <Page x:Class="ExpenseItHome"  
    ```  

1. Yapı ve uygulama bu noktada çalıştırırsanız, aşağıdaki resimde gösterildiği gibi görünmelidir:  
  
     ![ExpenseIt örnek ekran görüntüsü](../designers/media/gettingstartedfigure3.png "GettingStartedFigure3")  

### <a name="to-add-code-to-the-button"></a>Düğme kodu eklemek için

1. Açık **ExpenseItHome.XAML**.

1. Seçin `Button` öğesi ve aşağıdaki XAML kodu ekleyin hemen sonra `HorizontalAlignment="Right"` öğesi: `Click="Button_Click"`.
  
     Bu düğmenin için bir olay işleyicisi ekler `Click` olay. **Düğmesini** öğe kodu şimdi şöyle görünmelidir:  
  
    ```xaml  
    <!-- View report button -->  
      <Button Grid.Column="1" Grid.Row="3" Margin="0,10,0,0" Width="125"  
    Height="25" HorizontalAlignment="Right" Click="Button_Click">View</Button>  
    ```  

1. Açık **ExpenseItHome.xaml.cs** veya **ExpenseItHome.xaml.vb** dosya.

1. Aşağıdaki kodu ekleyin `ExpenseItHome` sınıfı:  
  
   ```csharp  
   private void Button_Click(object sender, RoutedEventArgs e)  
   {  
       // View Expense Report  
       ExpenseReportPage expenseReportPage = new ExpenseReportPage();  
       this.NavigationService.Navigate(expenseReportPage);    
   }  
   ```  
  
   ```vb  
   Private Sub Button_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)  
       ' View Expense Report  
       Dim expenseReportPage As New ExpenseReportPage()  
   Me.NavigationService.Navigate(expenseReportPage)  
   End Sub  
   ```

    Düğme tıklatıldığında bu olay işleyicisi harcama raporu sayfası açılır.

### <a name="to-create-the-ui-for-the-report-page"></a>Rapor sayfasının ilişkin kullanıcı Arabirimi oluşturmak için

1. Open **ExpenseReportPage.xaml**.

    Bu sayfa, giriş sayfasında seçilen kişi için harcama raporunu görüntüler.

1. Aşağıdaki XAML kodu arasında ekleyin `<Grid>` ve `</Grid>` etiketler:

    ```xaml  
    <Grid.Background>  
        <ImageBrush ImageSource="watermark.png" />  
    </Grid.Background>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition Width="230" />  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
    <Grid.RowDefinitions>  
        <RowDefinition Height="Auto" />  
        <RowDefinition />  
    </Grid.RowDefinitions>  
  
    <Label Grid.Column="1" VerticalAlignment="Center" FontFamily="Trebuchet MS"   
    FontWeight="Bold" FontSize="18" Foreground="#0066cc">  
        Expense Report For:  
    </Label>  
    <Grid Margin="10" Grid.Column="1" Grid.Row="1">  
  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
        <Grid.RowDefinitions>  
            <RowDefinition Height="Auto" />  
            <RowDefinition Height="Auto" />  
            <RowDefinition />  
        </Grid.RowDefinitions>  
  
        <!-- Name -->  
        <StackPanel Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="0" Orientation="Horizontal">  
            <Label Margin="0,0,0,5" FontWeight="Bold">Name:</Label>  
            <Label Margin="0,0,0,5" FontWeight="Bold"></Label>  
        </StackPanel>  
  
        <!-- Department -->  
        <StackPanel Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="1" Orientation="Horizontal">  
            <Label Margin="0,0,0,5" FontWeight="Bold">Department:</Label>  
            <Label Margin="0,0,0,5" FontWeight="Bold"></Label>  
        </StackPanel>  
  
        <Grid Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="2" VerticalAlignment="Top"   
              HorizontalAlignment="Left">  
            <!-- Expense type and Amount table -->  
            <DataGrid  AutoGenerateColumns="False" RowHeaderWidth="0" >  
                <DataGrid.ColumnHeaderStyle>  
                    <Style TargetType="{x:Type DataGridColumnHeader}">  
                        <Setter Property="Height" Value="35" />  
                        <Setter Property="Padding" Value="5" />  
                        <Setter Property="Background" Value="#4E87D4" />  
                        <Setter Property="Foreground" Value="White" />  
                    </Style>  
                </DataGrid.ColumnHeaderStyle>  
                <DataGrid.Columns>  
                    <DataGridTextColumn Header="ExpenseType" />  
                    <DataGridTextColumn Header="Amount"  />  
                </DataGrid.Columns>  
            </DataGrid>  
        </Grid>  
    </Grid>  
    ```  
  
     Bu UI giriş sayfasını oluşturulan UI benzer, ancak rapor verileri görüntülenir bir **DataGrid** denetim.

1. Derleme ve uygulamayı çalıştırın.

1. Seçin **Görünüm** düğmesi.
  
     Harcama Raporu sayfası görüntülenir.
  
     Aşağıdaki çizimde, harcama raporu sayfası gösterilir. Geri gezinti düğmesi etkinleştirilir dikkat edin.
  
     ![ExpenseIt örnek ekran görüntüsü](../designers/media/gettingstartedfigure4.png "GettingStartedFigure4")  
  
### <a name="to-style-controls"></a>Stili denetimleri  

1. Açık **App.xaml** (C#) dosyası ya da **Application.xaml** dosyası (Visual Basic).

1. Aşağıdaki XAML'i ekleyin `<Application.Resources>` ve `</Application.Resources>` etiketler:  
  
    ```xaml  
    <!-- Header text style -->  
    <Style x:Key="headerTextStyle">  
        <Setter Property="Label.VerticalAlignment" Value="Center"></Setter>  
        <Setter Property="Label.FontFamily" Value="Trebuchet MS"></Setter>  
        <Setter Property="Label.FontWeight" Value="Bold"></Setter>  
        <Setter Property="Label.FontSize" Value="18"></Setter>  
        <Setter Property="Label.Foreground" Value="#0066cc"></Setter>  
    </Style>  
  
    <!-- Label style -->  
    <Style x:Key="labelStyle" TargetType="{x:Type Label}">  
        <Setter Property="VerticalAlignment" Value="Top" />  
        <Setter Property="HorizontalAlignment" Value="Left" />  
        <Setter Property="FontWeight" Value="Bold" />  
        <Setter Property="Margin" Value="0,0,0,5" />  
    </Style>  
  
    <!-- DataGrid header style -->  
    <Style x:Key="columnHeaderStyle" TargetType="{x:Type DataGridColumnHeader}">  
        <Setter Property="Height" Value="35" />  
        <Setter Property="Padding" Value="5" />  
        <Setter Property="Background" Value="#4E87D4" />  
        <Setter Property="Foreground" Value="White" />  
    </Style>  
  
    <!-- List header style -->  
    <Style x:Key="listHeaderStyle" TargetType="{x:Type Border}">  
        <Setter Property="Height" Value="35" />  
        <Setter Property="Padding" Value="5" />  
        <Setter Property="Background" Value="#4E87D4" />  
    </Style>  
  
    <!-- List header text style -->  
    <Style x:Key="listHeaderTextStyle" TargetType="{x:Type Label}">  
        <Setter Property="Foreground" Value="White" />  
        <Setter Property="VerticalAlignment" Value="Center" />  
        <Setter Property="HorizontalAlignment" Value="Left" />  
    </Style>  
  
    <!-- Button style -->  
    <Style x:Key="buttonStyle" TargetType="{x:Type Button}">  
        <Setter Property="Width" Value="125" />  
        <Setter Property="Height" Value="25" />  
        <Setter Property="Margin" Value="0,10,0,0" />  
        <Setter Property="HorizontalAlignment" Value="Right" />  
    </Style>  
    ```  
  
     Bu XAML aşağıdaki stilleri ekler:  
  
    -   `headerTextStyle`: Sayfa başlığı Biçimlendirilecek `Label`.
  
    -   `labelStyle`: Biçimlendirilecek `Label` kontrol eder.
  
    -   `columnHeaderStyle`: Biçimlendirilecek `DataGridColumnHeader`.
  
    -   `listHeaderStyle`: List üstbilgisi Biçimlendirilecek `Border` kontrol eder.
  
    -   `listHeaderTextStyle`: List üstbilgisi Biçimlendirilecek **etiket**.
  
    -   `buttonStyle`: Biçimlendirilecek `Button` üzerinde **ExpenseItHome.XAML** pppage.

1. Açık **ExpenseItHome.XAML** ve arasındaki her şeyi değiştirin `<Grid>` ve `</Grid>` aşağıdaki XAML ile öğeleri:  
  
    ```xaml  
    <Grid.ColumnDefinitions>  
                <ColumnDefinition Width="230" />  
                <ColumnDefinition />  
            </Grid.ColumnDefinitions>  
  
            <Grid.RowDefinitions>  
                <RowDefinition/>  
                <RowDefinition Height="Auto"/>  
                <RowDefinition />  
                <RowDefinition Height="Auto"/>  
            </Grid.RowDefinitions>  
            <Label Grid.Column="1" Style="{StaticResource headerTextStyle}" >  
                View Expense Report  
            </Label>  
            <!-- People list -->  
                  <Border Grid.Column="1" Grid.Row="1" Style="{StaticResource listHeaderStyle}">  
                <Label Style="{StaticResource listHeaderTextStyle}">Names</Label>  
            </Border>  
            <ListBox Name="peopleListBox" Grid.Column="1" Grid.Row="2">  
                <ListBoxItem>Mike</ListBoxItem>  
                <ListBoxItem>Lisa</ListBoxItem>  
                <ListBoxItem>John</ListBoxItem>  
                <ListBoxItem>Mary</ListBoxItem>  
            </ListBox>  
  
            <!-- View report button -->  
            <Button Grid.Column="1" Grid.Row="3" Click="Button_Click" Style="{StaticResource buttonStyle}">View</Button>  
            <Grid.Background>  
                <ImageBrush ImageSource="watermark.png"  />  
            </Grid.Background>  
    ```  
  
     Gibi özellikler `VerticalAlignment` ve `FontFamily` her denetimin görünümünü tanımlamak kaldırılır ve stiller uygulayarak değiştirilir.

1. Açık **ExpenseReportPage.xaml** ve arasındaki her şeyi değiştirin `<Grid>` ve son `</Grid>` aşağıdaki XAML ile öğeleri:  
  
    ```xaml  
    <Grid.Background>  
        <ImageBrush ImageSource="watermark.png" />  
    </Grid.Background>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition Width="230" />  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
    <Grid.RowDefinitions>  
        <RowDefinition Height="Auto" />  
        <RowDefinition />  
    </Grid.RowDefinitions>  
    <Label Grid.Column="1" Style="{StaticResource headerTextStyle}">  
        Expense Report For:  
    </Label>  
    <Grid Margin="10" Grid.Column="1" Grid.Row="1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
        <Grid.RowDefinitions>  
            <RowDefinition Height="Auto" />  
            <RowDefinition Height="Auto" />  
            <RowDefinition />  
        </Grid.RowDefinitions>  
  
        <!-- Name -->  
        <StackPanel Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="0" Orientation="Horizontal">  
            <Label Style="{StaticResource labelStyle}">Name:</Label>  
            <Label Style="{StaticResource labelStyle}"></Label>  
        </StackPanel>  
  
        <!-- Department -->  
        <StackPanel Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="1"   
    Orientation="Horizontal">  
            <Label Style="{StaticResource labelStyle}">Department:</Label>  
            <Label Style="{StaticResource labelStyle}"></Label>  
        </StackPanel>  
  
        <Grid Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="2" VerticalAlignment="Top"   
              HorizontalAlignment="Left">  
            <!-- Expense type and Amount table -->  
            <DataGrid ColumnHeaderStyle="{StaticResource columnHeaderStyle}"   
                      AutoGenerateColumns="False" RowHeaderWidth="0" >  
                <DataGrid.Columns>  
                    <DataGridTextColumn Header="ExpenseType" />  
                    <DataGridTextColumn Header="Amount"  />  
                </DataGrid.Columns>  
            </DataGrid>  
        </Grid>  
    </Grid>    
    ```  
  
     Bu stiller ekler `<Label>` ve `<Border>` öğeleri.
  
## <a name="connecting-to-data"></a>Verilere Bağlanma  
 Bu bölümde, bir veri sağlayıcı ve veri şablonu oluşturmak ve verileri göstermek için denetimleri bağlamak.
  
### <a name="to-bind-data-to-a-control"></a>Bir denetime veri bağlamak için

1. Açık **ExpenseItHome.XAML** ve `<Grid>` öğesi...

1. Aşağıdaki XAML kodu ekleyin:  
  
    ```xaml    
    <Grid.Resources>  
    <!-- Expense Report Data -->  
    <XmlDataProvider x:Key="ExpenseDataSource" XPath="Expenses">  
        <x:XData>  
            <Expenses xmlns="">  
                <Person Name="Mike" Department="Legal">  
                    <Expense ExpenseType="Lunch" ExpenseAmount="50" />  
                    <Expense ExpenseType="Transportation" ExpenseAmount="50" />  
                </Person>  
                <Person Name="Lisa" Department="Marketing">  
                    <Expense ExpenseType="Document printing"  
          ExpenseAmount="50"/>  
                    <Expense ExpenseType="Gift" ExpenseAmount="125" />  
                </Person>  
                <Person Name="John" Department="Engineering">  
                    <Expense ExpenseType="Magazine subscription"   
         ExpenseAmount="50"/>  
                    <Expense ExpenseType="New machine" ExpenseAmount="600" />  
                    <Expense ExpenseType="Software" ExpenseAmount="500" />  
                </Person>  
                <Person Name="Mary" Department="Finance">  
                    <Expense ExpenseType="Dinner" ExpenseAmount="100" />  
                </Person>  
            </Expenses>  
        </x:XData>  
    </XmlDataProvider>  
    </Grid.Resources>  
    ```  
  
     Bu kod oluşturur bir `XmlDataProvider` her kişi için veriler içeren sınıf. Normalde bu dosya olarak yüklenir, ancak kolaylık sağlamak için veriler satır içi eklenir.

1. İçinde `<Grid.Resources>` öğesi, aşağıdaki XAML kodu ekleyin:  
  
    ```xaml  
    <!-- Name item template -->  
    <DataTemplate x:Key="nameItemTemplate">  
        <Label Content="{Binding XPath=@Name}"/>  
    </DataTemplate>  
    ```  
  
     Bu ekler bir `Data Template` verilerinin nasıl görüntüleneceğini tanımlayan **ListBox**.

1. Varolan `<ListBox>` aşağıdaki XAML sahip öğe:  
  
    ```xaml  
    <ListBox Name="peopleListBox" Grid.Column="1" Grid.Row="2"   
             ItemsSource="{Binding Source={StaticResource ExpenseDataSource}, XPath=Person}"  
             ItemTemplate="{StaticResource nameItemTemplate}">  
    </ListBox>  
    ```  
  
     Bu kod bağlar `ItemsSource` özelliği `ListBox` veri kaynağı ve veri şablon olarak geçerlidir `ItemTemplate`.
  
### <a name="to-connect-data-to-controls"></a>Veri denetimleri bağlanmak için  

1. Açık **ExpenseReportPage.xaml.vb** veya **ExpenseReportPage.xaml.cs**.

1. C# ' ta aşağıdaki oluşturucuyu ekleyin **ExpenseReportPage** sınıf ya da Visual Basic'te varolan bir sınıfa şununla değiştirin:  
  
   ```csharp  
   // Custom constructor to pass expense report data  
   public ExpenseReportPage(object data):this()  
   {  
       // Bind to expense report data.
       this.DataContext = data;  
   }  
   ```  
  
   ```vb  
   Partial Public Class ExpenseReportPage  
   Inherits Page  
       Public Sub New()  
       InitializeComponent()  
       End Sub  
  
       ' Custom constructor to pass expense report data  
       Public Sub New(ByVal data As Object)  
           Me.New()  
           ' Bind to expense report data.
           Me.DataContext = data  
       End Sub    
   End Class  
   ```  
  
   Bu oluşturucu bir veri nesnesini parametre olarak alır. Bu durumda veri nesnesi seçili kişinin adını içerir.

1. Açık **ExpenseItHome.xaml.vb** veya **ExpenseItHome.xaml.cs**.

1. Değiştir `Click` olay işleyici kodu aşağıdaki ile:  
  
   ```csharp  
   private void Button_Click(object sender, RoutedEventArgs e)  
   {  
       // View Expense Report  
       ExpenseReportPage expenseReportPage = new ExpenseReportPage(this.peopleListBox.SelectedItem);  
       this.NavigationService.Navigate(expenseReportPage);    
   }  
   ```  
  
   ```vb  
   Private Sub Button_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)  
       ' View Expense Report  
       Dim expenseReportPage As New ExpenseReportPage(Me.peopleListBox.SelectedItem)  
       Me.NavigationService.Navigate(expenseReportPage)  
   End Sub  
   ```  
  
   Bu kod, yeni oluşturucuyu çağırır.
  
### <a name="to-update-the-ui-with-data-templates"></a>Kullanıcı Arabirimi ile veri şablonlarını güncelleştirmek için  

1. Open **ExpenseReportPage.xaml**.

1. XAML kodunu değiştir **adı** ve **departmanı** `<StackPanel` aşağıdaki öğeleri:  
  
    ```xaml  
    <!-- Name -->  
    <StackPanel Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="0" Orientation="Horizontal">  
        <Label Style="{StaticResource labelStyle}">Name:</Label>  
        <Label Style="{StaticResource labelStyle}" Content="{Binding XPath=@Name}"></Label>  
    </StackPanel>  
  
    <!-- Department -->  
    <StackPanel Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="1" Orientation="Horizontal">  
        <Label Style="{StaticResource labelStyle}">Department:</Label>  
        <Label Style="{StaticResource labelStyle}" Content="{Binding XPath=@Department}"></Label>  
    </StackPanel>    
    ```  
  
     Bu bağlar **etiket** uygun veri kaynağı özelliklerini denetimleri.

1. Aşağıdaki XAML kodu eklemek `<Grid>` öğe:  
  
    ```xaml  
    <!--Templates to display expense report data-->  
    <Grid.Resources>  
        <!-- Reason item template -->  
        <DataTemplate x:Key="typeItemTemplate">  
            <Label Content="{Binding XPath=@ExpenseType}"/>  
        </DataTemplate>  
        <!-- Amount item template -->  
        <DataTemplate x:Key="amountItemTemplate">  
            <Label Content="{Binding XPath=@ExpenseAmount}"/>  
        </DataTemplate>  
    </Grid.Resources>    
    ```  
  
     Bu, harcama raporu verilerinin nasıl görüntüleneceğini tanımlar.

1. Değiştir `<DataGrid>` aşağıdaki öğeyle:  
  
    ```xaml  
    <!-- Expense type and Amount table -->  
    <DataGrid ItemsSource="{Binding XPath=Expense}" ColumnHeaderStyle="{StaticResource columnHeaderStyle}" AutoGenerateColumns="False" RowHeaderWidth="0" >  
  
        <DataGrid.Columns>  
            <DataGridTextColumn Header="ExpenseType" Binding="{Binding XPath=@ExpenseType}"  />  
            <DataGridTextColumn Header="Amount" Binding="{Binding XPath=@ExpenseAmount}" />  
        </DataGrid.Columns>  
  
    </DataGrid>  
    ```  
  
     Bu ekler bir **Itemsource'u** ve gider öğeleri için olan bağlamaları tanımlar.

1. Derleme ve uygulamayı çalıştırın.

1. Bir kişi seçin ve ardından **Görünüm** düğmesi.
  
     Aşağıdaki çizimde denetimleri, düzen, stiller, veri bağlama ve uygulanan veri şablonları ile ExpenseIt uygulamasının her iki sayfa gösterir.
  
     ![ExpenseIt örnek ekran görüntüleri](../designers/media/gettingstartedfigure5.png "GettingStartedFigure5")  
  
## <a name="best-practices"></a>Önerilen uygulamalar  

Bu örnek, WPF temelleri gösterilir ve sonuç olarak, uygulama geliştirme en iyi yöntemler izlemez. Kapsamlı WPF ve .NET Framework uygulama geliştirme en iyi uygulamalar için uygun şekilde aşağıdaki konulara bakın:  
  
-   Erişilebilirlik - [en iyi erişilebilirlik uygulamaları](/dotnet/framework/ui-automation/accessibility-best-practices)  
  
-   Güvenlik - [Windows Presentation Foundation güvenliği](/dotnet/framework/wpf/security-wpf)  
  
-   Yerelleştirme - [WPF Genelleştirme ve yerelleştirme genel bakış](/dotnet/framework/wpf/advanced/wpf-globalization-and-localization-overview)  
  
-   Performans - [WPF Uygulama performansı en iyi duruma getirme](/dotnet/framework/wpf/advanced/optimizing-wpf-application-performance)  
  
## <a name="whats-next"></a>Sırada ne var?  

Şimdi WPF kullanarak bir masaüstü uygulaması oluşturmak için tanziminizde çeşitli teknikler vardır. Veri bağlama WPF uygulaması yapı taşlarını temel bir anlayış şimdi olmalıdır. Bu konuda halinde kapsamlı, ancak ayrıca artık umarız bazı bu konudaki teknikleri ötesinde kendi keşfedebilirsiniz olasılıklar duygusu vardır.
  
WPF mimarisi ve programlama modelleri hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [WPF Mimarisi](/dotnet/framework/wpf/advanced/wpf-architecture)  
  
-   [XAML genel bakış](/dotnet/framework/wpf/advanced/xaml-overview-wpf)  
  
-   [Bağımlılık Özelliklerine Genel Bakış](/dotnet/framework/wpf/advanced/dependency-properties-overview)  
  
-   [Düzen sistemi](/dotnet/framework/wpf/advanced/layout)  
  
-   [Stiller ve Şablonlar](/dotnet/framework/wpf/controls/styles-and-templates)  
  
Uygulamaları oluşturma hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Uygulama geliştirme genel bakış](/dotnet/framework/wpf/app-development/index)  
  
-   [Denetimlerine genel bakış](/dotnet/framework/wpf/controls/index)  
  
-   [Veri Bağlamaya Genel Bakış](/dotnet/framework/wpf/data/data-binding-overview)  
  
-   [WPF grafikler, animasyon ve medya genel bakış](/dotnet/framework/wpf/graphics-multimedia/index)  
  
-   [WPF'deki Belgeler](/dotnet/framework/wpf/advanced/documents-in-wpf)  
  
## <a name="see-also"></a>Ayrıca bkz.

[Windows Presentation Foundation ile Modern Masaüstü Uygulamaları Oluşturma](../designers/create-modern-desktop-applications-with-windows-presentation-foundation.md)
