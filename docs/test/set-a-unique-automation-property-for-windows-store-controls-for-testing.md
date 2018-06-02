---
title: Test Etme Amacıyla UWP Denetimleri için Benzersiz Otomasyon Özelliği Ayarlama
ms.date: 05/31/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- uwp
author: gewarren
ms.openlocfilehash: fbb815dc17e8b71efcefee8410faa01df0914e35
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34692362"
---
# <a name="set-a-unique-automation-property-for-uwp-controls-for-testing"></a>Test Etme Amacıyla UWP Denetimleri için Benzersiz Otomasyon Özelliği Ayarlama

XAML tabanlı UWP uygulamanız için kodlanmış UI testleri çalıştırmak istiyorsanız, her denetim benzersiz Otomasyon özelliği tarafından tanımlanması gerekir. Uygulamanızda XAML denetimin türüne göre benzersiz Otomasyon özelliği atayabilirsiniz.

## <a name="static-xaml-definition"></a>Statik XAML tanımı

XAML dosyanızda tanımlanan bir denetim için benzersiz Otomasyon özelliği belirtmek için ayarlayabileceğiniz **AutomationProperties.AutomationId** veya **AutomationProperties.Name** örtük veya açık olarak, Aşağıdaki örneklerde gösterildiği gibi. Bu değerlerden birini ayarı denetimi kodlanmış UI testi veya eylem kaydetme oluşturduğunuzda denetimi tanımlamak için kullanılan benzersiz Otomasyon özelliği sağlar.

### <a name="set-the-property-implicitly"></a>Özellik örtük olarak ayarlayın

Ayarlama **AutomationProperties.AutomationId** için **ButtonX** kullanarak **adı** XAML denetimi için bir özellik.

```xaml
<Button Name="ButtonX" Height="31" HorizontalAlignment="Left" Margin="23,26,0,0"  VerticalAlignment="Top" Width="140" Click="ButtonX_Click" />
```

Ayarlama **AutomationProperties.Name** için **ButtonY** kullanarak **içerik** XAML denetimi için bir özellik.

```xaml
<Button Content="ButtonY" Height="31" HorizontalAlignment="Left" Margin="23,76,0,0" VerticalAlignment="Top" Width="140" Click="ButtonY_Click" />
```

### <a name="set-the-property-explicitly"></a>Özelliği açıkça ayarlayın

Ayarlama **AutomationProperties.AutomationId** için **ButtonX** denetiminin XAML'de açıkça.

```xaml
<Button AutomationProperties.AutomationId="ButtonX" Height="31" HorizontalAlignment="Left" Margin="23,26,0,0"  VerticalAlignment="Top" Width="140" Click="ButtonX_Click" />
```

Ayarlama **AutomationProperties.Name** için **ButtonY** denetiminin XAML'de açıkça.

```
<Button AutomationProperties.Name="ButtonY" Height="31" HorizontalAlignment="Left" Margin="23,76,0,0" VerticalAlignment="Top" Width="140" Click="ButtonY_Click" />
```

## <a name="assign-unique-names"></a>Benzersiz adlar atayın

Visual Studio için Blend'de düğmeleri, liste kutuları, birleşik giriş kutuları ve metin kutuları gibi etkileşimli öğeler benzersiz adlar atamak için bir seçenek belirleyebilirsiniz. Bu denetimler için benzersiz değerler verir **AutomationProperties.Name**.

Mevcut denetimleri benzersiz adlar atamak için seçin **Araçları** > **adı etkileşimli öğeler**.

