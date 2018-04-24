---
title: T4 Include Yönergesi
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 2a7b6d52d89da2b838d580bc2dbad9e36b9c73b9
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="t4-include-directive"></a>T4 Include Yönergesi

Metin şablonu içindeki [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], kullanarak başka bir dosyadan metin içerebilir bir `<#@include#>` yönergesi. Yerleştireceğiniz `include` yönergeleri metin şablonu birinci sınıf özelliği bloğu önce başka bir yerindeki `<#+ ... #>`. Eklenen dosyalar da içerebilir `include` yönergeleri ve diğer yönergeleri. Bu şablon kodunu ve demirbaş metni şablonlar arasında paylaşmanızı sağlar.

## <a name="using-include-directives"></a>Ekleme Yönergelerini Kullanma

```
<#@ include file="filePath" [once="true"] #>
```

-   `filePath` mutlak veya göreli geçerli şablon dosyası olabilir.

     Ayrıca, belirli [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uzantıları için dosyaları Ekle aramak için kendi dizinleriyle belirtebilirsiniz. Örneğin, Görselleştirme ve modelleme SDK (DSL araçları) yüklendiğinde şu klasörü ekleme listesine eklenir: `Program Files\Microsoft Visual Studio 10.0\Common7\IDE\Extensions\Microsoft\DSL SDK\DSL Designer\11.0\TextTemplates`.

     Bu ek içerme klasörleri içeren dosyanın dosya uzantısına bağlı olabilir. Örneğin, DSL araçlarda klasör dosya uzantısına sahip dosyaları dahil olmak üzere için erişilebilir durumda yalnızca `.tt`

-   `filePath` "%" ile sınırlandırılmış ortam değişkenleri içerebilir. Örneğin:

    ```
    <#@ include file="%HOMEPATH%\MyIncludeFile.t4" #>
    ```

-   Eklenen bir dosya adı uzantısını kullanacak şekilde yok `".tt"`.

     Başka bir uzantı gibi kullanmak isteyebilirsiniz `".t4"` dosyaları eklenmiştir. Eklediğinizde, bunun nedeni bir `.tt` bir proje dosyası [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] otomatik olarak ayarlar, **özel araç** özelliğine `TextTemplatingFileGenerator`. Tek tek dönüştürülecek dosyaları genellikle eklemek istemezsiniz.

     Diğer taraftan, bazı durumlarda, dosya uzantısının ek klasörlerin hangi include dosyalarının aranacağını etkilediğinin farkında olmalısınız. Diğer dosyaları içeren eklediğiniz bir dosya varsa, bu önemli olabilir.

-   Eklenen içerik ekleyen metin şablonunun hemen hemen parçasıymış gibi işlenir. Ancak, bir sınıf özelliği bloğu içeren bir dosya ekleyebilirsiniz `<#+...#>` olsa bile `include` yönergesi normal metin ve standart denetim blokları tarafından izlendiği.

-   Kullanım `once="true"` birden fazla diğer dahil etme dosyasından çağrılan olsa bile bir şablonu yalnızca bir kez dahil olduğundan emin olmak için.

     Konumundaki içerebilir yeniden kullanılabilir T4 parçacıkları kitaplığı oluşturmak kolay, endişelenmeden içinde bu özellik yapar başka bir kod parçacığında zaten bunları eklemiştir.  Örneğin, şablon işleme ve C# oluşturma ile ilgili çok hassas parçacıkları kitaplığınız varsayalım.  Buna karşılık, bunlar herhangi daha uygulamaya özgü şablondan sonra kullanabileceğiniz özel durumlar oluşturma gibi bazı fazla görev özgü yardımcı programlar tarafından kullanılır. Bağımlılık grafiği çizerseniz, bazı iş parçacıklarının birkaç kez dahil edildiğini görürsünüz. Ancak `once` parametresi sonraki içermeler önler.

 **MyTextTemplate.tt:**

```
<#@ output extension=".txt" #>
Output message 1 (from top template).
<#@ include file="TextFile1.t4"#>
Output message 5 (from top template).
<#
   GenerateMessage(6); // defined in TextFile1.t4
   AnotherGenerateMessage(7); // defined in TextFile2.t4
#>

```

 **TextFile1.t4:**

```
   Output Message 2 (from included file).
<#@include file="TextFile2.t4" #>
   Output Message 4 (from included file).
<#+ // Start of class feature control block.
void GenerateMessage(int n)
{
#>
   Output Message <#= n #> (from GenerateMessage method).
<#+
}
#>

```

 **TextFile2.t4:**

```
        Output Message 3 (from included file 2).
<#+ // Start of class feature control block.
void AnotherGenerateMessage(int n)
{
#>
       Output Message <#= n #> (from AnotherGenerateMessage method).
<#+
}
#>

```

 **Sonuç dosyası, MyTextTemplate.txt oluşturulur:**

```
Output message 1 (from top template).
   Output Message 2 (from included file).
        Output Message 3 (from included file 2).

   Output Message 4 (from included file).

Output message 5 (from top template).
   Output Message 6 (from GenerateMessage method).
       Output Message 7 (from AnotherGenerateMessage method).

```

##  <a name="msbuild"></a> MSBuild ve Visual Studio Proje özelliklerini kullanma
 Visual Studio makrosu $(SolutionDir) gibi bir içerme yönergesi kullanabilmenize karşın, bunların Msbuild'de çalışmıyor. Şablonları yapı makinenizde dönüştürmek isterseniz, bunun yerine proje özelliklerini kullanmanız gerekir.

 Proje özelliği tanımlamak için .csproj veya .vbproj dosyanızı düzenleyin. Bu örnek adlı bir özelliğini tanımlar `myIncludeFolder`:

```xml
<!-- Define a project property, myIncludeFolder: -->
<PropertyGroup>
    <myIncludeFolder>$(MSBuildProjectDirectory)\..\libs</myIncludeFolder>
</PropertyGroup>

<!-- Tell the MSBuild T4 task to make the property available: -->
<ItemGroup>
    <T4ParameterValues Include="myIncludeFolder">
      <Value>$(myIncludeFolder)</Value>
    </T4ParameterValues>
  </ItemGroup>

```

 Artık proje özelliğinizi metin şablonlarında kullanabilirsiniz, böylece hem Visual Studio hem de MSBuild içinde doğru dönüştürme yapılır:

```
<#@ include file="$(myIncludeFolder)\defs.tt" #>
```