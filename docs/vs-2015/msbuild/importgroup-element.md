---
title: Importgroup öğesi | Microsoft Docs
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
- <ImportGroup> element [MSBuild]
- ImportGroup element [MSBuild]
ms.assetid: dac3fa2d-6678-4017-af35-93686f53f302
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b579b75970539c6639f98e321bb6e0a03341aa59
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629601"
---
# <a name="importgroup-element"></a>ImportGroup Öğesi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Importgroup öğesi](https://docs.microsoft.com/visualstudio/msbuild/importgroup-element).  
  
  
Bir koleksiyonunu içeren `Import` isteğe bağlı bir koşul altında gruplandırılmış öğeler. Daha fazla bilgi için [içeri aktarma öğesi (MSBuild)](../msbuild/import-element-msbuild.md).  
  
 \<Proje >  
 \<Importgroup >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<ImportGroup Condition="'String A' == 'String B'">  
    <Import ... />  
    <Import ... />  
</ImportGroup>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Condition`|İsteğe bağlı öznitelik.<br /><br /> Değerlendirilecek koşul. Daha fazla bilgi için [koşullar](../msbuild/msbuild-conditions.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[içeri aktarma](../msbuild/import-element-msbuild.md)|Bir proje dosyasının içeriğini başka bir proje dosyasına aktarır.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Project](../msbuild/project-element-msbuild.md)|Gerekli kök öğesi bir [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] proje dosyası.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği kod `ImportGroup` öğesi.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ImportGroup>  
        <Import Project="$(Targets1.targets) />  
        <Import Project="$(Targets2.targets) />  
    </ImportGroup>  
...  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Öğeleri](../msbuild/msbuild-items.md)



