---
title: "OnError öğesi (MSBuild) | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#OnError
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- OnError Element [MSBuild]
- <OnError Element [MSBuild]
ms.assetid: 765767d3-ecb7-4cd9-ba1e-d9468964dddc
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ed8d48fe390f5a5990506a6b7eeab3d1efe8b5ed
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="onerror-element-msbuild"></a>OnError Öğesi (MSBuild)
Yürütmek bir veya daha fazla hedefleri neden `ContinueOnError` özniteliği `false` başarısız bir görev için.  

 \<Project>  
 \<Hedef >  
 \<OnError>  

## <a name="syntax"></a>Sözdizimi  

```  
<OnError ExecuteTargets="TargetName"  
    Condition="'String A'=='String B'" />  
```  

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  

### <a name="attributes"></a>Öznitelikler  

|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Condition`|İsteğe bağlı öznitelik.<br /><br /> Değerlendirilecek koşulu. Daha fazla bilgi için bkz: [koşullar](../msbuild/msbuild-conditions.md).|  
|`ExecuteTargets`|Gerekli öznitelik.<br /><br /> Bir görev başarısız olursa yürütmek için hedefler. Birden çok hedef noktalı virgülle ayırın. Birden çok hedef belirtilen sırada yürütülür.|  

### <a name="child-elements"></a>Alt Öğeler  
 Yok.  

### <a name="parent-elements"></a>Üst Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Hedef](../msbuild/target-element-msbuild.md)|İçin kapsayıcı öğe [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] görevler.|  

## <a name="remarks"></a>Açıklamalar  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] yürütür `OnError` öğe varsa, `Target` öğenin görevler başarısız oluyor `ContinueOnError` özniteliğini `ErrorAndStop` (veya `false`). Görev başarısız olduğunda, belirtilen hedefleri `ExecuteTargets` özniteliği gerçekleştirilir. Varsa birden fazla `OnError` hedef öğesinde `OnError` öğeleri görevi başarısız olduğunda sırayla yürütülen.  

 Hakkında bilgi için `ContinueOnError` özniteliği için bkz: [görev öğesi (MSBuild)](../msbuild/task-element-msbuild.md). Hedefleri hakkında daha fazla bilgi için bkz: [hedefleri](../msbuild/msbuild-targets.md).  

## <a name="example"></a>Örnek  
 Aşağıdaki kodu yürütür `TaskOne` ve `TaskTwo` görevler. Varsa `TaskOne` başarısız olursa [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] değerlendirir `OnError` öğesi ve yürütür `OtherTarget` hedef.  

```xml  
<Target Name="ThisTarget">  
    <TaskOne ContinueOnError="ErrorAndStop">  
    </TaskOne>  
    <TaskTwo>  
    </TaskTwo>  
    <OnError ExecuteTargets="OtherTarget" />  
</Target>  
```  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Hedefler](../msbuild/msbuild-targets.md)
