---
title: ItemGroup öğesi (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ItemGroup
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ItemGroup element [MSBuild]
- <ItemGroup> element [MSBuild]
ms.assetid: aac894e3-a9f1-4bbc-a796-6ef07001f35b
caps.latest.revision: 27
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c006d7622c8af76694618e828b014f695914fd58
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683744"
---
# <a name="itemgroup-element-msbuild"></a>ItemGroup Öğesi (MSBuild)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ItemGroup öğesi (MSBuild)](https://docs.microsoft.com/visualstudio/msbuild/itemgroup-element-msbuild).  
  
  
Kullanıcı tanımlı bir dizi içeren [öğesi](../msbuild/item-element-msbuild.md) öğeleri. Kullanılan her öğe bir [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] alt öğesi olarak proje belirtilen bir `ItemGroup` öğesi.  
  
 \<Proje >  
 \<ItemGroup >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<ItemGroup Condition="'String A' == 'String B'">  
    <Item1>... </Item1>  
    <Item2>... </Item2>  
</ItemGroup>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Condition`|İsteğe bağlı öznitelik. Değerlendirilecek koşul. Daha fazla bilgi için [koşullar](../msbuild/msbuild-conditions.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Öğesi](../msbuild/item-element-msbuild.md)|Yapı işlemi için girişler tanımlar. Sıfır veya daha fazla olabilir `Item` öğelerinde bir `ItemGroup`.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Project](../msbuild/project-element-msbuild.md)|Gerekli kök öğesi bir [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] proje dosyası.|  
|[Hedef](../msbuild/target-element-msbuild.md)|.NET Framework 3.5 ile başlayan `ItemGroup` öğe içindeki görünebilir bir `Target` öğesi. Daha fazla bilgi için [hedefleri](../msbuild/msbuild-targets.md).|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği kullanıcı tarafından tanımlanan öğe koleksiyonlarını gösterir `Res` ve `CodeFiles` içinde bildirilen bir `ItemGroup` öğesi. Her bir öğe içinde `Res` içeren kullanıcı tanımlı bir alt öğe koleksiyonu [Itemmetadata](../msbuild/itemmetadata-element-msbuild.md) öğesi.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Res Include = "Strings.fr.resources" >  
            <Culture>fr</Culture>  
        </Res>  
        <Res Include = "Dialogs.fr.resources" >  
            <Culture>fr</Culture>  
        </Res>  
  
        <CodeFiles Include="**\*.cs" Exclude="**\generated\*.cs" />  
        <CodeFiles Include="..\..\Resources\Constants.cs" />  
    </ItemGroup>  
...  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Öğeleri](../msbuild/msbuild-items.md)   
 [Yaygın MSBuild Proje Öğeleri](../msbuild/common-msbuild-project-items.md)



