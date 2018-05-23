---
title: ProvideDefaultName öğesi (Visual Studio şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProvideDefaultName
helpviewer_keywords:
- ProvideDefaultName element [Visual Studio project templates]
ms.assetid: 7b0e7b20-fd6b-42e2-81d0-e5100cea0528
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fbe291c838d006bea62450f7e397cde7e5d09ee3
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2018
---
# <a name="providedefaultname-element-visual-studio-templates"></a>ProvideDefaultName Öğesi (Visual Studio Şablonları)
Belirtir olup olmadığını [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proje sistemi, şablon için bir varsayılan ad oluşturacağını **Yeni Öğe Ekle** veya **yeni proje** iletişim kutusu.  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<ProvideDefaultName >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<ProvideDefaultName> true/false </ProvideDefaultName>  
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Gerekli öğe.<br /><br /> Şablon kategorilere ayırır ve nasıl ya da görüntüler tanımlar **yeni proje** veya **Yeni Öğe Ekle** iletişim kutusu.|  
  
## <a name="text-value"></a>Metin Değeri  
 Bir metin değeri gereklidir.  
  
 Metin ya da olmalıdır `true` veya `false`, şablon için bir varsayılan adı oluşturmak gerekip gerekmediğini belirten **Yeni Öğe Ekle** veya **yeni proje** iletişim kutusu.  
  
## <a name="remarks"></a>Açıklamalar  
 `ProvideDefaultName` İsteğe bağlı bir öğedir. Varsayılan değer `true` şeklindedir.  
  
 Varsa `ProvideDefaultName` öğesi `false`, **adı** kutularını **Yeni Öğe Ekle** ve **yeni proje** iletişim kutuları içeren değeri `<Enter_name>`.  
  
 Kullanım [DefaultName](../extensibility/defaultname-element-visual-studio-templates.md) projenin varsayılan adı belirtin veya öğesi için öğe **Yeni Öğe Ekle** ve **yeni proje** iletişim kutuları. Zaman değeri `ProvideDefaultName` öğesi `true`, Java'daki `DefaultName` öğesi projeleri için şablonun adı, diğer bir deyişle, değerinden iletişim kutusuyla doldurur [adı](../extensibility/name-element-visual-studio-templates.md) öğesi.
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kod `ProvideDefaultName` öğesine `false`.  
  
```  
<VSTemplate Type="Item" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyClass</Name>  
        <Description>My custom C# class.</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <ProvideDefaultName>false</ProvideDefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem>MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
 [Proje ve Öğe Şablonları Oluşturma](../ide/creating-project-and-item-templates.md)
