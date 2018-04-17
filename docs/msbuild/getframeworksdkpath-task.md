---
title: GetFrameworkSdkPath görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
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
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f274aec61ea583887650a6bd3548a184b151daae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="getframeworksdkpath-task"></a>GetFrameworkSdkPath Görevi
Yolunu alır [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)].  
  
## <a name="task-parameters"></a>Görev parametreleri  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `GetFrameworkSdkPath` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`FrameworkSdkVersion20Path`|İsteğe bağlı `String` salt okunur çıktı parametresi.<br /><br /> Yol varsa, sürüm 2.0, .NET SDK döndürür. Aksi takdirde döndürür `String.Empty`.|  
|`FrameworkSdkVersion35Path`|İsteğe bağlı `String` salt okunur çıktı parametresi.<br /><br /> Yol varsa, sürüm 3.5, .NET SDK döndürür. Aksi takdirde döndürür `String.Empty`.|  
|`FrameworkSdkVersion40Path`|İsteğe bağlı `String` salt okunur çıktı parametresi.<br /><br /> Yol varsa, .NET SDK'sı sürüm 4.0 döndürür. Aksi takdirde döndürür `String.Empty`.|  
|`Path`|İsteğe bağlı `String` çıkış parametresi.<br /><br /> Herhangi bir sürümü varsa, en son .NET SDK yolunu içerir. Aksi takdirde döndürür `String.Empty`.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `GetFrameworkSdkPath` yolunu depolamak için görev [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] içinde `SdkPath` özelliği.  
  
```xml  
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
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)