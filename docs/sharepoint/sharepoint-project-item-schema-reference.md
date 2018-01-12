---
title: "SharePoint proje öğesi şema başvurusu | Microsoft Docs"
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
helpviewer_keywords:
- FeatureProperty element
- SafeControls element
- SafeControl element
- .spdata files
- ExtensionData element
- FeatureProperties element
- ProjectOutputFile element
- Files element
- ProjectItemFolder element
- ProjectItemFile element
- ExtensionDataItem element
- ProjectItem element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 99a2471919483f02a9f58a35ad164527a12a39c5
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="sharepoint-project-item-schema-reference"></a>SharePoint Proje Öğesi Şema Başvurusu
  Visual Studio SharePoint proje öğesi şema .spdata dosyaları içeriğini doğrulamak için kullanır. .Spdata dosya içeriğini ve bir SharePoint proje öğesi davranışını belirtir. SharePoint Proje öğeleri içeriği hakkında daha fazla bilgi için bkz: [öğe şablonları oluşturma ve SharePoint Proje öğeleri için proje şablonları](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
 SharePoint proje öğesi şema ProjectItemModelSchema.xsd olarak adlandırılır ve % Program Files (x86)%\Microsoft Visual Studio 11.0\Xml\Schemas. varsayılan olarak yüklenir  
  
 Kök öğe [ProjectItem](../sharepoint/projectitem-element.md) öğesi. Aşağıdaki tabloda şema tarafından tanımlanan tüm öğeleri açıklanmaktadır.  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[ExtensionData](../sharepoint/extensiondata-element.md)|SharePoint proje öğesi ile ilişkili olan özel veri öğeleri koleksiyonunu temsil eder.|  
|[Extensiondataıtem](../sharepoint/extensiondataitem-element.md)|SharePoint proje öğesi anahtar/değer biçimi ile ilişkili bir özel veri öğesini temsil eder. Anahtar ve değer dize olmalıdır.|  
|[FeatureProperties](../sharepoint/featureproperties-element.md)|SharePoint için dağıtıldığında sahip bir özellik dahil olan özellik değerlerini koleksiyonunu temsil eder. Bir özellik dağıtıldıktan sonra kodunuzda özellik değerlerini erişebilir.|  
|[FeatureProperty](../sharepoint/featureproperty-element.md)|SharePoint'e dağıtıldığında, sahip bir özellik bulunan özel bir özelliği temsil eder. Bir özellik dağıtıldıktan sonra kodunuzda özelliği erişebilirsiniz.|  
|[Dosyaları](../sharepoint/files-element.md)|SharePoint proje öğesi, bir özellik öğesi dosyası veya bir proje çıktısı gibi ile dağıtmak için dosyaları belirtir.|  
|[ProjectItem](../sharepoint/projectitem-element.md)|Bir SharePoint proje öğesi temsil eder.|  
|[Projectıtemfile](../sharepoint/projectitemfile-element.md)|SharePoint için dağıtıldığında ile proje öğesi eklemek için özellik öğesi dosyası gibi bir SharePoint dosyayı temsil eder.|  
|[Projectıtemfolder](../sharepoint/projectitemfolder-element.md)|Eşlenmiş bir klasörde temsil eder.|  
|[ProjectOutputFile](../sharepoint/projectoutputfile-element.md)|SharePoint için dağıtıldığında ile proje öğesi eklemek için bir proje çıktısını gösterir.|  
|[SafeControl](../sharepoint/safecontrol-element.md)|Bir ASPX denetimi veya SharePoint sitesinde herhangi bir ASPX sayfasında erişmek herhangi bir kullanıcı için güvenli olarak tasarlanmış Web bölümünü temsil eder.|  
|[SafeControls](../sharepoint/safecontrols-element.md)|ASPX denetimleri ve SharePoint sitesindeki herhangi bir ASPX sayfasında erişmek herhangi bir kullanıcı için güvenli olarak tasarlanmış Web Bölümleri koleksiyonunu temsil eder.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Proje Öğeleri için Öğe Şablonları ve Proje Şablonları Oluşturma](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)  
  
  