---
title: Getassemblyıdentity görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#GetAssemblyIdentity
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, GetAssemblyIdentity task
- GetAssemblyIdentity task [MSBuild]
ms.assetid: a977e072-37ad-4941-84a6-32a4483be55d
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 528b27c46897b3e58498b113bc558e7303ca2896
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="getassemblyidentity-task"></a>GetAssemblyIdentity Görevi
Belirtilen dosyalardan derleme kimlikleri alır ve kimlik bilgilerini çıkarır.  
  
## <a name="task-parameters"></a>Görev parametreleri  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `GetAssemblyIdentity` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Assemblies`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Alınan derleme kimliklerini içerir.|  
|`AssemblyFiles`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametresi.<br /><br /> Kimliklerden almak için dosyaları belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Öğeleri tarafından çıkış `Assemblies` parametreyi içeren öğe meta veri girdilerini adlı `Version`, `PublicKeyToken`, ve `Culture`.  
  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, belirtilen dosyaları kimliğini alır. `MyAssemblies` öğesi ve bunlara çıkaran `MyAssemblyIdentities` öğesi.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <MyAssemblies Include="File1.dll;File2.dll" />  
    </ItemGroup>  
    <Target Name="RetrieveIdentities">  
        <GetAssemblyIdentity  
            AssemblyFiles="@(MyAssemblies)"  
            <Output  
                TaskParameter="Assemblies"  
                ItemName="MyAssemblyIdentities"  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)