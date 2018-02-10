---
title: "Özellik öğesi (MSBuild) | Microsoft Docs"
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
helpviewer_keywords:
- <Property> Element [MSBuild]
- Property Element [MSBuild]
ms.assetid: 69ab08ab-3e76-41dd-a01b-49aa1d2e0cac
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 9a71cb5d218c7c980e23f2fd9e87df2b614aece5
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="property-element-msbuild"></a>Özellik Öğesi (MSBuild)
Kullanıcı tanımlı özellik adını ve değerini içerir. Kullanılan her özellik bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] bir alt öğesi olarak proje belirtilen bir `PropertyGroup` öğesi.  

 \<Project>  
 \<PropertyGroup>  

## <a name="syntax"></a>Sözdizimi  

```  
<Property Condition="'String A' == 'String B'">  
    Property Value  
</Property>  
```  

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  

### <a name="attributes"></a>Öznitelikler  

|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Condition`|İsteğe bağlı öznitelik.<br /><br /> Değerlendirilecek koşulu. Daha fazla bilgi için bkz: [koşullar](../msbuild/msbuild-conditions.md).|  

### <a name="child-elements"></a>Alt Öğeler  
 Yok.  

### <a name="parent-elements"></a>Üst Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[PropertyGroup](../msbuild/propertygroup-element-msbuild.md)|Grouping öğesi özellikleri.|  

## <a name="text-value"></a>Metin Değeri  
 Metin değeri isteğe bağlıdır.  

 Bu metin özellik değerini belirtir ve XML içeriyor olabilir.  

## <a name="remarks"></a>Açıklamalar  
 Özellik adları, yalnızca ASCII karakterleri sınırlıdır. Özellik değerlerini başvurulan projede arasında özellik adı girerek "`$(`"ve"`)`". Örneğin, `$(builddir)\classes` "build\classes", çözümlemek `builddir` özellik değeri olan `build`. Özellikleri hakkında daha fazla bilgi için bkz: [MSBuild özellikleri](../msbuild/msbuild-properties.md).  

## <a name="example"></a>Örnek  
 Aşağıdaki kod kümeleri `Optimization` özelliğine `false` ve `DefaultVersion` özelliğine `1.0` varsa `Version` özelliği boşsa.  

```xml  
<PropertyGroup>  
    <Optimization>false</Optimization>  
    <DefaultVersion Condition="'$(Version)' == ''" >1.0</DefaultVersion>  
</PropertyGroup>  
```  

## <a name="see-also"></a>Ayrıca Bkz.
[MSBuild Özellikleri](../msbuild/msbuild-properties.md)  
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)
