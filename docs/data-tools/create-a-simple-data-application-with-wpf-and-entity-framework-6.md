---
title: WPF ve Entity Framework 6 ile basit veri uygulaması oluşturma
ms.date: 08/22/2017
ms.topic: conceptual
dev_langs:
- CSharp
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: c39546d48cd8b8bf71594685f944751c1f023750
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37117816"
---
# <a name="create-a-simple-data-application-with-wpf-and-entity-framework-6"></a>WPF ve Entity Framework 6 ile basit veri uygulaması oluşturma

Bu kılavuzda Visual Studio'da bir temel "veriler üzerinde forms" uygulaması oluşturulacağını gösterir. Uygulama, SQL Server yerel veritabanı, Northwind veritabanı, Entity Framework 6 ve Windows Presentation Foundation kullanır. Ana-ayrıntı görünümü ile temel veri bağlaması yapma gösterir ve ayrıca özel bağlama Gezgini için düğmelerle birlikte sahip **taşıma sonraki**, **taşıma önceki**, **taşımabaşlayaniçin**, **Sonuna taşı**, **güncelleştirme** ve **silmek**.

Bu makalede Visual Studio'da veri araçları kullanarak odaklanır ve tüm derinlemesine temel teknolojileri açıklamak çalışmaz. Bu, XAML, Entity Framework ve SQL temel olarak bilindiğini sahip olduğunuzu varsayar. Bu örnek ayrıca WPF uygulamaları için standart Model View ViewModel (MVVM) mimarisi gösterilmemiştir. Ancak, bu kodu uygulamanıza kendi MVVM birkaç değişiklik yapılması açısından kopyalayabilirsiniz.

## <a name="install-and-connect-to-northwind"></a>Yükleme ve Northwind olarak bağlan

Bu örnek, SQL Server Express LocalDB ve Northwind örnek veritabanı kullanır. Bu ürün için ADO.NET veri sağlayıcı Entity Framework destekliyorsa, bu da diğer SQL veritabanı ürünleri ile çalışması gerekir.

