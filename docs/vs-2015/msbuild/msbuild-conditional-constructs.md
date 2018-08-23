---
title: MSBuild koşullu yapıları | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <Choose> Element [MSBuild]
- Choose Element [MSBuild]
- conditional constructs [MSBuild]
- MSBuild, conditional constructs
- <When> Element [MSBuild]
- <Otherwise> Element [MSBuild]
- Otherwise Element [MSBuild]
- When Element [MSBuild]
ms.assetid: dd54258e-f4fb-448f-9da4-d1817e0cbaf2
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7997db7fc5c7dd866de8f9d573779ead29e5e9d2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633318"
---
# <a name="msbuild-conditional-constructs"></a>MSBuild Koşullu Yapıları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [MSBuild koşullu yapıları](https://docs.microsoft.com/visualstudio/msbuild/msbuild-conditional-constructs).  
  
  
[!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] için bir mekanizma sağlar / veya işlem ile [Seç](../msbuild/choose-element-msbuild.md), [olduğunda](../msbuild/when-element-msbuild.md), ve [Aksi takdirde](../msbuild/otherwise-element-msbuild.md) öğeleri.  
  
## <a name="using-the-choose-element"></a>Kullanarak öğe seç  
 `Choose` Öğesi içeren bir dizi `When` öğelerle `Condition` bir sonucunu verene kadar yukarıdan aşağıya sırasında test öznitelikleri `true`. Birden fazla ise `When` öğesi değerlendirilen `true`, yalnızca ilki kullanılır. Bir `Otherwise` öğesi, varsa değerlendirilir herhangi bir koşul, bir `When` öğesi değerlendirilen `true`.  
  
 `Choose` öğeleri alt öğeleri olarak kullanılabilir `Project`, `When` ve `Otherwise` öğeleri. `When` ve `Otherwise` öğeleri olabilir `ItemGroup`, `PropertyGroup`, veya `Choose` alt öğeleri.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte `Choose` ve `When` öğeleri ya da / veya işleme. Projesi için öğeler ve özellikler bağlı olarak değeri ayarlanır `Configuration` özelliği.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
    <PropertyGroup>  
        <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
        <OutputType>Exe</OutputType>  
        <RootNamespace>ConsoleApplication1</RootNamespace>  
        <AssemblyName>ConsoleApplication1</AssemblyName>  
        <WarningLevel>4</WarningLevel>  
    </PropertyGroup>  
    <Choose>  
        <When Condition=" '$(Configuration)'=='Debug' ">  
            <PropertyGroup>  
                <DebugSymbols>true</DebugSymbols>  
                <DebugType>full</DebugType>  
                <Optimize>false</Optimize>  
                <OutputPath>.\bin\Debug\</OutputPath>  
                <DefineConstants>DEBUG;TRACE</DefineConstants>  
            </PropertyGroup>  
            <ItemGroup>  
                <Compile Include="UnitTesting\*.cs" />  
                <Reference Include="NUnit.dll" />  
            </ItemGroup>  
        </When>  
        <When Condition=" '$(Configuration)'=='retail' ">  
            <PropertyGroup>  
                <DebugSymbols>false</DebugSymbols>  
                <Optimize>true</Optimize>  
                <OutputPath>.\bin\Release\</OutputPath>  
                <DefineConstants>TRACE</DefineConstants>  
            </PropertyGroup>  
        </When>  
    </Choose>  
    <!-- Rest of Project -->  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Öğe Seç (MSBuild)](../msbuild/choose-element-msbuild.md)   
 [Zaman öğesi (MSBuild)](../msbuild/when-element-msbuild.md)   
 [Otherwise öğesi (MSBuild)](../msbuild/otherwise-element-msbuild.md)   
 [MSBuild Başvurusu](../msbuild/msbuild-reference.md)



