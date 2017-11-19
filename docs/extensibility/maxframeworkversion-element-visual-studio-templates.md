---
title: "MaxFrameworkVersion öğesi (Visual Studio şablonları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <MaxFrameworkVersion> Element (Visual Studio Templates)
- MaxFrameworkVersion Element (Visual Studio Templates)
ms.assetid: f732a9d3-fc29-405b-9298-01ea83fc58b8
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: da1b30274254c5c1dd81ad20dd64e8749672f96e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="maxframeworkversion-element-visual-studio-templates"></a>MaxFrameworkVersion Öğesi (Visual Studio Şablonları)
Şablon tarafından gerekli .NET Framework'ün en yeni sürümün belirtir. Şablon olarak görüntülenip görüntülenmeyeceğini belirler **şablonları** bölümünü **Yeni Proje Ekle** iletişim kutusunda, seçili değere göre **hedef Framework sürümü** kutusunun **Yeni Proje Ekle** iletişim kutusu.  
  
 \<VSTemplate >  
 \<MaxFrameworkVersion >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
 `MaxFrameworkVersion`İsteğe bağlı bir öğedir. Öğe `TemplateData` .vstemplate dosyasının bölümü için bir filtre olarak görev yapan **şablonları** bölümünü **Yeni Proje Ekle** iletişim kutusu. Yalnızca, .NET Framework gereksinimleri şablonları değerinden `MaxFrameworkVersion` öğesi değerlerini görüntülenir, seçili değere göre **hedef Framework sürümü** kutusunun **Yeni Proje Ekle**iletişim kutusu. `MaxFrameworkVersion` Böylece yanlışlıkla şablonları .NET Framework'ün daha yeni sürümleriyle kullanıldığında görüntülenen neden değil olarak için gerekli olmadığı sürece öğesi'nin etmeyebilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir standart için meta verileri gösterir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] sınıf şablonu.  
  
```  
<VSTemplate Type="Item" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyClass</Name>  
        <Description>My custom C# class template.</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <MaxFrameworkVersion>3.5</MaxFrameworkVersion>  
        <DefaultName>MyClass</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem>MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
 Bu örnekte, şablon için gerekli .NET Framework'ün en yeni sürümün temsil ettiği `MaxFrameworkVersion`, 3.5. Yukarıdaki şablonu yalnızca 3.0 veya 3.5 içinde seçtiğinizde görüntülenir **hedef Framework sürümü** kutusunda **Yeni Proje Ekle** iletişim kutusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)