---
title: "Itemdefinitiongroup öğesi (MSBuild) | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#ItemDefinitionGroup
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ItemDefinitionGroup Element [MSBuild]
- <ItemDefinitionGroup> Element [MSBuild]
ms.assetid: 4e9fb04b-5148-4ae5-a394-42861dd62371
caps.latest.revision: "5"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 1a8444c63d7c025c04f212901e82cce6d5cf24da
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="itemdefinitiongroup-element-msbuild"></a>ItemDefinitionGroup Öğesi (MSBuild)
`ItemDefinitionGroup` Öğesi varsayılan olarak uygulanan tüm öğeleri projesinde, meta veri değerler öğe tanımları kümesini tanımlamak olanak sağlar. Itemdefinitiongroup yerini kullanmaya gerek [CreateItem görevi](../msbuild/createitem-task.md) ve [CreateProperty görevi](../msbuild/createproperty-task.md). Daha fazla bilgi için bkz: [öğe tanımları](../msbuild/item-definitions.md).  

 \<Proje >  
 \<Itemdefinitiongroup >  

## <a name="syntax"></a>Sözdizimi  

```  
<ItemDefinitionGroup Condition="'String A' == 'String B'">  
    <Item1>... </Item1>  
    <Item2>... </Item2>  
</ItemDefinitionGroup>  
```  

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  

### <a name="attributes"></a>Öznitelikler  

|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Condition`|İsteğe bağlı öznitelik. Değerlendirilecek koşulu. Daha fazla bilgi için bkz: [koşullar](../msbuild/msbuild-conditions.md).|  

### <a name="child-elements"></a>Alt Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Öğesi](../msbuild/item-element-msbuild.md)|Derleme işlemi için giriş tanımlar. Sıfır veya daha fazla olabilir `Item` öğelerinde bir `ItemDefinitionGroup`.|  

### <a name="parent-elements"></a>Üst Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Proje](../msbuild/project-element-msbuild.md)|Gerekli kök öğesinin bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyası.|  

## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde, m ve n, iki meta veri öğelerini bir Itemdefinitiongroup tanımlar. Bu örnekte, "m" meta veri öğesi "i" tarafından açıkça tanımlanmadığından varsayılan meta veri "m" "i" öğesine uygulanır. Ancak, meta verileri "n" "i" öğe tarafından zaten tanımlı olduğu için varsayılan meta veri "n" öğesi "i" uygulanmıyor.  

```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemDefinitionGroup>  
        <i>  
            <m>m1</m>  
            <n>n1</n>  
        </i>        
    </ItemDefinitionGroup>  
    <ItemGroup>  
        <i Include="a">  
            <o>o1</o>  
            <n>n2</n>  
        </i>  
    </ItemGroup>  
    ...  
</Project>  
```  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Öğeleri](../msbuild/msbuild-items.md)
