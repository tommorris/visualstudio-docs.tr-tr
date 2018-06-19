---
title: Öğe Seç (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Choose
dev_langs:
- VB
- CSharp
- C++
- jsharp
- xml
helpviewer_keywords:
- <Choose> Element [MSBuild]
- Choose Element [MSBuild]
ms.assetid: 7b8b025a-d944-4f5c-9018-c89fc2ef146d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dc467b859e3a02282c6d6165dc263931900c5bc2
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31569527"
---
# <a name="choose-element-msbuild"></a>Öğe Seç (MSBuild)
Bir grubu seçmek için alt öğeler değerlendirir `ItemGroup` öğeleri ve/veya `PropertyGroup` değerlendirmek için öğeleri.  

 \<Proje >  
 \<Seçin >  
 \<Zaman >  
 \<Seçin >  
 ...  
 \<Aksi takdirde >  
 \<Seçin >  
 ...  

## <a name="syntax"></a>Sözdizimi  

```  
<Choose>  
    <When Condition="'StringA'=='StringB'">... </When>  
    <Otherwise>... </Otherwise>  
</Choose>  
```  

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  

### <a name="attributes"></a>Öznitelikler  
 Yok.  

### <a name="child-elements"></a>Alt Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Aksi takdirde](../msbuild/otherwise-element-msbuild.md)|İsteğe bağlı öğe.<br /><br /> Kod bloğunu belirtir `PropertyGroup` ve `ItemGroup` olmadığını değerlendirmek için öğeleri tüm koşulları `When` öğeleri değerlendirmek için `false`. Sıfır veya bir olabilir `Otherwise` öğelerinde bir `Choose` öğesi ve onu son öğesi olması gerekir.|  
|[ne zaman](../msbuild/when-element-msbuild.md)|Gerekli öğe.<br /><br /> Kod için olası bir bloğunda belirtir `Choose` öğesini seçin. Bir veya daha fazla olabilir `When` öğelerinde bir `Choose` öğesi.|  

### <a name="parent-elements"></a>Üst Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Aksi takdirde](../msbuild/otherwise-element-msbuild.md)|Yürütülecek kod bloğunu belirtir tüm koşulları `When` öğeleri değerlendirmek için `false`.|  
|[Project](../msbuild/project-element-msbuild.md)|Gerekli kök öğesinin bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyası.|  
|[ne zaman](../msbuild/when-element-msbuild.md)|Kod için olası bir bloğunda belirtir `Choose` öğesini seçin.|  

## <a name="remarks"></a>Açıklamalar  
 `Choose`, `When`, Ve `Otherwise` öğelerini birlikte bir dizi olası alternatifler dışında yürütülecek kod bir bölüm seçmek için bir yol sağlamak için kullanılır. Daha fazla bilgi için bkz: [koşullu yapıları](../msbuild/msbuild-conditional-constructs.md).  

## <a name="example"></a>Örnek  
 Aşağıdaki proje kullanır `Choose` özellik değerlerinde hangi kümesini seçmek için öğe `When` öğeleri ayarlayın. Varsa `Condition` her ikisi de özniteliklerini `When` öğeleri değerlendirmek için `false`, özellik değerleri `Otherwise` öğesi ayarlanır.  

```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
    <PropertyGroup>  
        <Configuration Condition="'$(Configuration)' == ''">Debug</Configuration>  
        <OutputType>Exe</OutputType>  
        <RootNamespace>ConsoleApplication1</RootNamespace>  
        <AssemblyName>ConsoleApplication1</AssemblyName>  
        <WarningLevel>4</WarningLevel>  
    </PropertyGroup>  
    <Choose>  
        <When Condition=" '$(Configuration)'=='debug' ">  
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
        <Otherwise>  
            <PropertyGroup>  
                <DebugSymbols>true</DebugSymbols>  
                <Optimize>false</Optimize>  
                <OutputPath>.\bin\$(Configuration)\</OutputPath>  
                <DefineConstants>DEBUG;TRACE</DefineConstants>  
            </PropertyGroup>  
        </Otherwise>  
    </Choose>  
    <Import Project="$(MSBuildBinPath)\Microsoft.CSharp.targets" />  
</Project>  
```  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Koşullu yapılar](../msbuild/msbuild-conditional-constructs.md)   
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)
