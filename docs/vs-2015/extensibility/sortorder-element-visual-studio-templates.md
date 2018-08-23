---
title: SortOrder öğesi (Visual Studio şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#SortOrder
helpviewer_keywords:
- SortOrder element [Visual Studio Templates]
- <SortOrder> element [Visual Studio Templates]
ms.assetid: 151932c1-f08a-4f78-a8d0-bd2f32211a9c
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4619d151e66d288907dea97894a1ae133be8708b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689616"
---
# <a name="sortorder-element-visual-studio-templates"></a>SortOrder Öğesi (Visual Studio Şablonları)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [SortOrder öğesi (Visual Studio şablonları)](https://docs.microsoft.com/visualstudio/extensibility/sortorder-element-visual-studio-templates).  
  
Ya da göründüğü gibi aynı kategoride bulunan diğer şablonlar arasında şablonunu düzenlemek için kullanılan bir değer belirtir **yeni proje** veya **Yeni Öğe Ekle** iletişim kutusu.  
  
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Gerekli öğe.<br /><br /> Şablonu kategorilere ayırır ve nasıl görüntülendiğini tanımlar **yeni proje** veya **Yeni Öğe Ekle** iletişim kutusu.|  
  
## <a name="text-value"></a>Metin Değeri  
 Bir metin değeri gereklidir.  
  
 Bir `integer` sıralama sıra değeri temsil eden.  
  
## <a name="remarks"></a>Açıklamalar  
 `SortOrder` İsteğe bağlı bir öğedir. Varsayılan değer 100'dür ve tüm değerlerin 10'ın katları olmalıdır.  
  
 `SortOrder` Öğesi, kullanıcı tarafından oluşturulan şablonlarını için yoksayılır. Tüm kullanıcı tarafından oluşturulan şablonlarını alfabetik olarak sıralanır.  
  
 Düşük sıralama sipariş değerleri olan şablonlar görünür ya da **yeni proje** veya **Yeni Öğe Ekle** yüksek sıralama sipariş değerleri olan şablonları önce iletişim kutusu.  
  
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
        <SortOrder>290</SortOrder>  
        <DefaultName>MyClass</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem>MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
 Bu örnekte, `SortOrder` öğedir görece yüksek. Büyük olasılıkla diğer [!INCLUDE[csprcs](../includes/csprcs-md.md)] öğe şablonları sahip olacak bir `SortOrder` tutardan değeri `290` ve bu şablonda önce görünür **yeni öğe** iletişim kutusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
 [Proje ve Öğe Şablonları Oluşturma](../ide/creating-project-and-item-templates.md)

