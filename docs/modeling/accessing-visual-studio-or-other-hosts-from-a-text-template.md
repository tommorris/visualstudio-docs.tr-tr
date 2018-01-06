---
title: "Metin şablonundan Visual Studio'ya veya diğer Konaklara erişme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a68886da-7416-4785-8145-3796bb382cba
caps.latest.revision: "5"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: cc0f756637921b9f470e744ec8875ba3a2b54012
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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