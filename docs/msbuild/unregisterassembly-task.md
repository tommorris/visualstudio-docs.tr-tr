---
title: "UnregisterAssembly görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#UnregisterAssembly
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, UnregisterAssembly task
- UnregisterAssembly task [MSBuild]
ms.assetid: 04f549dd-3591-4dda-9c3a-cf6ede9df2c3
caps.latest.revision: "21"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f1f2f0826b89a7a06d1682d4c991087f29c274c9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="unregisterassembly-task"></a>UnregisterAssembly Görevi
Belirtilen derlemelere COM birlikte çalışma amacıyla kaydını siler. Tersi şeklinde gerçekleştirir [RegisterAssembly görevi](../msbuild/registerassembly-task.md).  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `UnregisterAssembly` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Assemblies`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Sona erdirilecek derlemeleri belirtir.|  
|`AssemblyListFile`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Arasında durumu hakkında bilgi içeren `RegisterAssembly` görev ve `UnregisterAssembly` görev. Bu görev kaydetmek için başarısız bir derleme kaydı denemelerini engeller `RegisterAssembly` görev.<br /><br /> Bu parametre belirtilmezse, `Assemblies` ve `TypeLibFiles` parametreleri yok sayılır.|  
|`TypeLibFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Belirtilen derleme belirtilen tür kitaplığından kaydını siler. **Not:** Bu parametre yalnızca tür kitaplığı dosya adını derleme adından farklı olduğunda gereklidir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu derleme başarılı olması bu görev için mevcut gerekli. Var olmayan bir derleme kaydı çalışırsanız, görev bir uyarı ile başarılı olur. Bu durum, derleme kayıt defterinden kaldırmak için bu görev iş kaynaklanır. Derleme mevcut değilse, kayıt defterinde değildir ve bu nedenle, görev başarılı oldu.  
  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.AppDomainIsolatedTaskExtension> sınıfı, kendisi <xref:System.MarshalByRefObject> sınıfı. `MarshalByRefObject` Sınıf ile aynı işlevselliği sağlar <xref:Microsoft.Build.Utilities.Task> sınıfı, ancak kendi uygulama etki alanında örneği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `UnregisterAssembly` görev tarafından belirtilen yoldaki derleme kaydı `OutputPath` ve `FileName` varsa özellikleri.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <PropertyGroup>  
        <OutputPath>\Output\</OutputPath>  
        <FileName>MyFile.dll</FileName>  
    </PropertyGroup>  
    <Target Name="UnregisterAssemblies">  
        <UnregisterAssembly  
            Condition="Exists('$(OutputPath)$(FileName)')"  
            Assemblies="$(OutputPath)$(FileName)" />  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [RegisterAssembly görevi](../msbuild/registerassembly-task.md)   
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)