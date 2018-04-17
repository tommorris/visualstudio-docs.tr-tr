---
title: Büyük projeler derlerken belleği verimli şekilde kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- memory use (MSBuild)
- msbuild, efficient memory use building large trees
- caching (MSBuild)
ms.assetid: 853a21ed-69f7-4817-af00-57f73e2c74b5
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 515ffab922eb44ce6ebc0054b3df6a61ac668505
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="using-memory-efficiently-when-you-build-large-projects"></a>Büyük Projeler Derlerken Belleği Verimli Şekilde Kullanma
Büyük projeler genellikle birçok alt projeler ve diğer bağımlılıkları içerir ve bunlar büyük miktarda sistem bellek derleme zamanında tüketebilir. Kullanılabilir sistem belleğini azalır, sistem performansını da azalabilir. Eski sürümleri [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projeleri kalan bellekte veya sürüm 3.5 projeleri kaldırıldı, ancak sonraki alınması için bir önbellek yapı sonuçlarında korunur.  
  
 Sürüm 4.0 işler bu bellek yönetim otomatik olarak projeleri gibi özellikleri kullanmak zorunda kalmaktan kaydetme `UnloadProjectsOnCompletion` ve `UseResultsCache`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Paralel olarak birden çok proje derleme](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)