---
title: "T4 İçe yönergesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 3f59641d733e16730d02868c368d53d6cbee0e74
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
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