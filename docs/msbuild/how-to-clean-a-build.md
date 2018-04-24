---
title: 'Nasıl yapılır: derlemeyi temizleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- Exec task [MSBuild]
- MSBuild, cleaning a build
- directories [.NET Framework], for output items
- output, removing items
ms.assetid: 999ba473-b0c4-45c7-930a-63ea7a510509
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 36e9af303b91cc0cdabc184f7ced329289eb7bd8
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-clean-a-build"></a>Nasıl Yapılır: Derlemeyi Temizleme
Derlemeyi temizleme, yalnızca proje ve bileşen dosyalarını bırakarak tüm ara ve çıktı dosyalarını silinir. Proje ve bileşen dosyalarından Ara yeni örneklerini ve çıktı dosyalarını sonra oluşturulabilir. Kitaplığı ile sağlanan ortak görevler [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] içeren bir [Exec](../msbuild/exec-task.md) sistem komutlarını çalıştırmak için kullanabileceğiniz bir görev. Görevler Kitaplığı hakkında daha fazla bilgi için bkz: [görev başvurusu](../msbuild/msbuild-task-reference.md).  
  
## <a name="creating-a-directory-for-output-items"></a>Çıktı öğeleri için bir dizin oluşturma  
 Varsayılan olarak, bir projeyi derlerken oluşturulan .exe dosyası proje ve kaynak dosyalarıyla aynı dizine yerleştirilir. Genellikle, ancak çıktı öğeleri ayrı bir dizin oluşturulur.  
  
#### <a name="to-create-a-directory-for-output-items"></a>Çıktı öğeleri için bir dizin oluşturmak için  
  
1.  Kullanım `Property` dizinin adını ve konumunu tanımlamak için öğesi. Örneğin, adlı bir dizin oluşturun `BuiltApp` proje ve kaynak dosyaları bulunduran dizini içinde:  
  
     `<builtdir>BuiltApp</builtdir>`  
  
2.  Kullanım [MakeDir](../msbuild/makedir-task.md) dizin yoksa, dizin oluşturmak için görev. Örneğin:  
  
     `<MakeDir Directories = "$(builtdir)"`  
  
     `Condition = "!Exists('$(builtdir)')" />`  
  
## <a name="removing-the-output-items"></a>Çıktı öğeleri kaldırma  
 Ara ve çıkış dosyalarının yeni kopyalarını oluşturmadan önce ara ve çıkış dosyalarının önceki tüm örneklerini temizleyin isteyebilirsiniz. Kullanım [RemoveDir](../msbuild/removedir-task.md) görev bir dizini ve tüm dosyaları ve içerdiği dizinleri bir diskten silin.  
  
#### <a name="to-remove-a-directory-and-all-files-contained-in-the-directory"></a>Bir dizin ve dizindeki tüm dosyaları kaldırmak için  
  
-   Kullanım `RemoveDir` görev dizini kaldırın. Örneğin:  
  
     `<RemoveDir Directories="$(builtdir)" />`  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örnek projesini içeren yeni bir hedef `Clean`, kullanan `RemoveDir` görev bir dizini ve tüm dosyaları ve içerdiği dizinleri silin. Ayrıca bu örnekte, `Compile` hedef yapı temizlendiğinde silinir çıktı öğeleri için ayrı bir dizin oluşturur.  
  
 `Compile` Varsayılan hedefi olarak tanımlanır ve farklı bir hedef veya hedeflerinin belirtmediğiniz sürece bu nedenle otomatik olarak kullanılır. Komut satırı anahtarını kullanmanız **/target** farklı bir hedef belirtmek için. Örneğin:  
  
 `msbuild <file name>.proj /target:Clean`  
  
 **/Target** anahtar kısaltılmış için **/t** ve birden fazla hedef belirtebilirsiniz. Örneğin, hedef kullanmak için `Clean` sonra hedef `Compile`, türü:  
  
 `msbuild <file name>.proj /t:Clean;Compile`  
  
```xml  
<Project DefaultTargets = "Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <PropertyGroup>  
        <!-- Set the application name as a property -->  
        <name>HelloWorldCS</name>  
  
        <!-- Set the output folder as a property -->  
        <builtdir>BuiltApp</builtdir>  
    </PropertyGroup>  
  
    <ItemGroup>  
        <!-- Specify the inputs by type and file name -->  
        <CSFile Include = "consolehwcs1.cs"/>  
    </ItemGroup>  
  
    <Target Name = "Compile">  
        <!-- Check whether an output folder exists and create  
        one if necessary -->  
        <MakeDir Directories = "$(builtdir)"   
            Condition = "!Exists('$(builtdir)')" />  
  
        <!-- Run the Visual C# compiler -->  
        <CSC Sources = "@(CSFile)"   
            OutputAssembly = "$(BuiltDir)\$(appname).exe">  
            <Output TaskParameter = "OutputAssembly"  
                ItemName = "EXEFile" />  
        </CSC>  
  
        <!-- Log the file name of the output file -->  
        <Message Text="The output file is @(EXEFile)"/>  
    </Target>  
  
    <Target Name = "Clean">  
        <RemoveDir Directories="$(builtdir)" />  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yürütme görevi](../msbuild/exec-task.md)   
 [MakeDir görevi](../msbuild/makedir-task.md)   
 [RemoveDir görevi](../msbuild/removedir-task.md)   
 [CSC görevi](../msbuild/csc-task.md)   
 [Hedefler](../msbuild/msbuild-targets.md)