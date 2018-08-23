---
title: CreateCSharpManifestResourceName görevi | Microsoft Docs
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
- MSBuild, CreateCSharpManifestResourceName task
- CreateCSharpManifestResourceName task [MSBuild]
ms.assetid: 2ace88c1-d757-40a7-8158-c1d3f5ff0511
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bf5f98d4eddf7daa6099b97d805a50c59902572c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42681373"
---
# <a name="createcsharpmanifestresourcename-task"></a>CreateCSharpManifestResourceName Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CreateCSharpManifestResourceName görevi](https://docs.microsoft.com/visualstudio/msbuild/createcsharpmanifestresourcename-task).  
  
  
Oluşturur bir [!INCLUDE[csprcs](../includes/csprcs-md.md)]-belirtilen .resx dosya adı veya diğer kaynak bildirim adı stili.  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri aşağıdaki tabloda açıklanmıştır [CreateCSharpManifestResourceName görevi](../msbuild/createcsharpmanifestresourcename-task.md).  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`ManifestResourceNames`|<xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi salt okunur.<br /><br /> Sonuçta elde edilen bildirim adları.|  
|`ResourceFiles`|Gerekli `String` parametresi.<br /><br /> Oluşturulacağı kaynak dosyasının adı [!INCLUDE[csprcs](../includes/csprcs-md.md)] bildirim adı.|  
|`RootNamespace`|İsteğe bağlı `String` parametresi.<br /><br /> Genellikle proje dosyasından alınan kaynak dosyasının kök ad alanı. Olabilir `null`.|  
|`PrependCultureAsDirectory`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, kültür adı bildirim kaynağı adına hemen önce bir dizin adı olarak eklenir. Varsayılan değer `true`.|  
|`ResourceFilesWithManifestResourceNames`|İsteğe bağlı salt okunur `String` çıkış parametresi.<br /><br /> Artık bildirim kaynağı adına içeren kaynak dosyasının adını döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 [CreateVisualBasicManifestResourceName görevi](../msbuild/createvisualbasicmanifestresourcename-task.md) belirli bir .resx veya başka bir kaynak dosyayı atamak için uygun bildirim kaynağı adını belirler. Görev, bir kaynak dosyası için mantıksal bir ad sağlar ve bir output parametresi olarak meta veriler ekler.  
  
 Yukarıda listelenen parametrelerin yanı sıra, bu görev parametreleri devralan <xref:Microsoft.Build.Tasks.TaskExtension> kendisi sınıfının devraldığı <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametrelerin ve Tanımlamaların bir listesi için bkz. [TaskExtension temel sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevleri](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)



