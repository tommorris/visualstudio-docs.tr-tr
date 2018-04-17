---
title: FeatureProperties öğesi | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- FeatureProperties element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 991d2c57da8a1fc45fba266cdafe38000cd3d594
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="featureproperties-element"></a>FeatureProperties Öğesi
  SharePoint için dağıtıldığında sahip bir özellik dahil olan özellik değerlerini koleksiyonunu temsil eder. Bir özellik dağıtıldıktan sonra kodunuzda özellik değerlerini erişebilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<FeatureProperties>  
  <FeatureProperty.../>  
</FeatureProperties>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[FeatureProperty](../sharepoint/featureproperty-element.md)|İsteğe bağlı öğe.<br /><br /> Anahtar/değer biçimde özel bir özelliği temsil eder.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[ProjectItem](../sharepoint/projectitem-element.md)|Bir SharePoint proje öğesi temsil eder. .Spdata dosyasının gerekli kök öğesidir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Özellik özellikleri hakkında daha fazla bilgi için bkz: [sağlama paketleme ve dağıtım bilgileri proje öğelerinde](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).  
  
## <a name="element-information"></a>Öğe Bilgisi  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|**Namespace**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**Şema adı**|SharePoint proje öğesi şeması|  
|**Dosya doğrulama**|ProjectItemModelSchema.xsd|  
|**Boş olamaz**|Hayır|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint proje öğesi şema başvurusu](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [Proje Öğelerinde Paketleme ve Dağıtım Bilgileri Sağlama](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)  
  
  