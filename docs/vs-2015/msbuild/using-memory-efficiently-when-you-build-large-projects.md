---
title: Büyük projeler derlerken belleği verimli şekilde kullanma | Microsoft Docs
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
- memory use (MSBuild)
- msbuild, efficient memory use building large trees
- caching (MSBuild)
ms.assetid: 853a21ed-69f7-4817-af00-57f73e2c74b5
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d2cb204fcfb5a96fe9833571895513dfda4449b8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687155"
---
# <a name="using-memory-efficiently-when-you-build-large-projects"></a>Büyük Projeler Derlerken Belleği Verimli Şekilde Kullanma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [kullanarak bellek etkin olduğunda, derleme büyük projeler](https://docs.microsoft.com/visualstudio/msbuild/using-memory-efficiently-when-you-build-large-projects).  
  
  
Büyük projeler çoğunlukla çok sayıda alt projeleri ve diğer bağımlılıklar içerir ve bunlar sistem belleği çok sayıda derleme zamanında tüketebilir. Kullanılabilir sistem belleğini azaldıkça, sistem performansı da azaltılabilir. Eski sürümlerini [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] projeleri kaldığını bellekte veya sürüm 3.5 projeleri kaldırıldı, ancak yapı sonuçlarını sonraki almak için bir önbellekte saklanır.  
  
 Sürüm 4.0 işleme bu bellek yönetimi otomatik olarak gibi özellikleri kullanmak zorunda kalmaktan projeleri kaydederek `UnloadProjectsOnCompletion` ve `UseResultsCache`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Paralel birden çok proje derleme](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)



