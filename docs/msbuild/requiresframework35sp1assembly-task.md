---
title: "RequiresFramework35SP1Assembly görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- RequiresFramework35SP1Assembly task [MSBuild]
- MSBuild, RequiresFramework35SP1Assembly task
ms.assetid: 755c018a-8a8b-4c94-8aee-3f171fc419e5
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e95632e1b339e7b86253763fa65237165eb05618
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="requiresframework35sp1assembly-task"></a>RequiresFramework35SP1Assembly Görevi
Uygulama .NET Framework 3.5 SP1 gerekli olup olmadığını belirler.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `RequiresFramework35SP1Assembly` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Assemblies`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Başvurulan bir derleme uygulamada belirtir.|  
|`CreateDesktopShortcut`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, yükleme sırasında masaüstünde bir kısayol simgesini oluşturur.|  
|`DeploymentManifestEntryPoint`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Uygulama bildirim dosyasının adını belirtir.|  
|`EntryPoint`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Uygulamayı çalıştırdığınızda, yürütülmesi gereken derleme belirtir.|  
|`ErrorReportUrl`|İsteğe bağlı `String` parametresi.<br /><br /> ClickOnce yüklemeleri sırasında karşılaşılan iletişim kutularında görüntülenen Web sitesini belirtir.|  
|`Files`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Uygulama yayımlandığında, dağıtılan dosyaların listesini belirtir.|  
|`ReferencedAssemblies`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Başvurulan bir derleme projede belirtir.|  
|`RequiresMinimumFramework35SP1`|İsteğe bağlı `Boolean` çıkış parametresi.<br /><br /> Varsa `true`, uygulama .NET Framework 3.5 SP1 gerektiriyor.|  
|`SigningManifests`|İsteğe bağlı `Boolean` çıkış parametresi.<br /><br /> Varsa `true`, ClickOnce bildirimlerini imzalanmıştır.|  
|`SuiteName`|İsteğe bağlı `String` parametresi.<br /><br /> Klasörün adını belirtir. **Başlat** menüsü, uygulama yüklenir.|  
|`TargetFrameworkVersion`|İsteğe bağlı `String` parametresi.<br /><br /> .NET Framework sürümünü belirtir, bu uygulama hedefler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tabloda listelenen parametreleri sahip olmaya ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)