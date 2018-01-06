---
title: "Nasıl yapılır: MSBuild özel karakterleri kaçış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- special characters, escaping
- characters, escapes
- escape characters
- MSBuild, escaping special characters
ms.assetid: 1aa3669c-1647-4960-b770-752e2532102f
caps.latest.revision: "12"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6d5fda1972cfc483a02a7f655a33b1fb9efdf43f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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