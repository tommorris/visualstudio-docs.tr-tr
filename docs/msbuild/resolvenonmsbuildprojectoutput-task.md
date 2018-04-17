---
title: ResolveNonMSBuildProjectOutput görevi | Microsoft Docs
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
- MSBuild, ResolveNonMSBuildProjectOutput task
- ResolveNonMSBuildProjectOutput task [MSBuild]
ms.assetid: a0b8fcec-8c8d-4867-85ac-5304c5108e5e
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6ab0c330634fcd830e797ee5b94136532a4dd5bb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="resolvenonmsbuildprojectoutput-task"></a>ResolveNonMSBuildProjectOutput Görevi
MSBuild dışındaki proje başvuruları için çıktı dosyaları belirler.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `ResolveNonMSBuildProjectOutput` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`PreresolvedProjectOutputs`|İsteğe bağlı `String` parametresi.<br /><br /> Proje çıktıları içeren bir XML dizesi çözülmüş belirtir.|  
|`ProjectReferences`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametresi.<br /><br /> Proje başvurularını belirtir.|  
|`ResolvedOutputPaths`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Çözümlenen başvuru yollar listesi içerir (ve orijinal proje başvuru öznitelikleri korur).|  
|`UnresolvedProjectReferences`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Çıkış preresolved listesini kullanarak çözümlenemedi proje başvurusu öğeleri listesini içerir.<br /><br /> Visual Studio yalnızca MSBuild olmayan projeleri preresolves olduğundan, bu listede proje başvuruları MSBuild biçiminde olduğunu gösterir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tabloda listelenen parametreleri sahip olmaya ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)