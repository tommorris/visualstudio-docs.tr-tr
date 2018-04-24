---
title: MSBuild özel karakterleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- escape characters
- escape
- MSBuild Escape Characters
ms.assetid: 545e6a59-1093-4514-935e-78679a46fb3c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c1a2f67204fd6df7c8eb12ce5f13e8d1f4ec29d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="msbuild-special-characters"></a>MSBuild Özel Karakterleri
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] bazı karakterler belirli bağlamlarda özel kullanımı için ayırır. Bunları tam anlamıyla Bunlar ayrılmış olan bağlamda kullanmak istiyorsanız, bu tür karakterlerinden Çık yeterlidir. Örneğin, yalnızca özel anlamı bir yıldız işareti olan `Include` ve `Exclude` öznitelikleri öğesi tanımının ve çağrılarında `CreateItem`. Bu içeriklerden birinde bir yıldız işareti olarak görünmesi için bir yıldız işareti istiyorsanız, kaçış gerekir. Her bağlamda, yalnızca görünmesini istediğiniz yere yıldız işareti girin.  
  
 Bir özel karakter kaçınmak için sözdizimi % kullanın*xx*, burada *xx* karakter ASCII onaltılı değerini temsil eder. Daha fazla bilgi için bkz: [nasıl yapılır: MSBuild kaçış özel karakterleri](../msbuild/how-to-escape-special-characters-in-msbuild.md).  
  
## <a name="special-characters"></a>Özel Karakterler  
 Aşağıdaki tabloda [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] özel karakterler:  
  
|**Karakter**|**ASCII**|**Ayrılmış kullanım**|  
|-------------------|---------------|------------------------|  
|%|%25|Meta veri başvurma|  
|$|%24|Özellikler başvurma|  
|@|%40|Başvuru öğesi listeleri|  
|'|%27|Koşullar ve diğer ifadeleri|  
|;|% 3B|Liste ayırıcısı|  
|?|% 3F|Dosya adlarında joker karakter `Include` ve `Exclude` öznitelikleri|  
|*|%2A|Dosya adlarında kullanmak için joker karakter `Include` ve `Exclude` öznitelikleri|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gelişmiş kavramlar](../msbuild/msbuild-advanced-concepts.md)   
 [Öğeleri](../msbuild/msbuild-items.md)