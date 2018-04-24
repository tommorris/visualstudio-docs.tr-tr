---
title: MSBuild toplu işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- batching [MSBuild]
- MSBuild, batching
ms.assetid: d35c085b-27b8-49d7-b6f8-8f2f3a0eec38
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e7b769cc89095aca5b22aed46375f56c2ab4c987
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="msbuild-batching"></a>MSBuild Toplu İşleme
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] öğe listelerini farklı kategorileri veya toplu işlemi bölme yeteneği, öğe meta verileri temel alarak ve bir hedef ya da görev her batch ile bir kez çalıştırın.  
  
## <a name="task-batching"></a>Toplu görev işleme  
 Toplu Görev işlemede öğe listelerini farklı yığınlara ayırmak ve her biri bu toplu göreve dönüştürme ayrı olarak geçirmek için bir yol sağlayarak proje dosyalarınıza basitleştirmenize olanak sağlar. Bu proje dosyası yalnızca birkaç kez çalıştırılabilir olsa bile görev ve bir kez bildirilen özniteliklerini sahip olması gerektiğini anlamına gelir.  
  
 İstediğinizi belirtin [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] kullanarak bir görev ile toplu işleme gerçekleştirmek için %(*ItemMetaDataName*) görev öznitelikleri birinde gösterimi. Aşağıdaki örnek böler `Example` toplu öğeyi listeye temel alarak `Color` öğe meta veri değeri ve geçişleri her toplu `MyTask` ayrı olarak görev.  
  
> [!NOTE]
>  Öğe listesinde başka bir yerde görev öznitelikleri başvurmadığından veya meta veri adı belirsiz olabilir, kullanabileceğiniz %(*ItemCollection.ItemMetaDataName*) toplu işleme için kullanılacak öğe meta veri değeri tam olarak nitelemek için gösterimi.  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <Example Include="Item1">  
            <Color>Blue</Color>  
        </Example>  
        <Example Include="Item2">  
            <Color>Red</Color>  
        </Example>  
    </ItemGroup>  
  
    <Target Name="RunMyTask">  
        <MyTask  
            Sources = "@(Example)"  
            Output = "%(Color)\MyFile.txt"/>  
    </Target>  
  
</Project>  
```  
  
 Toplu daha ayrıntılı örnekler için bkz: [toplu görev işlemede öğe meta verisi](../msbuild/item-metadata-in-task-batching.md).  
  
## <a name="target-batching"></a>Toplu hedef işlemede  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Hedef çalıştırılmadan önce girişleri ve çıkışları hedefinin güncel olup olmadığını denetler. Girişleri ve çıkışları güncel varsa, hedef atlanır. Toplu işleme, bir hedef içinde bir görevi kullanıyorsa, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] girişleri ve çıkışları öğelerinin her bir toplu iş için güncel olup olmadığını gerekiyor. Aksi takdirde, isabet edildiğinde hedef yürütülür.  
  
 Aşağıdaki örnekte gösterildiği bir `Target` içeren öğe bir `Outputs` ile öznitelik %(*ItemMetaDataName*) gösterimi. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] bölecek `Example` toplu öğeyi listeye temel alarak `Color` öğe meta verileri ve çıkış dosyalarının her toplu işlemi için zaman damgaları çözümleyin. Bir toplu çıkışlarından güncel değilse, hedef çalıştırılır. Aksi takdirde, hedef atlanır.  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <Example Include="Item1">  
            <Color>Blue</Color>  
        </Example>  
        <Example Include="Item2">  
            <Color>Red</Color>  
        </Example>  
    </ItemGroup>  
  
    <Target Name="RunMyTask"  
        Inputs="@(Example)"  
        Outputs="%(Color)\MyFile.txt">  
        <MyTask  
            Sources = "@(Example)"  
            Output = "%(Color)\MyFile.txt"/>  
    </Target>  
  
</Project>  
```  
  
 Toplu hedef işlemede başka bir örnek için bkz: [toplu hedef işlemede öğe meta verisi](../msbuild/item-metadata-in-target-batching.md).  
  
## <a name="property-functions-using-metadata"></a>Meta verileri kullanarak özellik işlevleri  
 Toplu işleme meta verileri içeren özellik işlevler tarafından denetlenebilir. Örneğin,  
  
 `$([System.IO.Path]::Combine($(RootPath),%(Compile.Identity)))`  
  
 kullanan <xref:System.IO.Path.Combine%2A> kök klasör yolu bir derleme yolu ile birleştirmek için.  
  
 Özellik işlevleri içindeki meta veri değerleri görünmeyebilir.  Örneğin,  
  
 `%(Compile.FullPath.Substring(0,3))`  
  
 izin verilmiyor.  
  
 Özellik işlevleri hakkında daha fazla bilgi için bkz: [özellik işlevleri](../msbuild/property-functions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Itemmetadata öğesi (MSBuild)](../msbuild/itemmetadata-element-msbuild.md)   
 [MSBuild kavramları](../msbuild/msbuild-concepts.md)   
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Gelişmiş kavramlar](../msbuild/msbuild-advanced-concepts.md)