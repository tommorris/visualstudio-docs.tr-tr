---
title: ResolveManifestFiles görevi | Microsoft Docs
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
- ResolveManifestFiles task [MSBuild]
- MSBuild, ResolveManifestFiles task
ms.assetid: e1e14f67-9b69-433f-94d4-a783a68676b2
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 07a3753180ed568db19c523fd89901995e048606
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="resolvemanifestfiles-task"></a>ResolveManifestFiles Görevi
Derleme sürecindeki aşağıdaki öğeleri için bildirim üretme dosyaları Çözümler: öğeler, bağımlılıkları, uydunuz, içerik, hata ayıklama simgeleri ve belgeleri oluşturulmuş.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `ResolveManifestFiles` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`DeploymentManifestEntryPoint`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Dağıtım bildirimi adını belirtir.|  
|`EntryPoint`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Yönetilen derleme veya bildirime giriş noktası ClickOnce bildirim başvuru belirtir.|  
|`ExtraFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Ek dosyaları belirtir.|  
|`ManagedAssemblies`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Yönetilen derlemeler belirtir.|  
|`NativeAssemblies`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Yerel derlemeleri belirtir.|  
|`OutputAssemblies`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Oluşturulan derlemeleri belirtir.|  
|`OutputDeploymentManifestEntryPoint`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> çıkış parametresi.<br /><br /> Çıktı dağıtım bildirim giriş noktası belirtir.|  
|`OutputEntryPoint`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> çıkış parametresi.<br /><br /> Çıktı giriş noktası belirtir.|  
|`OutputFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Çıktı dosyalarını belirtir.|  
|`PublishFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Yayımlama dosyalarını belirtir.|  
|`SatelliteAssemblies`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Uydu derlemeleri belirtir.|  
|`SigningManifests`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, bildirimler imzalanmıştır.|  
|`TargetCulture`|İsteğe bağlı `String` parametresi.<br /><br /> Hedef kültürle için uydu derlemeleri belirtir.|  
|`TargetFrameworkVersion`|İsteğe bağlı `String` parametresi.<br /><br /> Hedef .NET Framework sürümünü belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tabloda listelenen parametreleri sahip olmaya ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)