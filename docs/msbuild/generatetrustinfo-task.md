---
title: Generatetrustınfo görevi | Microsoft Docs
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
- MSBuild, GenerateTrustInfo task
- GenerateTrustInfo task [MSBuild]
ms.assetid: 3ca60816-4bb0-4fef-ae43-ca0bfb63def3
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d86369da4ecbae0aed08926705d4a805e1cfc7e9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="generatetrustinfo-task"></a>GenerateTrustInfo Görevi
Temel bildirim ve'ndan uygulama güven oluşturur `TargetZone` ve `ExcludedPermissions` parametreleri.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `GenerateTrustInfo` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`ApplicationDependencies`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Bağımlı derlemeleri belirtir.|  
|`BaseManifest`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Uygulama güven oluşturmak için temel bildirimi belirtir.|  
|`ExcludedPermissions`|İsteğe bağlı `String` parametresi.<br /><br /> Bölge varsayılan izni kümesinden çıkarılacak bir veya daha çok noktalı virgülle ayrılmış izni kimlik değerleri belirtir.|  
|`TargetZone`|İsteğe bağlı `String` parametresi.<br /><br /> Makine ilkesinden alınan bir bölge varsayılan izin kümesini belirtir.|  
|`TrustInfoFile`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> çıkış parametresi.<br /><br /> Uygulama güvenlik güven bilgilerini içeren dosyayı belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tabloda listelenen parametreleri sahip olmaya ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)