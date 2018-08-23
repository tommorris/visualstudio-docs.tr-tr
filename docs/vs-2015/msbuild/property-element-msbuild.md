---
title: Özellik öğesi (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
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
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e9f3494cb46aa18d9b79d29aa2936d31ae55997b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689559"
---
# <a name="property-element-msbuild"></a>Özellik Öğesi (MSBuild)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [özellik öğesi (MSBuild)](https://docs.microsoft.com/visualstudio/msbuild/property-element-msbuild).  
  
  
Bir kullanıcı tanımlı özellik adını ve değerini içerir. Kullanılan her bir özellik bir [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] alt öğesi olarak proje belirtilen bir `PropertyGroup` öğesi.  
  
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
|`Condition`|İsteğe bağlı öznitelik.<br /><br /> Değerlendirilecek koşul. Daha fazla bilgi için [koşullar](../msbuild/msbuild-conditions.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[PropertyGroup](../msbuild/propertygroup-element-msbuild.md)|Özellikler için gruplandırma öğesi.|  
  
## <a name="text-value"></a>Metin Değeri  
 Metin değeri isteğe bağlıdır.  
  
 Bu metin değerini belirtir ve XML içeriyor olabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 Özellik adları yalnızca ASCII karakterleri sınırlıdır. Özellik değerlerini başvurulan projede arasında özellik adı girerek "`$(`"ve"`)`". Örneğin, `$(builddir)\classes` "build\classes", çözümlemek `builddir` özellik değeri olan `build`. Özellikler hakkında daha fazla bilgi için bkz. [MSBuild özellikleri](msbuild-properties1.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod kümeleri `Optimization` özelliğini `false` ve `DefaultVersion` özelliğini `1.0` varsa `Version` özelliği boşsa.  
  
```  
<PropertyGroup>  
    <Optimization>false</Optimization>  
    <DefaultVersion Condition="'$(Version)' == ''" >1.0</DefaultVersion>  
</PropertyGroup>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.
[MSBuild Özellikleri](msbuild-properties1.md)  
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)



