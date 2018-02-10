---
title: "Nasıl yapılır: derlemede ortam değişkenlerini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- environment variables, referencing
- projects [.NET Framework], environment variables
- MSBuild, environment variables
ms.assetid: 7f9e4469-8865-4b59-aab3-3ff26bd36e77
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 246f13b340c0acea519dccd323c1e7b2c28dd344
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="how-to-use-environment-variables-in-a-build"></a>Nasıl Yapılır: Derlemede Ortam Değişkenlerini Kullanma
Projeleri oluşturduğunuzda, genellikle proje dosyası ya da projenizi oluşturan dosyaların değil bilgileri kullanarak yapılandırma seçeneklerini ayarlamak gereklidir. Bu bilgileri genellikle ortam değişkenleri olarak depolanır.  
  
## <a name="referencing-environment-variables"></a>Ortam değişkenleri başvurma  
 Tüm ortam değişkenleri kullanılabilir [!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] ([!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]) proje dosyası özellikleri olarak.  
  
> [!NOTE]
>  Proje dosyası bir ortam değişkeni ile aynı ada sahip bir özellik için açık bir tanımını içeriyorsa, proje dosyasında özelliği ortam değişkeninin değerini geçersiz kılar.  
  
#### <a name="to-use-an-environment-variable-in-an-msbuild-project"></a>Bir ortam değişkeni MSBuild projesinde kullanmak için  
  
-   Ortam değişkeni, proje dosyasında bildirilen bir değişken olduğu gibi başvuru. Örneğin, aşağıdaki kodu BIN_PATH ortam değişkeni başvuruyor:  
  
     `<FinalOutput>$(BIN_PATH)\MyAssembly.dll</FinalOutput>`  
  
 Kullanabileceğiniz bir `Condition` özniteliği ortam değişkeni ayarlanmamış ise bir özellik için varsayılan bir değer sağlayın.  
  
#### <a name="to-provide-a-default-value-for-a-property"></a>Bir özellik için varsayılan bir değer sağlamak için  
  
-   Kullanım bir `Condition` özellik değeri yalnızca IF ayarlamak için özellik öznitelikte değere sahip değil. Örneğin, aşağıdaki kod ayarlar `ToolsPath` c:\tools eksikse özelliğine `ToolsPath` ortam değişkeni ayarlı değil:  
  
     `<ToolsPath Condition="'$(TOOLSPATH)' == ''">c:\tools</ToolsPath>`  
  
    > [!NOTE]
    >  Özellik adları büyük küçük harfe duyarlı olmayan böylece hem `$(ToolsPath)` ve `$(TOOLSPATH)` aynı özellik veya ortam değişkeni başvurusu.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki proje dosyasını dizinler konumunu belirtmek için ortam değişkenlerini kullanır.  
  
```xml  
<Project DefaultTargets="FakeBuild">  
    <PropertyGroup>  
        <FinalOutput>$(BIN_PATH)\myassembly.dll</FinalOutput>  
        <ToolsPath Condition=" '$(ToolsPath)' == '' ">  
            C:\Tools  
        </ToolsPath>  
    </PropertyGroup>  
    <Target Name="FakeBuild">  
        <Message Text="Building $(FinalOutput) using the tools at $(ToolsPath)..."/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
    [MSBuild ](../msbuild/msbuild.md)
    [MSBuild Properties](../msbuild/msbuild-properties.md)
 [Nasıl Yapılır: Farklı Seçeneklerle Aynı Kaynak Dosyaları Derleme](../msbuild/how-to-build-the-same-source-files-with-different-options.md)