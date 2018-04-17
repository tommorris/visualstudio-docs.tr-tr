---
title: 'Nasıl yapılır: Proje dosyasının konumunu veya adını başvurusu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- locations, referencing
- locations
- MSBuildProjectName property
- MSBuild, referencing the project file
- names, referencing
- reserved properties
- project files, referencing
ms.assetid: c8fcc594-5d37-4e2e-b070-4d9c012043b5
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ede50f253032f53707461696f717825774c1e6d0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-reference-the-name-or-location-of-the-project-file"></a>Nasıl Yapılır: Proje Dosyasının Adına veya Konumuna Başvurma
Proje konumunu veya adını kendi özellik oluşturmak zorunda kalmadan proje dosyasının kendisini kullanabilirsiniz. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Proje dosyası adı başvuru ayrılmış özellikleri ve proje ile ilgili diğer özellikleri sağlar. Ayrılmış özellikler hakkında daha fazla bilgi için bkz: [MSBuild ayrılmış ve tanınmış özellikleri](../msbuild/msbuild-reserved-and-well-known-properties.md).  
  
## <a name="using-the-msbuildprojectname-property"></a>MSBuildProjectName özelliği kullanma  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Proje dosyalarınıza her zaman tanımlamadan kullanabileceğiniz bazı ayrılmış özellikleri sağlar. Örneğin, ayrılmış bir özellik `MSBuildProjectName` proje dosyası adı için bir başvuru sağlar.  
  
#### <a name="to-use-the-msbuildprojectname-property"></a>MSBuildProjectName özelliği kullanmak için  
  
-   Herhangi bir özellikte gibi $ () gösterimi ile proje dosyasında özellik başvuru. Örneğin:  
  
    ```xml  
    <CSC Sources = "@(CSFile)"   
        OutputAssembly = "$(MSBuildProjectName).exe"/>  
    </CSC>  
    ```  
  
 Ayrılmış bir özellik kullanmanın avantajı, proje dosyası adı yapılan değişikliklerin otomatik olarak eklenen olmasıdır. Proje derleme bir sonraki başlatılışında çıktı dosyası, yapmanız gereken başka bir eylem ile yeni ada sahip olacaktır.  
  
> [!NOTE]
>  Ayrılmış özellikler proje dosyasında tanımlanamaz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek proje dosyası çıktısı için bir ad belirtmek için ayrılmış bir özellik olarak proje adı başvurur.  
  
```xml  
<Project xmlns="http://scheams.microsoft.com/developer/msbuild/2003"   
    DefaultTargets = "Compile">  
  
    <!-- Specify the inputs -->  
    <ItemGroup>  
        <CSFile Include = "consolehwcs1.cs"/>  
    </ItemGroup>  
    <Target Name = "Compile">  
        <!-- Run the Visual C# compilation using  
        input files of type CSFile -->  
        <CSC Sources = "@(CSFile)"  
            OutputAssembly = "$(MSBuildProjectName).exe" >  
            <!-- Set the OutputAssembly attribute of the CSC task  
            to the name of the project -->  
            <Output  
                TaskParameter = "OutputAssembly"  
                ItemName = "EXEFile" />  
        </CSC>  
        <!-- Log the file name of the output file -->  
        <Message Text="The output file is @(EXEFile)"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[MSBuild](../msbuild/msbuild.md)  
 [MSBuild Ayrılmış ve Tanınmış Özellikleri](../msbuild/msbuild-reserved-and-well-known-properties.md)