---
title: ConvertToAbsolutePath görevi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ConvertToAbsolutePath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ConvertToAbsolutePath task [MSBuild]
- MSBuild, ConvertToAbsolutePath task
ms.assetid: f1af2cb8-b4ef-4a72-be80-22fa526c4491
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8438fcbbfffea57d3238b6a81b2cfa9e11118653
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631094"
---
# <a name="converttoabsolutepath-task"></a>ConvertToAbsolutePath Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ConvertToAbsolutePath görevi](https://docs.microsoft.com/visualstudio/msbuild/converttoabsolutepath-task).  
  
  
Bir göreli yol veya başvuru, bir mutlak yola dönüştürür.  
  
## <a name="task-parameters"></a>Görev parametreleri  
 Parametreleri aşağıdaki tabloda açıklanmıştır `ConvertToAbsolutePath` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Paths`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametresi.<br /><br /> Mutlak yoluna çevirmek için göreli yolların listesi.|  
|`AbsolutePaths`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Mutlak yollar geçirilen öğelerin listesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametrelerin yanı sıra, bu görev parametreleri devralan <xref:Microsoft.Build.Tasks.TaskExtension> kendisi sınıfının devraldığı <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametrelerin ve Tanımlamaların bir listesi için bkz. [TaskExtension temel sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevleri](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)



