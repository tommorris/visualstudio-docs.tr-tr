---
title: 'Nasıl yapılır: MSBuild özel karakterleri kaçış | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- special characters, escaping
- characters, escapes
- escape characters
- MSBuild, escaping special characters
ms.assetid: 1aa3669c-1647-4960-b770-752e2532102f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1d921236fe44c7402bb26800c02624e2c391301a
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39077072"
---
# <a name="how-to-escape-special-characters-in-msbuild"></a>Nasıl yapılır: özel msbuild'de kaçış karakterleri
Belirli karakterler özel bir anlamı olmayan [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyaları. Karakterler örnekleri noktalı virgül (;) ve yıldız işareti (*) içerir. Bu özel karakterlerin tam bir listesi için bkz. [MSBuild özel karakterleri](../msbuild/msbuild-special-characters.md).  
  
 Bu özel karakterlerin bir proje dosyasında sabit değer olarak kullanmak için söz dizimi % kullanarak belirtilmelidir\<xx >, burada \<xx > karakter ASCII onaltılık değerini temsil eder.  
  
## <a name="msbuild-special-characters"></a>MSBuild özel karakterleri  
 Bir özel karakter kullanıldığı örnek konusu `Include` öğesi listeleri özniteliği. Örneğin, aşağıdaki madde listesini iki öğe bildirir: *dosyam.cs* ve *MyClass.cs*.  
  
```xml  
<Compile Include="MyFile.cs;MyClass.cs"/>  
```  
  
 Adında bir noktalı virgül içeren bir öğe bildirmek istiyorsanız, % kullanmalısınız\<xx > noktalı virgül kaçış ve önlemek için söz dizimi [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] gelen iki ayrı öğeleri bildirme. Örneğin, aşağıdaki öğe noktalı virgül çıkışları ve bir öğe adlı bildirir *dosyam.cs; MyClass.cs*.  
  
```xml  
<Compile Include="MyFile.cs%3BMyClass.cs"/>  
```  
  
#### <a name="to-use-an-msbuild-special-character-as-a-literal-character"></a>MSBuild özel karakter değişmez değer olarak kullanmak için  
  
-   Gösterim % kullanmak\<xx > özel karakter yerine burada \<xx > ASCII karakter onaltılık değerini temsil eder. Örneğin, sabit karakter olarak yıldız işareti (*) kullanmak için değerini kullanın. `%2A`.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [MSBuild kavramları](../msbuild/msbuild-concepts.md)   
 [MSBuild](../msbuild/msbuild.md)   
 [Öğeleri](../msbuild/msbuild-items.md)   
