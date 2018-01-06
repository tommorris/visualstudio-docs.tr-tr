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
ms.workload: multiple
ms.openlocfilehash: 1e78afd0f76839d170f12cf4315610c183899fff
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="using-memory-efficiently-when-you-build-large-projects"></a>Büyük Projeler Derlerken Belleği Verimli Şekilde Kullanma
Büyük projeler genellikle birçok alt projeler ve diğer bağımlılıkları içerir ve bunlar büyük miktarda sistem bellek derleme zamanında tüketebilir. Kullanılabilir sistem belleğini azalır, sistem performansını da azalabilir. Eski sürümleri [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projeleri kalan bellekte veya sürüm 3.5 projeleri kaldırıldı, ancak sonraki alınması için bir önbellek yapı sonuçlarında korunur.  
  
 Sürüm 4.0 işler bu bellek yönetim otomatik olarak projeleri gibi özellikleri kullanmak zorunda kalmaktan kaydetme `UnloadProjectsOnCompletion` ve `UseResultsCache`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Paralel olarak birden çok proje derleme](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)