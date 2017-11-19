---
title: "Generatetrustınfo görevi | Microsoft Docs"
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
- MSBuild, GenerateTrustInfo task
- GenerateTrustInfo task [MSBuild]
ms.assetid: 3ca60816-4bb0-4fef-ae43-ca0bfb63def3
caps.latest.revision: "4"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 9360cce21ab859e962734e240977c67627b8739f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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