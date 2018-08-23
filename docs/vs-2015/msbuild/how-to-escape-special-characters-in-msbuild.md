---
title: 'Nasıl yapılır: MSBuild özel karakterleri kaçış | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- special characters, escaping
- characters, escapes
- escape characters
- MSBuild, escaping special characters
ms.assetid: 1aa3669c-1647-4960-b770-752e2532102f
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a900ebe49e95b512c0f53a5542f0ba8ee238a83f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693446"
---
# <a name="how-to-escape-special-characters-in-msbuild"></a>Nasıl Yapılır: MSBuild'de Kaçış Özel Karakterleri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: MSBuild kaçış özel karakterleri](https://docs.microsoft.com/visualstudio/msbuild/how-to-escape-special-characters-in-msbuild).  
  
  
Belirli karakterler özel bir anlamı olmayan [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] proje dosyaları. Karakterler örnekleri noktalı virgül (;) ve yıldız işareti (*) içerir. Bu özel karakterlerin tam bir listesi için bkz. [MSBuild özel karakterleri](../msbuild/msbuild-special-characters.md).  
  
 Bu özel karakterlerin bir proje dosyasında sabit değer olarak kullanmak için söz dizimi % kullanarak belirtilmelidir*xx*burada *xx* karakter ASCII onaltılık değerini temsil eder.  
  
## <a name="msbuild-special-characters"></a>MSBuild Özel Karakterleri  
 Bir özel karakter kullanıldığı örnek konusu `Include` öğesi listeleri özniteliği. Örneğin, aşağıdaki madde listesini iki öğe bildirir: `MyFile.cs` ve `MyClass.cs`.  
  
```  
<Compile Include="MyFile.cs;MyClass.cs"/>  
```  
  
 Adında bir noktalı virgül içeren bir öğe bildirmek istiyorsanız, % kullanmalısınız*xx* noktalı virgül kaçış ve önlemek için söz dizimi [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] gelen iki ayrı öğeleri bildirme. Örneğin, aşağıdaki öğe noktalı virgül çıkışları ve bir öğe adlı bildirir `MyFile.cs;MyClass.cs`.  
  
```  
<Compile Include="MyFile.cs%3BMyClass.cs"/>  
```  
  
#### <a name="to-use-an-msbuild-special-character-as-a-literal-character"></a>MSBuild özel karakter değişmez değer olarak kullanmak için  
  
-   Gösterim % kullanmak*xx* özel karakter yerine burada *xx* ASCII karakter onaltılık değerini temsil eder. Örneğin, sabit karakter olarak yıldız işareti (*) kullanmak için değerini kullanın. `%2A`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild kavramları](../msbuild/msbuild-concepts.md)   
 [MSBuild](msbuild.md) [öğeleri](../msbuild/msbuild-items.md)


