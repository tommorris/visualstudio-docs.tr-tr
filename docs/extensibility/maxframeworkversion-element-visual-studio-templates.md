---
title: MaxFrameworkVersion öğesi (Visual Studio şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- <MaxFrameworkVersion> Element (Visual Studio Templates)
- MaxFrameworkVersion Element (Visual Studio Templates)
ms.assetid: f732a9d3-fc29-405b-9298-01ea83fc58b8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4bc28fcc35a4a59852ef6864886acff4dc87ef60
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="maxframeworkversion-element-visual-studio-templates"></a>MaxFrameworkVersion Öğesi (Visual Studio Şablonları)

Şablon tarafından gerekli .NET Framework'ün en yeni sürümün belirtir. Kullanılabilir en yüksek değeri belirler **hedef Framework sürümü** açılır, **yeni proje** iletişim. Kullanıcıların bir framework sürümünü seçmek için sırayla de belirtmeniz gerekir [RequiredFrameworkVersion](../extensibility/requiredframeworkversion-element-visual-studio-templates.md) şablonu için en düşük .NET Framework sürümü olarak.

> [!IMPORTANT]
> Visual Studio 2017 sürüm 15,6, başlangıç **hedef Framework sürümü** açılır olduğu artık görüntülenen şablonlarında için bir filtre **şablonları** bölümünü **yeni proje** iletişim. Bunun yerine, **hedef Framework sürümü** açılır işlevleri Seçili şablon için bir çerçeve seçici olarak.

 \<VSTemplate > \<TemplateData > \<MaxFrameworkVersion >

## <a name="syntax"></a>Sözdizimi

```xml
<MaxFrameworkVersion> ... </MaxFrameworkVersion>
```

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.

### <a name="attributes"></a>Öznitelikler
 Yok.

### <a name="child-elements"></a>Alt Öğeler
 Yok.

### <a name="parent-elements"></a>Üst Öğeler

|Öğe|Açıklama|
|-------------|-----------------|
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Gerekli öğe.<br /><br /> Şablon kategorilere ayırır ve onu ya da nasıl görüntüleneceğini tanımlar **yeni proje** veya **Yeni Öğe Ekle** iletişim kutusu.|

## <a name="text-value"></a>Metin Değeri
 Bir metin değeri gereklidir.

 Metin şablonu tarafından izin verilen .NET Framework'ün en yüksek sürüm numarası olmalıdır.

## <a name="remarks"></a>Açıklamalar

`MaxFrameworkVersion` İsteğe bağlı bir öğedir. `MaxFrameworkVersion` Böylece yanlışlıkla şablonu için desteklenen çeşitli .NET Framework sürümleri değil olarak sınırlandıracak gerekli olmadığı sürece öğesi'nin etmeyebilirsiniz. .NET Framework şablonuna uygulanabilir değilse, ayrıca alınmamalıdır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir standart için meta verileri gösterir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] sınıf şablonu.

```xml
<VSTemplate Type="Item" Version="3.0.0"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>MyClass</Name>
        <Description>My custom C# class template.</Description>
        <Icon>Icon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
        <RequiredFrameworkVersion>3.0</RequiredFrameworkVersion>
        <MaxFrameworkVersion>4.7.1</MaxFrameworkVersion>
        <DefaultName>MyClass</DefaultName>
    </TemplateData>
    <TemplateContent>
        <ProjectItem>MyClass.cs</ProjectItem>
    </TemplateContent>
</VSTemplate>
```

Bu örnekte, şablon için gerekli .NET Framework'ün en yeni sürümün temsil ettiği `MaxFrameworkVersion`, 4.7.1 değil. Bu şablon kullanılarak oluşturulan bir proje .NET Framework sürümleri 4.7.1 kadar hedefleyebilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.

- [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)
- [Proje ve Öğe Şablonları Oluşturma](../ide/creating-project-and-item-templates.md)
