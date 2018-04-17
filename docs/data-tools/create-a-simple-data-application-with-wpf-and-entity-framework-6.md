---
title: WPF ve Entity Framework 6 ile basit veri uygulaması oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.topic: conceptual
dev_langs:
- CSharp
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 420b0999709f7e419c6c05df18bd03d7a1475b57
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="create-a-simple-data-application-with-wpf-and-entity-framework-6"></a>WPF ve Entity Framework 6 ile basit veri uygulaması oluşturma

Bu walkthough SQL Server yerel veritabanı, Northwind veritabanı, Entity Framework 6 ve Windows Presentation Foundation ile Visual Studio'da bir temel "veriler üzerinde forms" uygulaması oluşturulacağını gösterir. Ana-ayrıntı görünümü ile temel veri bağlaması yapma gösterir ve ayrıca bir özel "bağlama ile düğmeler için"İleri Taşı","Taşı ", başlangıcına Taşı" önceki,""Taşı sona erdirmek,"Gezgini" sahip "Güncelleştir" ve "Silin."  
  
 Bu makalede Visual Studio'da veri araçları kullanarak odaklanır ve tüm derinlemesine temel teknolojileri açıklamak çalışmaz. Bu, XAML, Entity Framework ve SQL temel olarak bilindiğini sahip olduğunuzu varsayar. Bu örnek ayrıca WPF uygulamaları için standart Model-görünüm-görünüm Model (MVVM) mimarisi gösterilmemiştir. Ancak, bu kodu uygulamanıza kendi MVVM çok az değişiklik yapılması açısından kopyalayabilirsiniz.  
  
## <a name="install-and-connect-to-northwind"></a>Yükleme ve Northwind olarak bağlan

Bu örnek, SQL Server Express LocalDB ve Northwind örnek veritabanı kullanır. Bu ürün için ADO.NET veri sağlayıcı Entity Framework destekliyorsa, bu da diğer SQL veritabanı ürünleri ile çalışması gerekir.  

