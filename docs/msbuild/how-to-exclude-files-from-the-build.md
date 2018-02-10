---
title: "Nasıl yapılır: dosyaları derlemeden dışlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, wildcards
- MSBuild, excluding files
- wildcards, MSBuild
ms.assetid: 1be36e45-01da-451c-972d-f9fc0e7d663c
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b11f292e27c192efcbd81376a79bcd67b0d08393
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="how-to-exclude-files-from-the-build"></a>Nasıl Yapılır: Dosyaları Derlemeden Dışlama
Proje dosyasında tüm dosyaları bir yapı için girdi olarak bir dizin veya dizinleri iç içe geçmiş bir dizi eklemek için joker karakterleri kullanabilirsiniz. Ancak, dizin veya iç içe geçmiş bir derleme için giriş olarak eklemek istiyor musunuz dizinleri birtakım bir dizinde bir dosyanız olabilir. Bu dosya veya dizin girişleri listeden açıkça dışlayabilirsiniz. Ayrıca olabilir. bir dosya yalnızca belirli koşullar altında dahil etmek istediğiniz bir proje. Bir derleme dosya dahil koşullar açıkça bildirebilir.  
  
## <a name="excluding-a-file-or-directory-from-the-inputs-for-a-build"></a>Bir dosya veya dizin girişlerinde bir derleme için dışlama  
 Öğe bir yapı için girdi dosyaları listeleridir. Dahil etmek istediğiniz öğeleri ayrı ayrı veya kullanarak bir grup olarak bildirilen `Include` özniteliği. Örneğin:  
  
```xml  
<CSFile Include="Form1.cs"/>  
<CSFile Include ="File1.cs;File2.cs"/>  
<CSFile Include="*.cs"/>  
<JPGFile Include="Images\**\*.jpg"/>  
```  
  
 Tüm dosyaları bir yapı için girdi olarak bir dizin veya dizinleri iç içe geçmiş bir dizi eklemek için joker karakter kullandıysanız, dizin veya bir dizinde bir veya daha fazla olabilir eklemek istiyor musunuz dizinleri iç içe geçmiş bir dizi. Öğe listesinden bir öğe çıkarmak için kullan `Exclude` özniteliği.  
  
#### <a name="to-include-all-cs-or-vb-files-except-form2"></a>Form2 dışındaki tüm .cs veya .vb dosyaları eklemek için  
  
-   Aşağıdakilerden birini kullanmak `Include` ve `Exclude` öznitelikleri:  
  
    ```xml  
    <CSFile Include="*.cs" Exclude="Form2.cs"/>  
    ```  
  
     - veya -  
  
    ```xml  
    <VBFile Include="*.vb" Exclude="Form2.vb"/>  
    ```  
  
#### <a name="to-include-all-cs-or-vb-files-except-form2-and-form3"></a>Form2 ve Form3 dışındaki tüm .cs veya .vb dosyaları eklemek için  
  
-   Aşağıdakilerden birini kullanmak `Include` ve `Exclude` öznitelikleri:  
  
    ```xml  
    <CSFile Include="*.cs" Exclude="Form2.cs;Form3.cs"/>  
    ```  
  
     - veya -  
  
    ```xml  
    <VBFile Include="*.vb" Exclude="Form2.vb;Form3.vb"/>  
    ```  
  
#### <a name="to-include-all-jpg-files-in-subdirectories-of-the-images-directory-except-those-in-the-version2-directory"></a>Version2 dizin hariç görüntüleri dizininin dizinlerdeki tüm .jpg dosyaları eklemek için  
  
-   Aşağıdaki `Include` ve `Exclude` öznitelikleri:  
  
    ```xml  
    <JPGFile  
        Include="Images\**\*.jpg"  
        Exclude = "Images\**\Version2\*.jpg"/>  
    ```  
  
    > [!NOTE]
    >  Her iki öznitelik yolunu belirtmeniz gerekir. Dosya konumları belirtmek için mutlak bir yol kullanıyorsanız `Include` özniteliği, mutlak bir yol da kullanmalıdır `Exclude` göreli bir yol kullanırsanız; özniteliği `Include` özniteliği, göreli bir yol kullanmalısınız`Exclude`özniteliği.  
  
## <a name="using-conditions-to-exclude-a-file-or-directory-from-the-inputs-for-a-build"></a>Bir dosya veya dizin girişlerinde bir yapı dışlamak için koşul kullanma  
 Dahil etmek istediğiniz öğeler varsa, örneğin, bir hata ayıklama derlemesi ancak bir yayın derlemesi kullanabileceğiniz `Condition` özniteliği hangi koşullar altında öğesi eklemek belirtin.  
  
#### <a name="to-include-the-file-formulavb-only-in-release-builds"></a>Yalnızca yayın derlemelerde Formula.vb dosya eklemek için  
  
-   Kullanım bir `Condition` özniteliği aşağıdakine benzer:  
  
    ```xml  
    <Compile  
        Include="Formula.vb"  
        Condition=" '$(Configuration)' == 'Release' " />  
    ```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, tüm Form2.cs dışında dizinindeki .cs dosyalarının bir proje oluşturur.  
  
```xml  
<Project DefaultTargets="Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <PropertyGroup>  
        <builtdir>built</builtdir>  
    </PropertyGroup>  
  
    <ItemGroup>  
        <CSFile Include="*.cs Exclude="Form2.cs"/>  
  
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
 [Öğeleri](../msbuild/msbuild-items.md)   
 [MSBuild](../msbuild/msbuild.md) [nasıl yapılır: derleme dosyalarını seçin](../msbuild/how-to-select-the-files-to-build.md)