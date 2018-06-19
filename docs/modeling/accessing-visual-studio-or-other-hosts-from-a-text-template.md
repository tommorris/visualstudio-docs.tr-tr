---
title: Metin Şablonundan Visual Studio'ya veya diğer Konaklara Erişme
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 657abba976e0f0d167651943289296d340981e62
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31946523"
---
# <a name="access-visual-studio-or-other-hosts-from-a-text-template"></a>Metin şablonundan Visual Studio'ya veya diğer Konaklara erişme

Bir metin şablonuna yöntemleri ve şablonu yürütür ana bilgisayar tarafından gösterilen özelliklerin kullanabilirsiniz. Visual Studio, bir konak örneğidir.

> [!NOTE]
> Normal metin şablonlarındaki ancak'de konak yöntemleri ve özellikleri kullanabilirsiniz *ön işlemesi yapılan* metin şablonları.

## <a name="obtain-access-to-the-host"></a>Ana bilgisayara erişim sağlamak

Ana erişmek için ayarlanmış `hostspecific="true"` içinde `template` yönergesi. Kullanabileceğiniz artık `this.Host`, türüne sahip <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>. <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost> Türü, örneğin, dosya adlarını çözemez ve hataları günlüğe kaydetmek için kullanabileceğiniz üyeler içeriyor.

### <a name="resolve-file-names"></a>Dosya adları çözümlemek

Metin şablonu göreli bir dosyanın tam yolunu bulmak için `this.Host.ResolvePath()`.

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ import namespace="System.IO" #>
<#
 // Find a path within the same project as the text template:
 string myFile = File.ReadAllText(this.Host.ResolvePath("MyFile.txt"));
#>
Content of myFile is:
<#= myFile #>
```

### <a name="display-error-messages"></a>Hata iletilerini görüntüleme

Bu örnek, şablon dönüştürme zaman iletilerini günlüğe kaydeder. Visual Studio ana bilgisayar ise, hataları eklenir **hata listesi**.

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ import namespace="System.CodeDom.Compiler" #>
<#
  string message = "test message";
  this.Host.LogErrors(new CompilerErrorCollection()
    { new CompilerError(
       this.Host.TemplateFile, // Identify the source of the error.
       0, 0, "0",   // Line, column, error ID.
       message) }); // Message displayed in error window.
#>
```

## <a name="use-the-visual-studio-api"></a>Visual Studio API kullanın

Visual Studio'da bir metin şablonuna yürütme, kullanabileceğiniz `this.Host` Visual Studio ve paketleri veya yüklenen uzantıları tarafından sağlanan hizmetlerine erişmek için.

Ayarlama hostspecific = "true" ve cast `this.Host` için <xref:System.IServiceProvider>.

Bu örnek Visual Studio API alır <xref:EnvDTE.DTE>, hizmet olarak:

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ assembly name="EnvDTE" #>
<#@ import namespace="EnvDTE" #>
<#
 IServiceProvider serviceProvider = (IServiceProvider)this.Host;
 DTE dte = serviceProvider.GetService(typeof(DTE)) as DTE;
#>
Number of projects in this solution: <#=  dte.Solution.Projects.Count #>
```

## <a name="use-hostspecific-with-template-inheritance"></a>Şablon kalıtım hostSpecific kullanın

Belirtin `hostspecific="trueFromBase"` de kullanıyorsanız `inherits` özniteliği ve belirten bir şablondan devralır `hostspecific="true"`. Bunu yapmazsanız, uyarı derleyici özelliği alabilirsiniz `Host` iki kez bildirildi.