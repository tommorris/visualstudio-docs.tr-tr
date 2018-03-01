---
title: "Öğe dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Files element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 609bd9e590362efefbabcc79fd910eef3653ff92
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="files-element"></a>Dosya Öğesi
  SharePoint proje öğesi özellik öğesi dosyaları gibi ve SharePoint olmayan bağımlı projeleri çıktısını dağıtmak için dosyaları belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<Files>  
  <ProjectItemFile.../>  
  <ProjectOutputFile.../>  
</Files>  
```  
  
## <a name="type"></a>Tür  
 **FileCollectionType**  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Projectıtemfile](../sharepoint/projectitemfile-element.md)|İsteğe bağlı **ProjectItemFileType** öğesi.<br /><br /> SharePoint için dağıtıldığında ile proje öğesi eklemek için özellik öğesi dosyası gibi bir SharePoint dosyayı temsil eder.|  
|[ProjectOutputFile](../sharepoint/projectoutputfile-element.md)|İsteğe bağlı **ProjectOutputFileType** öğesi.<br /><br /> SharePoint için dağıtıldığında ile proje öğesi eklemek için bir proje çıktısını gösterir.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[ProjectItem](../sharepoint/projectitem-element.md)|Bir SharePoint proje öğesi temsil eder. .Spdata dosyasının gerekli kök öğesidir.|  
  
## <a name="element-information"></a>Öğe Bilgisi  
  
|||  
|-|-|  
|**Namespace**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**Şema adı**|SharePoint proje öğesi şeması|  
|**Dosya doğrulama**|ProjectItemModelSchema.xsd|  
|**Boş olamaz**|Hayır|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Proje Öğesi Şema Başvurusu](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  