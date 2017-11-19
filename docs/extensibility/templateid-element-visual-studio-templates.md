---
title: "Templateıd öğesi (Visual Studio şablonları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/vstemplate/2005#TemplateID
helpviewer_keywords:
- <TemplateID> element [Visual Studio Templates]
- TemplateID element [Visual Studio Templates]
ms.assetid: 6ca24b4e-0325-4a9e-855e-0cbbe7361d8f
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5907a6953ae58c3cca042ce7aa975eec9f4563f1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="templateid-element-visual-studio-templates"></a>TemplateID Öğesi (Visual Studio Şablonları)
Öğe şablonları tarafından grubuna kategorilere ayrılmış bir öğe şablonu için bir tanımlayıcı belirtir [Templategroupıd](../extensibility/templategroupid-element-visual-studio-templates.md) öğesi.  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<Templateıd >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<TemplateID> ... </TemplateID>  
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
 A `string` temsil eden öğe şablonları tarafından grubuna kategorilere ayrılmış bir öğe şablonu için bir tanımlayıcı `TemplateGroupID` öğesi.  
  
## <a name="remarks"></a>Açıklamalar  
 `TemplateID`İsteğe bağlı bir öğedir.  
  
 .Vstemplate dosya çıkarırsa `TemplateID` öğesi, ardından [adı](../extensibility/name-element-visual-studio-templates.md) öğe, şablonu için tanımlayıcı olarak kullanılır.  
  
 Değeri `TemplateID` öğe proje sistemi kaydı ile birlikte kullanılır (HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\11.0\Projects\\) görünür filtre şablonlarına **Yeni Öğe Ekle** iletişim kutusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)