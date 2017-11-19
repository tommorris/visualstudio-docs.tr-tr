---
title: "PropertyGroup öğesi (MSBuild) | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#PropertyGroup
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <PropertyGroup> element [MSBuild]
- PropertyGroup element [MSBuild]
ms.assetid: ff1e6c68-b9a1-4263-a1ce-dc3b829a64d4
caps.latest.revision: "21"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 27284df9459210a3ead5f69ba4db8f952ead5028
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="propertygroup-element-msbuild"></a>PropertyGroup Öğesi (MSBuild)
Kullanıcı tanımlı bir kümesini içerir [özelliği](../msbuild/property-element-msbuild.md) öğeleri. Her `Property` kullanılan öğesi bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje bir alt öğesi olması gerekir bir `PropertyGroup` öğesi.  

 \<Proje >  
 \<PropertyGroup >  

## <a name="syntax"></a>Sözdizimi  

```  
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
|[Proje](../msbuild/project-element-msbuild.md)|Gerekli kök öğesinin bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyası.|  

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
 [MSBuild özellikleri](../msbuild/msbuild-properties.md)
