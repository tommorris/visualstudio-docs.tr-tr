---
title: "Öğe dosyaları | Microsoft Docs"
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
helpviewer_keywords: Files element
ms.assetid: 3c611d5b-28f1-48a7-a068-63e01fa2f3aa
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: dcb3e7e81d9897f23742eda83c72bb64caed65da
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [SharePoint proje öğesi şema başvurusu](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  