1.  SQL Server Express LocalDB yoksa, araçtan yüklemek [SQL Server Express indirme sayfası](https://www.microsoft.com/sql-server/sql-server-editions-express), aracılığıyla veya **Visual Studio yükleyicisi**. İçinde **Visual Studio yükleyicisi**, bir parçası olarak SQL Server Express LocalDB yükleyebilirsiniz **.NET masaüstü geliştirme** iş yükü veya tek bir bileşen olarak.

2.  Northwind örnek veritabanı, şu adımları izleyerek yükleyin:

    1. Visual Studio'da açın **SQL Server Nesne Gezgini** penceresi. (**SQL Server Nesne Gezgini** parçası olarak yüklenen **veri depolama ve işleme** iş yükü **Visual Studio yükleyicisi**.) Genişletme **SQL Server** düğümü. Yerel veritabanı örneğinde sağ tıklatıp **yeni sorgu**.

       Sorgu Düzenleyicisi penceresini açar.

    2. Kopya [Northwind Transact-SQL betiği](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) panonuza. Bu T-SQL betiği sıfırdan Northwind veritabanı oluşturur ve veri ile doldurur.

    3. T-SQL betiği sorgu düzenleyicisine yapıştırın ve ardından **yürütme** düğmesi.

       Kısa bir süre sonra sorgu tamamlanır ve Northwind veritabanı oluşturulur.

3.  [Yeni bağlantı ekleme](../data-tools/add-new-connections.md) Northwind için.

## <a name="configure-the-project"></a>Projeyi Yapılandırma

1.  Visual Studio'da, **dosya** > **yeni** > **proje** ve yeni bir C# WPF uygulaması oluşturun.

2.  Ardından, Entity Framework 6 için NuGet paketini ekleyin. İçinde **Çözüm Gezgini**, proje düğümünü seçin. Ana menüde seçin **proje** > **NuGet paketlerini Yönet**.

     ![Menü öğesi NuGet paketlerini Yönet](../data-tools/media/raddata_vs2015_manage_nuget_packages.png)

3.  İçinde **NuGet Paket Yöneticisi**, tıklayın **Gözat** bağlantı. Entity Framework listesinde üst paket olabilir. Tıklatın **yükleme** sağ bölmede ve yönergeleri izleyin. Çıktı penceresi yüklemeyi tamamladığında söyler.

     ![Entity Framework NuGet paketi](../data-tools/media/raddata_vs2015_nuget_ef.png)

4.  Şimdi Northwind veritabanına dayalı bir model oluşturmak için Visual Studio'yu kullanabilirsiniz.

## <a name="create-the-model"></a>Model oluşturma

1.  Çözüm Gezgini'nde proje düğümüne sağ tıklayın ve seçin **Ekle** > **yeni öğe**. Sol bölmede, C# düğümünün altında seçin **veri** ve orta bölmesinde seçin **ADO.NET varlık veri modeli**.

     ![Entity Framework modelini yeni proje öğesi](../data-tools/media/raddata-ef-new-project-item.png)

  2.  Model çağrısı `Northwind_model` ve **Tamam**. **Varlık veri modeli Sihirbazı** açar. Seçin **veritabanından EF Designer** ve ardından **sonraki**.

     ![Veritabanından EF modeli](../data-tools/media/raddata-ef-model-from-database.png)

3.  Sonraki ekranda, yerel veritabanı Northwind bağlantı tıklatın seçip **sonraki**.

4.  Sihirbazın sonraki sayfasında, hangi tabloları, saklı yordamları ve Entity Framework modele dahil edilecek diğer veritabanı nesneleri seçin. Ağaç görünümünde dbo düğümünü genişletin ve seçin **müşteriler**, **siparişleri**, ve **sipariş ayrıntılarını**. İşaretli Varsayılanları bırakabilir ve tıklayın **son**.

     ![Model için veritabanı nesneleri seçin](../data-tools/media/raddata-choose-ef-objects.png)

5.  Sihirbaz, Entity Framework modelini temsil eden C# sınıflar oluşturur. Sınıfları düz eski C# sınıflardır ve bunların hangi biz databind WPF kullanıcı arabirimi. *.Edmx* ilişkileri ve veritabanında nesne sınıfları ilişkilendirir diğer meta veri dosyası açıklar. *.Tt* veritabanına yapılan değişiklikleri kaydedin ve model üzerinde çalışır kodunu oluşturmak T4 şablonları dosyalarıdır. Bu tüm dosyalarda görebilirsiniz **Çözüm Gezgini** Northwind_model düğümü altında:

       ![Çözüm Gezgini EF modeli dosyaları](../data-tools/media/raddata-solution-explorer-ef-model-files.png)

     İçin tasarımcı yüzeyine *.edmx* dosya bazı özellikler ve ilişkiler modelinde değiştirmenize olanak sağlar. Biz bu kılavuzda Tasarımcı kullanacak şekilde yapmayacağınız.

6.  *.Tt* dosyalar genel amaçlı ve bunlardan birini ObservableCollections gerektiren WPF bağlama ile çalışmak için ince ayar gerekir. İçinde **Çözüm Gezgini**, bulana kadar Northwind_model düğümünü *Northwind_model.tt*. (Değilsinizdir emin *. Context.tt* doğrudan aşağıdaki dosya *.edmx* dosyası.)

    -   İki oluşumlarını Değiştir <xref:System.Collections.ICollection> ile <xref:System.Collections.ObjectModel.ObservableCollection%601>.

    -   İlk örneğini değiştirmek <xref:System.Collections.Generic.HashSet%601> ile <xref:System.Collections.ObjectModel.ObservableCollection%601> satır 51 geçici. Hashset'i ikinci oluşum değiştirmeyin.

    -   Yalnızca tekrarlamasını değiştirmek <xref:System.Collections.Generic> (etrafında satır 431) ile <xref:System.Collections.ObjectModel>.

7.  Tuşuna **Ctrl**+**Shift**+**B** Projeyi derlemek için. Derleme sona erdiğinde, modeli sınıfları için veri kaynağı Sihirbazı görünür.

Şimdi bu model için XAML sayfası görüntüleyebilir, gidin ve verileri değiştirme bağlanacağını hazırsınız demektir.

## <a name="databind-the-model-to-the-xaml-page"></a>DataBind XAML sayfası modeli

Kendi veri bağlamasını kod yazmak mümkündür, ancak bunu sizin için Visual Studio izin daha kolaydır.

1.  Ana menüden **proje** > **yeni veri kaynağı Ekle** ortaya çıkarmak için **veri kaynağı Yapılandırma Sihirbazı**. Seçin **nesne** veritabanına modeli sınıfları bağlama nedeni:

     ![Nesne kaynağı ile veri kaynağı Yapılandırma Sihirbazı](../data-tools/media/raddata-data-source-configuration-wizard-with-object-source.png)

2.  Seçin **müşteri**. (Siparişleri için kaynakları otomatik olarak müşteri siparişleri Gezinti özelliğinden oluşturulur.)

     ![Veri kaynakları olarak varlık sınıfları ekleme](../data-tools/media/raddata-add-entity-classes-as-data-sources.png)

3.  **Son**'a tıklayın.

4.  Gidin *MainWindow.xaml* kod görünümünde. Biz XAML bu örneğin amaçları doğrultusunda basitliğini. MainWindow başlığını daha tanımlayıcı değiştirmek ve yüksekliğini ve genişliğini 600 x 800 şimdilik artar. Her zaman, daha sonra değiştirebilirsiniz. Şimdi bu üç satır tanımları ekleme ana kılavuz, gezinti düğmelerini, bir müşteri'nin ayrıntılar için ve biri, emirleri gösterir kılavuz için bir satır için:

    ```xaml
    <Grid.RowDefinitions>
            <RowDefinition Height="auto"/>
            <RowDefinition Height="auto"/>
            <RowDefinition Height="*"/>
        </Grid.RowDefinitions>
    ```

5.  Şimdi açmak *MainWindow.xaml* böylece Tasarımcısı'nda görüntülüyorsunuz. Bu neden **veri kaynakları** Visual Studio penceresi kenar boşluğunda bir seçenek olarak yanına görünmesini penceresi **araç**. Penceresini veya başka sekmesini tıklatın **Shift**+**Alt**+**D** veya seçin **Görünüm**  >  **Diğer Windows** > **veri kaynakları**. Kendi tek tek metin kutusuna müşteriler sınıftaki her bir özellik görüntülemek olacak. İlk olarak, oku tıklatın **müşteriler** birleşik giriş kutusu ve seçin **ayrıntıları**. Ardından, Orta satırda gitmek istediğiniz Tasarımcı bilir şekilde düğüm tasarım yüzeyine Orta parça üzerine sürükleyin. Bu misplace, satır XAML daha sonra el ile belirtebilirsiniz. Varsayılan olarak, denetimleri dikey bir kılavuz öğesi içinde yer alır ancak formda istiyor ancak bu noktada, bunları düzenleyebilirsiniz. Örneğin, bunu put mantıklı olabilir **adı** adresi yukarıda üstte metin kutusu. Bu makalede örnek uygulama alanları yeniden sıralar ve iki sütunlara dağıtır.

     ![Müşteriler veri kaynağı tek tek denetimlerine bağlama](../data-tools/media/raddata-customers-data-source-binding-to-individual-controls.png)

     Kod görünümünde şimdi yeni bir görebilirsiniz `Grid` öğesinde satır 1 (Orta satır) üst kılavuz. Kılavuz olan üst bir `DataContext` eklenmiş bir CollectionViewSource başvurduğu özniteliği `Windows.Resources` öğesi. İlk metin kutusunu bağlar, bu veri bağlamı verilen **adresi**, bu adı eşlenmiş `Address` geçerli bir özellik `Customer` CollectionViewSource nesne.

    ```xaml
    <Grid DataContext="{StaticResource customerViewSource}">
    ```

6.  Bir müşteri penceresinin üst yarısında görünür olduğunda, emirleri alt yarım görmek istiyorsunuz. Bir tek Izgara Görünümü denetiminde siparişleri gösterir. Ana-ayrıntı databinding beklendiği şekilde çalışması ayrı bir sipariş düğümü için müşteriler sınıfı siparişleri özelliğinde bağlamak önemlidir. İsteğe bağlı olarak Tasarımcısı satır 2 koyar böylece müşteriler sınıfın siparişleri özelliği form alt yarısında için sürükleyin:

     ![Kılavuz siparişleri sınıfları sürükleyin](../data-tools/media/raddata-drag-orders-classes-as-grid.png)

7.  Visual Studio kullanıcı Arabirimi denetimlerini modelinde olayları bağlanan tüm bağlama kodu üretti. Bazı verileri görmek için gerçekleştirmeniz gereken tek şey model doldurmak için biraz kod yazalım. İlk olarak, gitmek *MainWindow.xaml.cs* ve veri üyesi veri bağlamı için MainWindow sınıfına ekleyin. Sizin için oluşturuldu, bu nesne değişiklikleri ve model olayları izleyen bir denetimi gibi davranır. Ayrıca oluşturucu başlatma mantığı ekleyeceksiniz. Sınıfının üstüne aşağıdaki gibi görünmelidir:

     [!code-csharp[MainWindow#1](../data-tools/codesnippet/CSharp/CreateWPFDataApp/MainWindow.xaml.cs#1)]

     Ekleme bir `using` kapsam içine yük genişletme yöntemi getirmek System.Data.Entity için yönerge:

     ```csharp
     using System.Data.Entity;
     ```

     Şimdi, aşağı kaydırın ve Bul `Window_Loaded` olay işleyicisi. Visual Studio CollectionViewSource nesne ekledi dikkat edin. Bu model oluştururken seçtiğiniz NorthwindEntities nesneyi temsil eder. Kod ekleyelim `Window_Loaded` böylece tüm yöntemi şimdi şöyle görünür:

     [!code-csharp[Window_Loaded#2](../data-tools/codesnippet/CSharp/CreateWPFDataApp/MainWindow.xaml.cs#2)]

8.  Tuşuna **F5**. CollectionViewSource alınmış ilk müşteri ayrıntılarını görmeniz gerekir. Ayrıca, emirleri veri kılavuzunda görmeniz gerekir. Biçimlendirme sağlandığından düzeltmesini harika değil. Diğer kayıtları görüntülemek ve temel CRUD işlemleri yapmak için bir yol da oluşturabilirsiniz.

## <a name="adjust-the-page-design-and-add-grids-for-new-customers-and-orders"></a>Sayfa Tasarımı ayarlamak ve yeni müşteriler ve siparişler için kılavuzları ekleyin

Visual Studio tarafından üretilen varsayılan düzenleme, uygulamanız için ideal olmadığından, bazı değişiklikler el ile XAML'de hale getireceğiz. Ayrıca yeni müşteri veya sipariş eklenecek kullanıcıyı etkinleştirmek için "(gerçekten kılavuzları olan) bazı formları" gerekir. Yeni müşteri ve sıra eklemeniz mümkün olması için verilere bağlı olmayan metin kutuları ayrı bir dizi gereksinim `CollectionViewSource`. İşleyici yöntemleri görünür özelliği ayarlanarak kullanıcı belirli bir zamanda görür hangi kılavuz kontrol. Son olarak, her bir sipariş Silinecek kullanıcı etkinleştirmek için siparişleri kılavuzunda her satıra bir Delete düğmesi ekleyin.

İlk olarak, bu stiller ekleyin `Windows.Resources` öğesinde *MainWindow.xaml*:

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
         <TextBox x:Name="customerIDTextBox" Grid.Row="0" Style="{StaticResource CustTextBox}"
                  Text="{Binding CustomerID, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Company Name:" Grid.Row="1" Style="{StaticResource Label}"/>
         <TextBox x:Name="companyNameTextBox" Grid.Row="1" Style="{StaticResource CustTextBox}"
                  Text="{Binding CompanyName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Contact Name:" Grid.Row="2" Style="{StaticResource Label}"/>
         <TextBox x:Name="contactNameTextBox" Grid.Row="2" Style="{StaticResource CustTextBox}"
                  Text="{Binding ContactName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Contact Title:" Grid.Row="3" Style="{StaticResource Label}"/>
         <TextBox x:Name="contactTitleTextBox" Grid.Row="3" Style="{StaticResource CustTextBox}"
                  Text="{Binding ContactTitle, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Address:" Grid.Row="4" Style="{StaticResource Label}"/>
         <TextBox x:Name="addressTextBox" Grid.Row="4" Style="{StaticResource CustTextBox}"
                  Text="{Binding Address, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="City:" Grid.Column="1" Grid.Row="0" Style="{StaticResource Label}"/>
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
         <TextBox x:Name="add_customerIDTextBox" Grid.Row="0" Style="{StaticResource CustTextBox}"
                  Text="{Binding CustomerID, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Company Name:" Grid.Row="1" Style="{StaticResource Label}"/>
         <TextBox x:Name="add_companyNameTextBox" Grid.Row="1" Style="{StaticResource CustTextBox}"
                  Text="{Binding CompanyName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true }"/>
         <Label Content="Contact Name:" Grid.Row="2" Style="{StaticResource Label}"/>
         <TextBox x:Name="add_contactNameTextBox" Grid.Row="2" Style="{StaticResource CustTextBox}"
                  Text="{Binding ContactName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Contact Title:" Grid.Row="3" Style="{StaticResource Label}"/>
         <TextBox x:Name="add_contactTitleTextBox" Grid.Row="3" Style="{StaticResource CustTextBox}"
                  Text="{Binding ContactTitle, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="Address:" Grid.Row="4" Style="{StaticResource Label}"/>
         <TextBox x:Name="add_addressTextBox" Grid.Row="4" Style="{StaticResource CustTextBox}"
                  Text="{Binding Address, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>
         <Label Content="City:" Grid.Column="1" Grid.Row="0" Style="{StaticResource Label}"/>
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
                         <Button Content="Delete" Command="{StaticResource DeleteOrderCommand}" CommandParameter="{Binding}"/>
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

Windows Forms uygulamalarında bir veritabanında satır gezinme ve temel CRUD işlemleri yapmak için düğmeler BindingNavigator nesnesiyle alın. WPF bir BindingNavigator sağlamaz, ancak oluşturmak kolayca. Yatay StackPanel içinde düğmelerle bunun ve düğmeleri arkasındaki kodda yöntemlere bağlı komutları ile ilişkilendirin.

Komut mantığı fours bölümü vardır: (1 komutları, (2 bağlamaları, (3) düğmeleri ve (4) arka plan kodu komut işleyiciler.

### <a name="add-commands-bindings-and-buttons-in-xaml"></a>XAML'de komutları, bağlamaları ve düğme ekleme

1.  İlk olarak, komutlar ekleyin *MainWindow.xaml* içinde dosya `Windows.Resources` öğe:

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

2.  Bir CommandBinding eşleyen bir `RoutedUICommand` bir yönteme arkasındaki kodda olay. Bu ekleme `CommandBindings` öğeden sonra `Windows.Resources` kapanış etiketi:

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

3.  Şimdi, ekleyin `StackPanel` Gezinti ile ekleme, silme ve güncelleştirme düğmeler. İlk olarak, bu stile `Windows.Resources`:

    ```xaml
    <Style x:Key="NavButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">
        <Setter Property="FontSize" Value="24"/>
        <Setter Property="FontFamily" Value="Segoe UI Symbol"/>
        <Setter Property="Margin" Value="2,2,2,0"/>
        <Setter Property="Width" Value="40"/>
        <Setter Property="Height" Value="auto"/>
    </Style>
    ```

     İkinci olarak, bu kodu yapıştırın hemen sonra `RowDefinitions` dış için `Grid` XAML sayfanın üstünde doğru öğe:

    ```xaml
    <StackPanel Orientation="Horizontal" Margin="2,2,2,0" Height="36" VerticalAlignment="Top" Background="Gainsboro" DataContext="{StaticResource customerViewSource}" d:LayoutOverrides="LeftMargin, RightMargin, TopMargin, BottomMargin">
        <Button Name="btnFirst" Content="|◄" Command="{StaticResource FirstCommand}" Style="{StaticResource NavButton}"/>
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

Arka plan kodu dışında Ekle ve Sil yöntemlerini düzeydedir. Gezinti CollectionViewSource görünüm özellikte yöntemleri çağırma gerçekleştirilir. `DeleteOrderCommandHandler` Bir siparişte art arda silme gerçekleştirmek nasıl gösterir. Biz öncelikle kendisiyle ilişkili Order_Details silmeniz gerekir. `UpdateCommandHandler` Yeni müşteri veya sipariş koleksiyona ekler, aksi takdirde yalnızca kullanıcı metin kutularına yapılan değişiklikleri bir var olan müşteri veya sipariş güncelleştirir.

MainWindow sınıfta bu işleyici yöntemleri eklemek *MainWindow.xaml.cs*. Ardından, CollectionViewSource Müşteriler tablosu için farklı bir ad varsa, bu yöntemlerin her biri adı ayarlamak gerekir:

[!code-csharp[CommandHandlers#3](../data-tools/codesnippet/CSharp/CreateWPFDataApp/MainWindow.xaml.cs#3)]

## <a name="run-the-application"></a>Uygulamayı çalıştırın

Hata ayıklama başlatmak için basın **F5**. Müşteri ve sipariş veri kılavuzunda doldurulmuş görmeniz gerekir ve Gezinti düğmelerinin beklendiği gibi çalışması gerekir. Tıklayın **yürütme** verileri girdikten sonra yeni müşteri veya sipariş modele eklemek için. Tıklayın **iptal** verileri kaydetmeden yeni müşteri ya da yeni sipariş formu dışında yedeklenir. Var olan müşteriler ve metin kutularındaki doğrudan siparişleri düzenlemeleri yapın ve bu değişiklikleri modeline otomatik olarak yazılır.

## <a name="see-also"></a>Ayrıca bkz.

- [.NET için Visual Studio veri araçları](../data-tools/visual-studio-data-tools-for-dotnet.md)
- [Entity Framework belgelerine](/ef/)