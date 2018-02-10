---
title: "Nasıl yapılır: derleme dosyalarına seçin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, wildcards
- MSBuild, including files
- Include attribute [MSBuild]
ms.assetid: f5ff182f-7b3a-46fb-9335-37df54cfb8eb
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: cccc76ed4adcd8339bc3f125bce759400ac4643d
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="how-to-select-the-files-to-build"></a>Nasıl Yapılır: Derlenecek Dosyaları Seçme
Bir projeyi derlerken birkaç dosyaları içeren, proje dosyası içinde ayrı ayrı her dosya listesi veya bir dizin veya dizinleri iç içe geçmiş bir dizi tüm dosyaları eklemek için joker karakterleri kullanabilirsiniz.  
  
## <a name="specifying-inputs"></a>Girişleri belirtme  
 Öğeleri bir yapı için girişleri temsil eder. Öğeleri hakkında daha fazla bilgi için bkz: [öğeleri](../msbuild/msbuild-items.md).  
  
 Derleme dosyalarını eklemek için bunlar bir öğe listesinde eklenmelidir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyası. Birden çok dosya, tek tek dosyalar dahil olmak üzere veya aynı anda çok sayıda dosya eklemek için joker karakter kullanılması öğesi listelerine eklenebilir.  
  
#### <a name="to-declare-items-individually"></a>Öğeleri tek tek bildirmek için  
  
-   Kullanım `Include` öznitelikleri benzer aşağıdaki:  
  
     `<CSFile Include="form1.cs"/>`  
  
     - veya -  
  
     `<VBFile Include="form1.vb"/>`  
  
    > [!NOTE]
    >  Proje dosyası ile aynı dizinde bir öğe koleksiyonu öğelerinin emin değilseniz, öğeyi tam veya göreli yolunu belirtmeniz gerekir. Örneğin: `Include="..\..\form2.cs"`.  
  
#### <a name="to-declare-multiple-items"></a>Birden çok öğe bildirmek için  
  
-   Kullanım `Include` öznitelikleri benzer aşağıdaki:  
  
     `<CSFile Include="form1.cs;form2.cs"/>`  
  
     - veya -  
  
     `<VBFile Include="form1.vb;form2.vb"/>`  
  
## <a name="specifying-inputs-with-wildcards"></a>Joker karakter olarak girişleri belirtme  
 Aynı zamanda bir yapı için girdi olarak yinelemeli olarak joker karakterler tüm dosyaları ya da yalnızca belirli dosyaları alt dizinleri. Joker karakterler hakkında daha fazla bilgi için bkz: [öğeleri](../msbuild/msbuild-items.md)  
  
 Aşağıdaki örnekler proje dizininde bulunan proje dosyası ile aşağıdaki dizinlerinde ve alt dizinlerinde, grafik dosyaları içeren bir proje dayanır:  
  
 Project\Images\BestJpgs  
  
 Project\Images\ImgJpgs  
  
 Project\Images\ImgJpgs\Img1  
  
#### <a name="to-include-all-jpg-files-in-the-images-directory-and-subdirectories"></a>Görüntü dizini ve alt dizinleri tüm .jpg dosyaları eklemek için  
  
-   Aşağıdaki `Include` özniteliği:  
  
     `Include="Images\**\*.jpg"`  
  
#### <a name="to-include-all-jpg-files-starting-with-img"></a>"İmg" ile başlayan tüm .jpg dosyaları eklemek için  
  
-   Aşağıdaki `Include` özniteliği:  
  
     `Include="Images\**\img*.jpg"`  
  
#### <a name="to-include-all-files-in-directories-with-names-ending-in-jpgs"></a>"Jpg"formatından içinde bitiş adlarıyla dizinlerde tüm dosyaları eklemek için  
  
-   Aşağıdakilerden birini kullanmak `Include` öznitelikleri:  
  
     `Include="Images\**\*jpgs\*.*"`  
  
     - veya -  
  
     `Include="Images\**\*jpgs\*"`  
  
## <a name="passing-items-to-a-task"></a>Bir görev öğelerine geçirme  
 Proje dosyasında kullandığınız @ tüm öğe listesinden bir yapı için giriş olarak belirtmek için görevler () gösterimi. Ayrı olarak tüm dosyaları listelemek veya joker karakterleri kullanırsanız, bu gösterim kullanabilirsiniz.  
  
#### <a name="to-use-all-visual-c-or-visual-basic-files-as-inputs"></a>Tüm Visual C# veya Visual Basic dosyaları girdi olarak kullanmak için  
  
-   Kullanım `Include` öznitelikleri aşağıdakine benzer:  
  
     `<CSC Sources="@(CSFile)">...</CSC>`  
  
     - veya -  
  
     `<VBC Sources="@(VBFile)">...</VBC>`  
  
> [!NOTE]
>  Joker karakter kısa öğelerine ile girişleri bir derleme için kullanmanız gerekir; kullanarak girişleri belirtemezsiniz `Sources` özniteliğini [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] gibi görevleri [Csc](../msbuild/csc-task.md) veya [Vbc](../msbuild/vbc-task.md). Aşağıdaki örnek bir proje dosyası geçerli değil:  
>   
>  `<CSC Sources="*.cs">...</CSC>`  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, tüm giriş dosyalarını ayrı olarak içeren bir proje gösterir.  
  
```xml  
<Project DefaultTargets="Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
    <PropertyGroup>  
        <Builtdir>built</Builtdir>  
    </PropertyGroup>  
  
    <ItemGroup>  
        <CSFile Include="Form1.cs"/>  
        <CSFile Include="AssemblyInfo.cs"/>  
  
        <Reference Include="System.dll"/>  
        <Reference Include="System.Data.dll"/>  
        <Reference Include="System.Drawing.dll"/>  
        <Reference Include="System.Windows.Forms.dll"/>  
        <Reference Include="System.XML.dll"/>  
    </ItemGroup>  
  
    <Target Name="PreBuild">  
        <Exec Command="if not exist $(builtdir) md $(builtdir)"/>  
    </Target>  
  
    <Target Name="Compile" DependsOnTargets="PreBuild">  
        <Csc Sources="@(CSFile)"  
            References="@(Reference)"  
            OutputAssembly="$(builtdir)\$(MSBuildProjectName).exe"  
            TargetType="exe" />  
    </Target>  
</Project>  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde bir joker karakter tüm .cs dosyaları eklemek için kullanır.  
  
```xml  
<Project DefaultTargets="Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <PropertyGroup>  
        <builtdir>built</builtdir>  
    </PropertyGroup>  
  
    <ItemGroup>  
        <CSFile Include="*.cs"/>  
  
        <Reference Include="System.dll"/>  
        <Reference Include="System.Data.dll"/>  
        <Reference Include="System.Drawing.dll"/>  
        <Reference Include="System.Windows.Forms.dll"/>  
        <Reference Include="System.XML.dll"/>  
    </ItemGroup>  
  
    <Target Name="PreBuild">  
        <Exec Command="if not exist $(builtdir) md $(builtdir)"/>  
    </Target>  
  
    <Target Name="Compile" DependsOnTargets="PreBuild">  
        <Csc Sources="@(CSFile)"  
            References="@(Reference)"  
            OutputAssembly="$(builtdir)\$(MSBuildProjectName).exe"  
            TargetType="exe" />  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: dosyaları derlemeden dışlama](../msbuild/how-to-exclude-files-from-the-build.md)   
 [Öğeleri](../msbuild/msbuild-items.md)