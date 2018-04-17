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
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 43981b2ba736318aaf53ee6ed47bb39ef930557f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-escape-special-characters-in-msbuild"></a>Nasıl Yapılır: MSBuild'de Kaçış Özel Karakterleri
Özel bir anlamı belirli karakterler olmayan [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyaları. Noktalı virgül (;) ve yıldız işareti (*) karakterlerini örneklerindendir. Şu özel karakterleri tam bir listesi için bkz: [MSBuild özel karakterleri](../msbuild/msbuild-special-characters.md).  
  
 Proje dosyası değişmez değerlerine olarak şu özel karakterleri kullanmak için bunlar sözdizimi % kullanarak belirtilmelidir*xx*, burada *xx* karakter ASCII onaltılı değerini temsil eder.  
  
## <a name="msbuild-special-characters"></a>MSBuild Özel Karakterleri  
 Bir özel karakterler kullanıldığı örnek konusu `Include` öğesi listeleri özniteliğidir. Örneğin, aşağıdaki öğeyi listede iki öğeleri bildirir: `MyFile.cs` ve `MyClass.cs`.  
  
```xml  
<Compile Include="MyFile.cs;MyClass.cs"/>  
```  
  
 Adı noktalı virgül içeren bir öğeyi bildirmek isterseniz, % kullanmalısınız*xx* noktalı kaçış ve engellemek için sözdizimi [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] iki ayrı öğeleri bildirme gelen. Örneğin, aşağıdaki öğeyi noktalı çıkışları ve bir öğe adlı bildirir `MyFile.cs;MyClass.cs`.  
  
```xml  
<Compile Include="MyFile.cs%3BMyClass.cs"/>  
```  
  
#### <a name="to-use-an-msbuild-special-character-as-a-literal-character"></a>MSBuild özel karakter harf karakter olarak kullanmak için  
  
-   Gösterimi % kullanın*xx* özel karakter yerine burada *xx* ASCII karakter onaltılı değerini temsil eder. Örneğin, bir harf karakter olarak yıldız işareti (*) kullanmak için değeri kullanın `%2A`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild kavramları](../msbuild/msbuild-concepts.md)   
 [MSBuild](../msbuild/msbuild.md) [öğeleri](../msbuild/msbuild-items.md)