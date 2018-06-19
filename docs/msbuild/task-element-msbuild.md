---
title: Görev öğesi (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Task element [MSBuild]
- <Task> element [MSBuild]
ms.assetid: d82e2485-e5f0-4936-a357-745bacccc299
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bc67d881f48c99cd8e53de086f0c8b08c96d7844
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31577990"
---
# <a name="task-element-msbuild"></a>Görev Öğesi (MSBuild)
Oluşturur ve bir örneğini yürüten bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] görev. Öğe adı, oluşturulan görev adı tarafından belirlenir.  

 \<Proje >  
 \<Hedef >  

## <a name="syntax"></a>Sözdizimi  

```  
<Task Parameter1="Value1"... ParameterN="ValueN"  
    ContinueOnError="WarnAndContinue/true/ErrorAndContinue/ErrorAndStop/false"  
    Condition="'String A' == 'String B'" >  
    <Output... />  
</Task>  
```  

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  

### <a name="attributes"></a>Öznitelikler  

|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Condition`|İsteğe bağlı öznitelik. Değerlendirilecek koşulu. Daha fazla bilgi için bkz: [koşullar](../msbuild/msbuild-conditions.md).|  
|`ContinueOnError`|İsteğe bağlı öznitelik. Aşağıdaki değerlerden birini içerebilir:<br /><br /> -   **WarnAndContinue** veya **doğru**. Bir görev başarısız olduğunda, sonraki görevlerinde [hedef](../msbuild/target-element-msbuild.md) öğesi ve yapı devam yürütmek ve görevin tüm hataları, uyarıları olarak kabul edilir.<br />-   **ErrorAndContinue**. Bir görev başarısız olduğunda, sonraki görevlerinde `Target` öğesi ve yapı devam yürütmek ve görevin tüm hataları hata olarak kabul edilir.<br />-   **ErrorAndStop** veya **false** (varsayılan). Bir görev başarısız olursa, kalan görevlere `Target` öğesi ve yapı olmayan yürütülen ve tüm `Target` öğesi ve yapı olarak kabul başarısız oldu.<br /><br /> Yalnızca desteklenen 4.5 önce .NET Framework sürümleri `true` ve `false` değerleri.<br /><br /> Daha fazla bilgi için bkz: [nasıl yapılır: görevlerdeki hataları Yoksay](../msbuild/how-to-ignore-errors-in-tasks.md).|  
|`Parameter`|Gerekli görev sınıfı içeriyor veya daha fazla özellik birlikte etiketli `[Required]` özniteliği.<br /><br /> Parametre değeri olarak değerini içeren bir kullanıcı tanımlı görev parametresi. Herhangi bir sayıda parametrelerinde olabilir `Task` her özniteliği eşlemesi görev sınıfında .NET özelliğine sahip bir öğe.|  

### <a name="child-elements"></a>Alt Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Output](../msbuild/output-element-msbuild.md)|Proje dosyasında görevden depoları çıkarır. Sıfır veya daha fazla olabilir `Output` görevdeki öğeleri.|  

### <a name="parent-elements"></a>Üst Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Hedef](../msbuild/target-element-msbuild.md)|İçin kapsayıcı öğe [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] görevler.|  

## <a name="remarks"></a>Açıklamalar  
 A `Task` öğesinde bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyası bir görev örneği oluşturur, özellikleri ayarlayan ve yürütür. `Output` Öğesi özellikler veya başka bir yerde proje dosyasında kullanılacak öğeleri çıkış parametreleri depolar.  

 Varsa [OnError](../msbuild/onerror-element-msbuild.md) üst öğeler `Target` öğesi görev başarısız olursa görev, bunlar yine değerlendirilir ve `ContinueOnError` değerine sahip `false`. Görevler hakkında daha fazla bilgi için bkz: [görevleri](../msbuild/msbuild-tasks.md).  

## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde bir örneğini oluşturur [Csc görevi](../msbuild/csc-task.md) sınıfı, altı özelliklerini ayarlar ve görev yürütür. Yürütme, değerini sonra `OutputAssembly` nesnesinin özelliği adlı bir öğe listesi yerleştirilen `FinalAssemblyName`.  

```xml  
<Target Name="Compile" DependsOnTarget="Resources" >  
    <Csc Sources="@(CSFile)"  
          TargetType="library"  
          Resources="@(CompiledResources)"  
          EmitDebugInformation="$(includeDebugInformation)"  
          References="@(Reference)"  
          DebugType="$(debuggingType)" >  
        <Output TaskParameter="OutputAssembly"  
                  ItemName="FinalAssemblyName" />  
    </Csc>  
</Target>  
```  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)
