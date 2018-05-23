---
title: Projectıtemfile öğesi | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ProjectItemFile element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 67d1ed00ef4781e0419d1fceda5f95a8c0c710fb
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="projectitemfile-element"></a>ProjectItemFile Öğesi
  SharePoint için dağıtıldığında ile proje öğesi eklemek için özellik öğesi dosyası gibi bir SharePoint dosyayı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<ProjectItemFile Source = "Name of the file"  
    Target = "Deployment path of the file"  
    Type = "Type of deployment for the file" />  
```  
  
## <a name="type"></a>Tür  
 **ProjectItemFileType**  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|**Kaynak**|Gerekli **xs: String** özniteliği.<br /><br /> Proje öğesi ile dağıtmak için dosyanın adı.|  
|**Hedef**|İsteğe bağlı **xs: String** özniteliği.<br /><br /> Dosya SharePoint üzerinde dağıtım kök klasörüne görelidir dağıtılacağı yolu. Dağıtım kök klasörü tarafından belirtilen dağıtım türü tarafından belirlenir **türü** özniteliği. Varsa **hedef** özniteliği belirtilmezse, belirtilen ada sahip bir klasöre dosya dağıtılacak **kaynak** özniteliği.<br /><br /> Açıklamaları için daha fazla bilgi için bkz **dağıtım yolu** ve **dağıtım kök** SharePoint özelliklerini proje öğelerinde [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md).|  
|**Türü**|Gerekli **xs: String** özniteliği.<br /><br /> Dosyası için dağıtım türü. Olası değerler hakkında daha fazla bilgi için açıklama için bkz. **dağıtım türü** SharePoint Proje öğeleri özelliği [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Dosyalar](../sharepoint/files-element.md)|SharePoint için dağıtıldığında ile SharePoint proje öğesi eklenecek dosyaları belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Genellikle başvuru SharePoint dosyaları **Projectıtemfile** öğeleri özellik öğesi dosyaları (Elements.xml), liste tanımları (Schema.xml) için şema dosyaları ve Web Bölümleri (.webpart) için Web Bölümü tanım dosyalarını içerir.  
  
## <a name="element-information"></a>Öğe Bilgisi  
  
|||  
|-|-|  
|**Namespace**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**Şema adı**|SharePoint proje öğesi şeması|  
|**Dosya doğrulama**|ProjectItemModelSchema.xsd|  
|**Boş olamaz**|Hayır|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Proje Öğesi Şema Başvurusu](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  