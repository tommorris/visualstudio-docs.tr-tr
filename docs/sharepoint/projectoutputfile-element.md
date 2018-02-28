---
title: "ProjectOutputFile öğesi | Microsoft Docs"
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
- ProjectOutputFile element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 5b57f00960629d65f264f22532a16202d6ae5d7a
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="projectoutputfile-element"></a>ProjectOutputFile Öğesi
  SharePoint için dağıtıldığında ile proje öğesi eklemek için ayrı bir proje çıktısını gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<ProjectOutputFile ProjectId = "GUID of the project"  
    ProjectPath = "Relative path of the project"  
    Target = "Deployment path of the project output"  
    Type = "Type of deployment for the project output" />  
```  
  
## <a name="type"></a>Tür  
 **ProjectOutputFileType**  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|**ProjectId**|Gerekli **xs: String** özniteliği.<br /><br /> GUID bağımlı projenin dahil etmek istediğiniz çıktıyı içerir. Bu karşılık **ProjectGuid** bağımlı proje öğesi.|  
|**ProjectPath**|Gerekli **xs: String** özniteliği.<br /><br /> Proje dosyası adını dahil etmek istediğiniz çıkış sahip bağımlı projeyi de dahil olmak üzere, göreli yol. SharePoint proje öğesi içeren SharePoint Proje kök klasörüne görelidir yoludur.|  
|**Hedef**|İsteğe bağlı **xs: String** özniteliği.<br /><br /> Bağımlı proje çıktı dağıtım kök klasöre göreli SharePoint sunucusuna dağıtılması bulunduğu yolu. Dağıtım kök klasörü tarafından belirtilen dağıtım türü tarafından belirlenir **türü** özniteliği.<br /><br /> Açıklamaları için daha fazla bilgi için bkz **dağıtım yolu** ve **dağıtım kök** SharePoint özelliklerini proje öğelerinde [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md).|  
|**Türü**|Gerekli **xs: String** özniteliği.<br /><br /> Bağımlı proje çıktı için kullanılacak dağıtım türü. Olası değerler hakkında daha fazla bilgi için açıklama için bkz. **dağıtım türü** SharePoint Proje öğeleri özelliği [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Dosyaları](../sharepoint/files-element.md)|SharePoint için dağıtıldığında ile SharePoint proje öğesi eklenecek dosyaları belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım **ProjectOutputFile** bir proje çıktı SharePoint proje öğesi dağıtımda öğesi. Farklı bir proje veya proje öğesi içeren aynı projeye belirtebilirsiniz. Daha fazla bilgi için bkz: [sağlama paketleme ve dağıtım bilgileri proje öğelerinde](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).  
  
## <a name="element-information"></a>Öğe Bilgisi  
  
|||  
|-|-|  
|**Namespace**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**Şema adı**|SharePoint proje öğesi şeması|  
|**Dosya doğrulama**|ProjectItemModelSchema.xsd|  
|**Boş olamaz**|Hayır|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint proje öğesi şema başvurusu](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [Paketleme ve dağıtım bilgileri proje öğeleri sağlama](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)   
 [SharePoint Çözümleri Geliştirme](../sharepoint/developing-sharepoint-solutions.md)  
  
  