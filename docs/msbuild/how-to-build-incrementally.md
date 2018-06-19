---
title: 'Nasıl yapılır: artımlı olarak derleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, incremental builds
- incremental builds
- MSBuild, building incrementally
ms.assetid: 8d82d7d8-a2f1-4df6-9d2f-80b9e0cb3ac3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3fac1ce26c95d0a0c51c77e6ca1525d034a4e01f
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31578269"
---
# <a name="how-to-build-incrementally"></a>Nasıl Yapılır: Artımlı Olarak Derleme
Büyük bir proje oluşturduğunuzda, daha önce hala güncel bileşenleri yerleşik değil yeniden önemlidir. Her zaman tüm hedefleri oluşturulduysa, her yapı tamamlanması uzun zaman sürer. Artımlı derlemeler etkinleştirmek için (hangi derlemelerde önce oluşturulmuş değil veya hedefleyen hedeflerin güncel değil, yalnızca yeniden), [!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] ([!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]) girdi dosyaları zaman damgaları ve çıkış dosyalarının zaman damgalı karşılaştırabilirsiniz ve Atla, yapı veya kısmen hedef yeniden belirleyin. Ancak, bire bir eşleme girişleri ve çıkışları arasında olmalıdır. Bu doğrudan eşleme tanımlamak hedefleri etkinleştirmek için dönüşümler kullanabilirsiniz. Dönüşümler hakkında daha fazla bilgi için bkz: [dönüştüren](../msbuild/msbuild-transforms.md).  
  
## <a name="specifying-inputs-and-outputs"></a>Girişleri ve çıkışları belirtme  
 Proje dosyasında girişleri ve çıkışları belirtilmezse, bir hedef artımlı olarak oluşturulabilir.  
  
#### <a name="to-specify-inputs-and-outputs-for-a-target"></a>Giriş ve çıkış için bir hedef belirtmek için  
  
-   Kullanım `Inputs` ve `Outputs` özniteliklerini `Target` öğesi. Örneğin:  
  
    ```xml  
    <Target Name="Build"  
        Inputs="@(CSFile)"  
        Outputs="hello.exe">  
    ```  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Giriş dosyaları zaman damgaları ve çıkış dosyalarının zaman damgalı karşılaştırın ve Atla, yapı veya kısmen hedef yeniden belirleme kullanabilirsiniz. Aşağıdaki örnekte, herhangi bir dosya varsa `@(CSFile)` öğe listesi hello.exe dosyadan daha yeni [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] hedef çalışır; aksi atlanır:  
  
```xml  
<Target Name="Build"   
    Inputs="@(CSFile)"   
    Outputs="hello.exe">  
  
    <Csc  
        Sources="@(CSFile)"   
        OutputAssembly="hello.exe"/>  
</Target>  
```  
  
 Girişleri ve çıkışları bir hedef olarak belirtildiğinde, her çıktı için yalnızca bir giriş eşleyebilirsiniz veya girişleri ve çıkışları arasında doğrudan eşleme olabilir. Önceki [Csc görevi](../msbuild/csc-task.md), örneğin, çıktı hello.exe, herhangi bir tek giriş eşlenemeyen - hepsinde bağlıdır.  
  
> [!NOTE]
>  Girişleri ve çıkışları arasında doğrudan eşleme olduğu bir hedef her zaman içinde her çıktı eşlenebilir için yalnızca bir giriş için bir hedef daha sık oluşturacaksınız [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] hangi çıkışları bazı girdi değiştirdiyseniz yeniden gerek belirleyemiyor .  
  
 İçinde belirleyebilir giriş ve çıkış arasında doğrudan bir eşleme gibi görevleri [LC görevi](../msbuild/lc-task.md), gibi görevleri aksine artımlı derlemeler için en uygun olan `Csc` ve [Vbc](../msbuild/vbc-task.md), hangi ürettiği bir derleme numarasından girdi çıkış.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir kuramsal Yardım sistemi için Yardım dosyalarını derlemeler bir proje kullanır. Proje sonra Yardım sistemi tarafından kullanılan son .help dosya oluşturmak için XML meta veri dosyaları ile birleştirilmiş Ara .content dosyalarını kaynağı .txt dosyaları dönüştürerek çalışır. Proje aşağıdaki kuramsal görevleri kullanır:  
  
-   `GenerateContentFiles`: .txt dosyaları .content dosyalarına dönüştürür.  
  
-   `BuildHelp`: .content ve son .help dosyasını oluşturmak için XML meta veri dosyaları birleştirir.  
  
 Proje dönüşümler girdi arasında bire bir eşleme oluşturmak için kullanır ve içinde çıkarır `GenerateContentFiles` görev. Daha fazla bilgi için bkz: [dönüştüren](../msbuild/msbuild-transforms.md). Ayrıca, `Output` öğesi çıkışlarından otomatik olarak kullanmak üzere ayarlanmış `GenerateContentFiles` görev için girdi olarak `BuildHelp` görev.  
  
 Bu proje dosyası içeren `Convert` ve `Build` hedefler. `GenerateContentFiles` Ve `BuildHelp` görevleri yerleştirilir `Convert` ve `Build` böylece her hedef artımlı olarak oluşturulabilir sırasıyla hedefler. Kullanarak `Output` öğesi, çıkışları `GenerateContentFiles` görev yerleştirilir `ContentFile` öğe listesinden, burada bunlar olarak kullanılabilir girdileri `BuildHelp` görev. Kullanarak `Output` öğesi bu şekilde otomatik olarak sağlar bir görevin çıkış girdi olarak başka bir görev için böylece veya her görev listelerinde el ile madde bireysel öğeleri listeler gerekmez.  
  
> [!NOTE]
>  Ancak `GenerateContentFiles` hedef artımlı olarak oluşturabilir, bu hedefin tüm çıktıları için girdi olarak her zaman gereklidir `BuildHelp` hedef. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] kullanırken bir hedeften tüm çıkışları başka bir hedef için girdi olarak otomatik olarak sağlar `Output` öğesi.  
  
```xml  
<Project DefaultTargets="Build"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <ItemGroup>  
        <TXTFile Include="*.txt"/>  
        <XMLFiles Include="\metadata\*.xml"/>  
    </ItemGroup>  
  
    <Target Name = "Convert"  
        Inputs="@(TXTFile)"  
        Outputs="@(TXTFile->'%(Filename).content')">  
  
        <GenerateContentFiles  
            Sources = "@(TXTFile)">  
            <Output TaskParameter = "OutputContentFiles"  
                ItemName = "ContentFiles"/>  
        </GenerateContentFiles>  
    </Target>  
  
    <Target Name = "Build" DependsOnTargets = "Convert"  
        Inputs="@(ContentFiles);@(XMLFiles)"  
        Outputs="$(MSBuildProjectName).help">  
  
        <BuildHelp  
            ContentFiles = "@(ContentFiles)"  
            MetadataFiles = "@(XMLFiles)"  
            OutputFileName = "$(MSBuildProjectName).help"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hedefleri](../msbuild/msbuild-targets.md)   
 [Hedef öğe (MSBuild)](../msbuild/target-element-msbuild.md)   
 [Dönüşümler](../msbuild/msbuild-transforms.md)   
 [CSC görevi](../msbuild/csc-task.md)   
 [Vbc Görevi](../msbuild/vbc-task.md)
