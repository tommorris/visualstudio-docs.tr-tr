---
title: T4 metin şablonları ile çalışma süresi metni oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- Preprocessed Text Template project item
- TextTemplatingFilePreprocessor custom tool
- text templates, TransformText() method
- text templates, generating files at run time
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 30956435c321a45a3a1ee32a305080d35b073293
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="run-time-text-generation-with-t4-text-templates"></a>T4 Metin Şablonları İle Çalışma Süresi Metni Oluşturma

Visual Studio çalışma zamanı metin şablonları kullanarak çalışma zamanında, uygulamanızda metin dizelerini oluşturabilir. Burada uygulama yürütür bilgisayarda Visual Studio mevcut değil. Derleme zamanında çalışma zamanında yürütülen kod şablon oluşturduğundan çalışma zamanı şablonları bazen "metin şablonları ön işlemesi yapılan" olarak adlandırılır.

Her bir şablon metni karışımını aynıdır oluşturulan dize ve program kod parçaları görünür. Program parçaları dize değişken bölümleri için değerler sağlayın ve ayrıca koşullu ve yinelenen bölümleri denetleyin.

Örneğin, aşağıdaki şablonu bir HTML raporu oluşturur bir uygulamada kullanılabilir.

```html
<#@ template language="C#" #>
<html><body>
<h1>Sales for Previous Month</h2>
<table>
    <# for (int i = 1; i <= 10; i++)
       { #>
         <tr><td>Test name <#= i #> </td>
             <td>Test value <#= i * i #> </td> </tr>
    <# } #>
 </table>
This report is Company Confidential.
</body></html>
```

Şablon değişkeni bölümleri program kodu ile değiştirilmiştir HTML sayfası olduğuna dikkat edin. Bu tür bir sayfanın tasarımını HTML sayfası statik prototipi yazarak başlamadan. Ardından Tablo ve değişken diğer bölümleri değişir içerik bir gün sonraki oluşturur program kodu yerine.

Bir şablon kullanarak, uygulama yapar, örneğin, bir uzun dizi yazma deyimi, oranla son formun çıkış görmek daha kolay olur. Çıkış biçimine değişiklik yapmadan daha kolay ve daha güvenilirdir.

## <a name="creating-a-run-time-text-template-in-any-application"></a>Herhangi bir uygulamada bir çalışma zamanı metin şablonu oluşturma

### <a name="to-create-a-run-time-text-template"></a>Çalışma zamanı metin şablonu oluşturmak için

1. Çözüm Gezgini'nde, proje kısayol menüsünden seçin **Ekle**, **yeni öğe**.

