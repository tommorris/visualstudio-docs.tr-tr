---
title: ProjectExtensions öğesi (MSBuild) | Microsoft Docs
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
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 156a35a953169c5b1ed8208c8d4f044f7b9fa36f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688158"
---
# <a name="projectextensions-element-msbuild"></a>ProjectExtensions Öğesi (MSBuild)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ProjectExtensions öğesi (MSBuild)](https://docs.microsoft.com/visualstudio/msbuild/projectextensions-element-msbuild).  
  
  
Sağlar [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] proje dosyalarını içerecek olmayan[!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] bilgileri. Herhangi bir şey içinde bir `ProjectExtensions` öğesi tarafından yoksayılacak [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)].  
  
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
|[Project](../msbuild/project-element-msbuild.md)|Gerekli kök öğesi bir [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] proje dosyası.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yalnızca bir `ProjectExtensions` öğesi olarak kullanılabilir bir [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] proje.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği bilgileri depolanıyor tümleşik geliştirme ortamından gösterir bir `ProjectExtensions` öğesi.  
  
```  
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
 [MSBuild](msbuild.md)


