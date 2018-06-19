---
title: RequiredFrameworkVersion öğesi (Visual Studio şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- <RequiredFrameworkVersion> (Visual Studio Templates)
- RequiredFrameworkVersion (Visual Studio Templates)
ms.assetid: 08a4f609-51a5-4723-b89f-99277fb18871
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: adc1a138c50c0fe13962f6601449eb3498d90398
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31137842"
---
# <a name="requiredframeworkversion-element-visual-studio-templates"></a>RequiredFrameworkVersion Öğesi (Visual Studio Şablonları)

Şablon tarafından gerekli .NET Framework'ün en düşük sürüm belirtir. Neden **hedef Framework sürümü** görüntülenmesini açılır **yeni proje** iletişim. `RequiredFrameworkVersion` Öğesi de açılır menüde kullanılabilir en düşük değer belirler.

> [!IMPORTANT]
> Visual Studio 2017 sürüm 15,6, başlangıç **hedef Framework sürümü** açılır olduğu artık görüntülenen şablonlarında için bir filtre **şablonları** bölümünü **yeni proje** iletişim. Bunun yerine, seçili şablon için bir çerçeve Seçici açılan görür.

 \<VSTemplate > \<TemplateData > \<RequiredFrameworkVersion >

## <a name="syntax"></a>Sözdizimi

```xml
<RequiredFrameworkVersion> .... </RequiredFrameworkVersion>
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

 Metin şablonu için gerekli olan .NET Framework'ün en düşük sürüm numarası olmalıdır.

## <a name="remarks"></a>Açıklamalar

`RequiredFrameworkVersion` İsteğe bağlı bir öğedir. Şablonu yalnızca belirli en düşük sürüm (ve sonraki sürümleri varsa) destekliyorsa bu öğeyi kullanın .NET Framework'ün. Belirtirseniz `RequiredFrameworkVersion` öğesi ve şablonunuzu belirli en düşük sürüm .NET Framework'ün desteklemiyor **hedef Framework sürümü** açılan geçerli olmadığında görüntüler.

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

Bu örnekte, şablon için gerekli .NET Framework'ün en düşük sürüm temsil ettiği `RequiredFrameworkVersion`, 3.0. Bu şablon kullanılarak oluşturulan bir proje .NET Framework sürüm 3.0 uygulamasından başlangıç hedefleyebilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.

- [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)
- [Proje ve Öğe Şablonları Oluşturma](../ide/creating-project-and-item-templates.md)
- [Belirli Bir .NET Framework Sürümünü Hedefleme](../ide/targeting-a-specific-dotnet-framework-version.md)
