---
title: FindAppConfigFile görevi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- FindAppConfigFile task [MSBuild]
- MSBuild, FindAppConfigFile task
ms.assetid: e292de3e-7482-4426-83ce-d921061808bf
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1f3bffd988f10f5f396e96c920a27369c708012a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631104"
---
# <a name="findappconfigfile-task"></a>FindAppConfigFile Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [FindAppConfigFile görevi](https://docs.microsoft.com/visualstudio/msbuild/findappconfigfile-task).  
  
  
Sağlanan listelerinde app.config dosyasına bulur  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri aşağıdaki tabloda açıklanmıştır `FindAppConfigFile` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`AppConfigFile`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Varsa listesinde bulunan eşleşen ilk öğeyi belirtir.|  
|`PrimaryList`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametresi.<br /><br /> Arama için birincil listesini belirtir.|  
|`SecondaryList`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametresi.<br /><br /> Arama için ikincil listesini belirtir.|  
|`TargetPath`|Gerekli `String` parametresi.<br /><br /> Meta veri olarak eklemek için bir değer belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tabloda listelenen parametreleri sahip olmaya ek olarak, bu görev parametreleri devralan <xref:Microsoft.Build.Tasks.TaskExtension> kendisi sınıfının devraldığı <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametrelerin ve Tanımlamaların bir listesi için bkz. [TaskExtension temel sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevleri](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)



