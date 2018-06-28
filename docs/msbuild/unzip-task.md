---
title: Görev sıkıştırmasını | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Unzip
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Unzip task [MSBuild]
- MSBuild, Unzip task
ms.assetid: 916bb2e3-3017-4828-ae27-c0b5c99bbb48
caps.latest.revision: 16
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4a46f2a079cc35e6c1add9e53abdcbdd283ddb9e
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37059357"
---
# <a name="unzip-task"></a>Görev sıkıştırmasını açın
Unzips bir `.zip` arşiv belirtilen konum için.

**Not:** `Unzip` görevdir MSBuild 15,8 ve yalnızca yukarıda kullanılabilir.
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `Unzip` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`DestinationFolder`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> parametresi<br /><br /> Dosyaya sıkıştırmasını açmak için hedef klasörü belirtir.|
|`OverwriteReadOnlyFiles`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, salt okunur dosyaların üzerine yazar. Varsayılan olarak `false`.|
|`SkipUnchangedFiles`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, değiştirilmemiş olan dosyaları şunu atlar. Varsayılan olarak `true`. `Unzip` görevi, dosyalar aynı boyuta ve aynı son değiştirme tarihine sahipse bu dosyaları değişmemiş kabul eder.|
|`SourceFiles`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametresi.<br /><br /> Sıkıştırmasını açmak için bir veya daha fazla belirtir. Birden çok dosya aynı klasöre sırayla sıkıştırması açılmış belirtirken.|
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir arşiv unzips ve salt okunur dosyaların üzerine yazar.
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <Target Name="UnzipArchive" BeforeTargets="Build">
        <Unzip
            SourceFiles="MyArchive.zip"
            DestinationFolder="$(OutputPath)\unzipped"
            OverwriteReadOnlyFiles="true"
        />
    </Target>

</Project>
```
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)
