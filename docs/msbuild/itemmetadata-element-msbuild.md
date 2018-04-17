---
title: Itemmetadata öğesi (MSBuild) | Microsoft Docs
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
- ItemMetadata Element [MSBuild]
- <ItemMetadata> Element [MSBuild]
ms.assetid: e3db5122-202d-43a9-b2f4-3e0ec4ed3d08
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7c943243a1fc3a9ca2c6dc95bfc9c3e1824083ed
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="itemmetadata-element-msbuild"></a>ItemMetadata Öğesi (MSBuild)
Öğe meta veri değeri içeren bir kullanıcı tanımlı öğeyi meta verileri anahtar içerir. Bir öğe meta verileri anahtar-değer çiftleri herhangi bir sayıda olabilir.  

 \<Proje >  
 \<ItemGroup >  
 \<Öğe >  

## <a name="syntax"></a>Sözdizimi  

```  
<ItemMetadataName> Item Metadata value</ItemMetadataName>  
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
|[Öğesi](../msbuild/item-element-msbuild.md)|Derleme işlemi için giriş tanımlayan bir kullanıcı tanımlı öğesi.|  

## <a name="text-value"></a>Metin Değeri  
 Metin değeri isteğe bağlıdır.  

 Bu metin, metin veya XML öğesi meta veri değeri belirtir.  

## <a name="remarks"></a>Açıklamalar  

## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde nasıl ekleyeceğiniz gösterilmiştir `Culture` meta veri değeri ile `fr` öğesine `CSFile`.  

```xml  
<ItemGroup>  
    <CSFile Include="main.cs" >  
        <Culture>fr</Culture>  
    </CSFile>  
</ItemGroup>  
```  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Öğeleri](../msbuild/msbuild-items.md)
