---
title: "Projectıtemfolder öğesi | Microsoft Docs"
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
- ProjectItemFolder element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: df3c5b91e5f95d6ec794bff08c2251c5bf5e5307
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
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
 [Nasıl yapılır: Eşlenmiş Klasörler Ekleme ve Kaldırma](../sharepoint/how-to-add-and-remove-mapped-folders.md)  
  
  