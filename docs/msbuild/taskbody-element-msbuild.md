---
title: TaskBody öğesi (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- TaskBody element [MSBuild]
- <TaskBody> element [MSBuild]
ms.assetid: 49d8741b-f1ea-4470-94fd-a1ac27341a6a
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2ed55911dbb4d2cf477482885fb451be6a35e0e3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="taskbody-element-msbuild"></a>TaskBody Öğesi (MSBuild)
Geçirilen verileri içeren bir `UsingTask``TaskFactory`. Daha fazla bilgi için bkz: [UsingTask öğesi (MSBuild)](../msbuild/usingtask-element-msbuild.md).  

 \<Proje >  
 \<UsingTask >  
 \<TaskBody >  

## <a name="syntax"></a>Sözdizimi  

```  
<TaskBody Evaluate="true/false" />  
```  

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  

### <a name="attributes"></a>Öznitelikler  

|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Evaluate`|İsteğe bağlı Boole öznitelik.<br /><br /> Varsa `true`, MSBuild herhangi bir iç öğe değerlendirir ve bilgileri geçirmeden önce öğeleri ve özelliklerini genişletir `TaskFactory` görev örneği olduğunda.|  

### <a name="child-elements"></a>Alt Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|Veri|Metni arasında `TaskBody` etiketler için verbatim gönderilir `TaskFactory`.|  

### <a name="parent-elements"></a>Üst Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[UsingTask](../msbuild/usingtask-element-msbuild.md)|Görevleri kaydetmek için bir yol sağlar [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Sıfır veya daha fazla olabilir `UsingTask` proje öğelerinde.|  

## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `TaskBody` öğesi ile bir `Evaluate` özniteliği.  

```xml  
<UsingTask TaskName="MyTask" AssemblyName="My.Assembly" TaskFactory="MyTaskFactory">  
       <ParameterGroup>  
              <Parameter1 ParameterType="System.String" Required="False" Output="False"/>  
              <Parameter2 ParameterType="System.Int" Required="True" Output="False"/>  
              ...  
</ParameterGroup>  
       <TaskBody Evaluate="true">  
      ... Task factory-specific data ...  
       </TaskBody>  
</UsingTask>  
```  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)
