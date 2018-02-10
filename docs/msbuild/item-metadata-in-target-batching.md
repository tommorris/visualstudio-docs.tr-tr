---
title: "Toplu hedef işlemede meta veri öğesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching [MSBuild]
- MSBuild, target batching
- target batching [MSBuild]
ms.assetid: f3cc4186-6a4c-4161-bbe5-1ec638b4925b
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c15870bb47d1f53f1943882ed0685c222e82b326
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="item-metadata-in-target-batching"></a>Toplu Hedef İşlemede Öğe Meta Verileri
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] girişleri ve çıkışları derleme hedefi üzerinde bağımlılık çözümlemesi özelliğine sahiptir. Giriş veya çıkış hedef güncel belirlenir, hedef atlanacak ve yapı procede olur. `Target`öğeleri kullanmak `Inputs` ve `Outputs` bağımlılık Çözümleme sırasında incelemek için öğelerini belirtmek için öznitelikler.  
  
 Bir hedef toplu öğeleri girişleri veya çıkışları, kullanan bir görevi içeriyorsa `Target` hedef öğe içinde toplu işleme kullanması gereken kendi `Inputs` veya `Outputs` etkinleştirmek için öznitelikler [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] zaten güncel olan öğelerin toplu atlamak için.  
  
## <a name="batching-targets"></a>Hedefleri toplu işleme  
 Aşağıdaki örnek, adlı bir öğe listesi içerir `Res` göre iki toplu içine bölünmüş `Culture` öğe meta verileri. Bu toplu her içine geçirilir `AL` bir çıkış derlemesi için her bir toplu iş oluşturur görev. Üzerinde toplu işleme kullanarak `Outputs` özniteliği `Target` öğesi, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] her biri ayrı toplu hedef çalıştırmadan önce güncel olup olmadığını belirleyebilirsiniz. Toplu hedef işlemede kullanmadan hedef yürütüldü her zaman iki toplu öğelerinin görev tarafından çalıştırılmaz.  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <Res Include="Strings.fr.resources">  
            <Culture>fr</Culture>  
        </Res>  
        <Res Include="Strings.jp.resources">  
            <Culture>jp</Culture>  
        </Res>  
        <Res Include="Menus.fr.resources">  
            <Culture>fr</Culture>  
        </Res>  
        <Res Include="Dialogs.fr.resources">  
            <Culture>fr</Culture>  
        </Res>  
        <Res Include="Dialogs.jp.resources">  
            <Culture>jp</Culture>  
        </Res>  
        <Res Include="Menus.jp.resources">  
            <Culture>jp</Culture>  
        </Res>  
    </ItemGroup>  
  
    <Target Name="Build"  
        Inputs="@(Res)"  
        Outputs="%(Culture)\MyApp.resources.dll">  
  
        <AL Resources="@(Res)"  
            TargetType="library"  
            OutputAssembly="%(Culture)\MyApp.resources.dll"  
  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: artımlı olarak derleme](../msbuild/how-to-build-incrementally.md)   
 [Toplu işleme](../msbuild/msbuild-batching.md)   
 [Hedef öğe (MSBuild)](../msbuild/target-element-msbuild.md)   
 [Toplu Görev İşlemede Öğe Meta Verileri](../msbuild/item-metadata-in-task-batching.md)