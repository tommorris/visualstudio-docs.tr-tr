---
title: Silme görevi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Delete
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Delete task [MSBuild]
- MSBuild, Delete task
ms.assetid: 916bb2e3-3017-4828-ae27-c0b5c99bbb48
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1fc4c6d295c4154ab7c166b004af6c7432bbd88b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629003"
---
# <a name="delete-task"></a>Silme Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [görevi Sil](https://docs.microsoft.com/visualstudio/msbuild/delete-task).  
  
  
Belirtilen dosyaları siler.  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri aşağıdaki tabloda açıklanmıştır `Delete` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`DeletedFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Başarıyla silinen dosyaları belirtir.|  
|`Files`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametresi.<br /><br /> Dosyaları silmek için belirtir.|  
|`TreatErrorsAsWarnings`|İsteğe bağlı `Boolean` parametresi<br /><br /> Varsa `true`, hataları uyarı olarak kaydedilir. Varsayılan değer `false`.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametrelerin yanı sıra, bu görev parametreleri devralan <xref:Microsoft.Build.Tasks.TaskExtension> kendisi sınıfının devraldığı <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametrelerin ve Tanımlamaların bir listesi için bkz. [TaskExtension temel sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek dosyayı siler `MyApp.pdb`.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <PropertyGroup>  
        <AppName>MyApp</AppName>  
    </PropertyGroup>  
  
    <Target Name="DeleteFiles">  
        <Delete Files="$(AppName).pdb" />  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevleri](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)



