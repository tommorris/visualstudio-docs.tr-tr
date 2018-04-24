---
title: L2DBForm.XAML kaynak kodu
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: sample
ms.assetid: 624e96d4-6d27-4195-8ac2-2f3835f6c57e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 70e367342afa442e6e3af83de99c9559baa44892
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="l2dbformxaml-source-code"></a>L2DBForm.XAML kaynak kodu

Bu konu içerir ve XAML kaynak dosyası açıklar [kullanarak WPF veri bağlama LINQ'xml örneği için](../designers/wpf-data-binding-using-linq-to-xml-example.md), L2DBForm.xaml.

## <a name="overall-ui-structure"></a>Genel kullanıcı Arabirimi yapısı

Bir WPF projesi için tipik olarak, bu dosya tek bir üst öğe içeren bir <xref:System.Windows.Window> türetilmiş sınıf ile ilişkili XML öğesi `L2XDBFrom` içinde `LinqToXmlDataBinding` ad alanı.

İstemci alanı içinde yer alan bir <xref:System.Windows.Controls.StackPanel> açık mavi arka planı verilir. Bu panoyu dört içeren <xref:System.Windows.Controls.DockPanel> UI bölümlere ayrılmış <xref:System.Windows.Controls.Separator> çubukları. Bu bölümler amacı açıklanan **açıklamalar** içinde [önceki konu](../designers/walkthrough-linqtoxmldatabinding-example.md).

Her bölüm onu tanımlayan bir etiket içerir. İlk iki bölümde bu etiketin 90 derece kullanılarak döndürülür. bir <xref:System.Windows.FrameworkElement.LayoutTransform%2A>. Bölümün geri kalanında bu bölümün amacı uygun kullanıcı Arabirimi öğeleri içerir: metin blokları, metin kutuları, düğmeler ve benzeri. Bazen bir alt <xref:System.Windows.Controls.StackPanel> bu alt denetimleri hizalamak için kullanılır.

## <a name="window-resource-section"></a>Pencere kaynak bölümü

Açılış `<Window.Resources>` etiketi 9 satırındaki penceresi kaynak bölümü başlangıcını gösterir. 35 satırındaki kapanış etiketi ile sona erer.

`<ObjectDataProvider>` Satırları 11 25 aracılığıyla yayılan, etiket bildiren bir <xref:System.Windows.Data.ObjectDataProvider>, adlandırılmış `LoadedBooks`, kullanan bir <xref:System.Xml.Linq.XElement> kaynağı olarak. <xref:System.Xml.Linq.XElement> Katıştırılmış bir XML belgesi ayrıştırarak başlatılır (bir `CDATA` öğesi). Bu boşluk katıştırılmış XML belgesi bildirirken korunur dikkat edin ve ayrıca zaman onu ayrıştırılır. Boşluk, çünkü korunur <xref:System.Windows.Controls.TextBlock> ham XML görüntülemek için kullanılan denetimi sahip hiçbir özel XML özellikleri biçimlendirme.

Son olarak, bir <xref:System.Windows.DataTemplate> adlı `BookTemplate` 34 aracılığıyla 28 satırlarındaki tanımlanır. Bu şablon girişleri görüntülemek için kullanılan **kitap listesi** UI bölümü. Veri bağlama ve LINQ XML dinamik özellikleri kitap kimliği ve aşağıdaki atamaları ile defteri adını almak için kullanır:

```
Text="{Binding Path=Attribute[id].Value}"Text="{Binding Path=Value}"
```

## <a name="data-binding-code"></a>Veri bağlama kodu

Ek olarak <xref:System.Windows.DataTemplate> öğesi, veri bağlama, bu dosyadaki diğer yerler, çeşitli kullanılır.

Açılışında `<StackPanel>` satırında 38, etiket <xref:System.Windows.FrameworkElement.DataContext%2A> bu panelinin özelliği ayarlanmış `LoadedBooks` veri sağlayıcısı.

```
DataContext="{Binding Source={StaticResource LoadedBooks}}
```

Veri bağlamı ayarı mümkün kılar (satırında, 46) için <xref:System.Windows.Controls.TextBlock> adlı `tbRawXml` bu veri sağlayıcısının bağlayarak ham XML görüntülenecek `Xml` özelliği:

```
Text="{Binding Path=Xml}"
```

<xref:System.Windows.Controls.ListBox> İçinde **kitap listesi** UI bölüm 62 aracılığıyla 58 satırlarındaki ayarlar, görüntü öğeleri için şablon `BookTemplate` penceresi kaynak bölümünde tanımlanan:

```
ItemTemplate ="{StaticResource BookTemplate}"
```

Sonra 59 62 aracılığıyla satırlarında bu liste kutusu books gerçek değerler bağlıdır:

```
<ListBox.ItemsSource>
    <Binding Path="Elements[{http://www.mybooks.com}book]"/>
</ListBox.ItemsSource>
```

Üçüncü UI bölüm **Düzenle seçili kitap**, ilk bağlar <xref:System.Windows.FrameworkElement.DataContext%2A> üst <xref:System.Windows.Controls.StackPanel> şu anda seçili öğesinde için **kitap listesi** UI bölümüne (satır 82):

```
DataContext="{Binding ElementName=lbBooks, Path=SelectedItem}"
```

Böylece kitap öğelerini geçerli değerlerini görüntülenecek ve Kimden, iki metin kutusuna bu bölmedeki güncelleştirilmiş sonra iki yönlü veri bağlama kullanır. Veri bağlama Dinamik özellikler için kullanılan veri bağlama için benzer `BookTemplate` veri şablonu:

```
Text="{Binding Path=Attribute[id].Value}"...Text="{Binding Path=Value}"
```

Son kullanıcı Arabirimi bölümde **yeni rehberi Ekle**, veri bağlama kendi XAML kodunda kullanmaz. Bunun yerine, veri bağlama, olay dosyasındaki kodu işleme bulunduğu *L2DBForm.xaml.cs*.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

> [!NOTE]
> Satır numaralarını izlemek daha kolay olması C# kaynak kodu düzenleyicisinde Visual Studio gibi bir kod düzenleyicisine altına aşağıdaki kodu kopyalayın öneririz.

### <a name="code"></a>Kod

```xml
<Window x:Class="LinqToXmlDataBinding.L2XDBForm"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:system="clr-namespace:System;assembly=mscorlib"
    xmlns:xlinq="clr-namespace:System.Xml.Linq;assembly=System.Xml.Linq"
    xmlns:local="clr-namespace:LinqToXmlDataBinding"
    Title="WPF Data Binding using LINQ-to-XML" Height="665" Width="500" ResizeMode="NoResize">

    <Window.Resources>
        <!-- Books provider and inline data -->
        <ObjectDataProvider x:Key="LoadedBooks" ObjectType="{x:Type xlinq:XElement}" MethodName="Parse">
            <ObjectDataProvider.MethodParameters>
                <system:String xml:space="preserve">
<![CDATA[
<books xmlns="http://www.mybooks.com">
  <book id="0">book zero</book>
  <book id="1">book one</book>
  <book id="2">book two</book>
  <book id="3">book three</book>
</books>
]]>
                </system:String>
                <xlinq:LoadOptions>PreserveWhitespace</xlinq:LoadOptions>
            </ObjectDataProvider.MethodParameters>
        </ObjectDataProvider>

        <!-- Template for use in Books List listbox. -->
        <DataTemplate x:Key="BookTemplate">
            <StackPanel Orientation="Horizontal">
                <TextBlock Margin="3" Text="{Binding Path=Attribute[id].Value}"/>
                <TextBlock Margin="3" Text="-"/>
                <TextBlock Margin="3" Text="{Binding Path=Value}"/>
            </StackPanel>
        </DataTemplate>
    </Window.Resources>

    <!-- Main visual content container -->
    <StackPanel Background="lightblue" DataContext="{Binding Source={StaticResource LoadedBooks}}">
        <!-- Raw XML display section -->
        <DockPanel Margin="5">
            <Label  Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" FontWeight="Bold">XML
            <Label.LayoutTransform>
                <RotateTransform Angle="90"/>
            </Label.LayoutTransform>
            </Label>
            <TextBlock Name="tbRawXml" Height="200" Background="LightGray" Text="{Binding Path=Xml}" TextTrimming="CharacterEllipsis" />
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- List box to display all books section -->
        <DockPanel Margin="5">
            <Label  Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" FontWeight="Bold">Book List
                <Label.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </Label.LayoutTransform>
            </Label>
            <ListBox Name="lbBooks" Height="200" Width="415" ItemTemplate ="{StaticResource BookTemplate}">
                <ListBox.ItemsSource>
                    <Binding Path="Elements[{http://www.mybooks.com}book]"/>
                </ListBox.ItemsSource>
            </ListBox>
            <Button Margin="5" DockPanel.Dock="Right" Height="30" Width ="130" Content="Remove Selected Book" Click="OnRemoveBook">
            <Button.LayoutTransform>
                <RotateTransform Angle="90"/>
            </Button.LayoutTransform>
            </Button>
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- Edit current selection section -->
        <DockPanel Margin="5">
            <TextBlock Margin="5" Height="30" Width="65" DockPanel.Dock="Right" Background="LightGray" TextWrapping="Wrap" TextAlignment="Center">
                    Changes are live!
                <TextBlock.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </TextBlock.LayoutTransform>
            </TextBlock>
            <StackPanel>
                <Label Width="450" Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Left" FontWeight="Bold">Edit Selected Book</Label>
                <StackPanel Margin="1" DataContext="{Binding ElementName=lbBooks, Path=SelectedItem}">
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">ID:</Label>
                        <TextBox Name="editAttributeTextBox" Width="410" Text="{Binding Path=Attribute[id].Value}">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Edit the selected book ID and see it changed.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">Value:</Label>
                        <TextBox Name="editValueTextBox" Width="410" Text="{Binding Path=Value}" Height="25">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Edit the selected book Value and see it changed.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                </StackPanel>
            </StackPanel>
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- Add new book section -->
        <DockPanel Margin="5">
            <Button Margin="5" Height="30" DockPanel.Dock="Right" Click ="OnAddBook">Add Book
                <Button.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </Button.LayoutTransform>
            </Button>
            <StackPanel>
                <Label Width="450" Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Left" FontWeight="Bold">Add New Book</Label>
                <StackPanel Margin="1">
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">ID:</Label>
                        <TextBox Name="tbAddID" Width="410">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Enter a book ID and Value pair, then click Add Book.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">Value:</Label>
                        <TextBox Name="tbAddValue" Width="410" Height="25">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="UltraBold" TextAlignment="Center">
                                    <Label>Enter a book ID and Value pair, then click Add Book.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                </StackPanel>
            </StackPanel>
        </DockPanel>
    </StackPanel>
</Window>

```

### <a name="comments"></a>Açıklamalar

C# kaynak kodu WPF UI öğeleriyle ilişkili olay işleyicileri için bkz: [L2DBForm.xaml.cs kaynak kodu](../designers/l2dbform-xaml-cs-source-code.md).

## <a name="see-also"></a>Ayrıca bkz.

- [İzlenecek Yol: LinqToXmlDataBinding Örneği](../designers/walkthrough-linqtoxmldatabinding-example.md)
- [L2DBForm.xaml.cs Kaynak Kodu](../designers/l2dbform-xaml-cs-source-code.md)