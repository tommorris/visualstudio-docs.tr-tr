---
title: PropertyGroup öğesi (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#PropertyGroup
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <PropertyGroup> element [MSBuild]
- PropertyGroup element [MSBuild]
ms.assetid: ff1e6c68-b9a1-4263-a1ce-dc3b829a64d4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1b7d300a1a47499f963e7ff717c12f72e2483e05
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36326325"
---
# <a name="propertygroup-element-msbuild"></a>PropertyGroup Öğesi (MSBuild)
Kullanıcı tanımlı bir kümesini içerir [özelliği](../msbuild/property-element-msbuild.md) öğeleri. Her `Property` kullanılan öğesi bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje bir alt öğesi olması gerekir bir `PropertyGroup` öğesi.  

 \<Proje >  
 \<PropertyGroup >  

## <a name="syntax"></a>Sözdizimi  

```xml  
<PropertyGroup Condition="'String A' == 'String B'">  
    <Property1>...</Property1>  
    <Property2>...</Property2>  
</PropertyGroup>  
```  

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  

### <a name="attributes"></a>Öznitelikler  

|Öznitelik|Açıklama|  
|---------------|-----------------|  
|Koşul|İsteğe bağlı öznitelik.<br /><br /> Değerlendirilecek koşulu. Daha fazla bilgi için bkz: [koşullar](../msbuild/msbuild-conditions.md).|  

### <a name="child-elements"></a>Alt Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Özelliği](../msbuild/property-element-msbuild.md)|İsteğe bağlı öğe.<br /><br /> Özellik değeri içeren bir kullanıcı tanımlı özellik adı. Sıfır veya daha fazla olabilir *özelliği* öğelerinde bir `PropertyGroup` öğesi.|  

### <a name="parent-elements"></a>Üst Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Project](../msbuild/project-element-msbuild.md)|Gerekli kök öğesinin bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyası.|  

## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde bir koşula göre özelliklerin nasıl ayarlanacağını gösterir. Bu örnekte, değeri `CompileConfig` özelliği `DEBUG`, `Optimization`, `Obfuscate`, ve `OutputPath` özelliklerini içinde `PropertyGroup` öğesi ayarlanır.  

```xml  
<PropertyGroup Condition="'$(CompileConfig)' == 'DEBUG'" >  
    <Optimization>false</Optimization>  
    <Obfuscate>false</Obfuscate>  
    <OutputPath>$(OutputPath)\debug</OutputPath>  
</PropertyGroup>  
```  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)  
 [MSBuild Özellikleri](../msbuild/msbuild-properties.md)
