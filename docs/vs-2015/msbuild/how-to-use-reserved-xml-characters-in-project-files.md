---
title: 'Nasıl yapılır: proje dosyalarında ayrılmış XML karakterlerini kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSBuild, using reserved XML characters
- MSBuild, reserved XML characters
ms.assetid: 1ae37275-96bf-4e6e-897b-6b048e5bbe93
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f045195a4e934fcb6e140da68528ca43f104136d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688236"
---
# <a name="how-to-use-reserved-xml-characters-in-project-files"></a>Nasıl Yapılır: Proje Dosyalarında Ayrılmış XML Karakterlerini Kullanma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: proje dosyalarında ayrılmış XML karakterlerini kullanma](https://docs.microsoft.com/visualstudio/msbuild/how-to-use-reserved-xml-characters-in-project-files).  
  
  
Proje dosyaları yazdığınızda, ayrılmış XML karakterleri, örneğin özellik değerlerini veya görev parametresi değerleri kullanmak gerekebilir. Ancak, proje dosyası ayrıştırıldığında, bazı ayrılmış karakterleri adlandırılmış varlık tarafından değiştirilmelidir.  
  
## <a name="using-reserved-characters"></a>Ayrılmış karakterleri kullanma  
 Aşağıdaki tabloda, ayrılmış XML karakterlerini karşılık gelen adlandırılmış varlık tarafından değiştirilmelidir ve böylece proje dosyası ayrıştırıldığında açıklanmaktadır.  
  
|Ayrılmış karakter|Adlandırılmış varlık|  
|------------------------|------------------|  
|\<|&lt;|  
|>|&gt;|  
|&|&amp;|  
|"|&quot;|  
|'|&apos;|  
  
#### <a name="to-use-double-quotes-in-a-project-file"></a>Çift tırnak işareti bir proje dosyasında kullanmak için  
  
-   Adlandırılmış varlık, ilgili ile çift tırnak işaretleri yerine &quot;. Örneğin, çift tırnak işaretlerini yerleştirmek için `EXEFile` öğe listesi, türü:  
  
    ```  
    <Message Text="The output file is "@(EXEFile)"."/>  
    ```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde proje dosyası tarafından çıkış iletisini dosya adında vurgulamak için çift tırnak işareti kullanılır.  
  
```  
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
        <Message Text="The output file is "@(EXEFile)"."/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild başvurusu](../msbuild/msbuild-reference.md) [MSBuild](msbuild.md)


