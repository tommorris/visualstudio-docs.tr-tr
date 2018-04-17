---
title: CreateProperty görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
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
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 461e2111f81919e7f6da72e540d8becfb9ed1c2e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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