![Visual Studio için blend'de adı etkileşimli öğeler](../test/media/cuit_windowsstoreproperty_blend_1.png)

Otomatik olarak eklediğiniz yeni denetimleri için benzersiz bir ad vermek için seçin **Araçları** > **seçenekleri** açmak için **seçenekleri** iletişim. Seçin **XAML Tasarımcısı** ve ardından **oluşturma etkileşimli öğelerde'otomatik olarak ad**. Seçin **Tamam** iletişim kutusunu kapatın.

## <a name="use-a-data-template"></a>Veri şablonu kullanın

Basit bir şablon kullanarak tanımlayabilirsiniz **ItemTemplate** değişkenleri için değerleri bir liste kutusunda bağlamak için:

```xaml
<ListBox Name="listBox1" ItemsSource="{Binding Source={StaticResource employees}}">
   <ListBox.ItemTemplate>
      <DataTemplate>
         <StackPanel Orientation="Horizontal">
            <TextBlock Text="{Binding EmployeeName}" />
            <TextBlock Text="{Binding EmployeeID}" />
         </StackPanel>
      </DataTemplate>
   </ListBox.ItemTemplate>
</ListBox>
```

Bir şablonla de kullanabilirsiniz **ItemContainerStyle** değişkenlere değerler bağlamak için:

```xaml
<ListBox Name="listBox1" ItemsSource="{Binding Source={StaticResource employees}}">
   <ListBox.ItemContainerStyle>
      <Style TargetType="ListBoxItem">
         <Setter Property="Template">
            <Setter.Value>
               <ControlTemplate TargetType="ListBoxItem">
                  <Grid>
                     <Button Content="{Binding EmployeeName}" AutomationProperties.AutomationId="{Binding EmployeeID}"/>
                  </Grid>
               </ControlTemplate>
            </Setter.Value>
         </Setter>
      </Style>
   </ListBox.ItemContainerStyle>
</ListBox>
```

Daha sonra hem de bu örnekler için geçersiz kılmalısınız **ToString()** yöntemi **Itemsource'u**, aşağıdaki kod örneğinde gösterildiği gibi. Bu kod, emin yapar **AutomationProperties.Name** değeri ayarlanır ve bağlama kullanarak her veriye bağlı bir liste öğesi için benzersiz Otomasyon özelliği ayarlanamıyor çünkü benzersizdir. İçin benzersiz bir değere ayarlama **Otomasyon Properties.Name** bu durumda yeterlidir.

> [!NOTE]
> Bu yaklaşımı kullanarak, liste öğesinin iç içeriği de çalışan sınıfı içindeki bir dizeye bağlama aracılığıyla ayarlanabilir. Örnekte gösterildiği gibi her liste öğesi içindeki düğme denetim çalışan kimliği olan benzersiz Otomasyon bir kimlik atanır

```csharp
Employee[] employees = new Employee[]
{
   new Employee("john", "4384"),
   new Employee("margaret", "7556"),
   new Employee("richard", "8688"),
   new Employee("george", "1293")
};

listBox1.ItemsSource = employees;

public override string ToString()
{
    return EmployeeName + EmployeeID; // Unique Identification to be set as the AutomationProperties.Name
}
```

## <a name="use-a-control-template"></a>Bir denetim şablonu kullanın

Böylece kodu tanımlandığında belirli bir türdeki her örneğini benzersiz Otomasyon özelliği alır, bir denetim şablonu kullanabilirsiniz. Şablonu oluşturmak için **AutomationProperty** denetim örneğinde benzersiz bir kimliği bağlar. Bu bağlama ile bir denetim şablonu oluşturmak için bir yaklaşım aşağıdaki XAML gösterir:

```xaml
<Style x:Key="MyButton" TargetType="Button">
<Setter Property="Template">
   <Setter.Value>
<ControlTemplate TargetType="Button">
   <Grid>
      <CheckBox HorizontalAlignment="Left" AutomationProperties.AutomationId="{TemplateBinding Content}"></CheckBox>
      <Button Width="90" HorizontalAlignment="Right" Content="{TemplateBinding Content}" AutomationProperties.AutomationId="{TemplateBinding Content}"></Button>
   </Grid>
</ControlTemplate>
   </Setter.Value>
</Setter>
</Style>
```

Bu denetim şablonu kullanarak bir düğme iki örneğini tanımladığınızda, Otomasyon kimliği denetimleri şablonu için benzersiz içerik dizesi aşağıdaki XAML'de gösterildiği şekilde ayarlanır:

```xaml
<Button Content="Button1" Style="{StaticResource MyButton}" Width="140"/>
<Button Content="Button2" Style="{StaticResource MyButton}" Width="140"/>
```

### <a name="dynamic-controls"></a>Dinamik denetimleri

Kodunuz aracılığıyla dinamik olarak oluşturulan ve statik olarak ya da XAML dosyaları şablonlarında aracılığıyla oluşturulmamış denetimleri varsa, ayarlamalısınız **içerik** veya **adı** denetim özelliklerini. Bu dinamik her denetim benzersiz Otomasyon özelliği sahip olduğundan emin olur. Örneğin, bir liste öğesini seçtiğinizde, görüntülenmesi gerekir bir onay kutusu varsa, aşağıda gösterildiği gibi bu özellikleri ayarlayabilirsiniz:

```csharp
private void CreateCheckBox(string txt, StackPanel panel)
{
   CheckBox cb = new CheckBox();
   cb.Content = txt; // Sets the AutomationProperties.Name
   cb.Height = 50;
   cb.Width = 100;
   cb.Name = "DynamicCheckBoxAid"+ txt; // Sets the AutomationProperties.AutomationId
   panel.Children.Add(cb);
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [Kodlanmış UI testleri ile test UWP uygulamaları](../test/test-uwp-app-with-coded-ui-test.md)