1.  SQL Server Express LocalDB yoksa, araçtan yüklemek [SQL Server Express indirme sayfası](https://www.microsoft.com/sql-server/sql-server-editions-express), aracılığıyla veya **Visual Studio yükleyicisi**. Visual Studio Yükleyicisi'nde, SQL Server Express LocalDB parçası olarak yüklenebilir **.NET masaüstü geliştirme** iş yükü veya tek bir bileşen olarak.

2.  Northwind örnek veritabanı, şu adımları izleyerek yükleyin:  

    1. Visual Studio'da açın **SQL Server Nesne Gezgini** penceresi. (SQL Server Nesne Gezgini parçası olarak yüklü **veri depolama ve işleme** Visual Studio yükleyicisi iş yükündeki.) Genişletme **SQL Server** düğümü. Yerel veritabanı örneğinde sağ tıklatıp **yeni sorgu...** .  

       Sorgu Düzenleyicisi penceresini açar.  

    2. Kopya [Northwind Transact-SQL betiği](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) panonuza. Bu T-SQL betiği sıfırdan Northwind veritabanı oluşturur ve veri ile doldurur.  

    3. T-SQL betiği sorgu düzenleyicisine yapıştırın ve ardından **yürütme** düğmesi.  

       Kısa bir süre sonra sorgu yürütme tamamlandıktan ve Northwind veritabanı oluşturulur.  
  
3.  [Yeni bağlantı ekleme](../data-tools/add-new-connections.md) Northwind için.  
  
## <a name="configure-the-project"></a>Projeyi Yapılandırma
  
1.  Visual Studio'da, **dosya**, **yeni**, **proje...**  ve yeni bir C# WPF uygulaması oluşturun.  
  
2.  Entity Framework 6 için NuGet paketi sonraki ekleyeceğiz. Çözüm Gezgini'nde proje düğümünü seçin. Ana menüde seçin **proje**, **NuGet paketlerini Yönet...**  
  
     ![Menü öğesi NuGet paketlerini Yönet](../data-tools/media/raddata_vs2015_manage_nuget_packages.png "raddata_vs2015_manage_nuget_packages")  
  
3.  NuGet Paket Yöneticisi'nde tıklayın **Gözat** bağlantı. Entity Framework listesinde üst paket olabilir. Tıklatın **yükleme** sağ bölmede ve yönergeleri izleyin. Çıktı penceresi yükleme bittiğinde size bildirir.  
  
     ![Entity Framework NuGet paketi](../data-tools/media/raddata_vs2015_nuget_ef.png "raddata_vs2015_Nuget_EF")  
  
4.  Şimdi biz Northwind veritabanına dayalı bir model oluşturmak için Visual Studio'yu kullanabilirsiniz.  
  
## <a name="create-the-model"></a>Model oluşturma
  
1.  Çözüm Gezgini'nde proje düğümüne sağ tıklayın ve seçin **Ekle**, **yeni öğe...** . Sol bölmede, C# düğümünün altında seçin **veri** ve Orta bölmede seçin **ADO.NET varlık veri modeli**.  
  
     ![Entity Framework modelini yeni proje öğesi](../data-tools/media/raddata-ef-new-project-item.png "raddata EF yeni proje öğesi")  

  2.  Model çağrı `Northwind_model` ve Tamam'ı seçin. Bu işlem sonrasında **varlık veri modeli Sihirbazı**. Seçin **veritabanından EF Designer** ve ardından **sonraki**.  
  
     ![Veritabanından EF modeli](../data-tools/media/raddata-ef-model-from-database.png "raddata veritabanından EF modeli")  
  
3.  Sonraki ekranda, yerel veritabanı Northwind bağlantı tıklatın seçip **sonraki**.  
  
4.  Sihirbazın sonraki sayfasında hangi tabloları, saklı yordamları ve Entity Framework modele dahil edilecek diğer veritabanı nesneleri seçin. Ağaç görünümünde dbo düğümünü genişletin ve müşteriler, siparişler ve sipariş ayrıntıları seçin. İşaretli Varsayılanları bırakabilir ve tıklayın **son**.  
  
     ![Model için veritabanı nesneleri seçin](../data-tools/media/raddata-choose-ef-objects.png "raddata EF nesneleri seçin")  
  
5.  Sihirbaz, Entity Framework modelini temsil eden C# sınıflar oluşturur. Bu düz eski C# sınıflardır ve bunlar şunları yapacağız databind WPF kullanıcı arabirimi. .Edmx dosyasının ilişkileri ve veritabanında nesne sınıfları ilişkilendirir diğer meta verileri açıklar.  Kod oluşturma T4 şablonları model üzerinde çalışır ve değişiklikleri veritabanına kaydetmek .tt dosyalarıdır. Tüm bu dosyalar Çözüm Gezgini'nde Northwind_model düğümü altında görebilirsiniz:  

       ![Çözüm Gezgini EF modeli dosyaları](../data-tools/media/raddata-solution-explorer-ef-model-files.png "raddata Solution Explorer EF modeli dosyaları")  
  
     .Edmx dosyasının Tasarımcı yüzeyine, bazı özellikler ve ilişkiler modelinde değiştirmenize olanak sağlar. Biz bu kılavuzda Tasarımcı kullanacak şekilde yapmayacağınız.  
  
6.  .Tt dosyaları genel amaçlı ve bunlardan birini ObservableCollections gerektiren WPF bağlama ile çalışmak için ince ayar yapmamız gerekir.  Northwind_model.tt bulana kadar Çözüm Gezgini'nde Northwind_model düğümünü genişletin. (Siz olduğundan emin olun **değil** içinde *. Doğrudan .edmx dosyasının bağlam .tt dosyasını).  
  
    -   İki oluşumlarını Değiştir <xref:System.Collections.ICollection> ile <xref:System.Collections.ObjectModel.ObservableCollection%601>.  
  
    -   İlk örneğini değiştirmek <xref:System.Collections.Generic.HashSet%601> ile <xref:System.Collections.ObjectModel.ObservableCollection%601> satır 51 geçici. Hashset'i ikinci oluşum değiştirmeyin  
  
    -   Yalnızca tekrarlamasını değiştirmek <xref:System.Collections.Generic> (etrafında satır 431) ile <xref:System.Collections.ObjectModel>.  
  
7.  Tuşuna **Ctrl + Shift + B** Projeyi derlemek için. Derleme sona erdiğinde, modeli sınıfları için veri kaynağı Sihirbazı görünür.  
  
Şimdi Biz bu model için XAML sayfası böylece biz görüntüleyebilir, gidin ve verileri değiştirme bağlanacağını hazırsınız demektir.  
  
## <a name="databind-the-model-to-the-xaml-page"></a>DataBind XAML sayfası modeli

Kendi veri bağlamasını kod yazmak mümkündür, ancak bunu sizin için Visual Studio izin daha kolaydır.  
  
1.  Ana menüden **Proje > Yeni veri kaynağı Ekle** ortaya çıkarmak için **veri kaynağı Yapılandırma Sihirbazı**. Seçin **nesne** veritabanına model sınıflarına bağlıyorsanız nedeni:  
  
     ![Veri Kaynağı Yapılandırma Sihirbazı nesne kaynağıyla](../data-tools/media/raddata-data-source-configuration-wizard-with-object-source.png "raddata nesne kaynağı ile veri kaynağı Yapılandırma Sihirbazı")  
  
2.  Müşteri seçin.  (Otomatik olarak kaynakları siparişleri için müşteri siparişleri Gezinti özelliğinden oluşturulacak.)  
  
     ![Veri kaynakları olarak varlık sınıfları eklemek](../data-tools/media/raddata-add-entity-classes-as-data-sources.png "raddata Ekle varlık sınıfları veri kaynakları olarak")  
  
3.  Tıklatın **son**  
  
4.  Kod görünümünde MainWindow.xaml gidin. Bu örneğin amaçları doğrultusunda XAML çok basit tutmak olacak. MainWindow başlığını daha tanımlayıcı değiştirmek ve yüksekliğini ve genişliğini 600 x 800 şimdilik artar. Her zaman, daha sonra değiştirebilirsiniz. Şimdi bu üç satır tanımları ana kılavuz, bir müşteri'nin ayrıntılar için bunların siparişleri gösterir kılavuz için bir tane gezinti düğmeleri için bir satır ekleyin:  

    ```xaml  
    <Grid.RowDefinitions>  
            <RowDefinition Height="auto"/>  
            <RowDefinition Height="auto"/>  
            <RowDefinition Height="*"/>  
        </Grid.RowDefinitions>
    ```

5.  Şimdi Tasarımcısı'nda görüntülediğiniz şekilde MainWindow.xaml açın. Bu araç Visual Studio penceresi kenar bir seçenek olarak görünmesi veri kaynakları penceresinden neden olur. Penceresini veya başka sekmesini tıklatın **Shift + Alt + D** veya seçin **Görünüm &#124; diğer pencereler &#124; veri kaynakları**. Kendi tek tek metin kutusuna müşteriler sınıftaki her bir özellik görüntülemek olacak. İlk Müşteriler birleşik giriş kutusu oku tıklatın ve seçin **ayrıntıları**. Böylece ikinci satırda gitmek istediğiniz Tasarımcı bilir düğüm tasarım yüzeyine Orta parça üzerine sürükleyin.  Bu misplace, satır XAML daha sonra el ile belirtebilirsiniz. Varsayılan olarak, denetimleri dikey bir kılavuz öğesi içinde yer alır ancak formda istiyor ancak bu noktada, bunları düzenleyebilirsiniz.  Örneğin, bu adres yukarıda üstte adı metin kutusuna yerleştirmek için mantıklı olabilir. Bu makalede örnek uygulama alanları yeniden sıralar ve iki sütunlara dağıtır.  
  
     ![Müşteriler veri kaynağına bağlama ayrı ayrı denetimler için](../data-tools/media/raddata-customers-data-source-binding-to-individual-controls.png "raddata müşteriler veri kaynağı tek tek denetimlerine bağlama")  
  
     Kod görünümünde şimdi yeni bir görebilirsiniz `Grid` öğesinde satır 1 (Orta satır) üst kılavuz. Kılavuz olan üst bir `DataContext` için eklenen bir CollectionViewSource başvurduğu özniteliği `Windows.Resources` öğesi. İlk metin kutusunda, örneğin, bu veri bağlamı verilen "adı adres için" bağlamalar eşleştirilir `Address` geçerli bir özellik `Customer` CollectionViewSource nesne.  
  
    ```xaml  
    <Grid DataContext="{StaticResource customerViewSource}">  
    ```  

6.  Bir müşteri penceresinin üst yarısında görünür olduğunda, kendi siparişleri alt yarım görmek istiyoruz. Bir tek Izgara Görünümü denetiminde siparişleri göstereceğiz. Ana-ayrıntı databinding beklendiği şekilde çalışması biz müşteriler sınıfında değil ayrı siparişleri düğüme siparişleri özelliğine bağlama önemlidir. Aşağıdaki çizimde dikkat! İsteğe bağlı olarak Tasarımcısı satır 2 koyar böylece müşteriler sınıfın siparişleri özelliği form alt yarısında için sürükleyin:  
  
     ![Kılavuz siparişleri sınıfları sürükleyin](../data-tools/media/raddata-drag-orders-classes-as-grid.png "raddata sürükleme siparişleri kılavuz sınıfları")  
  
7.  Visual Studio kullanıcı Arabirimi denetimlerini modelinde olayları bağlanan tüm bağlama kodu üretti. Biz, bazı verileri görmek için yapmanız gereken tek şey model doldurmak için bazı kodlar yazmak için. İlk şimdi için MainWindow.xaml.cs gidin ve bir veri üyesi veri bağlamı için MainWindow sınıfına ekleyin. Bize oluşturuldu, bu nesne değişiklikleri ve model olayları izleyen bir denetimi gibi davranır. Oluşturucu başlatma mantığı de ekleyeceğiz. Bizim sınıfının üstüne aşağıdaki gibi görünmelidir:  
  
     [!code-csharp[MainWindow#1](../data-tools/codesnippet/CSharp/CreateWPFDataApp/MainWindow.xaml.cs#1)]  
     
     Ekleme bir `using` kapsam içine yük genişletme yöntemi getirmek System.Data.Entity için yönerge:  
  
     ```csharp
     using System.Data.Entity;  
     ```  

     Şimdi aşağıya kaydırın ve Window_Loaded olay işleyicisi bulun. Visual Studio CollectionViewSource nesne bize eklediğini dikkat edin. Bu model oluşturduğumuz yükleyen seçtik NorthwindEntities nesneyi temsil eder. Böylece tüm yöntemi şimdi şöyle kod için Window_Loaded ekleyelim:  

     [!code-csharp[Window_Loaded#2](../data-tools/codesnippet/CSharp/CreateWPFDataApp/MainWindow.xaml.cs#2)]  

8.  Tuşuna **F5**. CollectionViewSource alınmış ilk müşteri ayrıntılarını görmeniz gerekir. Ayrıca, emirleri veri kılavuzunda görmeniz gerekir. Biçimlendirme sağlandığından düzeltmesini harika değil. Diğer kayıtları görüntülemek ve temel CRUD işlemleri yapmak için bir yol da oluşturacağız.  

## <a name="adjust-the-page-design-and-add-grids-for-new-customers-and-orders"></a>Sayfa Tasarımı ayarlamak ve yeni müşteriler ve siparişler için kılavuzları ekleyin

Visual Studio tarafından üretilen varsayılan düzenleme uygulamamız için ideal olmadığından bazı değişiklikler el ile XAML'de vermiyoruz. Biz de "(gerçekten kılavuzları olan) bazı formları" yeni müşteri veya sipariş eklenecek kullanıcının etkinleştirmeniz gerekir. Verilere bağlı olmayan metin kutuları ayrı bir dizi ihtiyacımız yeni müşteri ve sıra eklemeniz mümkün olması için `CollectionViewSource`. Biz işleyici yöntemleri görünür özelliği ayarlanarak kullanıcı belirli bir zamanda görür hangi kılavuz kontrol. Son olarak, her bir sipariş Silinecek kullanıcı etkinleştirmek için siparişleri kılavuzunda her satıra bir Delete düğmesi ekleyeceğiz.  
  
İlk olarak, bu stiller MainWindow.xaml Windows.Resources öğe ekleyin:  
  
```xaml  
<Style x:Key="Label" TargetType="{x:Type Label}" BasedOn="{x:Null}">  
    <Setter Property="HorizontalAlignment" Value="Left"/>  
    <Setter Property="VerticalAlignment" Value="Center"/>  
    <Setter Property="Margin" Value="3"/>  
    <Setter Property="Height" Value="23"/>  
</Style>  
<Style x:Key="CustTextBox" TargetType="{x:Type TextBox}" BasedOn="{x:Null}">  
    <Setter Property="HorizontalAlignment" Value="Right"/>  
    <Setter Property="VerticalAlignment" Value="Center"/>  
    <Setter Property="Margin" Value="3"/>  
    <Setter Property="Height" Value="26"/>  
    <Setter Property="Width" Value="120"/>  
</Style>  
```  
  
Ardından, tüm dış kılavuz bu biçimlendirme ile değiştirin:  
  
```xaml  
<Grid>  
     <Grid.RowDefinitions>  
         <RowDefinition Height="auto"/>  
         <RowDefinition Height="auto"/>  
         <RowDefinition Height="*"/>  
     </Grid.RowDefinitions>   
     <Grid x:Name="existingCustomerGrid" Grid.Row="1" HorizontalAlignment="Left" Margin="5" Visibility="Visible" VerticalAlignment="Top" Background="AntiqueWhite" DataContext="{StaticResource customerViewSource}">  
         <Grid.ColumnDefinitions>  
             <ColumnDefinition Width="Auto" MinWidth="233"/>  
             <ColumnDefinition Width="Auto" MinWidth="397"/>  
         </Grid.ColumnDefinitions>  
         <Grid.RowDefinitions>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
         </Grid.RowDefinitions>  
         <Label Content="Customer ID:" Grid.Row="0" Style="{StaticResource Label}"/>  
         <TextBox x:Name="customerIDTextBox"  Grid.Row="0" Style="{StaticResource CustTextBox}"   
                  Text="{Binding CustomerID, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Company Name:"  Grid.Row="1" Style="{StaticResource Label}"/>  
         <TextBox x:Name="companyNameTextBox"  Grid.Row="1" Style="{StaticResource CustTextBox}"   
                  Text="{Binding CompanyName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Contact Name:"  Grid.Row="2" Style="{StaticResource Label}"/>  
         <TextBox x:Name="contactNameTextBox" Grid.Row="2" Style="{StaticResource CustTextBox}"   
                  Text="{Binding ContactName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Contact Title:"  Grid.Row="3" Style="{StaticResource Label}"/>  
         <TextBox x:Name="contactTitleTextBox" Grid.Row="3" Style="{StaticResource CustTextBox}"   
                  Text="{Binding ContactTitle, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Address:" Grid.Row="4" Style="{StaticResource Label}"/>  
         <TextBox x:Name="addressTextBox" Grid.Row="4" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Address, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="City:" Grid.Column="1" Grid.Row="0"  Style="{StaticResource Label}"/>  
         <TextBox x:Name="cityTextBox" Grid.Column="1" Grid.Row="0" Style="{StaticResource CustTextBox}"   
                  Text="{Binding City, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Country:" Grid.Column="1" Grid.Row="1" Style="{StaticResource Label}"/>  
         <TextBox x:Name="countryTextBox" Grid.Column="1" Grid.Row="1" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Country, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Fax:" Grid.Column="1" Grid.Row="2" Style="{StaticResource Label}"/>  
         <TextBox x:Name="faxTextBox" Grid.Column="1" Grid.Row="2" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Fax, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Phone:" Grid.Column="1" Grid.Row="3" Style="{StaticResource Label}"/>  
         <TextBox x:Name="phoneTextBox" Grid.Column="1" Grid.Row="3" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Phone, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Postal Code:" Grid.Column="1" Grid.Row="4" VerticalAlignment="Center" Style="{StaticResource Label}"/>  
         <TextBox x:Name="postalCodeTextBox" Grid.Column="1" Grid.Row="4" Style="{StaticResource CustTextBox}"   
                  Text="{Binding PostalCode, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Region:" Grid.Column="1" Grid.Row="5" Style="{StaticResource Label}"/>  
         <TextBox x:Name="regionTextBox" Grid.Column="1" Grid.Row="5" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Region, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
     </Grid>  
     <Grid x:Name="newCustomerGrid" Grid.Row="1" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="5" DataContext="{Binding RelativeSource={RelativeSource FindAncestor, AncestorType={x:Type Window}}, Path=newCustomer, UpdateSourceTrigger=Explicit}" Visibility="Collapsed" Background="CornflowerBlue">  
         <Grid.ColumnDefinitions>  
             <ColumnDefinition Width="Auto" MinWidth="233"/>  
             <ColumnDefinition Width="Auto" MinWidth="397"/>  
         </Grid.ColumnDefinitions>  
         <Grid.RowDefinitions>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
         </Grid.RowDefinitions>  
         <Label Content="Customer ID:" Grid.Row="0" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_customerIDTextBox"  Grid.Row="0"  Style="{StaticResource CustTextBox}"   
                  Text="{Binding CustomerID, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Company Name:"  Grid.Row="1" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_companyNameTextBox"  Grid.Row="1" Style="{StaticResource CustTextBox}"   
                  Text="{Binding CompanyName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true }"/>  
         <Label Content="Contact Name:"  Grid.Row="2" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_contactNameTextBox" Grid.Row="2" Style="{StaticResource CustTextBox}"   
                  Text="{Binding ContactName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Contact Title:"  Grid.Row="3" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_contactTitleTextBox" Grid.Row="3" Style="{StaticResource CustTextBox}"   
                  Text="{Binding ContactTitle, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Address:" Grid.Row="4" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_addressTextBox" Grid.Row="4" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Address, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="City:" Grid.Column="1" Grid.Row="0"  Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_cityTextBox" Grid.Column="1" Grid.Row="0" Style="{StaticResource CustTextBox}"   
                  Text="{Binding City, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Country:" Grid.Column="1" Grid.Row="1" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_countryTextBox" Grid.Column="1" Grid.Row="1" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Country, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Fax:" Grid.Column="1" Grid.Row="2" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_faxTextBox" Grid.Column="1" Grid.Row="2" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Fax, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Phone:" Grid.Column="1" Grid.Row="3" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_phoneTextBox" Grid.Column="1" Grid.Row="3" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Phone, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Postal Code:" Grid.Column="1" Grid.Row="4" VerticalAlignment="Center" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_postalCodeTextBox" Grid.Column="1" Grid.Row="4" Style="{StaticResource CustTextBox}"   
                  Text="{Binding PostalCode, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Region:" Grid.Column="1" Grid.Row="5" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_regionTextBox" Grid.Column="1" Grid.Row="5" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Region, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
     </Grid>  
     <Grid x:Name="newOrderGrid" Grid.Row="1" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="5" DataContext="{Binding Path=newOrder, Mode=TwoWay}" Visibility="Collapsed" Background="LightGreen">  
         <Grid.ColumnDefinitions>  
             <ColumnDefinition Width="Auto" MinWidth="233"/>  
             <ColumnDefinition Width="Auto" MinWidth="397"/>  
         </Grid.ColumnDefinitions>  
         <Grid.RowDefinitions>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
         </Grid.RowDefinitions>  
         <Label Content="New Order Form" FontWeight="Bold"/>  
         <Label Content="Employee ID:"  Grid.Row="1" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_employeeIDTextBox" Grid.Row="1" Style="{StaticResource CustTextBox}"   
                  Text="{Binding EmployeeID, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Order Date:"  Grid.Row="2" Style="{StaticResource Label}"/>  
         <DatePicker x:Name="add_orderDatePicker" Grid.Row="2"  HorizontalAlignment="Right" Width="120"  
                 SelectedDate="{Binding OrderDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>  
         <Label Content="Required Date:" Grid.Row="3" Style="{StaticResource Label}"/>  
         <DatePicker x:Name="add_requiredDatePicker" Grid.Row="3" HorizontalAlignment="Right" Width="120"  
                  SelectedDate="{Binding RequiredDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>  
         <Label Content="Shipped Date:"  Grid.Row="4"  Style="{StaticResource Label}"/>  
         <DatePicker x:Name="add_shippedDatePicker"  Grid.Row="4"  HorizontalAlignment="Right" Width="120"  
                 SelectedDate="{Binding ShippedDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>  
         <Label Content="Ship Via:"  Grid.Row="5" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_ShipViaTextBox"  Grid.Row="5" Style="{StaticResource CustTextBox}"   
                  Text="{Binding ShipVia, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Freight"  Grid.Row="6" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_freightTextBox" Grid.Row="6" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Freight, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
     </Grid>  
     <DataGrid x:Name="ordersDataGrid" SelectionUnit="Cell" SelectionMode="Single" AutoGenerateColumns="False" CanUserAddRows="false" IsEnabled="True" EnableRowVirtualization="True" Width="auto" ItemsSource="{Binding Source={StaticResource customerOrdersViewSource}}" Margin="10,10,10,10" Grid.Row="2" RowDetailsVisibilityMode="VisibleWhenSelected">  
         <DataGrid.Columns>  
             <DataGridTemplateColumn>  
                 <DataGridTemplateColumn.CellTemplate>  
                     <DataTemplate>  
                         <Button Content="Delete"  Command="{StaticResource DeleteOrderCommand}" CommandParameter="{Binding}"/>  
                     </DataTemplate>  
                 </DataGridTemplateColumn.CellTemplate>  
             </DataGridTemplateColumn>  
             <DataGridTextColumn x:Name="customerIDColumn" Binding="{Binding CustomerID}" Header="Customer ID" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="employeeIDColumn" Binding="{Binding EmployeeID}" Header="Employee ID" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="freightColumn" Binding="{Binding Freight}" Header="Freight" Width="SizeToHeader"/>  
             <DataGridTemplateColumn x:Name="orderDateColumn" Header="Order Date" Width="SizeToHeader">  
                 <DataGridTemplateColumn.CellTemplate>  
                     <DataTemplate>  
                         <DatePicker SelectedDate="{Binding OrderDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>  
                     </DataTemplate>  
                 </DataGridTemplateColumn.CellTemplate>  
             </DataGridTemplateColumn>  
             <DataGridTextColumn x:Name="orderIDColumn" Binding="{Binding OrderID}" Header="Order ID" Width="SizeToHeader"/>  
             <DataGridTemplateColumn x:Name="requiredDateColumn" Header="Required Date" Width="SizeToHeader">  
                 <DataGridTemplateColumn.CellTemplate>  
                     <DataTemplate>  
                         <DatePicker SelectedDate="{Binding RequiredDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>  
                     </DataTemplate>  
                 </DataGridTemplateColumn.CellTemplate>  
             </DataGridTemplateColumn>  
             <DataGridTextColumn x:Name="shipAddressColumn" Binding="{Binding ShipAddress}" Header="Ship Address" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="shipCityColumn" Binding="{Binding ShipCity}" Header="Ship City" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="shipCountryColumn" Binding="{Binding ShipCountry}" Header="Ship Country" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="shipNameColumn" Binding="{Binding ShipName}" Header="Ship Name" Width="SizeToHeader"/>  
             <DataGridTemplateColumn x:Name="shippedDateColumn" Header="Shipped Date" Width="SizeToHeader">  
                 <DataGridTemplateColumn.CellTemplate>  
                     <DataTemplate>  
                         <DatePicker SelectedDate="{Binding ShippedDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>  
                     </DataTemplate>  
                 </DataGridTemplateColumn.CellTemplate>  
             </DataGridTemplateColumn>  
             <DataGridTextColumn x:Name="shipPostalCodeColumn" Binding="{Binding ShipPostalCode}" Header="Ship Postal Code" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="shipRegionColumn" Binding="{Binding ShipRegion}" Header="Ship Region" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="shipViaColumn" Binding="{Binding ShipVia}" Header="Ship Via" Width="SizeToHeader"/>  
         </DataGrid.Columns>  
     </DataGrid>  
 </Grid>  
```  
  
## <a name="add-buttons-to-navigate-add-update-and-delete"></a>Gidin, ekleme, güncelleştirme ve silme düğmeleri ekleme  

Windows Forms uygulamalarında bir veritabanında satır gezinme ve temel CRUD işlemleri yapmak için düğmeler BindingNavigator nesnesiyle alın. WPF bir BindingNavigator sağlamaz, ancak oluşturmak kolayca. Yatay StackPanel içinde düğmelerle bunu ve biz düğmeleri arkasındaki kodda yöntemlere bağlı komutlarını ilişkilendirmek.  
  
Komut mantığı fours bölümü vardır: (1 komutları, (2 bağlamaları, (3) düğmeleri ve (4) arka plan kodu komut işleyiciler.  
  
### <a name="add-commands-bindings-and-buttons-in-xaml"></a>XAML'de komutları, bağlamaları ve düğme ekleme
  
1.  İlk olarak, komutlar Windows.Resources öğesinin içine bizim MainWindow.xaml dosyasındaki ekleyelim:  
  
    ```xaml  
    <RoutedUICommand x:Key="FirstCommand" Text="First"/>  
    <RoutedUICommand x:Key="LastCommand" Text="Last"/>  
    <RoutedUICommand x:Key="NextCommand" Text="Next"/>  
    <RoutedUICommand x:Key="PreviousCommand" Text="Previous"/>  
    <RoutedUICommand x:Key="DeleteCustomerCommand" Text="Delete Customer"/>  
    <RoutedUICommand x:Key="DeleteOrderCommand" Text="Delete Order"/>  
    <RoutedUICommand x:Key="UpdateCommand" Text="Update"/>  
    <RoutedUICommand x:Key="AddCommand" Text="Add"/>  
    <RoutedUICommand x:Key="CancelCommand" Text="Cancel"/>  
    ```  
  
2.  Bir CommandBinding RoutedUICommand olay arkasındaki kodda bir yöntem eşler. Bu CommandBindings öğe kapanış etiketi Windows.Resources sonra ekleyin:  
  
    ```xaml  
    <Window.CommandBindings>  
        <CommandBinding Command="{StaticResource FirstCommand}" Executed="FirstCommandHandler"/>  
        <CommandBinding Command="{StaticResource LastCommand}" Executed="LastCommandHandler"/>  
        <CommandBinding Command="{StaticResource NextCommand}" Executed="NextCommandHandler"/>  
        <CommandBinding Command="{StaticResource PreviousCommand}" Executed="PreviousCommandHandler"/>  
        <CommandBinding Command="{StaticResource DeleteCustomerCommand}" Executed="DeleteCustomerCommandHandler"/>  
        <CommandBinding Command="{StaticResource DeleteOrderCommand}" Executed="DeleteOrderCommandHandler"/>  
        <CommandBinding Command="{StaticResource UpdateCommand}" Executed="UpdateCommandHandler"/>  
        <CommandBinding Command="{StaticResource AddCommand}" Executed="AddCommandHandler"/>  
        <CommandBinding Command="{StaticResource CancelCommand}" Executed="CancelCommandHandler"/>  
    </Window.CommandBindings>  
    ```  
  
3.  Şimdi şimdi Gezinti ile StackPanel eklemek, ekleme, silme ve güncelleştirme düğmeler. İlk olarak, bu stili için Windows.Resources ekleyin:  
  
    ```xaml  
    <Style x:Key="NavButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">  
        <Setter Property="FontSize" Value="24"/>  
        <Setter Property="FontFamily" Value="Segoe UI Symbol"/>  
        <Setter Property="Margin" Value="2,2,2,0"/>  
        <Setter Property="Width" Value="40"/>  
        <Setter Property="Height" Value="auto"/>  
    </Style>  
    ```  
  
     İkinci olarak, sayfanın üst kısmındaki XAML doğru dış kılavuz öğesi RowDefinitions hemen sonra bu kodu yapıştırın:  
  
    ```xaml  
    <StackPanel Orientation="Horizontal" Margin="2,2,2,0" Height="36" VerticalAlignment="Top" Background="Gainsboro" DataContext="{StaticResource customerViewSource}" d:LayoutOverrides="LeftMargin, RightMargin, TopMargin, BottomMargin">  
        <Button Name="btnFirst" Content="|◄" Command="{StaticResource FirstCommand}" Style="{StaticResource NavButton}"  />  
        <Button Name="btnPrev" Content="◄" Command="{StaticResource PreviousCommand}" Style="{StaticResource NavButton}"/>  
        <Button Name="btnNext" Content="►" Command="{StaticResource NextCommand}" Style="{StaticResource NavButton}"/>  
        <Button Name="btnLast" Content="►|" Command="{StaticResource LastCommand}" Style="{StaticResource NavButton}"/>  
        <Button Name="btnDelete" Content="Delete Customer" Command="{StaticResource DeleteCustomerCommand}" FontSize="11" Width="120" Style="{StaticResource NavButton}"/>  
        <Button Name="btnAdd" Content="New Customer" Command="{StaticResource AddCommand}" FontSize="11" Width="80" Style="{StaticResource NavButton}"/>  
        <Button Content="New Order" Name="btnNewOrder" FontSize="11" Width="80" Style="{StaticResource NavButton}" Click="NewOrder_click"/>  
        <Button Name="btnUpdate" Content="Commit" Command="{StaticResource UpdateCommand}" FontSize="11" Width="80" Style="{StaticResource NavButton}"/>  
        <Button Content="Cancel" Name="btnCancel" Command="{StaticResource CancelCommand}" FontSize="11" Width="80" Style="{StaticResource NavButton}"/>  
    </StackPanel>  
    ```  
  
### <a name="add-command-handlers-to-the-mainwindow-class"></a>Komut işleyicileri MainWindow sınıfına ekleyin  
  
Arka plan kodu dışında Ekle ve Sil yöntemlerini düzeydedir. Gezinti CollectionViewSource görünüm özellikte yöntemleri çağırma gerçekleştirilir. DeleteOrderCommandHandler bir siparişte art arda silme gerçekleştirmek nasıl gösterir. Biz öncelikle kendisiyle ilişkili Order_Details silmeniz gerekir. UpdateCommandHandler yeni müşteri veya sipariş koleksiyona ekler, aksi takdirde yalnızca kullanıcı metin kutularına yapılan değişiklikleri bir var olan müşteri veya sipariş güncelleştirir.  
  
Bu işleyici yöntemleri MainWindow.xaml.cs MainWindow sınıfında ekleyin. Ardından, CollectionViewSource Müşteriler tablosu için farklı bir ad varsa, bu yöntemlerin her biri adı ayarlamak gerekir:  
  
[!code-csharp[CommandHandlers#3](../data-tools/codesnippet/CSharp/CreateWPFDataApp/MainWindow.xaml.cs#3)]  
  
## <a name="run-the-application"></a>Uygulamayı çalıştırın

Hata ayıklama başlatmak için basın **F5**. Müşteri ve sipariş veri kılavuzunda doldurulmuş görmeniz gerekir ve Gezinti düğmelerinin beklendiği gibi çalışması gerekir. "Verileri girdikten sonra yeni müşteri veya sipariş modele eklemek için üzerinde yürütme"'i tıklatın. Yeni müşteri ya da yeni sipariş formu dışında verileri kaydetmeden yedeklemek için "İptal"'i tıklatın. Var olan müşteriler ve metin kutularındaki doğrudan siparişleri düzenlemeleri yapın ve bu değişiklikleri modeline otomatik olarak yazılır.  
  
## <a name="see-also"></a>Ayrıca bkz.

[.NET için Visual Studio veri araçları](../data-tools/visual-studio-data-tools-for-dotnet.md)  
[Entity Framework belgelerine](/ef/)