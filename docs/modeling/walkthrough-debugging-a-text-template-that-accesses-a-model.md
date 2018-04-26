---
title: 'İzlenecek yol: Modele Erişen Metin Şablonunda Hata Ayıklama'
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 560849eaeefc8efd8337cbc98ad3de91e4d15fd9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-debugging-a-text-template-that-accesses-a-model"></a>İzlenecek yol: Modele Erişen Metin Şablonunda Hata Ayıklama
Değiştirme veya bir etki alanına özgü dil çözümde metin şablonları ekleme, şablonu kaynak koduna veya oluşturulan kod derlediğinde altyapısı dönüştüren olduğunda hataları alabilirsiniz. Aşağıdaki yönergeler metin şablonu hata ayıklamak için yapabileceği şeylerden bazıları gösterir.

> [!NOTE]
>  Metin hakkında daha fazla bilgi için genel olarak, bkz: şablonları [kod oluşturma ve T4 metin şablonları](../modeling/code-generation-and-t4-text-templates.md). Metin şablonları hata ayıklama hakkında daha fazla bilgi için bkz: [izlenecek yol: bir metin şablonuna ilişkin hata ayıklama](http://msdn.microsoft.com/Library/5c3fd3b7-c110-4e86-a22f-d5756be6b94f).

## <a name="creating-a-domain-specific-language-solution"></a>Bir etki alanına özgü dil çözümü oluşturma
 Bu yordamda, aşağıdaki özelliklere sahip bir etki alanına özgü dil çözümü oluşturun:

-   Ad: DebuggingTestLanguage

-   Çözüm şablonu: en az bir dil

-   Dosya uzantısı: .ddd

-   Şirket adı: Fabrikam

 Bir etki alanına özgü dil çözümü oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir etki alanına özgü dil çözümü oluşturma](../modeling/how-to-create-a-domain-specific-language-solution.md).

## <a name="creating-a-text-template"></a>Metin şablonu oluşturma
 Metin şablonu çözümünüze ekleyin.

#### <a name="to-create-a-text-template"></a>Metin şablonu oluşturmak için

1.  Çözümü derlemek ve hata ayıklayıcısı'ndaki çalıştırma başlatın. (Üzerinde **yapı** menüsünde tıklatın **çözümü yeniden derle**ve ardından **hata ayıklama** menüsünde tıklatın **hata ayıklamayı Başlat**.) Visual Studio yeni bir örneğini hata ayıklama projeyi açar.

2.  Adlı bir metin dosyasına eklemek `DebugTest.tt` hata ayıklama projeye.

3.  Olduğundan emin olun **özel araç** DebugTest.tt özelliği ayarlanmış `TextTemplatingFileGenerator`.

## <a name="debugging-directives-that-access-a-model-from-a-text-template"></a>Metin şablonundan bir model erişim yönergeleri hata ayıklama
 Bir model ifadeleri ve bir metin şablonuna ifadelerinde erişebilmeniz için önce oluşturulan bir yönerge işlemcisi çağırmanız gerekir. Oluşturulan yönerge işlemcisi çağırma sınıfları modelinizde metin şablonu kodunun özellikleri olarak kullanılabilmesini sağlar. Daha fazla bilgi için bkz: [metin şablonları erişme modellerinden](../modeling/accessing-models-from-text-templates.md).

 Aşağıdaki yordamlarda, hatalı bir yönerge ad ve bir yanlış özellik adı ayıklama.

#### <a name="to-debug-an-incorrect-directive-name"></a>Hatalı bir yönerge adı hata ayıklamak için

1.  DebugTest.tt kodu aşağıdaki kodla değiştirin:

    > [!NOTE]
    >  Bir hata kodunu içerir. Hata ayıklamak için hata piyasaya sunmaktadır.

    ```csharp
    <#@ template language="C#" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ modelRoot processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>

    Model: <#= this.ExampleModel #>
    <#
    foreach (ExampleElement element in this.ExampleModel.Elements)
    {
    #>
        Element: <#= element.Name #>
    <#
    }
    #>
    ```

    ```vb
    <#@ template language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ modelRoot processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>

    Model: <#= Me.ExampleModel #>
    <#
    For Each element as ExampleElement in Me.ExampleModel.Elements
    #>
        Element: <#= element.Name #>
    <#
    Next
    #>
    ```

