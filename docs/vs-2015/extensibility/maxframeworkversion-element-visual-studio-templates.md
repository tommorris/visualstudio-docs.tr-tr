---
title: MaxFrameworkVersion öğesi (Visual Studio şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- <MaxFrameworkVersion> Element (Visual Studio Templates)
- MaxFrameworkVersion Element (Visual Studio Templates)
ms.assetid: f732a9d3-fc29-405b-9298-01ea83fc58b8
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7be6bf858130310f3b7a13078482746edf74a65a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686446"
---
# <a name="maxframeworkversion-element-visual-studio-templates"></a>MaxFrameworkVersion Öğesi (Visual Studio Şablonları)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [MaxFrameworkVersion öğesi (Visual Studio şablonları)](https://docs.microsoft.com/visualstudio/extensibility/maxframeworkversion-element-visual-studio-templates).  
  
Şablon tarafından gerekli .NET Framework'ün en yüksek sürümü belirtir. Şablon içinde görüntülenip görüntülenmeyeceğini belirler **şablonları** bölümünü **Yeni Proje Ekle** iletişim kutusunda, seçili değere göre **hedef Framework sürümü** kutusunun **Yeni Proje Ekle** iletişim kutusu.  
  
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Gerekli öğe.<br /><br /> Şablonu kategorilere ayırır ve ya da nasıl görüntüleneceğini tanımlar **yeni proje** veya **Yeni Öğe Ekle** iletişim kutusu.|  
  
## <a name="text-value"></a>Metin Değeri  
 Bir metin değeri gereklidir.  
  
 Metin şablon tarafından izin verilen .NET Framework'ün en yüksek sürüm numarası olmalıdır.  
  
## <a name="remarks"></a>Açıklamalar  
 `MaxFrameworkVersion` İsteğe bağlı bir öğedir. Öğesinde `TemplateData` için bir filtre olarak görev yapar .vstemplate dosyasının **şablonları** bölümünü **Yeni Proje Ekle** iletişim kutusu. Yalnızca, .NET Framework gereksinimleri olan şablonları küçüktür `MaxFrameworkVersion` öğe değerlerini görüntülenir, seçilen değere göre **hedef Framework sürümü** kutusunun **Yeni Proje Ekle**iletişim kutusu. `MaxFrameworkVersion` Şekilde yanlışlıkla şablonları .NET Framework'ün yeni sürümleriyle kullanıldığında görüntülenen neden değil olarak gerekli olmadığı sürece öğesi'nin etmeyebilirsiniz.  
  
## <a name="example"></a>Örnek  
 Standart için meta veriler aşağıdaki örnekte [!INCLUDE[csprcs](../includes/csprcs-md.md)] sınıf şablonu.  
  
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
  
 Bu örnekte, şablon tarafından gerekli .NET Framework'ün en yeni sürümün temsil ettiği `MaxFrameworkVersion`, 3.5. Yukarıdaki şablonu yalnızca 3.0 veya 3.5 seçtiğinizde görüntülenir **hedef Framework sürümü** kutusunda **Yeni Proje Ekle** iletişim kutusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
 [Proje ve Öğe Şablonları Oluşturma](../ide/creating-project-and-item-templates.md)

