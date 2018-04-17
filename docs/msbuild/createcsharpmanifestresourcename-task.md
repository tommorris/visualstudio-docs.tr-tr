---
title: CreateCSharpManifestResourceName görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, CreateCSharpManifestResourceName task
- CreateCSharpManifestResourceName task [MSBuild]
ms.assetid: 2ace88c1-d757-40a7-8158-c1d3f5ff0511
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8b46f6802ce07adf67af61cd5efb92f65ee16035
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="createcsharpmanifestresourcename-task"></a>CreateCSharpManifestResourceName Görevi
Oluşturur bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]-stil bildirim adı verilen .resx dosya adı veya diğer kaynak.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır [CreateCSharpManifestResourceName görevi](../msbuild/createcsharpmanifestresourcename-task.md).  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`ManifestResourceNames`|<xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi salt okunur.<br /><br /> Sonuçta elde edilen bildirim adları.|  
|`ResourceFiles`|Gerekli `String` parametresi.<br /><br /> Oluşturulacağı kaynak dosyasının adı [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] bildirim adını.|  
|`RootNamespace`|İsteğe bağlı `String` parametresi.<br /><br /> Normalde proje dosyasından alınan kaynak dosyasını, kök ad alanı. Olabilir `null`.|  
|`PrependCultureAsDirectory`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, kültür adı bildirim kaynağı adı hemen önce bir dizin adı olarak eklenir. Varsayılan değer `true`.|  
|`ResourceFilesWithManifestResourceNames`|İsteğe bağlı salt okunur `String` çıkış parametresi.<br /><br /> Şimdi bildirim kaynağı adını içeren kaynak dosyasının adını döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 [CreateVisualBasicManifestResourceName görevi](../msbuild/createvisualbasicmanifestresourcename-task.md) verilen .resx veya diğer kaynak dosyası atamak için uygun bildirim kaynağı adını belirler. Görev bir kaynak dosya için mantıksal bir ad sağlar ve bir output parametresi meta veri olarak ekler.  
  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)