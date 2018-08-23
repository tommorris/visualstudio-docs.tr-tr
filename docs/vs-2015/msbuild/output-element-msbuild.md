---
title: Çıktı öğesi (MSBuild) | Microsoft Docs
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
- http://schemas.microsoft.com/developer/msbuild/2003#Output
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <Output> Element [MSBuild]
- Output Element [MSBuild]
ms.assetid: 34bc7cd1-efd3-4b57-b691-4584eeb6a0e9
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 26535408374f2617ff9eda3a36b803116d848ecc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42697409"
---
# <a name="output-element-msbuild"></a>Çıktı Öğesi (MSBuild)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [çıktı öğesi (MSBuild)](https://docs.microsoft.com/visualstudio/msbuild/output-element-msbuild).  
  
  
Öğeleri ve özellikleri depoları Görev çıkış değerleri.  
  
 \<Proje >  
 \<Hedef >  
 \<Görev >  
 \<Çıkış >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<Output TaskParameter="Parameter"  
    PropertyName="PropertyName"   
    Condition = "'String A' == 'String B'" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`TaskParameter`|Gerekli öznitelik.<br /><br /> Görev adı çıkış parametresi.|  
|`PropertyName`|Ya da `PropertyName` veya `ItemName` özniteliği gereklidir.<br /><br /> Parametre değeri çıkış görev alan özelliği. Projenizi sonra özelliğiyle başvuruda `$(` *PropertyName* `)` söz dizimi. Bu özellik adı ya da yeni bir özellik adı veya projede zaten tanımlı bir ad olabilir.<br /><br /> Bu öznitelik, kullanılamaz `ItemName` da kullanılıyor.|  
|`ItemName`|Ya da `PropertyName` veya `ItemName` özniteliği gereklidir.<br /><br /> Parametre değeri çıkış görev alan öğesi. Projenizi ardından öğeyle başvurabilirsiniz `@(` *ItemName* `)` söz dizimi. Öğe adı ya da yeni bir öğe adı veya projede zaten tanımlı bir ad olabilir.<br /><br /> Bu öznitelik, kullanılamaz `PropertyName` da kullanılıyor.|  
|`Condition`|İsteğe bağlı öznitelik.<br /><br /> Değerlendirilecek koşul. Daha fazla bilgi için [koşullar](../msbuild/msbuild-conditions.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Görev](../msbuild/task-element-msbuild.md)|Oluşturur ve yürütür örneği bir [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] görev.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği kod `Csc` görev içinde yürütülen bir `Target` öğesi. Bu örnekte kapsamı dışında öğeleri ve görev parametrelerine geçirilen özellikleri bildirilir. Çıkış parametresi değerinden `OutputAssembly` depolanan `FinalAssemblyName` öğesi ve çıkış parametresi değerinden `BuildSucceeded` depolanan `BuildWorked` özelliği. Daha fazla bilgi için [görevleri](../msbuild/msbuild-tasks.md).  
  
```  
<Target Name="Compile" DependsOnTargets="Resources">  
    <Csc  Sources="@(CSFile)"  
            TargetType="library"  
            Resources="@(CompiledResources)"  
            EmitDebugInformation="$(includeDebugInformation)"  
            References="@(Reference)"  
            DebugType="$(debuggingType)"  
            OutputAssembly="$(builtdir)\$(MSBuildProjectName).dll" >  
        <Output TaskParameter="OutputAssembly"  
                  ItemName="FinalAssemblyName" />  
        <Output TaskParameter="BuildSucceeded"  
                  PropertyName="BuildWorked" />  
    </Csc>  
</Target>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Görevleri](../msbuild/msbuild-tasks.md)



