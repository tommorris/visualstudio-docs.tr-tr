---
title: "Parametre öğesi | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
- xml
helpviewer_keywords:
- Parameter element [MSBuild]
- <Parameter> element [MSBuild]
ms.assetid: b273afff-b500-4e97-8cfd-31f39fa64a51
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 1ae8927c8a8f3a3fcd3f57075de281e3ee0679a1
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="parameter-element"></a>Parametre öğesi
Tarafından oluşturulan bir görev için söz konusu parametre hakkında bilgi içeren bir `UsingTask``TaskFactory`.  Öğesinin adı parametresi adıdır.  Daha fazla bilgiler için bkz: [UsingTask öğesi (MSBuild)](../msbuild/usingtask-element-msbuild.md).  

 \<Project>  
 \<UsingTask >  
 \<ParameterGroup>  
 \<Parametresi >  

## <a name="syntax"></a>Sözdizimi  

```  
<ParameterGroup ParameterType="SystemType"  
    Output="true/false"  
    Required="true/false" />  
```  

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  

### <a name="attributes"></a>Öznitelikler  

|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`ParameterType`|İsteğe bağlı öznitelik.<br /><br /> Örneğin, "System.String" parametresinin .NET türü.|  
|`Output`|İsteğe bağlı Boole öznitelik.<br /><br /> Varsa `true`, bu parametre bir görevin çıkış parametresidir. Varsayılan değer olan `false`.|  
|`Required`|İsteğe bağlı Boole öznitelik.<br /><br /> Varsa `true`, bu parametre görev için gerekli bir parametredir. Varsayılan değer olan `false`.|  

### <a name="child-elements"></a>Alt Öğeler  
 Yok.  

### <a name="parent-elements"></a>Üst Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[ParameterGroup](../msbuild/parametergroup-element.md)|Tarafından oluşturulan görev mevcut olacaktır parametreleri isteğe bağlı bir listesini içeren bir `UsingTask``TaskFactory`.|  

## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `Parameter` öğesi.  

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
