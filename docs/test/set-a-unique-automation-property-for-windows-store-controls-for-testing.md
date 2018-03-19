---
title: "Visual Studio'da Test etmek için UWP denetimleri için benzersiz Otomasyon özelliği ayarlama | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- uwp
author: gewarren
ms.openlocfilehash: 473404bbd3bbfbf6b7cd6cee589a98bc1da4746c
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="set-a-unique-automation-property-for-uwp-controls-for-testing"></a>Test etmek için UWP denetimleri için benzersiz Otomasyon özelliği ayarlama

XAML tabanlı UWP uygulamanız için kodlanmış UI testleri çalıştırmak istiyorsanız, her denetim tanımlayan bir benzersiz Otomasyon özelliği olması gerekir.

 Uygulamanızda XAML denetimin türüne göre benzersiz Otomasyon özelliği atayabilirsiniz. Aşağıdaki durumlarda bu benzersiz Otomasyon özelliği atama şöyledir:

-   [Denetimleri statik XAML tanımı](#UniquePropertyWindowsStoreControlsStaticXAML)

-   [Visual Studio için Visual Studio veya Blend kullanarak benzersiz Otomasyon özelliklerini atayın](#UniquePropertyWindowsStoreControlsExpressionBlend)

-   [Bir DataTemplate kullanın](#UniquePropertyWindowsStoreControlsDataTemplate)

-   [Bir denetim şablonu kullanın](#UniquePropertyWindowsStoreControlsControlTemplate)

-   [Dinamik denetimleri](#UniquePropertyWindowsStoreControlsDynamicControls)

## <a name="use-methods-to-assign-a-unique-automation-property"></a>Yöntemleri benzersiz Otomasyon özelliği atamak için kullan

###  <a name="UniquePropertyWindowsStoreControlsStaticXAML"></a> Statik XAML tanımı
 XAML dosyanızda tanımlanan bir denetim için benzersiz Otomasyon özelliği belirtmek için AutomationProperties.AutomationId veya AutomationProperties.Name örtük veya açık olarak, aşağıdaki örneklerde gösterildiği gibi ayarlayabilirsiniz. Bu değerlerden birini ayarı denetimi kodlanmış UI testi veya eylem kaydetme oluşturduğunuzda denetimi tanımlamak için kullanılan benzersiz Otomasyon özelliği sağlar.

 **Özellik örtük olarak ayarlayın**

AutomationProperties.AutomationId kümesine **ButtonX** Name özelliği XAML'de denetimi için kullanma.

```xaml
<Button Name="ButtonX" Height="31" HorizontalAlignment="Left" Margin="23,26,0,0"  VerticalAlignment="Top" Width="140" Click="ButtonX_Click" />
```

AutomationProperties.Name kümesine **ButtonY** içerik özelliği XAML'de denetimi için kullanma.

```xaml
<Button Content="ButtonY" Height="31" HorizontalAlignment="Left" Margin="23,76,0,0" VerticalAlignment="Top" Width="140" Click="ButtonY_Click" />
```

 **Özelliği açıkça ayarlayın**

 AutomationProperties.AutomationId kümesine **ButtonX** denetiminin XAML'de açıkça.

```xaml
<Button AutomationProperties.AutomationId="ButtonX" Height="31" HorizontalAlignment="Left" Margin="23,26,0,0"  VerticalAlignment="Top" Width="140" Click="ButtonX_Click" />
```

 AutomationProperties.Name kümesine **ButtonY** denetiminin XAML'de açıkça.

```
<Button AutomationProperties.Name="ButtonY" Height="31" HorizontalAlignment="Left" Margin="23,76,0,0" VerticalAlignment="Top" Width="140" Click="ButtonY_Click" />
```

###  <a name="UniquePropertyWindowsStoreControlsExpressionBlend"></a> Visual Studio için Visual Studio veya Blend kullanarak benzersiz Otomasyon özelliklerini atayın
 Düğmeleri, liste kutuları, birleşik giriş kutuları ve metin kutuları gibi etkileşimli öğeler benzersiz adlar atamak için Visual Studio veya Visual Studio için Blend kullanabilirsiniz. Bu denetim AutomationProperties.Name için benzersiz bir değer verir.

 **Visual Studio:** üzerinde **Araçları** menüsündeki **seçenekleri** ve ardından **metin düzenleyici**, ardından **XAML**ve son olarak **Çeşitli**.

 Seçin **oluşturma etkileşimli öğelerde'otomatik olarak ad** ve ardından **Tamam**.

 ![XAML çeşitli seçenekleri](../test/media/cuit_windowsstoreapp_b.png "CUIT_WindowsStoreApp_B")

 **Visual Studio için Blend:** Visual Studio için Blend bunun için aşağıdaki yöntemlerden birini kullanın.

> [!NOTE]
>  Bu gibi durumlarda, bu yöntem yalnızca statik olarak XAML kullanılarak oluşturulmuş denetimler için kullanabilirsiniz.

 **Var olan denetimleri için benzersiz bir ad vermek için**

 Üzerinde **Araçları** menüsünde seçin **adı etkileşimli öğeler**, aşağıda gösterildiği gibi:

 ![Araçlar menüsünden adı etkileşimli öğeler](../test/media/cuit_windowsstoreproperty_blend_1.png "CUIT_WindowsStoreProperty_Blend_1")

 **Otomatik olarak oluşturduğunuz denetimleri için benzersiz bir ad vermek için**

 Üzerinde **Araçları** menüsündeki **seçenekleri**ve ardından **proje**. Seçin **oluşturma etkileşimli öğelerde'otomatik olarak ad** ve ardından **Tamam**, aşağıda gösterildiği gibi:

 ![Ad etkileşimli öğeleri kümesi projeye](../test/media/cuit_windowsstoreproeprty_blend_2.png "CUIT_WindowsStoreProeprty_Blend_2")

###  <a name="UniquePropertyWindowsStoreControlsDataTemplate"></a> Veri şablonu kullanın
 Liste kutusu değerleri aşağıdaki XAML kullanarak değişkenlere bağlamak için ItemTemplate kullanarak basit bir şablon tanımlayabilirsiniz.

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

 Aşağıdaki XAML kullanarak değişkenlere değerler bağlamak için ItemContainerStyle bir şablon da kullanabilirsiniz:

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

 Hem de bu örnekler için ardından Itemsource'u, ToString() yöntemini aşağıdaki kod örneğinde gösterildiği gibi geçersiz kılmanız gerekir. Bu kod AutomationProperties.Name değeri ayarlanır ve bağlama kullanarak her bir veri ilişkili liste öğesi için benzersiz Otomasyon özelliği ayarlanamaz benzersiz olduğundan emin olur. Otomasyon Properties.Name için benzersiz bir değer ayarlanması, bu durumda yeterlidir.

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

###  <a name="UniquePropertyWindowsStoreControlsControlTemplate"></a> Bir denetim şablonu kullanın

Böylece kodu tanımlandığında belirli bir türdeki her örneğini benzersiz Otomasyon özelliği alır, bir denetim şablonu kullanabilirsiniz. Şablon oluşturun, böylece denetim örneğinde benzersiz bir kimliği AutomationProperty bağlar. Bu bağlama ile bir denetim şablonu oluşturmak için bir yaklaşım aşağıdaki XAML gösterir.

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

###  <a name="UniquePropertyWindowsStoreControlsDynamicControls"></a> Dinamik denetimleri
 Kodunuzdan dinamik olarak oluşturulan ve statik olarak ya da XAML dosyaları şablonlarında aracılığıyla oluşturulmamış denetimleri varsa, denetimin içerik veya ad özelliklerini ayarlamanız gerekir. Bu dinamik her denetim benzersiz Otomasyon özelliği sahip olduğundan emin olur. Örneğin, bir liste öğesini seçtiğinizde, görüntülenmesi gerekir bir onay kutusu varsa, aşağıda gösterildiği gibi bu özellikleri ayarlayabilirsiniz:

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

- [Kodlanmış UI Testleriyle Windows UWP Uygulamalarını Test Etme](../test/test-windows-store-8-1-apps-with-coded-ui-tests.md)
