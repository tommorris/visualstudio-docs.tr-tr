---
title: "SortOrder öğesi (Visual Studio şablonları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#SortOrder
helpviewer_keywords:
- SortOrder element [Visual Studio Templates]
- <SortOrder> element [Visual Studio Templates]
ms.assetid: 151932c1-f08a-4f78-a8d0-bd2f32211a9c
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a6473e867655974f42f41a276b8becfd12fbab7a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="sortorder-element-visual-studio-templates"></a>SortOrder Öğesi (Visual Studio Şablonları)
Ya da göründüğü gibi diğer şablonları aynı kategoride arasında şablonu düzenlemek için kullanılan bir değeri belirtir **yeni proje** veya **Yeni Öğe Ekle** iletişim kutusu.  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<SortOrder >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<SortOrder> ... </SortOrder>  
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
  
 Bir `integer` sıralama sıra değeri temsil eden.  
  
## <a name="remarks"></a>Açıklamalar  
 `SortOrder`İsteğe bağlı bir öğedir. Varsayılan değer 100'dür ve tüm değerlerin 10'ün katları olmalıdır.  
  
 `SortOrder` Öğesi için kullanıcı tarafından oluşturulan şablonlar göz ardı edilir. Tüm kullanıcı tarafından oluşturulan şablonlar alfabetik olarak sıralanır.  
  
 Düşük sıralama sipariş değerlere sahip şablonları ya da görünür **yeni proje** veya **Yeni Öğe Ekle** yüksek sıralama sipariş değerlere sahip şablonları önce iletişim kutusu.  
  
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
        <SortOrder>290</SortOrder>  
        <DefaultName>MyClass</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem>MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
 Bu örnekte, `SortOrder` öğesidir görece yüksek. Büyük olasılıkla diğer [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] öğe şablonları sahip olacak bir `SortOrder` değerinden daha düşük değer `290` ve bu şablonda önce görünür **yeni öğe** iletişim kutusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
 [Proje ve Öğe Şablonları Oluşturma](../ide/creating-project-and-item-templates.md)