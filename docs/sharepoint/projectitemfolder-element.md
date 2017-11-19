---
title: "Projectıtemfolder öğesi | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: ProjectItemFolder element
ms.assetid: 15b386dd-f523-4425-9fcc-517325681358
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c108540f24529866a03c4e4eb22dc027037d1185
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="projectitemfolder-element"></a>ProjectItemFolder Öğesi
  Eşlenmiş bir klasörde temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<ProjectItemFolder Target = "Path of SharePoint folder the mapped folder corresponds to"  
    Type = "Type of deployment for the mapped folder" />  
```  
  
## <a name="type"></a>Tür  
 **ProjectItemFolderType**  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|**Hedef**|Gerekli **xs: String** özniteliği.<br /><br /> Eşlenmiş klasörü, dağıtım kök klasörüne görelidir karşılık gelen SharePoint yükleme klasöründe yolu. Dağıtım kök klasörü tarafından belirtilen dağıtım türü tarafından belirlenir **türü** özniteliği.<br /><br /> Açıklamaları için daha fazla bilgi için bkz **dağıtım yolu** ve **dağıtım kök** SharePoint özelliklerini proje öğelerinde [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md).|  
|**Türü**|Gerekli **xs: String** özniteliği.<br /><br /> Eşlenmiş klasörü için dağıtım türü. Olası değerler hakkında daha fazla bilgi için açıklama için bkz. **dağıtım türü** SharePoint Proje öğeleri özelliği [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[ProjectItem](../sharepoint/projectitem-element.md)|Bir SharePoint proje öğesi temsil eder. .Spdata dosyasının gerekli kök öğesidir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Eşlenen klasörler hakkında daha fazla bilgi için bkz: [nasıl yapılır: eşlenmiş klasörler ekleyip](../sharepoint/how-to-add-and-remove-mapped-folders.md).  
  
## <a name="element-information"></a>Öğe Bilgisi  
  
|||  
|-|-|  
|**Namespace**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**Şema adı**|SharePoint proje öğesi şeması|  
|**Dosya doğrulama**|ProjectItemModelSchema.xsd|  
|**Boş olamaz**|Hayır|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint proje öğesi şema başvurusu](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [Nasıl yapılır: ekleme ve kaldırma eşlenen klasörler](../sharepoint/how-to-add-and-remove-mapped-folders.md)  
  
  