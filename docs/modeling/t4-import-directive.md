---
title: T4 İçe yönergesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 05891c415e801a7d08a3b168dec854d8566363d2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="t4-import-directive"></a>T4 İçe Aktarma Yönergesi
Kod blokları bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] T4 metin şablonu `import` yönergesi bir tam ad sağlamadan başka bir ad alanı öğeleri başvurmak olanak tanır. Eşdeğeridir `using` C# veya `imports` içinde [!INCLUDE[vb_current_short](../debugger/includes/vb_current_short_md.md)].  
  
 T4 metin şablonları yazma genel bir bakış için bkz: [T4 metin şablonu yazma](../modeling/writing-a-t4-text-template.md).  
  
## <a name="using-the-import-directive"></a>İçeri Aktarma Yönergesini Kullanma  
  
```  
<#@ import namespace="namespace" #>  
```  
  
 Bu örnekte, şablonu kodu, System.IO üyeleri için açık ad alanını atlayabilir:  
  
```  
<#@ import namespace="System.IO" #>  
<#   
   string fileContent = File.ReadAllText("C:\x.txt"); // System.IO.File  
#>   
The file contains: <#=  fileContent #>  
```  
  
## <a name="standard-imports"></a>Standart İçeri Aktarmalar  
 Aşağıdaki ad alanı otomatik olarak içeri aktarılır, böylece onun için içeri aktarma yönergesi yazmanıza gerek kalmaz:  
  
-   `System`  
  
 Ayrıca, özel yönerge kullanıyorsanız, yönerge işlemcisi bazı ad alanlarını otomatik olarak içeri aktarabilir.  
  
 Örneğin, etki alanına özgü dil (DSL) için şablonlar yazarsanız, aşağıdaki ad alanları için içeri aktarma yönergeleri yazmak gerekmez:  
  
-   `Microsoft.VisualStudio.Modeling`  
  
-   DSL'ın ad alanı  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [T4 Derleme Yönergesi](../modeling/t4-assembly-directive.md)