2.  İçinde **Çözüm Gezgini**DebugTest.tt sağ tıklayın ve ardından **çalıştırmak özel araç**.

     **Hata listesi** penceresi, bu hatayı görüntüler:

     **'DebuggingTestLanguageDirectiveProcessor' adlı İşlemci 'modelRoot' adlı yönergesi desteklemez. Dönüştürme çalışmaz.**

     Bu durumda, hatalı bir yönerge adı yönerge çağrı içerir. Belirttiğiniz `modelRoot` yönerge adı ancak doğru yönerge adı olarak `DebuggingTestLanguage`.

3.  Hatayı çift tıklatın **hata listesi** koda atlama penceresi.

4.  Kod düzeltmek için yönerge adına değiştirmek `DebuggingTestLanguage`.

     Değişiklik vurgulanır.

    ```csharp
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>
    ```

    ```vb
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>
    ```

5.  İçinde **Çözüm Gezgini**DebugTest.tt sağ tıklayın ve ardından **çalıştırmak özel araç**.

     Artık sistem metin şablonu dönüştürür ve karşılık gelen çıktı dosyası oluşturur. Hatalarını göreceksiniz **hata listesi** penceresi.

#### <a name="to-debug-an-incorrect-property-name"></a>Yanlış özellik adı hata ayıklamak için

1.  DebugTest.tt kodu aşağıdaki kodla değiştirin:

    > [!NOTE]
    >  Bir hata kodunu içerir. Hata ayıklamak için hata piyasaya sunmaktadır.

    ```csharp
    <#@ template language="C#" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>

    Model: <#= this.ExampleModel #>
    <#
    foreach (ExampleElement element in this.ExampleModel.Elements)
    {
    #>
        Element: <#= element.Name #>
    <#
    }
    #>
    ```

    ```vb
    <#@ template language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>

    Model: <#= Me.ExampleModel #>
    <#
    For Each element as ExampleElement in Me.ExampleModel.Elements
    #>
        Element: <#= element.Name #>
    <#
    Next
    #>
    ```

2.  İçinde **Çözüm Gezgini**DebugTest.tt sağ tıklayın ve ardından **çalıştırmak özel araç**.

     **Hata listesi** penceresi görüntülenir ve bu hatalar birini görüntüler:

     (C#)

     **Dönüştürme derleme: Microsoft.VisualStudio.TextTemplating\<GUID >. GeneratedTextTransformation' bir 'ExampleModel' için tanıma sahip değil**

     (Visual Basic)

     **Dönüştürme derleme: 'ExampleModel' üyesi değil ' Microsoft.VisualStudio.TextTemplating\<GUID >. GeneratedTextTransformation'.**

     Bu durumda, metin şablonu kodu yanlış özellik adını içerir. Belirttiğiniz `ExampleModel` özellik adı, ancak doğru özelliği adıdır `LibraryModel`. Doğru özellik adında bulabilirsiniz parametresi, aşağıdaki kodda gösterildiği gibi sağlar:

    ```
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>
    ```

3.  Koda atlama için hata listesi penceresini hatayı çift tıklatın.

4.  Kod düzeltmek için özellik adı değiştirmek `LibraryModel` metin şablonu kodu.

     Değişiklikler vurgulanır.

    ```csharp
    <#@ template language="C#" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>

    Model: <#= this.LibraryModel #>
    <#
    foreach (ExampleElement element in this.LibraryModel.Elements)
    {
    #>
        Element: <#= element.Name #>
    <#
    }
    #>
    ```

    ```vb
    <#@ template language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>

    Model: <#= Me.LibraryModel #>
    <#
    For Each element as ExampleElement in Me.LibraryModel.Elements
    #>
        Element: <#= element.Name #>
    <#
    Next
    #>
    ```

5.  İçinde **Çözüm Gezgini**DebugTest.tt sağ tıklayın ve ardından **çalıştırmak özel araç**.

     Artık sistem metin şablonu dönüştürür ve karşılık gelen çıktı dosyası oluşturur. Hatalarını göreceksiniz **hata listesi** penceresi.