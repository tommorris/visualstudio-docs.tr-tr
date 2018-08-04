---
title: T4 İçe Aktarma Yönergesi
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 6b0479bf427930d19b12fa0de5728f26e7cdb10d
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2018
ms.locfileid: "39510184"
---
# <a name="t4-import-directive"></a>T4 İçe Aktarma Yönergesi

Kod blokları bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] T4 metin şablonu `import` yönergesi, tam bir ad sağlamadan başka bir ad alanındaki öğeler başvurmak olanak sağlar. Denk olan `using` C# veya `imports` içinde [!INCLUDE[vb_current_short](../debugger/includes/vb_current_short_md.md)].

T4 metin şablonlarını yazmayla ilgili genel bilgiler için bkz: [T4 metin şablonu yazma](../modeling/writing-a-t4-text-template.md).

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

-   DSL'NİZİN ad alanı

## <a name="see-also"></a>Ayrıca Bkz.

- [T4 Derleme Yönergesi](../modeling/t4-assembly-directive.md)