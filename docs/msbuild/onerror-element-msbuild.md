---
title: OnError öğesi (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: conceptual
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
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f70588c512716cac854bab446c7a7d695e392a28
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="onerror-element-msbuild"></a>OnError Öğesi (MSBuild)
Yürütmek bir veya daha fazla hedefleri neden `ContinueOnError` özniteliği `false` başarısız bir görev için.  

 \<Proje >  
 \<Hedef >  
 \<OnError >  

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
