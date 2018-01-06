---
title: MSBuild hedefleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: MSBuild, targets
ms.assetid: 8060b4d2-e4a9-48cf-a437-852649ceb417
caps.latest.revision: "26"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 1055a11a428d477ef44645fbc85d3f281b523357
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="msbuild-targets"></a>MSBuild Hedefleri
Hedefler, belirli bir sırada görevleri gruplamak ve daha küçük birimlere oluşturmak amacıyla yapı işlemine izin. Örneğin, bir hedef başka bir proje için girişleri derler ve boş dizinde yerleştirir derleme için hazırlamak için çıktı dizindeki tüm dosyaları silebilirsiniz. Görevler hakkında daha fazla bilgi için bkz: [görevleri](../msbuild/msbuild-tasks.md).  
  
## <a name="declaring-targets-in-the-project-file"></a>Proje dosyasında hedefleri bildirme  
 Proje dosyası ile içinde bildirilen hedefleri [hedef](../msbuild/target-element-msbuild.md) öğesi. Örneğin, aşağıdaki XML derleme öğe türüne sahip Csc görevi çağırır yapı adlı bir hedef oluşturur.  
  
```xml  
<Target Name="Construct">  
    <Csc Sources="@(Compile)" />  
</Target>  
```  
  
 MSBuild özellikleri gibi hedefleri tanımlanabilir. Örneğin,  
  
```xml  
<Target Name="AfterBuild" >  
    <Message Text="First occurrence" />  
</Target>  
<Target Name="AfterBuild" >  
    <Message Text="Second occurrence" />  
</Target>  
```  
  
 AfterBuild yürütülürse, yalnızca "ikinci oluşum" görüntüler.  
  
## <a name="target-build-order"></a>Hedef Derleme Sırası  
 Bir hedef girdisi başka bir hedef Çıkışta bağımlıysa hedefleri sıralanmalıdır. Çalıştırma hangi hedeflerin sırayı belirtmek için çeşitli yolları vardır.  
  
-   İlk hedefleri  
  
-   Varsayılan hedefler  
  
-   İlk hedef  
  
-   Hedef bağımlılıklar  
  
-   `BeforeTargets`ve `AfterTargets` (MSBuild 4.0)  
  
 Bir sonraki hedef derlemede bağımlı olsa bile bir hedef iki kez tek derleme sırasında hiçbir zaman çalışır. Çalıştıran bir hedef sonra yapı kendi katkısı tamamlanır.  
  
 Derleme sırası ayrıntılarını ve hedef hakkında daha fazla bilgi için bkz: [hedef derleme sırası](../msbuild/target-build-order.md).  
  
## <a name="target-batching"></a>Toplu hedef işlemede  
 Hedef öğe olabilir bir `Outputs` form % (meta verileri) meta veri belirten özniteliği. Bu durumda, MSBuild gruplandırma veya "Bu meta verileri değere sahip öğeleri toplu işleme" hedef her benzersiz meta veri değeri için bir kez çalışır. Örneğin,  
  
```xml  
<ItemGroup>  
    <Reference Include="System.Core">  
      <RequiredTargetFramework>3.5</RequiredTargetFramework>  
    </Reference>  
    <Reference Include="System.Xml.Linq">  
      <RequiredTargetFramework>3.5</RequiredTargetFramework>  
    </Reference>  
    <Reference Include="Microsoft.CSharp">  
      <RequiredTargetFramework>4.0</RequiredTargetFramework>  
    </Reference>  
</ItemGroup>  
<Target Name="AfterBuild"  
    Outputs="%(Reference.RequiredTargetFramework)">  
    <Message Text="Reference:  
      @(Reference->'%(RequiredTargetFramework)')" />  
</Target>  
```  
  
 Başvuru öğeleri kendi RequiredTargetFramework meta verileri toplu işler. Hedef çıktısı şu şekildedir:  
  
```  
Reference: 3.5;3.5  
Reference: 4.0  
```  
  
 Toplu hedef işlemede gerçek derlemelerde nadiren kullanılır. Toplu görev işleme daha yaygın bir durumdur. Daha fazla bilgi için bkz: [Batching](../msbuild/msbuild-batching.md).  
  
## <a name="incremental-builds"></a>Artımlı Derlemeler  
 Artımlı derlemeler en iyi duruma getirilir ve böylece hedefleri ile ilgili giriş dosyalarına göre güncel çıktı dosyaları yürütülmez derlemeleri ' dir. Hedef öğe hem de sağlayabilirsiniz `Inputs` ve `Outputs` öznitelikler, hangi hedef öğeler belirten giriş olarak bekler ve hangi üretir çıkış olarak öğeler.  
  
 Tüm çıktı öğeleri güncel olup olmadığını MSBuild yapı hızı önemli ölçüde iyileştirir hedef atlar. Bu artımlı bir yapı hedef çağrılır. Yalnızca bazı dosyaları güncel MSBuild hedef güncel öğeleri olmadan yürütür. Bu, kısmi bir artımlı derleme hedef adı verilir. Daha fazla bilgi için bkz: [artımlı derlemeler](../msbuild/incremental-builds.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild kavramları](../msbuild/msbuild-concepts.md)   
 [Nasıl Yapılır: Birden Çok Proje Dosyasında Aynı Hedefi Kullanma](../msbuild/how-to-use-the-same-target-in-multiple-project-files.md)