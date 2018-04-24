---
title: Zaman öğesi (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#When
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <When> Element [MSBuild]
- When Element [MSBuild]
ms.assetid: eb27de6f-4e71-4e87-87e2-d93f7bf5899c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e0a1587a429c92fe1bac5d2cd0bcd63c0f27a68c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="when-element-msbuild"></a>When Öğesi (MSBuild)
Kod için olası bir bloğunda belirtir `Choose` öğesini seçin.  
  
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
<When Condition="'StringA'=='StringB'">  
    <PropertyGroup>... </PropertyGroup>  
    <ItemGroup>... </ItemGroup>  
    <Choose>... </Choose>  
</When>  
```  

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  

### <a name="attributes"></a>Öznitelikler  

|Öznitelik|Açıklama|  
|---------------|-----------------|  
|Koşul|Gerekli öznitelik.<br /><br /> Değerlendirilecek koşulu. Daha fazla bilgi için bkz: [koşullar](../msbuild/msbuild-conditions.md).|  

### <a name="child-elements"></a>Alt Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[seçin](../msbuild/choose-element-msbuild.md)|İsteğe bağlı öğe.<br /><br /> Kod yürütmek için bir bölüm seçmek için alt öğeler değerlendirir. Sıfır veya daha fazla olabilir `Choose` öğelerinde bir `When` öğesi.|  
|[ItemGroup](../msbuild/itemgroup-element-msbuild.md)|İsteğe bağlı öğe.<br /><br /> Kullanıcı tanımlı bir kümesini içerir [öğesi](../msbuild/item-element-msbuild.md) öğeleri. Sıfır veya daha fazla olabilir `ItemGroup` öğelerinde bir `When` öğesi.|  
|[PropertyGroup](../msbuild/propertygroup-element-msbuild.md)|İsteğe bağlı öğe.<br /><br /> Kullanıcı tanımlı bir kümesini içerir [özelliği](../msbuild/property-element-msbuild.md) öğeleri. Sıfır veya daha fazla olabilir `PropertyGroup` öğelerinde bir `When` öğesi.|  

### <a name="parent-elements"></a>Üst Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Öğe Seç (MSBuild)](../msbuild/choose-element-msbuild.md)|Kod yürütmek için bir bölüm seçmek için alt öğeler değerlendirir.|  

## <a name="remarks"></a>Açıklamalar  
 Varsa `Condition` özniteliği alt true olarak değerlendirilir `ItemGroup` ve `PropertyGroup` öğeleri `When` öğesi yürütülen ve sonraki tüm `When` öğeleri atlanır.  

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