2. İçinde **Yeni Öğe Ekle** iletişim kutusunda **çalışma zamanı metin şablonu**. (Visual Basic'te konum altında **ortak öğeler** > **genel**.)

3. Şablon dosyanız için bir ad yazın.

    > [!NOTE]
    > Şablon dosyası adı, oluşturulan kodda bir sınıf adı olarak kullanılır. Bu nedenle, boşluk veya noktalama olmamalıdır.

4. Seçin **eklemek**.

    Yeni bir dosya uzantısına sahip oluşturulan **.tt**. Kendi **özel araç** özelliği ayarlanmış **TextTemplatingFilePreprocessor**. Aşağıdaki satırları içerir:

    ```
    <#@ template language="C#" #>
    <#@ assembly name="System.Core" #>
    <#@ import namespace="System.Linq" #>
    <#@ import namespace="System.Text" #>
    <#@ import namespace="System.Collections.Generic" #>
    ```

## <a name="converting-an-existing-file-to-a-run-time-template"></a>Varolan bir dosyayı bir çalışma zamanı şablonu dönüştürme

Bir şablon oluşturmak için en iyi yolu varolan çıktısı örneği dönüştürmek için ' dir. Örneğin, uygulamanızın HTML dosyaları oluşturur, bir düz HTML dosyası oluşturarak başlatabilirsiniz. Düzgün çalıştığını ve hizmetin görünümünü doğru olduğundan emin olun. Ardından bu Visual Studio projenize ekleyin ve şablona dönüştürebilirsiniz.

### <a name="to-convert-an-existing-text-file-to-a-run-time-template"></a>Var olan bir metin dosyasını bir çalışma zamanı şablonu dönüştürmek için

1. Dosya Visual Studio projenize ekleyin. Çözüm Gezgini'nde proje kısayol menüsünden seçin **Ekle** > **varolan öğeyi**.

2. Dosyanın ayarlamak **özel Araçlar** özelliğine **TextTemplatingFilePreprocessor**. Çözüm Gezgini'nde dosyayı kısayol menüsünden seçin **özellikleri**.

    > [!NOTE]
    > Özellik zaten ayarladıysanız, bu olduğundan emin olun **TextTemplatingFilePreprocessor** ve **TextTemplatingFileGenerator**. Zaten uzantısına sahip bir dosya içeriyorsa bu durum oluşabilir **.tt**.

3. Dosya adı uzantısına değişiklik **.tt**. Bu adım isteğe bağlı olsa da, yanlış bir düzenleyicide dosyayı açmayı önlemenize yardımcı olabilir.

4. Herhangi bir boşluk veya noktalama dosya adı ana bölümünden kaldırın. Örneğin, "My Web Page.tt" yanlış olur, ancak "MyWebPage.tt" doğrudur. Dosya adı, oluşturulan kodda bir sınıf adı olarak kullanılır.

5. Aşağıdaki satırı dosyanın başına ekleyin. Visual Basic projesinde çalışıyorsanız, "C#" "VB" ile değiştirin.

    `<#@ template language="C#" #>`

## <a name="the-content-of-the-run-time-template"></a>Çalışma zamanı şablonu içeriği

### <a name="template-directive"></a>Şablon yönergesi

Dosyasını oluştururken haliyle şablonun ilk satırı tutun:

`<#@ template language="C#" #>`

Language parametresini, projenizin dile bağlıdır.

### <a name="plain-content"></a>Düz içerik

Düzen **.tt** uygulamanızı oluşturmak için istediğiniz metni içeren dosya. Örneğin:

```html
<html><body>
<h1>Sales for January</h2>
<!-- table to be inserted here -->
This report is Company Confidential.
</body></html>
```

### <a name="embedded-program-code"></a>Katıştırılmış program kodu

Program kod arasında ekleyebilirsiniz `<#` ve `#>`. Örneğin:

```csharp
<table>
    <# for (int i = 1; i <= 10; i++)
       { #>
         <tr><td>Test name <#= i #> </td>
             <td>Test value <#= i * i #> </td> </tr>
    <# } #>
 </table>
```

```vb
<table>
<#
    For i As Integer = 1 To 10
#>
    <tr><td>Test name <#= i #> </td>
      <td>Test value <#= i*i #> </td></tr>
<#
    Next
#>
</table>
```

Deyimleri arasında eklenen fark `<# ... #>` ve ifadeler arasına eklenir `<#= ... #>`. Daha fazla bilgi için bkz: [T4 metin şablonu yazma](../modeling/writing-a-t4-text-template.md).

## <a name="using-the-template"></a>Şablon kullanma

### <a name="the-code-built-from-the-template"></a>Şablondan oluşturulan kodu

Kaydettiğinizde **.tt** dosya, bir temsilcisine **.cs** veya **.vb** dosyası oluşturulur. Çözüm Gezgini'nde bu dosyayı görmek için genişletin **.tt** dosya düğümü. Visual Basic projesinde öncelikle seçin **tüm dosyaları göster** Çözüm Gezgini araç çubuğunda.

Şube dosya adında bir yöntem içeren bir parçalı sınıf içerdiğine dikkat edin `TransformText()`. Bu yöntem uygulamanızdan çağırabilirsiniz.

### <a name="generating-text-at-run-time"></a>Çalışma zamanında metin oluşturma

Uygulama kodunuzda bu çağrısıyla kullanarak şablonunuzu içeriğini oluşturabilirsiniz:

```csharp
MyWebPage page = new MyWebPage();
String pageContent = page.TransformText();
System.IO.File.WriteAllText("outputPage.html", pageContent);
```

```vb
Dim page = New My.Templates.MyWebPage
Dim pageContent = page.TransformText()
System.IO.File.WriteAllText("outputPage.html", pageContent)
```

Oluşturulan sınıfın belirli bir ad alanına yerleştirmek için ayarlanmış **özel aracı Namespace** metin şablonu dosyasının özelliği.

### <a name="debugging-runtime-text-templates"></a>Hata ayıklama çalışma zamanı metin şablonları

Hata ayıklama ve çalışma zamanı metin şablonları sıradan kodu aynı şekilde test edin.

Bir metin şablonu bir kesme noktası ayarlayabilirsiniz. Visual Studio'da hata ayıklama modunda uygulama başlatırsanız kod boyunca adım ve her zamanki gibi izleme deyimleri değerlendirin.

### <a name="passing-parameters-in-the-constructor"></a>Oluşturucuda parametreleri geçirme

Genellikle bir şablonu bazı veriler uygulamanın diğer bölümleri içe aktarmanız gerekir. Bu kolaylaştırmak için şablon tarafından oluşturulmuş bir parçalı sınıf kodudur. Aynı sınıfın başka bir bölümünü başka bir dosyaya projenizde oluşturabilirsiniz. Bu dosya bir Oluşturucu parametreleri, özellikleri ve şablonda katıştırılmış bir kod tarafından hem uygulama geri kalanı tarafından erişilen olabilir işlevleri içerebilir.

Örneğin, ayrı bir dosya oluşturabilirsiniz **MyWebPageCode.cs**:

```csharp
partial class MyWebPage
{
    private MyData m_data;
    public MyWebPage(MyData data) { this.m_data = data; }}
```

Şablon dosyası **MyWebPage.tt**, yazma:

```html
<h2>Sales figures</h2>
<table>
<# foreach (MyDataItem item in m_data.Items)
   // m_data is declared in MyWebPageCode.cs
   { #>
      <tr><td> <#= item.Name #> </td>
          <td> <#= item.Value #> </td></tr>
<# } // end of foreach
#>
</table>
```

Bu şablon uygulamada kullanmak için:

```csharp
MyData data = ...;
MyWebPage page = new MyWebPage(data);
String pageContent = page.TransformText();
System.IO.File.WriteAllText("outputPage.html", pageContent);
```

#### <a name="constructor-parameters-in-visual-basic"></a>Visual Basic'te Oluşturucu parametreleri

Visual Basic'te ayrı bir dosya **MyWebPageCode.vb** içerir:

```vb
Namespace My.Templates
  Partial Public Class MyWebPage
    Private m_data As MyData
    Public Sub New(ByVal data As MyData)
      m_data = data
    End Sub
  End Class
End Namespace
```

Şablon dosyası içerebilir:

```html
<#@ template language="VB" #>
<html><body>
<h1>Sales for January</h2>
<table>
<#
    For Each item In m_data.Items
#>
    <tr><td>Test name <#= item.Name #> </td>
      <td>Test value <#= item.Value #> </td></tr>
<#
    Next
#>
</table>
This report is Company Confidential.
</body></html>
```

Şablon çağrılan oluşturucuda parametresini geçirerek:

```vb
Dim data = New My.Templates.MyData
    ' Add data values here ....
Dim page = New My.Templates.MyWebPage(data)
Dim pageContent = page.TransformText()
System.IO.File.WriteAllText("outputPage.html", pageContent)
```

#### <a name="passing-data-in-template-properties"></a>Şablon özelliklerinde veri geçirme

Veri geçirme alternatif bir yol şablonu için bir parçalı sınıf tanımında Şablon sınıfı için genel özellikleri eklemektir. Uygulamanızı çağırmadan önce özellikleri ayarlayabilirsiniz `TransformText()`.

Şablon sınıfınız kısmi tanımında alanlar ekleyebilirsiniz. Bu, şablonun birbirini izleyen yürütmeleri arasında veri iletmek sağlar.

### <a name="use-partial-classes-for-code"></a>Kısmi sınıflar için kodu kullanın

Çoğu geliştiricinin kod büyük gövdeleri şablonlarında yazılmasını engellemek tercih edilir. Bunun yerine, şablon dosyası olarak aynı ada sahip bir parçalı sınıf yöntemlerini tanımlayabilirsiniz. Bu yöntemlerin şablondan çağırın. Bu şekilde, daha fazla şablon gösterir açıkça hedef çıkış dizesi gibi görünecektir. Sonucun görünümü hakkındaki tartışmalara görüntülediği verileri oluşturma mantığından ayrılabilir.

### <a name="assemblies-and-references"></a>Derlemeler ve başvurular

Bir .NET veya diğer derleme gibi başvurmak için şablon kodunuzu istiyorsanız **System.Xml.dll**, projenizin eklemek **başvuruları** normal şekilde.

Aynı şekilde bir ad alanı içe aktarmak istediğiniz bir `using` deyimi, bunu yapabilirsiniz ile `import` yönergesi:

```
<#@ import namespace="System.Xml" #>
```

Bu yönergeleri dosyasının başında hemen sonra yerleştirilmelidir `<#@template` yönergesi.

### <a name="shared-content"></a>Paylaşılan içerik

Çeşitli şablonlar arasında paylaşılan metin varsa, ayrı bir dosyaya yerleştirin ve görünmesi gereken her dosyasına eklenecek:

```
<#@include file="CommonHeader.txt" #>
```

Eklenen içeriğe program kodunu ve düz metin herhangi bir karışımını içerebilir ve diğer içerebilir yönergeleri ve diğer yönergeleri içerir.

INCLUDE yönergesi herhangi bir şablon dosyası veya içerdiği metnin içinde kullanılabilir.

### <a name="inheritance-between-run-time-text-templates"></a>Çalışma zamanı metin şablonları arasındaki devralma

Özet bir temel sınıf şablonu yazarak çalışma zamanı şablonları arasında içerik paylaşabilirsiniz. Kullanım `inherits` parametresinin `<@#template#>` başka bir çalışma zamanı Şablon sınıfı başvurmak için yönergesi.

#### <a name="inheritance-pattern-fragments-in-base-methods"></a>Devralma deseni: parçaları temel yöntemler

Aşağıdaki örnekte kullanılan düzende aşağıdaki noktaları dikkat edin:

- Taban sınıfı `SharedFragments` sınıf özelliği blokları içinde yöntemlerini tanımlar `<#+ ... #>`.

- Taban sınıf boş metin içermiyor. Bunun yerine, tüm metin bloğu içinde sınıf özelliği yöntemlerini oluşur.

- Türetilmiş sınıf içinde tanımlanan yöntemler çağırır `SharedFragments`.

- Uygulama çağrıları `TextTransform()` yöntemi türetilmiş sınıfın temel sınıf dönüştürmez ancak `SharedFragments`.

- Temel ve türetilmiş sınıflarının çalışma zamanı metin şablonları; yine de uygun istiyor musunuz? diğer bir deyişle, **özel araç** özelliği ayarlanmış **TextTemplatingFilePreprocessor**.

**SharedFragments.tt:**

```
<#@ template language="C#" #>
<#+
protected void SharedText(int n)
{
#>
   Shared Text <#= n #>
<#+
}
// Insert more methods here if required.
#>
```

**MyTextTemplate1.tt:**

```
<#@ template language="C#" inherits="SharedFragments" #>
begin 1
   <# SharedText(2); #>
end 1
```

**MyProgram.cs:**

```csharp
...
MyTextTemplate1 t1  = new MyTextTemplate1();
string result = t1.TransformText();
Console.WriteLine(result);
```

**Sonuçta çıktı:**

```
begin 1
    Shared Text 2
end 1
```

#### <a name="inheritance-pattern-text-in-base-body"></a>Devralma deseni: Temel gövdesinde metin

Şablon devralma kullanarak bu alternatif yaklaşımda metin toplu temel şablonunda tanımlanır. Veri türetilmiş şablonları sağlar ve metin temel içerik uyan parça.

**AbstractBaseTemplate1.tt:**

```
<#@ template language="C#" #>

Here is the description for this derived template:
  <#= this.Description #>

Here is the fragment specific to this derived template:
<#
  this.PushIndent("  ");
  SpecificFragment(42);
  this.PopIndent();
#>
End of common template.
<#+
  // State set by derived class before calling TextTransform:
  protected string Description = "";
  // 'abstract' method to be defined in derived classes:
  protected virtual void SpecificFragment(int n) { }
#>
```

**DerivedTemplate1.tt:**

```
<#@ template language="C#" inherits="AbstractBaseTemplate1" #>
<#
  // Set the base template properties:
  base.Description = "Description for this derived class";

  // Run the base template:
  base.TransformText();

#>
End material for DerivedTemplate1.

<#+
// Provide a fragment specific to this derived template:

protected override void SpecificFragment(int n)
{
#>
   Specific to DerivedTemplate1 : <#= n #>
<#+
}
#>
```

**Uygulama kodu:**

```csharp
...
DerivedTemplate1 t1 = new DerivedTemplate1();
string result = t1.TransformText();
Console.WriteLine(result);
```

**Sonuçta çıktı:**

```
Here is the description for this derived template:
  Description for this derived class

Here is the fragment specific to this derived template:
     Specific to DerivedTemplate1 : 42
End of common template.
End material for DerivedTemplate1.
```

## <a name="related-topics"></a>İlgili Konular

Tasarım zamanı şablonları: kod oluşturmak için bir şablon kullanmak istiyorsanız, uygulamanızı bir parçası haline gelir, bkz: [T4 metin şablonları kullanarak tasarım zamanı kodu oluşturma](../modeling/design-time-code-generation-by-using-t4-text-templates.md).

Çalışma zamanı şablonları şablonları ve bunların içeriği derleme zamanında burada belirlenen herhangi bir uygulamada kullanılabilir. Ancak çalışma zamanında değiştirme şablonlardan metin oluşturan bir Visual Studio uzantısı yazmak isterseniz bkz [bir VS uzantısında metin dönüştürmeyi çağırma](../modeling/invoking-text-transformation-in-a-vs-extension.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Kod Oluşturma ve T4 Metin Şablonları](../modeling/code-generation-and-t4-text-templates.md)
- [T4 Metin Şablonu Yazma](../modeling/writing-a-t4-text-template.md)
- [T4 araç kutusu](http://olegsych.com/T4Toolbox/)