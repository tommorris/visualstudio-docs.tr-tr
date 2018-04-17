---
title: 'Nasıl yapılır: farklı seçeneklerle aynı kaynak dosyaları derleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- source files, building with different options
- MSBuild, properties
- project properties, modifying
- Hello World example [Visual Studio]
ms.assetid: d14f1212-ddd9-434f-b138-f840011b0fb2
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f1105c9122d47e405ad309531abd4913484991fa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-build-the-same-source-files-with-different-options"></a>Nasıl Yapılır: Farklı Seçeneklerle Aynı Kaynak Dosyaları Derleme
Projeleri oluşturduğunuzda, farklı yapılandırma seçenekleriyle aynı bileşenleri sık derleyin. Örneğin, sembol bilgileri veya sembol bilgileri ile ancak iyileştirmeler yayın derlemesinde hata ayıklama derlemesi oluşturabilirsiniz. Veya x86 gibi belirli bir platformda çalıştırmak için bir proje oluşturabilirsiniz veya [!INCLUDE[vcprx64](../extensibility/internals/includes/vcprx64_md.md)]. Bu durumlarda, yapı seçeneklerin çoğu aynı kalır; derleme yapılandırması denetlemek için yalnızca birkaç seçenekleri değişir. İle [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], farklı bir yapı yapılandırmaları oluşturmak için özellikleri ve koşulları kullanın.  
  
## <a name="using-properties-to-modify-projects"></a>Projeleri değiştirmek için özelliklerini kullanma  
 `Property` Öğe, birkaç kez geçici bir dizine konumu gibi bir proje dosyası içinde başvurulan bir değişken tanımlar veya kullanılan özelliklerinin değerlerini ayarlamak için hata ayıklama derlemesi ve sürüm gibi çeşitli yapılandırmaları oluşturabilirsiniz. Özellikleri hakkında daha fazla bilgi için bkz: [MSBuild özellikleri](../msbuild/msbuild-properties.md).  
  
 Proje dosyası değiştirmek zorunda kalmadan, derleme yapılandırmasını değiştirmek için özellikler kullanabilirsiniz. `Condition` Özniteliği `Property` öğesi ve `PropertyGroup` öğesi özelliklerinin değerini değiştirmenize olanak sağlar. Hakkında daha fazla bilgi için [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] koşullar bkz [koşullar](../msbuild/msbuild-conditions.md).  
  
#### <a name="to-set-a-group-of-properties-based-on-another-property"></a>Bir grubu başka bir özelliğe dayalı özelliklerini ayarlamak için  
  
-   Kullanım bir `Condition` özniteliğini bir `PropertyGroup` öğesi aşağıdakine benzer:  
  
    ```xml  
    <PropertyGroup Condition="'$(Flavor)'=='DEBUG'">  
        <DebugType>full</DebugType>  
        <Optimize>no</Optimize>  
    </PropertyGroup>  
    ```  
  
#### <a name="to-define-a-property-based-on-another-property"></a>Başka bir özelliğe dayalı bir özellik tanımlamak için  
  
-   Kullanım bir `Condition` özniteliğini bir `Property` öğesi aşağıdakine benzer:  
  
    ```xml  
    <DebugType Condition="'$(Flavor)'=='DEBUG'">full</DebugType>  
    ```  
  
## <a name="specifying-properties-on-the-command-line"></a>Komut satırında özelliklerini belirtme  
 Birden çok yapılandırmaları kabul etmek için proje dosyanızı yazıldıktan sonra projenizi derleme olduğunda bu yapılandırmaları değiştirme olanağına sahip gerekir. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] komut satırını kullanarak belirtilmesini özellikleri sağlayarak bu yeteneği sağlar **/property** veya **/p** geçin.  
  
#### <a name="to-set-a-project-property-at-the-command-line"></a>Komut satırında bir proje özelliği ayarlamak için  
  
-   Kullanım **/property** anahtar özellik ve özellik değeri. Örneğin:  
  
    ```  
    msbuild file.proj /property:Flavor=Debug  
    ```  
  
     - veya -  
  
    ```  
    Msbuild file.proj /p:Flavor=Debug  
    ```  
  
#### <a name="to-specify-more-than-one-project-property-at-the-command-line"></a>Komut satırında birden çok proje özelliği belirtmek için  
  
