---
title: Çıktı öğesi (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Output
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <Output> Element [MSBuild]
- Output Element [MSBuild]
ms.assetid: 34bc7cd1-efd3-4b57-b691-4584eeb6a0e9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 50786f1f42c27a793c48cb06c871b7f11c2dda25
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36325439"
---
# <a name="output-element-msbuild"></a>Çıktı Öğesi (MSBuild)
Depoları Görev çıkış değerleri öğeleri ve özellikler.  

 \<Proje >  
 \<Hedef >  
 \<Görev >  
 \<Çıktı >  

## <a name="syntax"></a>Sözdizimi  

```xml  
<Output TaskParameter="Parameter"  
    PropertyName="PropertyName"   
    Condition = "'String A' == 'String B'" />  
```  

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  

### <a name="attributes"></a>Öznitelikler  

|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`TaskParameter`|Gerekli öznitelik.<br /><br /> Görev adı parametresi çıktı.|  
|`PropertyName`|Ya da `PropertyName` veya `ItemName` özniteliği gereklidir.<br /><br /> Görev alır özelliği parametre değeri çıktı. Projenizi sonra özelliğiyle başvuruda bulunabilir `$(` *PropertyName* `)` sözdizimi. Bu özellik adı ya da yeni bir özellik adı veya projede zaten tanımlı bir ad olabilir.<br /><br /> Bu öznitelik, kullanılamaz `ItemName` de kullanılıyor.|  
|`ItemName`|Ya da `PropertyName` veya `ItemName` özniteliği gereklidir.<br /><br /> Görev alan öğesi parametre değeri çıktı. Projenizi sonra sahip öğe başvurusu yapabilir `@(` *ItemName* `)` sözdizimi. Öğe adı ya da yeni bir öğe adı veya projede zaten tanımlı bir ad olabilir.<br /><br /> Bu öznitelik, kullanılamaz `PropertyName` de kullanılıyor.|  
|`Condition`|İsteğe bağlı öznitelik.<br /><br /> Değerlendirilecek koşulu. Daha fazla bilgi için bkz: [koşullar](../msbuild/msbuild-conditions.md).|  

### <a name="child-elements"></a>Alt Öğeler  
 Yok.  

### <a name="parent-elements"></a>Üst Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Görev](../msbuild/task-element-msbuild.md)|Oluşturur ve bir örneğini yürüten bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] görev.|  

## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği kod `Csc` içine yürütülmekte olan görev bir `Target` öğesi. Bu örnek kapsamı dışında görev parametreler özellikleri ve öğeleri bildirilir. Çıkış parametresi değerinden `OutputAssembly` depolanan `FinalAssemblyName` öğesi ve çıkış parametresi değerinden `BuildSucceeded` depolanan `BuildWorked` özelliği. Daha fazla bilgi için bkz: [görevleri](../msbuild/msbuild-tasks.md).  

```xml  
<Target Name="Compile" DependsOnTargets="Resources">  
    <Csc  Sources="@(CSFile)"  
            TargetType="library"  
            Resources="@(CompiledResources)"  
            EmitDebugInformation="$(includeDebugInformation)"  
            References="@(Reference)"  
            DebugType="$(debuggingType)"  
            OutputAssembly="$(builtdir)\$(MSBuildProjectName).dll" >  
        <Output TaskParameter="OutputAssembly"  
                  ItemName="FinalAssemblyName" />  
        <Output TaskParameter="BuildSucceeded"  
                  PropertyName="BuildWorked" />  
    </Csc>  
</Target>  
```  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Görevler](../msbuild/msbuild-tasks.md)
