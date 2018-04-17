---
title: FindUnderPath görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#FindUnderPath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, FindUnderPath task
- FindUnderPath task [MSBuild]
ms.assetid: 3c6d58b0-36e8-47aa-bfca-b73dd2045d91
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a63c8df23caa8befdd4e8c9ebfd05aba273053dc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="findunderpath-task"></a>FindUnderPath Görevi
Belirtilen öğe koleksiyonunda hangi öğelerin veya belirtilen klasör altındaki yolları olduğunu belirler.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `FindUnderPath` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Files`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Yolları tarafından belirtilen yol ile karşılaştırılabilir dosyaları belirtir `Path` parametresi.|  
|`InPath`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Belirtilen yolu altında bulunan öğeler içeriyor.|  
|`OutOfPath`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Belirtilen yolun bulunamadı öğeleri içerir.|  
|`Path`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Referans olarak kullanmak üzere klasörün yolunu belirtir.|  
|`UpdateToAbsolutePaths`|İsteğe bağlı `Boolean` parametresi.<br /><br /> TRUE ise, çıktı öğeleri yollarını mutlak yollar olacak şekilde güncelleştirilir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `FindUnderPath` dosyaları içinde yer alan varsa belirlemek için görev `MyFiles` öğesi tarafından belirtilen yolun altındaki mevcut yoluna sahip `SearchPath` özelliği. Görev tamamlandıktan sonra `FilesNotFoundInPath` öğeyi içeren `File1.txt` dosyası ve `FilesFoundInPath` öğeyi içeren `File2.txt` dosya.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <MyFiles Include="C:\File1.txt" />  
        <MyFiles Include="C:\Projects\MyProject\File2.txt" />  
    </ItemGroup>  
  
    <PropertyGroup>  
        <SearchPath>C:\Projects\MyProject</SearchPath>  
    </PropertyGroup>  
  
    <Target Name="FindFiles">  
        <FindUnderPath  
            Files="@(MyFiles)"  
            Path="$(SearchPath)">  
            <Output  
                TaskParameter="InPath"  
                ItemName="FilesFoundInPath" />  
            <Output  
                TaskParameter="OutOfPath"  
                ItemName="FilesNotFoundInPath" />  
        </FindUnderPath>  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Görevler](../msbuild/msbuild-tasks.md)   
 [MSBuild Kavramları](../msbuild/msbuild-concepts.md)