-   Kullanmak **/property** veya **/p** özelliği ve özellik değerleri ile birden çok kez geçiş veya kullanın **/property** veya **/p** geçin ve birden çok özellik noktalı virgülle (;) ayırın. Örneğin:  
  
    ```  
    msbuild file.proj /p:Flavor=Debug;Platform=x86  
    ```  
  
     - veya -  
  
    ```  
    msbuild file.proj /p:Flavor=Debug /p:Platform=x86  
    ```  
  
 Ortam değişkenleri de özellikleri olarak kabul edilir ve tarafından otomatik olarak dahil [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Ortam değişkenlerini kullanma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir derleme kullanma ortam değişkenleri](../msbuild/how-to-use-environment-variables-in-a-build.md).  
  
 Komut satırında belirtilen özellik değeri, proje dosyasında aynı özelliği için ayarlanır ve değer proje dosyasında bir ortam değişkeni değeri önceliklidir herhangi bir değer daha önceliklidir.  
  
 Kullanarak bu davranışı değiştirebilirsiniz `TreatAsLocalProperty` proje etiketinde öznitelik. Bu öznitelik ile listelenen özellik adları için komut satırında belirtilen özellik değeri proje dosyasındaki değer önceliklidir değil. Bu konuda daha sonra bir örnek bulabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde, "Hello World" projenin hata ayıklama derlemesi ve yayın derlemesi oluşturmak için kullanılan iki yeni özellik gruplarını içerir.  
  
 Bu projenin hata ayıklama sürümü oluşturmak için şunu yazın:  
  
```  
msbuild consolehwcs1.proj /p:flavor=debug  
```  
  
 Bu proje perakende sürümünü oluşturmak için şunu yazın:  
  
```  
msbuild consolehwcs1.proj /p:flavor=retail  
```  
  
```xml  
<Project DefaultTargets = "Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <!-- Sets the default flavor of an environment variable called   
    Flavor is not set or specified on the command line -->  
    <PropertyGroup>  
        <Flavor Condition="'$(Flavor)'==''">DEBUG</Flavor>  
    </PropertyGroup>  
  
    <!-- Define the DEBUG settings -->  
    <PropertyGroup Condition="'$(Flavor)'=='DEBUG'">  
        <DebugType>full</DebugType>  
        <Optimize>no</Optimize>  
    </PropertyGroup>  
  
    <!-- Define the RETAIL settings -->  
    <PropertyGroup Condition="'$(Flavor)'=='RETAIL'">  
        <DebugType>pdbonly</DebugType>  
        <Optimize>yes</Optimize>  
    </PropertyGroup>  
  
    <!-- Set the application name as a property -->  
    <PropertyGroup>  
        <appname>HelloWorldCS</appname>  
    </PropertyGroup>  
  
    <!-- Specify the inputs by type and file name -->  
    <ItemGroup>  
        <CSFile Include = "consolehwcs1.cs"/>  
    </ItemGroup>  
  
    <Target Name = "Compile">  
        <!-- Run the Visual C# compilation using input files  
        of type CSFile -->  
        <CSC  Sources = "@(CSFile)"  
            DebugType="$(DebugType)"  
            Optimize="$(Optimize)"  
            OutputAssembly="$(appname).exe" >  
  
            <!-- Set the OutputAssembly attribute of the CSC  
            task to the name of the executable file that is   
            created -->  
            <Output TaskParameter="OutputAssembly"  
                ItemName = "EXEFile" />  
        </CSC>  
        <!-- Log the file name of the output file -->  
        <Message Text="The output file is @(EXEFile)"/>  
    </Target>  
</Project>  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını anlatan `TreatAsLocalProperty` özniteliği. `Color` Özellik değerine sahip `Blue` proje dosyasında ve `Green` komut satırında. İle `TreatAsLocalProperty="Color"` proje etiketinde komut satırı özelliği (`Green`) proje dosyasında tanımlanan özelliği geçersiz kılmaz (`Blue`).  
  
 Projeyi oluşturmak için aşağıdaki komutu girin:  
  
```  
msbuild colortest.proj /t:go /property:Color=Green  
```  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003"  
ToolsVersion="4.0" TreatAsLocalProperty="Color">  
  
    <PropertyGroup>  
        <Color>Blue</Color>  
    </PropertyGroup>  
  
    <Target Name="go">  
        <Message Text="Color: $(Color)" />  
    </Target>  
</Project>  
  
<!--  
  Output with TreatAsLocalProperty="Color" in project tag:  
     Color: Blue  
  
  Output without TreatAsLocalProperty="Color" in project tag:  
     Color: Green  
-->  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[MSBuild](../msbuild/msbuild.md)  
 [MSBuild kavramları](../msbuild/msbuild-concepts.md)   
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Proje Öğesi (MSBuild)](../msbuild/project-element-msbuild.md)