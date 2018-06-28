---
title: ZipDirectory görev | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ZipDirectory
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ZipDirectory task [MSBuild]
- MSBuild, ZipDirectory task
ms.assetid: 916bb2e3-3017-4828-ae27-c0b5c99bbb48
caps.latest.revision: 16
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e0d818c6ffbef8502634e80903f6cf1dc853e6ce
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37059356"
---
# <a name="zipdirectory-task"></a>ZipDirectory görevi
Oluşturur bir `.zip` bir dizinin içeriğini arşivinden.

**Not:** `ZipDirectory` görevdir MSBuild 15,8 ve yalnızca yukarıda kullanılabilir.
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `ZipDirectory` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`DestinationFile`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> parametresi<br /><br /> Tam yolunu `.zip` oluşturmak için dosya.|
|`Overwrite`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, hedef dosya varsa yazılır atlar. Varsayılan olarak `false`.|
|`SourceDirectory`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Dizini oluşturmak için belirtir bir `.zip` dan arşivleyin.|
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir `.zip` bir projesi oluşturduktan sonra çıktı dizini arşivinden.
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <PropertyGroup>
      <ZipOutputPath>$(MSBuildProjectDirectory)</ZipOutputPath>
    </PropertyGroup>

    <Target Name="ZipOutputPath" AfterTargets="Build">
        <ZipDirectory
            SourceDirectory="$(OutputPath)"
            DestinationFile="$(MSBuildProjectDirectory)\output.zip">
        />
    </Target>

</Project>
```
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)
