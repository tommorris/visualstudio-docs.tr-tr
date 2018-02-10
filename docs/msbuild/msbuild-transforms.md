---
title: "MSBuild dönüşümleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, transforms
- transforms [MSBuild]
ms.assetid: d0bcfc3c-14fa-455e-805c-63ccffa4a3bf
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 670465059f86e7dd5ccbe725bc0d86aed2fc97b1
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="msbuild-transforms"></a>MSBuild Dönüşümleri
Bir dönüştürme başka bir bire bir dönüştürme bir öğe listesi değildir. Bir proje öğesi listeleri dönüştürmek etkinleştirmeye ek olarak, bir dönüşüm kendi giriş ve çıkış arasında doğrudan bir eşleme tanımlamak bir hedef sağlar. Bu konu dönüşümler açıklar ve nasıl [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projeleri daha verimli bir şekilde oluşturmak için bunları kullanır.  
  
## <a name="transform-modifiers"></a>Transform Modifiers  
 Dönüşümler rasgele değildir, ancak özel sözdizimi, tüm dönüştürme değiştiricileri biçiminde olmalıdır %(tarafından sınırlı*ItemMetaDataName*). Herhangi bir öğe meta veri dönüştürme değiştiricisi olarak kullanılabilir. Bu, oluşturulduğunda, her öğeye atanan tanınmış öğe meta verileri içerir. İyi bilinen öğe meta verileri bir listesi için bkz: [tanınmış öğe meta verisi](../msbuild/msbuild-well-known-item-metadata.md).  
  
 Aşağıdaki örnekte, .resx dosyaları listesini .resources dosyaları listesine dönüştürüldüğünde. %(Filename) dönüştürme değiştiricisi her .resources dosyası karşılık gelen .resx dosyası olarak aynı dosya adına sahip olduğunu belirtir.  
  
```  
@(RESXFile->'%(filename).resources')  
```  
  
> [!NOTE]
>  Standart Madde listesini ayırıcısı belirttiğiniz aynı şekilde dönüştürülmüş öğe listesi için özel bir ayırıcı belirtebilirsiniz. Örneğin, varsayılan noktalı virgül (;) yerine bir virgülle (,) kullanarak dönüştürülmüş öğesi listesini ayırmak için aşağıdaki XML kullanın.  
  
```  
@(RESXFile->'Toolset\%(filename)%(extension)', ',')  
```  
  
 Örneğin, @(RESXFile) öğesi listedeki öğeler varsa `Form1.resx`, `Form2.resx`, ve `Form3.resx`, dönüştürülmüş listesinde çıkışları olacaktır `Form1.resources`, `Form2.resources`, ve `Form3.resources`.  
  
## <a name="using-multiple-modifiers"></a>Birden çok değiştiricileri kullanma  
 Bir dönüştürme ifadesi herhangi bir sırada birleştirilebilir ve tekrarlanabilir birden çok değiştiricileri içerebilir. Aşağıdaki örnekte, dosyaları içeren dizinin adını değiştirilir, ancak özgün adı ve dosya adı uzantısı dosyaları korur.  
  
```  
@(RESXFile->'Toolset\%(filename)%(extension)')  
```  
  
 Örneğin olan öğeler, içinde yer alan `RESXFile` öğe listesi `Project1\Form1.resx`, `Project1\Form2.resx`, ve `Project1\Form3.text`, dönüştürülmüş listesinde çıkışları olacaktır `Toolset\Form1.resx`, `Toolset\Form2.resx`, ve `Toolset\Form3.text`.  
  
## <a name="dependency-analysis"></a>Bağımlılık çözümleme  
 Dönüşümler dönüştürülmüş öğe listesi ve özgün öğe listesi arasında bire bir eşleme garanti. Bu nedenle, bir hedef dönüşümler girdi olan çıktıları oluşturursa [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] girişleri ve çıkışları damgalarının çözümleyebilir ve Atla, yapı veya kısmen hedef yeniden gerekmediğine karar verin.  
  
 İçinde [kopyalama görevi](../msbuild/copy-task.md) aşağıdaki örnekte, her dosyasında `BuiltAssemblies` öğe listesi eşleyen bir dönüştürme kullanılarak belirtilen görev, hedef klasörde bir dosyaya `Outputs` özniteliği. Bir dosya `BuiltAssemblies` öğe listesi değişiklikleri `Copy` görev için yalnızca değiştirilen dosya çalıştırılır ve diğer tüm dosyalar atlanacak. Bağımlılık çözümleme ve dönüşümler kullanma hakkında daha fazla bilgi için bkz: [nasıl yapılır: artımlı olarak derleme](../msbuild/how-to-build-incrementally.md).  
  
```xml  
<Target Name="CopyOutputs"  
    Inputs="@(BuiltAssemblies)"  
    Outputs="@(BuiltAssemblies -> '$(OutputPath)%(Filename)%(Extension)')">  
  
    <Copy  
        SourceFiles="@(BuiltAssemblies)"  
        DestinationFolder="$(OutputPath)"/>  
  
</Target>  
```  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnekte gösterildiği bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] dönüşümler kullanan proje dosyası. Bu örnek c:\sub0\sub1\sub2\sub3 dizinde yalnızca bir .xsd dosyası olduğunu ve çalışma dizinini c:\sub0 olduğunu varsayar.  
  
### <a name="code"></a>Kod  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Schema Include="sub1\**\*.xsd"/>  
    </ItemGroup>  
  
    <Target Name="Messages">  
        <Message Text="rootdir: @(Schema->'%(rootdir)')"/>  
        <Message Text="fullpath: @(Schema->'%(fullpath)')"/>  
        <Message Text="rootdir + directory + filename + extension: @(Schema->'%(rootdir)%(directory)%(filename)%(extension)')"/>  
        <Message Text="identity: @(Schema->'%(identity)')"/>  
        <Message Text="filename: @(Schema->'%(filename)')"/>  
        <Message Text="directory: @(Schema->'%(directory)')"/>  
        <Message Text="relativedir: @(Schema->'%(relativedir)')"/>  
        <Message Text="extension: @(Schema->'%(extension)')"/>  
    </Target>  
</Project>  
```  
  
### <a name="comments"></a>Açıklamalar  
 Bu örnek şu çıkışı üretir.  
  
```  
rootdir: C:\  
fullpath: C:\xmake\sub1\sub2\sub3\myfile.xsd  
rootdir + directory + filename + extension: C:\xmake\sub1\sub2\sub3\myfile.xsd  
identity: sub1\sub2\sub3\myfile.xsd  
filename: myfile  
directory: xmake\sub1\sub2\sub3\  
relativedir: sub1\sub2\sub3\  
extension: .xsd  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild kavramları](../msbuild/msbuild-concepts.md)   
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Nasıl Yapılır: Artımlı Olarak Derleme](../msbuild/how-to-build-incrementally.md)