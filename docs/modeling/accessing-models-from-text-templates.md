---
title: Metin Şablonlarından Modellere Erişme
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, accessing models
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 54bd5c4989f23b1de64a17bdf8d88ccebeb65a38
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="accessing-models-from-text-templates"></a>Metin Şablonlarından Modellere Erişme
Metin şablonları kullanarak raporu dosyalarını, kaynak kodu dosyaları ve etki alanına özgü dil modellerinde bağlı diğer metin dosyaları oluşturabilirsiniz. Metin şablonları hakkında temel bilgiler için bkz: [kod oluşturma ve T4 metin şablonları](../modeling/code-generation-and-t4-text-templates.md). Metin şablonları, DSL ayıklarken Deneysel modunda çalışır ve DSL dağıtmış olan bir bilgisayarda da çalışır.

> [!NOTE]
>  DSL çözüm, örnek metin şablonu oluşturduğunuzda  **\*.tt** dosyaları, hata ayıklama projede oluşturulur. Etki alanı sınıflarının adlarını değiştirdiğinizde, bu şablonları artık çalışmaz. Bununla birlikte, bunlar gereken temel yönergeleri içerir ve, DSL eşleşecek şekilde güncelleştirebilirsiniz örnekler sağlar.

 Metin şablonundan bir model erişmek için:

-   Şablon yönergesi devral özelliğini ayarla <xref:Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation>. Bu deposuna erişim sağlar.

-   Yönerge işlemcileri erişmek istediğiniz DSL için belirtin. Etki alanı sınıfları, özellikleri ve ilişkileri metin şablonu kodda kullanabilmesi için bu, DSL derlemelerde yükler. Ayrıca, belirttiğiniz modeli dosyası yükler.

 A `.tt` dosyası aşağıdaki örneğe benzer, hata ayıklama projesinde oluşturulursa, yeni bir oluşturduğunuzda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] DSL en az dil şablonu çözümden.

```
<#@ template inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation" #>
<#@ output extension=".txt" #>
<#@ MyLanguage processor="MyLanguageDirectiveProcessor" requires="fileName='Sample.myDsl1'" #>

This text will be output directly.

This is the name of the model: <#= this.ModelRoot.Name #>

Here is a list of elements in the model:
<#
  // When you change the DSL Definition, some of the code below may not work.
  foreach (ExampleElement element in this.ExampleModel.Elements)
  {#>
<#= element.Name #>
<#
  }
#>

```

 Bu şablonla ilgili aşağıdaki noktaları dikkat edin:

-   Şablon, etki alanı sınıfları, özellikleri ve DSL tanımı içinde tanımlanan ilişkileri kullanabilirsiniz.

-   Belirttiğiniz modeli dosyası şablon yüklendiğinde `requires` özelliği.

-   Bir özelliğin `this` kök öğe içeriyor. Buradan, kodunuzu diğer model öğelerine gidebilirsiniz. Özelliğin adı genellikle, DSL kök etki alanı sınıfı ile aynıdır. Bu örnek, `this.ExampleModel`.

-   Kod parçaları yazılmış olan dil C# olsa da, herhangi bir türde metin oluşturabilir. Alternatif olarak kod yazabilirsiniz [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] özelliği ekleyerek `language="VB"` için `template` yönergesi.

-   Şablon hatalarını ayıklamak için ekleme `debug="true"` için `template` yönergesi. Şablon başka bir kopyasında açılır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir özel durum oluşursa. Hata ayıklayıcı kodda belirli bir noktada içine kesmek istediğinizden, deyim takın. `System.Diagnostics.Debugger.Break();`

     Daha fazla bilgi için bkz: [T4 metin şablonuna ilişkin hata ayıklama](../modeling/debugging-a-t4-text-template.md).

## <a name="about-the-dsl-directive-processor"></a>DSL yönerge işlemcisi hakkında
 Şablon DSL tanımı'nda tanımlanan etki alanı sınıflarını kullanabilirsiniz. Bu genellikle şablon başlangıcı görünür bir yönerge tarafından getirilene. Önceki örnekte verilmiştir.

```
<#@ MyLanguage processor="MyLanguageDirectiveProcessor" requires="fileName='Sample.myDsl1'" #>
```

 Yönerge adı ( `MyLanguage`, bu örnekte), DSL adından türetilir. Bunu çağıran bir *yönerge işlemcisi* , DSL bir parçası olarak oluşturulur. Kendi kaynak kodunda bulabilirsiniz **Dsl\GeneratedCode\DirectiveProcessor.cs**.

 DSL yönerge işlemcisi iki asıl görevleri gerçekleştirir:

