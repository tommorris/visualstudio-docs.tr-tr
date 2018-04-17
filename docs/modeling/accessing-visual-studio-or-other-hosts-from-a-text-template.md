---
title: Metin şablonundan Visual Studio'ya veya diğer Konaklara erişme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: e5478ffd578aa63a528d3c3e463872a169354555
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="accessing-visual-studio-or-other-hosts-from-a-text-template"></a>Metin Şablonundan Visual Studio'ya veya diğer Konaklara Erişme
Bir metin şablonuna yöntemleri ve şablon gibi yürütür ana bilgisayar tarafından kullanıma sunulan özellikler kullanabilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
 Bu değil önceden işlenmiş metin şablonları normal metin şablonları için geçerlidir.  
  
## <a name="obtaining-access-to-the-host"></a>Konağa erişim elde etme  
 Ayarlama `hostspecific="true"` içinde `template` yönergesi. Bu kullanmanıza olanak sağlayan `this.Host`, türüne sahip <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>. Bu tür, örneğin, dosya adları çözümlemek için ve hataları günlüğe kaydetmek için kullanabileceğiniz üye içermiyor.  
  
### <a name="resolving-file-names"></a>Dosya adları çözme  
 Metin şablonu göreli bir dosyanın tam yolunu bulmak için bunu kullanın. Host.ResolvePath().  
  
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
  
### <a name="displaying-error-messages"></a>Hata iletilerini görüntüleme  
 Bu örnek, şablon dönüştürme zaman iletilerini günlüğe kaydeder. Ana bilgisayar ise [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], hata penceresine eklenir.  
  
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
  
## <a name="using-the-visual-studio-api"></a>Visual Studio API kullanarak  
 Bir metin şablonuna çalıştırıldığında [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], kullanabileceğiniz `this.Host` tarafından sağlanan hizmetlerine erişmek için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve paketleri veya yüklenen uzantıları.  
  
 Ayarlama hostspecific = "true" ve cast `this.Host` için <xref:System.IServiceProvider>.  
  
 Bu örnek alır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] API, <xref:EnvDTE.DTE>, hizmet olarak:  
  
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
  
## <a name="using-hostspecific-with-template-inheritance"></a>Şablon kalıtım hostSpecific kullanma  
 Belirtin `hostspecific="trueFromBase"` de kullanıyorsanız `inherits` özniteliği ve belirten bir şablondan devralır `hostspecific="true"`. Derleyici Uyarısı etkili olması için bu ortadan kaldırır, özellik `Host` iki kez bildirildi.