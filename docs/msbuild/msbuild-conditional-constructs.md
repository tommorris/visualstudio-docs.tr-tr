---
title: "MSBuild koşullu yapıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
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
caps.latest.revision: "9"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: bb6244ceed63fead2925c0af7d98669b1bf5bfc2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="msbuild-conditional-constructs"></a>MSBuild Koşullu Yapıları
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]için bir mekanizma sağlar / veya işlem ile [Seç](../msbuild/choose-element-msbuild.md), [zaman](../msbuild/when-element-msbuild.md), ve [Aksi durumda](../msbuild/otherwise-element-msbuild.md) öğeleri.  
  
## <a name="using-the-choose-element"></a>Kullanarak öğe seç  
 `Choose` Öğesi içeren bir dizi `When` öğeleriyle `Condition` değerlendiren bir kadar sırayla üstten alta test öznitelikleri `true`. Birden fazla ise `When` öğesi hesaplar için `true`, yalnızca ilki kullanılır. Bir `Otherwise` öğesi, varsa, değerlendirilmesi üzerinde herhangi bir koşul ise bir `When` öğesi hesaplar için `true`.  
  
 `Choose`öğeleri alt öğeleri olarak kullanılabilir `Project`, `When` ve `Otherwise` öğeleri. `When`ve `Otherwise` öğeleri olabilir `ItemGroup`, `PropertyGroup`, veya `Choose` alt öğeleri.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `Choose` ve `When` öğeleri ya da / veya işlem. Proje öğeleri ve Özellikler değeri bağlı olarak ayarlanır `Configuration` özelliği.  
  
```xml  
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
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)