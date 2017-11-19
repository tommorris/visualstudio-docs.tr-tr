---
title: "Büyük projeler derlerken belleği verimli şekilde kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- memory use (MSBuild)
- msbuild, efficient memory use building large trees
- caching (MSBuild)
ms.assetid: 853a21ed-69f7-4817-af00-57f73e2c74b5
caps.latest.revision: "11"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: e9484e0b8771ad665f1891298ff2f6a8a1d0005e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="using-memory-efficiently-when-you-build-large-projects"></a>Büyük Projeler Derlerken Belleği Verimli Şekilde Kullanma
Büyük projeler genellikle birçok alt projeler ve diğer bağımlılıkları içerir ve bunlar büyük miktarda sistem bellek derleme zamanında tüketebilir. Kullanılabilir sistem belleğini azalır, sistem performansını da azalabilir. Eski sürümleri [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projeleri kalan bellekte veya sürüm 3.5 projeleri kaldırıldı, ancak sonraki alınması için bir önbellek yapı sonuçlarında korunur.  
  
 Sürüm 4.0 işler bu bellek yönetim otomatik olarak projeleri gibi özellikleri kullanmak zorunda kalmaktan kaydetme `UnloadProjectsOnCompletion` ve `UseResultsCache`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Paralel olarak birden çok proje derleme](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)