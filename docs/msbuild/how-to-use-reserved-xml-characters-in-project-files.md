---
title: 'Nasıl yapılır: proje dosyalarında ayrılmış XML karakterlerini kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, using reserved XML characters
- MSBuild, reserved XML characters
ms.assetid: 1ae37275-96bf-4e6e-897b-6b048e5bbe93
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e64e6d2b4850a46f839a09e19f82d2b2a9563a78
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-use-reserved-xml-characters-in-project-files"></a>Nasıl Yapılır: Proje Dosyalarında Ayrılmış XML Karakterlerini Kullanma
Proje dosyaları yazarken, örneğin, özellik değerleri veya görev parametre değerlerini ayrılmış XML karakterlerini kullanmanız gerekebilir. Ancak, böylece proje dosyası ayrıştırılabilir bazı ayrılmış karakterler adlandırılmış bir varlık tarafından değiştirilmesi gerekir.  
  
## <a name="using-reserved-characters"></a>Ayrılmış karakterlerini kullanma  
 Aşağıdaki tabloda karşılık gelen adlandırılmış varlık tarafından değiştirilmesi gerekir ve böylece proje dosyası ayrıştırılabilir ayrılmış XML karakterlerini açıklanmaktadır.  
  
|Ayrılmış karakter|Adlandırılmış varlık|  
|------------------------|------------------|  
|\<|&amp;lt;|  
|>|&amp;gt;|  
|&|&amp;amp;|  
|"|&amp;quot;|  
|'|&amp;apos;|  
  
#### <a name="to-use-double-quotes-in-a-project-file"></a>Proje dosyasında çift tırnak işareti kullanmak için  
  
-   Varlık adlı karşılık gelen ile çift tırnak işareti yerine &amp;quot;. Örneğin, çift tırnak yerleştirmek için `EXEFile` öğe listesi, türü:  
  
    ```xml  
    <Message Text="The output file is &quot;@(EXEFile)&quot;."/>  
    ```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde çift tırnak işareti çıkış iletisini dosya adında vurgulamak için proje dosyası tarafından kullanılır.  
  
```xml  
<Project DefaultTargets="Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
    <!-- Set the application name as a property -->  
    <PropertyGroup>  
        <appname>"HelloWorldCS"</appname>  
    </PropertyGroup>  
    <!-- Specify the inputs -->  
    <ItemGroup>  
        <CSFile Include = "consolehwcs1.cs" />  
    </ItemGroup>  
    <Target Name = "Compile">  
        <!-- Run the Visual C# compilation using input  
        files of type CSFile -->  
        <Csc Sources = "@(CSFile)">  
            <!-- Set the OutputAssembly attribute of the CSC task  
            to the name of the executable file that is created -->  
            <Output  
                TaskParameter = "OutputAssembly"  
                ItemName = "EXEFile"/>  
        </Csc>  
        <!-- Log the file name of the output file -->  
        <Message Text="The output file is &quot;@(EXEFile)&quot;."/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)    
 [MSBuild](../msbuild/msbuild.md)    
