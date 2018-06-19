---
title: DefaultName öğesi (Visual Studio şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#DefaultName
helpviewer_keywords:
- DefaultName element [Visual Studio project templates]
ms.assetid: 0ff056c8-b9d2-4747-9308-92adf1811491
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e67d8970859906e839abf89e85e38c24c2d88066
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126864"
---
# <a name="defaultname-element-visual-studio-templates"></a>DefaultName Öğesi (Visual Studio Şablonları)
Oluşturulduğunda proje ve öğe için Visual Studio Proje sistemi oluşturacak ad belirtir.  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<DefaultName >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<DefaultName>  
    Default Project Name  
</DefaultName>  
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
  
 Bu metin proje veya öğe varsayılan adını belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 `DefaultName` İsteğe bağlı bir öğedir.  
  
 Projeler için bu öğe projeye diskte depolar dizinin adını belirtir. Öğeleri için kaynak dosyasının dosya adını belirtir.  
  
 Bir proje veya öğesi oluşturduğunuzda, varsayılan adını kullanarak değiştirebilirsiniz **adı** herhangi birinden kullanılabilir seçeneği **yeni proje** iletişim kutusu veya **Yeni Öğe Ekle** iletişim kutusu.  
  
 Proje ve öğe için varsayılan adı oluşturmak için proje sistemi istemiyorsanız, daha sonra ayarlamak [ProvideDefaultName](../extensibility/providedefaultname-element-visual-studio-templates.md) öğesine `False`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek standart madde şablon için meta verileri gösterilmektedir bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] sınıfı.  
  
```  
<VSTemplate Type="Item" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyClass</Name>  
        <Description>My custom C# class.</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <DefaultName>MyClass.cs</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem ReplaceParameters="true">MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
 [Proje ve Öğe Şablonları Oluşturma](../ide/creating-project-and-item-templates.md)