-   Etkili bir şekilde derleme ve içeri aktarma yönergeleri, DSL başvuran şablona ekler. Bu şablon kodunda, etki alanı sınıflarını kullanmanıza olanak sağlar.

-   Belirttiğiniz dosya yükler `requires` parametresi ve bir özellik ayarlar `this` yüklenen modeli kök öğesine başvuruyor.

## <a name="validating-the-model-before-running-the-template"></a>Şablon çalıştırmadan önce model doğrulama
 Şablon yürütülmeden önce doğrulanacak model neden olabilir.

```
<#@ MyLanguage processor="MyLanguageDirectiveProcessor" requires="fileName='Sample.myDsl1';validation='open|load|save|menu'" #>

```

 Şunlara dikkat edin:

1.  `filename` Ve `validation` parametreleri ayrılmış olan ";" ve diğer ayırıcılar veya boşluk olması gerekir.

2.  Doğrulama kategori listesi, hangi doğrulama yöntemlerini yürütülecek belirler. Birden çok kategori ile ayrılmalıdır "&#124;" ve diğer ayırıcılar veya boşluk olması gerekir.

 Bir hata bulunursa, hatalar penceresinde bildirilir ve sonuç dosyası bir hata iletisi içerir.

##  <a name="Multiple"></a> Metin şablonundan birden fazla modeli erişme

> [!NOTE]
>  Bu yöntem, aynı şablonu birden fazla modellerinde Okuma olanak tanır ancak ModelBus başvuruları desteklemez. ModelBus başvurular birbirine modelleri okumak için bkz: [kullanarak Visual Studio ModelBus metin şablonunda](../modeling/using-visual-studio-modelbus-in-a-text-template.md).

 Birden fazla model aynı metin şablonundan erişmek isterseniz, her modeli için bir kez oluşturulan yönerge işlemcisi çağırmanız gerekir. Her modelinde dosya adını belirtmeniz gerekir `requires` parametresi. Kök etki alanı sınıf için kullanmak istediğiniz adları belirtmelisiniz `provides` parametresi. İçin farklı değerler belirtmeniz gerekir `provides` her yönerge çağrılarının parametreleri. Örneğin, Library.xyz, School.xyz ve Work.xyz adlı üç modeli dosyalarının olduğunu varsayın. Aynı metin şablonundan erişmek için aşağıdaki ayarlara benzer üç yönerge çağrıları yazmanız gerekir.

```
<#@ ExampleModel processor="<YourLanguageName>DirectiveProcessor" requires="fileName='Library.xyz'" provides="ExampleModel=LibraryModel" #>
<#@ ExampleModel processor="<YourLanguageName>DirectiveProcessor" requires="fileName='School.xyz'" provides="ExampleModel=SchoolModel" #>
<#@ ExampleModel processor="<YourLanguageName>DirectiveProcessor" requires="fileName='Work.xyz'" provides="ExampleModel=WorkModel" #>
```

> [!NOTE]
>  Bu kod örneği en az bir dil çözüm şablona dayalı bir dil içindir.

 Metin şablonu modellerinde erişmek için artık aşağıdaki örnekte koda benzer bir kod yazabilirsiniz.

```csharp
<#
foreach (ExampleElement element in this.LibraryModel.Elements)
...
foreach (ExampleElement element in this.SchoolModel.Elements)
...
foreach (ExampleElement element in this.WorkModel.Elements)
...
#>
```

```vb
<#
For Each element As ExampleElement In Me.LibraryModel.Elements
...
For Each element As ExampleElement In Me.SchoolModel.Elements
...
For Each element As ExampleElement In Me.WorkModel.Elements
...
#>
```

