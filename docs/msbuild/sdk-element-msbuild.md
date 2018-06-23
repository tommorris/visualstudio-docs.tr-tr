---
title: SDK öğesi (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 01/25/2018
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Project
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Sdk element [MSBuild]
- <Sdk> element [MSBuild]
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3d674e7613898816f905e0d0a11bdc2484cf4f25
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36325329"
---
# <a name="sdk-element-msbuild"></a>Sdk Öğesi (MSBuild)
Başvurular bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] SDK projesi.  

 \<Proje >  
 \<Sdk>  


## <a name="syntax"></a>Sözdizimi  

```xml  
<Sdk Name="My.Custom.Sdk"
     Version="1.0.0" />  
```  

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  

### <a name="attributes"></a>Öznitelikler  

|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Name`|Gerekli öznitelik.<br /><br /> SDK proje adı.|  
|`Version`|İsteğe bağlı öznitelik.<br /><br /> Proje SDK sürümü|  

### <a name="child-elements"></a>Alt Öğeler  
 Yok.

### <a name="parent-elements"></a>Üst Öğeler  
 |Öğe|Açıklama|  
|-------------|-----------------|  
|[Project](../msbuild/project-element-msbuild.md)|Gerekli kök öğesinin bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyası.|  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: MSBuild proje SDK başvurusu](../msbuild/how-to-use-project-sdk.md)   
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)   
 [MSBuild](../msbuild/msbuild.md)
