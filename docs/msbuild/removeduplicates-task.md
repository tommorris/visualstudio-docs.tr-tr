---
title: RemoveDuplicates görevi | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2018
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#RemoveDuplicates
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, RemoveDuplicates task
- RemoveDuplicates task [MSBuild]
ms.assetid: 481cbab6-73ff-488c-aba5-2c09f9eb1e04
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f80fbff39f8db777ece495d1f777862b33821ccb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="removeduplicates-task"></a>RemoveDuplicates Görevi
Yinelenen öğe belirtilen öğeyi koleksiyondan kaldırır.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `RemoveDuplicates` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Filtered`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Öğe koleksiyonunun kaldırılan tüm yinelenen öğeler içeriyor. Her yinelenen öğe ilk örneği koruyarak giriş öğelerin sırasını korunur.|  
|`Inputs`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Yinelenen öğeleri kaldırmak için öğe koleksiyonu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu görev büyük/küçük harfe duyarlıdır ve öğe meta verisi çoğaltmaları belirlerken karşılaştırın değil.  
  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `RemoveDuplicates` yinelenen öğeleri kaldırmak için görev `MyItems` öğe koleksiyonu. Görev tamamlandığında, `FilteredItems` öğe koleksiyonunun bir öğe içeriyor.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MyItems Include="MyFile.cs"/>  
        <MyItems Include="MyFile.cs">  
            <Culture>fr</Culture>  
        </MyItems>  
        <MyItems Include="myfile.cs"/>  
    </ItemGroup>  
  
    <Target Name="RemoveDuplicateItems">  
        <RemoveDuplicates  
            Inputs="@(MyItems)">  
            <Output  
                TaskParameter="Filtered"  
                ItemName="FilteredItems"/>  
        </RemoveDuplicates>  
    </Target>  
</Project>  
```  

 Aşağıdaki örnekte gösterilir `RemoveDuplicates` görev kendi giriş sırası korur. Görev tamamlandığında, `FilteredItems` öğe koleksiyonu bu sırayla "MyFile2.cs", "MyFile1.cs" ve "MyFile3.cs" öğelerini içerir.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MyItems Include="MyFile2.cs"/>  
        <MyItems Include="MyFile1.cs" />  
        <MyItems Include="MyFile3.cs" />  
        <MyItems Include="myfile1.cs"/>  
    </ItemGroup>  
  
    <Target Name="RemoveDuplicateItems">  
        <RemoveDuplicates  
            Inputs="@(MyItems)">  
            <Output  
                TaskParameter="Filtered"  
                ItemName="FilteredItems"/>  
        </RemoveDuplicates>  
    </Target>  
</Project>  
```  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [MSBuild kavramları](../msbuild/msbuild-concepts.md)   
 [Görevler](../msbuild/msbuild-tasks.md)
