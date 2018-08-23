---
title: CreateVisualBasicManifestResourceName görevi | Microsoft Docs
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
- MSBuild, CreateVisualBasicManifestResourceName task
- CreateVisualBasicManifestResourceName task [MSBuild]
ms.assetid: 251c47b9-de32-414b-a138-bf45290af12e
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7a1588ce170ad9e833f7378a837e4e75853c19ba
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687175"
---
# <a name="createvisualbasicmanifestresourcename-task"></a>CreateVisualBasicManifestResourceName Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CreateVisualBasicManifestResourceName görevi](https://docs.microsoft.com/visualstudio/msbuild/createvisualbasicmanifestresourcename-task).  
  
  
Oluşturur bir [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]-belirtilen .resx dosya adı veya diğer kaynak bildirim adı stili.  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri aşağıdaki tabloda açıklanmıştır [CreateVisualBasicManifestResourceName görevi](../msbuild/createvisualbasicmanifestresourcename-task.md).  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`ManifestResourceNames`|<xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi salt okunur.<br /><br /> Sonuçta elde edilen bildirim adları.|  
|`ResourceFiles`|Gerekli `String` parametresi.<br /><br /> Oluşturulacağı kaynak dosyasının adı [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] bildirim adı.|  
|`RootNamespace`|İsteğe bağlı `String` parametresi.<br /><br /> Genellikle proje dosyasından alınan kaynak dosyasının kök ad alanı. Olabilir `null`.|  
|`PrependCultureAsDirectory`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, kültür adı bildirim kaynağı adına hemen önce bir dizin adı olarak eklenir. Varsayılan değer `true`.|  
|`ResourceFilesWithManifestResourceNames`|İsteğe bağlı salt okunur `String` çıkış parametresi.<br /><br /> Artık bildirim kaynağı adına içeren kaynak dosyasının adını döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 [CreateVisualBasicManifestResourceName görevi](../msbuild/createvisualbasicmanifestresourcename-task.md) belirli bir .resx veya başka bir kaynak dosyayı atamak için uygun bildirim kaynağı adını belirler. Görev, bir kaynak dosyası için mantıksal bir ad sağlar ve bir output parametresi olarak meta veriler ekler.  
  
 Yukarıda listelenen parametrelerin yanı sıra, bu görev parametreleri devralan <xref:Microsoft.Build.Tasks.TaskExtension> kendisi sınıfının devraldığı <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametrelerin ve Tanımlamaların bir listesi için bkz. [TaskExtension temel sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevleri](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)



