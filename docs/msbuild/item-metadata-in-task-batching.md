---
title: "Toplu görev işleme meta veri öğesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching [MSBuild]
- MSBuild, batching
- task batching [MSBuild]
- MSBuild, task batching
ms.assetid: 31e480f8-fe4d-4633-8c54-8ec498e2306d
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ee203056edb24bd2338caf1ad1b5608e4c5d3ca9
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="item-metadata-in-task-batching"></a>Toplu Görev İşlemede Öğe Meta Verileri
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] öğe listelerini farklı kategorileri veya toplu işlemi bölme yeteneği, öğe meta verileri temel alarak ve bir görev her batch ile bir kez çalıştırın. Hangi öğeleri hangi batch ile tam olarak geçirilen anlamak kafa karıştırıcı olabilir. Bu konuda toplu işleme ile ilgili aşağıdaki ortak senaryolar için geçerlidir.  
  
-   Bir öğe listesi yığınlara bölme  
  
-   Yığınlara birkaç öğe listesi bölme  
  
-   Bir öğe aynı anda toplu işleme  
  
-   Filtreleme öğesi listeleri  
  
 Toplu işleme ile ilgili daha fazla bilgi için [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], bkz: [Batching](../msbuild/msbuild-batching.md).  
  
## <a name="dividing-an-item-list-into-batches"></a>Bir öğe listesi yığınlara bölme  
 Toplu işleme, öğe meta verileri temel alarak farklı toplu bir öğe listesi böler ve her toplu göreve dönüştürme ayrı olarak geçirin olanak sağlar. Uydu derlemeleri oluşturma için kullanışlıdır.  
  
 Aşağıdaki örnek, öğe meta verileri temel alarak toplu bir öğe listesi bölmek gösterilmiştir. `ExampColl` Öğe listesi göre üç toplu bölündüğü `Number` öğe meta verileri. Varlığını `%(ExampColl.Number)`içinde `Text` özniteliği bildirir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] toplu işleme gerçekleştirilmesi. `ExampColl` Öğe listesi göre üç toplu bölündüğü `Number` meta verileri ve her bir toplu iş geçirilir ayrı olarak göreve dönüştürebilir.  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <ExampColl Include="Item1">  
            <Number>1</Number>  
        </ExampColl>  
        <ExampColl Include="Item2">  
            <Number>2</Number>  
        </ExampColl>  
        <ExampColl Include="Item3">  
            <Number>3</Number>  
        </ExampColl>  
        <ExampColl Include="Item4">  
            <Number>1</Number>  
        </ExampColl>  
        <ExampColl Include="Item5">  
            <Number>2</Number>  
        </ExampColl>  
        <ExampColl Include="Item6">  
            <Number>3</Number>  
        </ExampColl>  
    </ItemGroup>  
  
    <Target Name="ShowMessage">  
        <Message  
            Text = "Number: %(ExampColl.Number) -- Items in ExampColl: @(ExampColl)"/>  
    </Target>  
  
</Project>  
```  
  
 [İleti görevi](../msbuild/message-task.md) görev aşağıdaki bilgileri görüntüler:  
  
 `Number: 1 -- Items in ExampColl: Item1;Item4`  
  
 `Number: 2 -- Items in ExampColl: Item2;Item5`  
  
 `Number: 3 -- Items in ExampColl: Item3;Item6`  
  
## <a name="dividing-several-item-lists-into-batches"></a>Birden fazla öğe bölerek yığınlara listeler  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] birden çok öğe listesi, aynı meta verileri temel alarak toplu bölebilirsiniz. Bu, farklı öğe listelerini birden çok derleme yapı yığınlara ayırmak kolaylaştırır. Örneğin, bir uygulama toplu ve bir derleme toplu ve kaynak dosyalarının bir uygulama toplu ve bir derleme toplu olarak ayrılmış bir öğe listesi bölünmüş .cs dosyaların bir öğe listesi olabilir. Bu öğe listelerini tek bir görev geçip uygulama ve derleme yapı toplu işleme sonra kullanabilirsiniz.  
  
> [!NOTE]
>  Bir görev geçirilen bir öğe listesi başvurulan meta verilerle hiç öğe içeriyorsa, bu öğesi listesindeki her öğenin her toplu geçirilir.  
  
 Aşağıdaki örnek, öğe meta verileri temel alarak toplu birden çok öğe listesi bölmek gösterilmiştir. `ExampColl` Ve `ExampColl2` öğesi listeleri her bölünen göre üç toplu içine `Number` öğe meta verileri. Varlığını `%(Number)`içinde `Text` özniteliği bildirir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] toplu işleme gerçekleştirilmesi. `ExampColl` Ve `ExampColl2` öğesi listeleri göre üç toplu içine bölünen `Number` meta verileri ve her bir toplu iş geçirilir ayrı olarak göreve dönüştürebilir.  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
  
        <ExampColl Include="Item1">  
            <Number>1</Number>  
        </ExampColl>  
        <ExampColl Include="Item2">  
            <Number>2</Number>  
        </ExampColl>  
        <ExampColl Include="Item3">  
            <Number>3</Number>  
        </ExampColl>  
  
        <ExampColl2 Include="Item4">  
            <Number>1</Number>  
        </ExampColl2>  
        <ExampColl2 Include="Item5">  
            <Number>2</Number>  
        </ExampColl2>  
        <ExampColl2 Include="Item6">  
            <Number>3</Number>  
        </ExampColl2>  
  
    </ItemGroup>  
  
    <Target Name="ShowMessage">  
        <Message  
            Text = "Number: %(Number) -- Items in ExampColl: @(ExampColl) ExampColl2: @(ExampColl2)"/>  
    </Target>  
  
</Project>  
```  
  
 [İleti görevi](../msbuild/message-task.md) görev aşağıdaki bilgileri görüntüler:  
  
 `Number: 1 -- Items in ExampColl: Item1 ExampColl2: Item4`  
  
 `Number: 2 -- Items in ExampColl: Item2 ExampColl2: Item5`  
  
 `Number: 3 -- Items in ExampColl: Item3 ExampColl2: Item6`  
  
