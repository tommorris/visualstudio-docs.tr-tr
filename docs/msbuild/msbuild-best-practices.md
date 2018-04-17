---
title: MSBuild en iyi yöntemleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- best practices, MSBuild
- MSBuild, best practices
ms.assetid: 90ef8693-e921-410a-a377-fe4d13f58c48
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 98d85a336a1741f6495959249fe605332d85aac2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="msbuild-best-practices"></a>MSBuild En İyi Yöntemleri
MSBuild komut dosyaları yazmak için aşağıdaki en iyi uygulamaları öneririz:  
  
-   Varsayılan özellik değerleri, kullanarak en iyi şekilde işlenir `Condition` özniteliği ve komut satırında bildirme varsayılan değeri geçersiz bir özellik tarafından. Örneğin, kullanın  
  
     `<MyProperty Condition="'$(MyProperty)' == ''">`  
  
     `MyDefaultValue`  
  
     `</MyProperty>`  
  
-   Öğeler seçtiğinizde joker karakterler kaçının. Bunun yerine, dosyaları açıkça belirtin. Bu, ekleyin veya dosya sildiğinizde oluşabilecek hatalar izlemek kolaylaştırır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gelişmiş kavramlar](../msbuild/msbuild-advanced-concepts.md)
