---
title: "Toplu hedef işlemede meta veri öğesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching [MSBuild]
- MSBuild, target batching
- target batching [MSBuild]
ms.assetid: f3cc4186-6a4c-4161-bbe5-1ec638b4925b
caps.latest.revision: "6"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 84be1157000e44b40f93ef51ca173247b3851d5f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="item-metadata-in-target-batching"></a>Toplu Hedef İşlemede Öğe Meta Verileri
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]girişleri ve çıkışları derleme hedefi üzerinde bağımlılık çözümlemesi özelliğine sahiptir. Giriş veya çıkış hedef güncel belirlenir, hedef atlanacak ve yapı procede olur. `Target`öğeleri kullanmak `Inputs` ve `Outputs` bağımlılık Çözümleme sırasında incelemek için öğelerini belirtmek için öznitelikler.  
  
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