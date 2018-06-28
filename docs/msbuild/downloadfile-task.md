---
title: DownloadFile görev | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#DownloadFile
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- DownloadFile task [MSBuild]
- MSBuild, DownloadFile task
ms.assetid: 916bb2e3-3017-4828-ae27-c0b5c99bbb48
caps.latest.revision: 16
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1f8a5a5ab1f1ca86b0378b14e666c8569a01fb27
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37059358"
---
# <a name="downloadfile-task"></a>DownloadFile görevi
Köprü Metni Aktarım Protokolü (HTTP) kullanarak belirtilen dosyaları indirir.

**Not:** `DownloadFile` görevdir MSBuild 15,8 ve yalnızca yukarıda kullanılabilir.
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `DownloadFile` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`DestinationFileName`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi<br /><br /> İndirilen Dosya için kullanılacak ad.  Varsayılan olarak, dosya adı türetildiği `SourceUrl` veya uzak sunucu.|
|`DestinationFolder`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Dosyayı indirmek için hedef klasörü belirtir.  Henüz yoksa klasörü oluşturduysanız.|
|`DownloadedFile`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> çıkış parametresi.<br /><br /> İndirilen dosyayı belirtir.|
|`Retries`|İsteğe bağlı `Int32` parametresi.<br /><br /> Tüm önceki deneme başarısız olursa, indirmeye için kaç kez belirtir. Varsayılan olarak sıfırdır.|  
|`RetryDelayMilliseconds`|İsteğe bağlı `Int32` parametresi.<br /><br /> Gerekli tüm yeniden denemeler arasındaki milisaniye cinsinden gecikme süresini belirtir. Varsayılan olarak 5000.|  
|`SkipUnchangedFiles`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, değiştirilmemiş olan dosya indirme atlar. Varsayılan olarak `true`. `DownloadFile` Görev, aynı boyutta varsa ve aynı son değiştirme zamanı uzak sunucu göre değişmeden kopyalanacak dosyaların göz önünde bulundurur. **Not:** dosyaların son değiştirilme tarihini yeniden yüklenecek dosyayı neden olacak tüm HTTP sunucuları belirtin.|
|`SourceUrl`|Gerekli `String` parametresi.<br /><br /> Karşıdan yüklemek için URL'yi belirtir.|
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir dosya yükler ve içinde içerir `Content` proje oluşturma önce öğeler.
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <PropertyGroup>  
      <MyUrl>https://raw.githubusercontent.com/Microsoft/msbuild/master/LICENSE</MyUrl>
    </PropertyGroup>  

    <Target Name="DownloadContentFiles" BeforeTargets="Build">
        <DownloadFile
            SourceUrl="$(MyUrl)"
            DestinationFolder="$(MSBuildProjectDirectory)">
        <Output TaskParameter="DownloadedFile" ItemName="Content" />
      </DownloadFile>
    </Target>

</Project>
```
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)
