---
title: CreateProperty görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#CreateProperty
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- CreateProperty task [MSBuild]
- MSBuild, CreateProperty task
ms.assetid: fbc31a88-62d4-43d2-b739-68ef3fac38f5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 817d888a14d20b4778b28f81811b876c6d97ad61
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="createproperty-task"></a>CreateProperty Görevi
Geçirilen değerleri özellikleri doldurur. Bu, bir özellik veya dize diğerine kopyalanması için değerler sağlar.  
  
## <a name="attributes"></a>Öznitelikler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `CreateProperty` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Value`|İsteğe bağlı `String` çıkış parametresi.<br /><br /> Yeni özellik kopyalamak için bir değer belirtir.|  
|`ValueSetByTask`|İsteğe bağlı `String` çıkış parametresi.<br /><br /> Aynı değeri içeren `Value` parametresi. Yalnızca tarafından belirlenen output özelliği zorunda kalmamak istemiyorsanız bu parametreyi kullanın [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] zaman onu atlar kapsayan hedef çıkışları güncel olduğundan.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `CreateProperty` oluşturmak için görev `NewFile` özellik değerlerinin birleşimini kullanarak `SourceFilename` ve `SourceFileExtension` özelliği.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <PropertyGroup>  
        <SourceFilename>Module1</SourceFilename>  
        <SourceFileExtension>vb</SourceFileExtension>  
    </PropertyGroup>  
  
    <Target Name="CreateProperties">  
  
        <CreateProperty  
            Value="$(SourceFilename).$(SourceFileExtension)">  
            <Output  
                TaskParameter="Value"  
                PropertyName="NewFile" />  
        </CreateProperty>  
  
    </Target>  
  
</Project>  
```  
  
 Değeri, projenin çalıştırdıktan sonra `NewFile` özelliği `Module1.vb`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Görevler](../msbuild/msbuild-tasks.md)