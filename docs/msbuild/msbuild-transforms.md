---
title: MSBuild dönüşümleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, transforms
- transforms [MSBuild]
ms.assetid: d0bcfc3c-14fa-455e-805c-63ccffa4a3bf
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: eb1a7ba3bff8265e6e707605f02e0bbaba85aff5
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31571626"
---
# <a name="msbuild-transforms"></a>MSBuild Dönüşümleri
Bir dönüştürme başka bir bire bir dönüştürme bir öğe listesi değildir. Bir proje öğesi listeleri dönüştürmek etkinleştirmeye ek olarak, bir dönüşüm kendi giriş ve çıkış arasında doğrudan bir eşleme tanımlamak bir hedef sağlar. Bu konu dönüşümler açıklar ve nasıl [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projeleri daha verimli bir şekilde oluşturmak için bunları kullanır.  
  
## <a name="transform-modifiers"></a>Değiştiriciler dönüştürme  
Dönüşümler rasgele değildir, ancak özel sözdizimi, tüm dönüştürme değiştiricileri biçiminde olmalıdır %(tarafından sınırlı*ItemMetaDataName*). Herhangi bir öğe meta veri dönüştürme değiştiricisi olarak kullanılabilir. Bu, oluşturulduğunda, her öğeye atanan tanınmış öğe meta verileri içerir. İyi bilinen öğe meta verileri bir listesi için bkz: [tanınmış öğe meta verisi](../msbuild/msbuild-well-known-item-metadata.md).  
  
Aşağıdaki örnekte, bir listesini *.resx* dosyaları bir listeye dönüştürülen *.resources* dosyaları. %(Filename) dönüştürme değiştiricisi, her belirtir *.resources* dosya ilgili olarak aynı dosya adına sahip *.resx* dosya.  
  
```  
@(RESXFile->'%(filename).resources')  
```

Örneğin, @(RESXFile) öğesi listedeki öğeler varsa *Form1.resx*, *Form2.resx*, ve *Form3.resx*, dönüştürülmüş listesinde çıkışları olacaktır  *Form1.Resources*, *Form2.resources*, ve *Form3.resources*.  

> [!NOTE]
>  Standart Madde listesini ayırıcısı belirttiğiniz aynı şekilde dönüştürülmüş öğe listesi için özel bir ayırıcı belirtebilirsiniz. Örneğin, varsayılan noktalı virgül (;) yerine bir virgülle (,) kullanarak dönüştürülmüş öğesi listesini ayırmak için aşağıdaki XML kullanın:  
> `@(RESXFile->'Toolset\%(filename)%(extension)', ',')`
  
## <a name="using-multiple-modifiers"></a>Birden çok değiştiricileri kullanma  
 Bir dönüştürme ifadesi herhangi bir sırada birleştirilebilir ve tekrarlanabilir birden çok değiştiricileri içerebilir. Aşağıdaki örnekte, dosyaları içeren dizinin adını değiştirilir, ancak özgün adı ve dosya adı uzantısı dosyaları korur.  
  
```  
@(RESXFile->'Toolset\%(filename)%(extension)')  
```  
  
 Örneğin olan öğeler, içinde yer alan `RESXFile` öğe listesi *Project1\Form1.resx*, *Project1\Form2.resx*, ve *Project1\Form3.text*, Dönüştürülen listeyi çıktılarında olacaktır *Toolset\Form1.resx*, *Toolset\Form2.resx*, ve *Toolset\Form3.text*.  
  
## <a name="dependency-analysis"></a>Bağımlılık çözümleme  
 Dönüşümler dönüştürülmüş öğe listesi ve özgün öğe listesi arasında bire bir eşleme garanti. Bu nedenle, bir hedef dönüşümler girdi olan çıktıları oluşturursa [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] girişleri ve çıkışları damgalarının çözümleyebilir ve Atla, yapı veya kısmen hedef yeniden gerekmediğine karar verin.  
  
 İçinde [kopyalama görevi](../msbuild/copy-task.md) aşağıdaki örnekte, her dosyasında `BuiltAssemblies` öğe listesi eşleyen bir dönüştürme kullanılarak belirtilen görev, hedef klasörde bir dosyaya `Outputs` özniteliği. Bir dosya `BuiltAssemblies` öğe listesi değişiklikleri `Copy` görev, yalnızca değiştirilen dosya için çalışır ve diğer tüm dosyalar atlandı. Bağımlılık çözümleme ve dönüşümler kullanma hakkında daha fazla bilgi için bkz: [nasıl yapılır: artımlı olarak derleme](../msbuild/how-to-build-incrementally.md).  
  
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
 Bu örnek şu çıkışı üretir:  
  
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