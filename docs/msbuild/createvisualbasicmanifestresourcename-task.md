---
title: "CreateVisualBasicManifestResourceName görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
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
caps.latest.revision: "8"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 7f7b0858ec112bd78a0f2da6c9c6923414ada5e7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="createvisualbasicmanifestresourcename-task"></a>CreateVisualBasicManifestResourceName Görevi
Oluşturur bir [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]-stil bildirim adı verilen .resx dosya adı veya diğer kaynak.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır [CreateVisualBasicManifestResourceName görevi](../msbuild/createvisualbasicmanifestresourcename-task.md).  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`ManifestResourceNames`|<xref:Microsoft.Build.Framework.ITaskItem>`[]` çıkış parametresi salt okunur.<br /><br /> Sonuçta elde edilen bildirim adları.|  
|`ResourceFiles`|Gerekli `String` parametresi.<br /><br /> Oluşturulacağı kaynak dosyasının adı [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] bildirim adını.|  
|`RootNamespace`|İsteğe bağlı `String` parametresi.<br /><br /> Normalde proje dosyasından alınan kaynak dosyasını, kök ad alanı. Olabilir `null`.|  
|`PrependCultureAsDirectory`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, kültür adı bildirim kaynağı adı hemen önce bir dizin adı olarak eklenir. Varsayılan değer `true`.|  
|`ResourceFilesWithManifestResourceNames`|İsteğe bağlı salt okunur `String` çıkış parametresi.<br /><br /> Şimdi bildirim kaynağı adını içeren kaynak dosyasının adını döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 [CreateVisualBasicManifestResourceName görevi](../msbuild/createvisualbasicmanifestresourcename-task.md) verilen .resx veya diğer kaynak dosyası atamak için uygun bildirim kaynağı adını belirler. Görev bir kaynak dosya için mantıksal bir ad sağlar ve bir output parametresi meta veri olarak ekler.  
  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)