## <a name="loading-models-dynamically"></a>Modelleri dinamik olarak yükleme
 Çalışma zamanında yüklemek için hangi modelleri belirlemek istiyorsanız, bir model dosyası dinamik olarak DSL özgü yönergesi kullanmak yerine, program kodunuzda yükleyebilirsiniz.

 Şablon kodu bu DSL tanımlanan etki alanı sınıflarını kullanabilmesi için ancak DSL özgü yönergesi işlevleri DSL ad alanı içe aktarmak için biridir. Yönergesi kullanmadığınızdan eklemelisiniz  **\<derleme >** ve  **\<alma >** yük tüm modelleri için yönergeleri. Yük farklı modelleri aynı DSL tüm örneklerini varsa bu kolaydır.

 Dosyasını yüklemek için en etkili kullanarak yöntemdir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ModelBus. Tipik bir senaryoda, metin şablonu DSL özgü yönergesi ilk modeli normal şekilde yüklemek için kullanır. Bu model başka bir model ModelBus başvurular içerir. ModelBus başvurulan model açın ve belirli bir öğesine erişmek için kullanabilirsiniz. Daha fazla bilgi için bkz: [kullanarak Visual Studio ModelBus metin şablonunda](../modeling/using-visual-studio-modelbus-in-a-text-template.md).

 Daha az normal bir senaryoda, yalnızca bir dosya adı, elinizde bir model dosyası açmak isteyebilirsiniz ve geçerli olmayabilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projesi. Bu durumda, açıklanan teknikleri kullanarak dosyayı açabilmek için [nasıl yapılır: Program kodundaki dosyasından Model açmak](../modeling/how-to-open-a-model-from-file-in-program-code.md).

## <a name="generating-multiple-files-from-a-template"></a>Bir şablondan birden çok dosya oluşturma
 Çeşitli dosyalar - oluşturmak istiyorsanız, örneğin, bir modeldeki her öğe için ayrı bir dosya oluşturmak için birkaç olası yaklaşım vardır. Varsayılan olarak, her şablon dosyasından tek bir dosya oluşturulur.

### <a name="splitting-a-long-file"></a>Uzun dosya bölme
 Bu yöntemde, tek bir sınırlayıcıyla ayrılmış bir dosya oluşturmak için bir şablon kullanın. Ardından, dosyayı kendi bölün. Tek dosya ve bölmek için diğer oluşturmak için iki şablonları vardır.

 **LoopTemplate.t4** uzun tek dosya oluşturur. Tıkladığınızda, doğrudan bu işlenmesi gerektiğini değil çünkü dosya uzantısını ".t4" olduğuna dikkat edin **tüm şablonları dönüştürme**. Bu şablon kesimleri ayıran sınırlayıcı dizeyi belirtir bir parametre alır:

```
<#@ template ninherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation" #>
<#@ parameter name="delimiter" type="System.String" #>
<#@ output extension=".txt" #>
<#@ MyDSL processor="MyDSLDirectiveProcessor" requires="fileName='SampleModel.mydsl1';validation='open|load|save|menu'" #>
<#
  // Create a file segment for each element:
  foreach (ExampleElement element in this.ExampleModel.Elements)
  {
    // First item is the delimiter:
#>
<#= string.Format(delimiter, element.Id) #>

   Element: <#= element.Name #>
<#
   // Here you generate more content derived from the element.
  }
#>

```

 `LoopSplitter.tt` çağırır `LoopTemplate.t4`ve sonra sonuçta elde edilen dosyasını kendi parçalara ayırır. Model okumaz çünkü bu şablonu bir modelleme şablonu olmasını olmadığından emin dikkat edin.

```
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ import namespace="Microsoft.VisualStudio.TextTemplating" #>
<#@ import namespace="System.Runtime.Remoting.Messaging" #>
<#@ import namespace="System.IO" #>

<#
  // Get the local path:
  string itemTemplatePath = this.Host.ResolvePath("LoopTemplate.t4");
  string dir = Path.GetDirectoryName(itemTemplatePath);

  // Get the template for generating each file:
  string loopTemplate = File.ReadAllText(itemTemplatePath);

  Engine engine = new Engine();

  // Pass parameter to new template:
  string delimiterGuid = Guid.NewGuid().ToString();
  string delimiter = "::::" + delimiterGuid + ":::";
  CallContext.LogicalSetData("delimiter", delimiter + "{0}:::");
  string joinedFiles = engine.ProcessTemplate(loopTemplate, this.Host);

  string [] separateFiles = joinedFiles.Split(new string [] {delimiter}, StringSplitOptions.None);

  foreach (string nameAndFile in separateFiles)
  {
     if (string.IsNullOrWhiteSpace(nameAndFile)) continue;
     string[] parts = nameAndFile.Split(new string[]{":::"}, 2, StringSplitOptions.None);
     if (parts.Length < 2) continue;
#>
 Generate: [<#= dir #>] [<#= parts[0] #>]
<#
     // Generate a file from this item:
     File.WriteAllText(Path.Combine(dir, parts[0] + ".txt"), parts[1]);
  }
#>

```