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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 386a15bb0eb1d4fb88a89fc3683b7e0bdc088d6e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="using-memory-efficiently-when-you-build-large-projects"></a>Büyük Projeler Derlerken Belleği Verimli Şekilde Kullanma
Büyük projeler genellikle birçok alt projeler ve diğer bağımlılıkları içerir ve bunlar büyük miktarda sistem bellek derleme zamanında tüketebilir. Kullanılabilir sistem belleğini azalır, sistem performansını da azalabilir. Eski sürümleri [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projeleri kalan bellekte veya sürüm 3.5 projeleri kaldırıldı, ancak sonraki alınması için bir önbellek yapı sonuçlarında korunur.  
  
 Sürüm 4.0 işler bu bellek yönetim otomatik olarak projeleri gibi özellikleri kullanmak zorunda kalmaktan kaydetme `UnloadProjectsOnCompletion` ve `UseResultsCache`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Paralel olarak birden çok proje derleme](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)