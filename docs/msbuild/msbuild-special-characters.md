---
title: "MSBuild özel karakterleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- escape characters
- escape
- MSBuild Escape Characters
ms.assetid: 545e6a59-1093-4514-935e-78679a46fb3c
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e1d7dc27d4a831e8e0a54cada37fcfdb94afd718
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="msbuild-special-characters"></a>MSBuild Özel Karakterleri
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] bazı karakterler belirli bağlamlarda özel kullanımı için ayırır. Bunları tam anlamıyla Bunlar ayrılmış olan bağlamda kullanmak istiyorsanız, bu tür karakterlerinden Çık yeterlidir. Örneğin, yalnızca özel anlamı bir yıldız işareti olan `Include` ve `Exclude` öznitelikleri öğesi tanımının ve çağrılarında `CreateItem`. Bu içeriklerden birinde bir yıldız işareti olarak görünmesi için bir yıldız işareti istiyorsanız, kaçış gerekir. Her bağlamda, yalnızca görünmesini istediğiniz yere yıldız işareti girin.  
  
 Bir özel karakter kaçınmak için sözdizimi % kullanın*xx*, burada *xx* karakter ASCII onaltılı değerini temsil eder. Daha fazla bilgi için bkz: [nasıl yapılır: MSBuild kaçış özel karakterleri](../msbuild/how-to-escape-special-characters-in-msbuild.md).  
  
## <a name="special-characters"></a>Özel Karakterler  
 Aşağıdaki tabloda [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] özel karakterler:  
  
|**Character**|**ASCII**|**Ayrılmış kullanım**|  
|-------------------|---------------|------------------------|  
|%|%25|Meta veri başvurma|  
|$|%24|Özellikler başvurma|  
|@|%40|Başvuru öğesi listeleri|  
|'|%27|Koşullar ve diğer ifadeleri|  
|;|%3B|Liste ayırıcısı|  
|?|%3F|Dosya adlarında joker karakter `Include` ve `Exclude` öznitelikleri|  
|*|%2A|Dosya adlarında kullanmak için joker karakter `Include` ve `Exclude` öznitelikleri|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gelişmiş kavramlar](../msbuild/msbuild-advanced-concepts.md)   
 [Öğeleri](../msbuild/msbuild-items.md)