## <a name="batching-one-item-at-a-time"></a>Bir öğe aynı anda toplu işleme  
 Toplu işleme de oluşturulduktan sonra her öğeye atanan tanınmış öğe meta verileri üzerinde gerçekleştirilebilir. Bu toplu işlem için kullanılacak bir koleksiyondaki her öğe bazı meta verileri gerekir güvence altına alır. `Identity` Meta veri değeri her öğe için benzersizdir ve her bir öğe listesi öğesinde ayrı bir toplu iş bölmek için yararlıdır. İyi bilinen öğe meta verisi tam bir listesi için bkz: [tanınmış öğe meta verisi](../msbuild/msbuild-well-known-item-metadata.md).  
  
 Aşağıdaki örnekte, her bir öğe listesinden bir öğe aynı anda toplu olarak gösterilmiştir. Çünkü `Identity` meta verileri her öğenin değeri benzersiz `ExampColl` öğe listesinden bir öğe öğe listesinin içeren her bir toplu iş altı yığınlara bölünür. Varlığını `%(Identity)`içinde `Text` özniteliği bildirir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] toplu işleme gerçekleştirilmesi.  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
  
        <ExampColl Include="Item1"/>  
        <ExampColl Include="Item2"/>  
        <ExampColl Include="Item3"/>  
        <ExampColl Include="Item4"/>  
        <ExampColl Include="Item5"/>  
        <ExampColl Include="Item6"/>  
  
    </ItemGroup>  
  
    <Target Name="ShowMessage">  
        <Message  
            Text = "Identity: "%(Identity)" -- Items in ExampColl: @(ExampColl)"/>  
    </Target>  
  
</Project>  
```  
  
 [İleti görevi](../msbuild/message-task.md) görev aşağıdaki bilgileri görüntüler:  
  
```  
Identity: "Item1" -- Items in ExampColl: Item1  
Identity: "Item2" -- Items in ExampColl: Item2  
Identity: "Item3" -- Items in ExampColl: Item3  
Identity: "Item4" -- Items in ExampColl: Item4  
Identity: "Item5" -- Items in ExampColl: Item5  
Identity: "Item6" -- Items in ExampColl: Item6  
```  
  
## <a name="filtering-item-lists"></a>Filtreleme öğesi listeler  
 Toplu işleme göreve geçirmeden önce bir öğe listesi belirli öğeleri filtrelemek için kullanılabilir. Örneğin, filtre `Extension` iyi bilinen öğe meta veri değeri, yalnızca belirli bir uzantıya sahip dosyaların bir görevi çalıştırmayı sağlar.  
  
 Aşağıdaki örnek, öğe meta verileri temel alarak toplu bir öğe listesi böler ve bir görev geçirildiğinde bu toplu filtre gösterilmektedir. `ExampColl` Öğe listesi göre üç toplu bölündüğü `Number` öğe meta verileri. `Condition` Görevinin özniteliği belirtir, yalnızca toplu işlemleri ile bir `Number` öğe meta veri değeri `2` göreve geçirilen  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
  
        <ExampColl Include="Item1">  
            <Number>1</Number>  
        </ExampColl>  
        <ExampColl Include="Item2">  
            <Number>2</Number>  
        </ExampColl>  
        <ExampColl Include="Item3">  
            <Number>3</Number>  
        </ExampColl>  
        <ExampColl Include="Item4">  
            <Number>1</Number>  
        </ExampColl>  
        <ExampColl Include="Item5">  
            <Number>2</Number>  
        </ExampColl>  
        <ExampColl Include="Item6">  
            <Number>3</Number>  
        </ExampColl>  
  
    </ItemGroup>  
  
    <Target Name="Exec">  
        <Message  
            Text = "Items in ExampColl: @(ExampColl)"  
            Condition="'%(Number)'=='2'"/>  
    </Target>  
  
</Project>  
```  
  
 [İleti görevi](../msbuild/message-task.md) görev aşağıdaki bilgileri görüntüler:  
  
```  
Items in ExampColl: Item2;Item5  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tanınmış öğe meta verisi](../msbuild/msbuild-well-known-item-metadata.md)   
 [Öğe unsuru (MSBuild)](../msbuild/item-element-msbuild.md)   
 [Itemmetadata öğesi (MSBuild)](../msbuild/itemmetadata-element-msbuild.md)   
 [Toplu işleme](../msbuild/msbuild-batching.md)   
 [MSBuild kavramları](../msbuild/msbuild-concepts.md)   
 [MSBuild Başvurusu](../msbuild/msbuild-reference.md)