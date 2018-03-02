---
title: "Nasıl yapılır: MSBuild.exe kullanarak çözümlerde belirli hedefleri derleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, building specific targets in a solution
- msbuild.exe, building specific targets in a solution
- MSBuild, msbuild.exe
ms.assetid: f46feb9b-4c16-4fec-b6e1-36a959692ba3
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4437c8030f66ae24d94a83d796c0d0edf7e59c79
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2018
---
# <a name="how-to-build-specific-targets-in-solutions-by-using-msbuildexe"></a>Nasıl Yapılır: MSBuild.exe Kullanarak Çözümlerde Belirli Hedefleri Derleme
MSBuild.exe belirli projelerin bir çözümde belirli hedefler derleme için kullanabilirsiniz.  
  
### <a name="to-build-a-specific-target-of-a-specific-project-in-a-solution"></a>Bir çözümde belirli bir projenin belirli bir hedefe oluşturmak için  
  
1.  Komut satırında `MSBuild.exe <SolutionName>.sln`, burada `<SolutionName>` yürütmek istediğiniz hedef içeren çözümü dosya adına karşılık gelir.  
  
2. Sonra hedef belirtin `/target:` geçiş biçiminde  **`ProjectName`**  `:`  **`TargetName`** . Proje adı karakterlerden herhangi birini içeriyorsa, `%`, `$`, `@`, `;`, `.`, `(`, `)`, veya `'`, bunlarla yerine bir `_` belirtilen Hedef adı.
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek yürütür `Rebuild` hedefinin `NotInSlnFolder` proje ve ardından yürütür `Clean` hedefinin `InSolutionFolder` bulunan proje `NewFolder` Çözüm klasörü.  
  
```
msbuild SlnFolders.sln /target:NotInSlnfolder:Rebuild;NewFolder\InSolutionFolder:Clean`
```

## <a name="troubleshooting"></a>Sorun giderme

Kullanabileceğiniz seçenekler incelemek isterseniz, bunu yapmak için MSBuild tarafından sağlanan bir hata ayıklama seçeneği kullanabilirsiniz. Ortam değişkeni `MSBUILDEMITSOLUTION=1` ve çözümünüzü oluşturun. Bu adlı bir MSBuild dosya üretecektir `<SolutionName>.sln.metaproj` derleme zamanında MSBuild'ın iç çözüm görünümünü gösterir. Hangi hedefleri oluşturmak kullanılabilir olduğunu belirlemek için bu görünümü inceleyebilirsiniz.

Bu ortam değişkenini iç bu görünüm gerekmedikçe Ayarla derleme değil. Bu ayar, çözümünüzdeki projeler derleme sorunlara neden olabilir.

## <a name="see-also"></a>Ayrıca Bkz.  
 [Komut satırı başvurusu](../msbuild/msbuild-command-line-reference.md)   
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [ MSBuild](../msbuild/msbuild.md)  
 [MSBuild Kavramları](../msbuild/msbuild-concepts.md)
