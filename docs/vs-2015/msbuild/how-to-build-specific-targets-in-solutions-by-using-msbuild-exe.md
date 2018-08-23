---
title: 'Nasıl yapılır: MSBuild.exe kullanarak çözümlerde belirli hedefleri derleme | Microsoft Docs'
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
- MSBuild, building specific targets in a solution
- msbuild.exe, building specific targets in a solution
- MSBuild, msbuild.exe
ms.assetid: f46feb9b-4c16-4fec-b6e1-36a959692ba3
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0bdc5d824d802916c38ef0267dae0de85e8814e8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631724"
---
# <a name="how-to-build-specific-targets-in-solutions-by-using-msbuildexe"></a>Nasıl Yapılır: MSBuild.exe Kullanarak Çözümlerde Belirli Hedefleri Derleme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: belirli hedefleri derleme çözümler tarafından kullanarak MSBuild.exe içinde](https://docs.microsoft.com/visualstudio/msbuild/how-to-build-specific-targets-in-solutions-by-using-msbuild-exe).  
  
  
MSBuild.exe belirli projelerin bir çözümde belirli hedefler oluşturmak için kullanabilirsiniz.  
  
### <a name="to-build-a-specific-target-of-a-specific-project-in-a-solution"></a>Belirli bir hedef bir çözümde belirli bir proje oluşturmak için  
  
1.  Komut satırında `MSBuild.exe <SolutionName>.sln`burada `<SolutionName>` yürütmek istediğiniz hedef içeren çözüm dosya adına karşılık gelir.  
  
2.  Sonra hedef belirtmek **/t** geçiş biçiminde *ProjectName*:*TargetName*.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek yürütür `Rebuild` hedefinin `NotInSlnFolder` proje ve sonra yürütür `Clean` hedefinin `InSolutionFolder` bulunan proje `NewFolder` Çözüm klasörü.  
  
```  
msbuild SlnFolders.sln /t:NotInSlnfolder:Rebuild;NewFolder\InSolutionFolder:Clean  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komut satırı başvurusu](../msbuild/msbuild-command-line-reference.md)   
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [ MSBuild](msbuild.md)  
 [MSBuild Kavramları](../msbuild/msbuild-concepts.md)


