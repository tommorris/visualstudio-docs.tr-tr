---
title: ProjectExtensions öğesi (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ProjectExtensions
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <ProjectExtensions> element [MSBuild]
- ProjectExtensions element [MSBuild]
ms.assetid: f95f312f-ff92-41eb-9469-ad99e236a307
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bfa7d566291cfd544845f4fb688ef335a470440d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="projectextensions-element-msbuild"></a>ProjectExtensions Öğesi (MSBuild)
Verir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyalarını içeren olmayan[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] bilgi. Herhangi bir şey içinde bir `ProjectExtensions` öğesi tarafından yoksayılacak [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)].  

 \<Proje >  
 \<ProjectExtensions >  

## <a name="syntax"></a>Sözdizimi  

```  
<ProjectExtensions>  
    Non-MSBuild information to include in file.  
</ProjectExtensions>  
```  

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  

### <a name="attributes"></a>Öznitelikler  
 Yok.  

### <a name="child-elements"></a>Alt Öğeler  
 Yok.  

### <a name="parent-elements"></a>Üst Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Project](../msbuild/project-element-msbuild.md)|Gerekli kök öğesinin bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyası.|  

## <a name="remarks"></a>Açıklamalar  
 Yalnızca bir `ProjectExtensions` öğesi olarak kullanılabilir bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projesi.  

## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde depolanıyor tümleşik geliştirme ortamını bilgilerinden gösterir bir `ProjectExtensions` öğesi.  

```xml  
<ProjectExtensions>  
    <VSIDE>  
        <External>  
            <!--  
            Raw XML passed to the IDE by an external source  
            -->  
        </External>  
    </VSIDE>  
</ProjectExtensions>  
```  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)  
 [MSBuild](../msbuild/msbuild.md)
