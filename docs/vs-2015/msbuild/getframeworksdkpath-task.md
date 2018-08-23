---
title: GetFrameworkSdkPath görevi | Microsoft Docs
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
- http://schemas.microsoft.com/developer/msbuild/2003#GetFrameworkSdkPath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- GetFrameworkSdkPath task [MSBuild]
- MSBuild, GetFrameworkSdkPath task
ms.assetid: 2ef82b98-02b6-40cf-a9b5-f0e882fb5064
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d3e35cac8399ab97ae3825e35de5b249db7e23a7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629359"
---
# <a name="getframeworksdkpath-task"></a>GetFrameworkSdkPath Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [GetFrameworkSdkPath görevi](https://docs.microsoft.com/visualstudio/msbuild/getframeworksdkpath-task).  
  
  
Yolunu alır [!INCLUDE[winsdklong](../includes/winsdklong-md.md)].  
  
## <a name="task-parameters"></a>Görev parametreleri  
 Parametreleri aşağıdaki tabloda açıklanmıştır `GetFrameworkSdkPath` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`FrameworkSdkVersion20Path`|İsteğe bağlı `String` salt okunur çıkış parametresi.<br /><br /> Yol varsa, .NET SDK'sı sürüm 2.0, döndürür. Aksi halde döndürür `String.Empty`.|  
|`FrameworkSdkVersion35Path`|İsteğe bağlı `String` salt okunur çıkış parametresi.<br /><br /> Yol varsa, sürüm 3.5, .NET SDK döndürür. Aksi halde döndürür `String.Empty`.|  
|`FrameworkSdkVersion40Path`|İsteğe bağlı `String` salt okunur çıkış parametresi.<br /><br /> Yol varsa, .NET SDK'sı sürüm 4.0 döndürür. Aksi halde döndürür `String.Empty`.|  
|`Path`|İsteğe bağlı `String` çıkış parametresi.<br /><br /> Herhangi bir sürümü varsa, en son .NET SDK yolunu içerir. Aksi halde döndürür `String.Empty`.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametrelerin yanı sıra, bu görev parametreleri devralan <xref:Microsoft.Build.Tasks.TaskExtension> kendisi sınıfının devraldığı <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametrelerin ve Tanımlamaların bir listesi için bkz. [TaskExtension temel sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte `GetFrameworkSdkPath` yolunu depolamak için görev [!INCLUDE[winsdkshort](../includes/winsdkshort-md.md)] içinde `SdkPath` özelliği.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="GetPath">  
        <GetFrameworkSdkPath>  
            <Output  
                TaskParameter="Path"  
                PropertyName="SdkPath" />  
        </GetFrameworkSdkPath>  
        <Message Text="$(SdkPath)"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevleri](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)



