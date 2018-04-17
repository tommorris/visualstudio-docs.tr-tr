---
title: Özellik öğesi (MSBuild) | Microsoft Docs
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
- <Property> Element [MSBuild]
- Property Element [MSBuild]
ms.assetid: 69ab08ab-3e76-41dd-a01b-49aa1d2e0cac
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7fdabde0da74ca2ae0c7417c3cc0c82016b0149d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="property-element-msbuild"></a>Özellik Öğesi (MSBuild)
Kullanıcı tanımlı özellik adını ve değerini içerir. Kullanılan her özellik bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] bir alt öğesi olarak proje belirtilen bir `PropertyGroup` öğesi.  

 \<Proje >  
 \<PropertyGroup >  

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
