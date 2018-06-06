---
title: Öğe dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Files element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 330c408aa0e283eb282b93f77726ccc5d9547795
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766912"
---
# <a name="files-element"></a>Dosyalar öğesi
  SharePoint proje öğesi özellik öğesi dosyaları gibi ve SharePoint olmayan bağımlı projeleri çıktısını dağıtmak için dosyaları belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<Files>  
  <ProjectItemFile.../>  
  <ProjectOutputFile.../>  
</Files>  
```  
  
## <a name="type"></a>Tür  
 **FileCollectionType**  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve öğeler
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt öğeleri
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Projectıtemfile](../sharepoint/projectitemfile-element.md)|İsteğe bağlı **ProjectItemFileType** öğesi.<br /><br /> SharePoint için dağıtıldığında ile proje öğesi eklemek için özellik öğesi dosyası gibi bir SharePoint dosyayı temsil eder.|  
|[ProjectOutputFile](../sharepoint/projectoutputfile-element.md)|İsteğe bağlı **ProjectOutputFileType** öğesi.<br /><br /> SharePoint için dağıtıldığında ile proje öğesi eklemek için bir proje çıktısını gösterir.|  
  
### <a name="parent-elements"></a>Üst öğeler
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[ProjectItem](../sharepoint/projectitem-element.md)|Bir SharePoint proje öğesi temsil eder. Bu öğe gerekli kök öğesi, `.spdata` dosya.|  
  
## <a name="element-information"></a>Öğe bilgileri
  
|||  
|-|-|  
|**Namespace**|HTTP<nolink>: //schemas.microsoft.com/VisualStudio/<br>SharePointTools/2010/SharePointProjectItemModel|  
|**Şema adı**|SharePoint proje öğesi şeması|  
|**Dosya doğrulama**|ProjectItemModelSchema.xsd|  
|**Boş olamaz**|Hayır|  
  
## <a name="see-also"></a>Ayrıca bkz.
 [SharePoint Proje Öğesi Şema Başvurusu](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  
