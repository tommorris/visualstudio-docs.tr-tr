---
title: SharePoint proje öğesi şema başvurusu | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
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
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9b039b1cf31a04a24819b03114c661a3ab1b108a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
|[Dosyalar](../sharepoint/files-element.md)|SharePoint proje öğesi, bir özellik öğesi dosyası veya bir proje çıktısı gibi ile dağıtmak için dosyaları belirtir.|  
|[ProjectItem](../sharepoint/projectitem-element.md)|Bir SharePoint proje öğesi temsil eder.|  
|[Projectıtemfile](../sharepoint/projectitemfile-element.md)|SharePoint için dağıtıldığında ile proje öğesi eklemek için özellik öğesi dosyası gibi bir SharePoint dosyayı temsil eder.|  
|[Projectıtemfolder](../sharepoint/projectitemfolder-element.md)|Eşlenmiş bir klasörde temsil eder.|  
|[ProjectOutputFile](../sharepoint/projectoutputfile-element.md)|SharePoint için dağıtıldığında ile proje öğesi eklemek için bir proje çıktısını gösterir.|  
|[SafeControl](../sharepoint/safecontrol-element.md)|Bir ASPX denetimi veya SharePoint sitesinde herhangi bir ASPX sayfasında erişmek herhangi bir kullanıcı için güvenli olarak tasarlanmış Web bölümünü temsil eder.|  
|[SafeControls](../sharepoint/safecontrols-element.md)|ASPX denetimleri ve SharePoint sitesindeki herhangi bir ASPX sayfasında erişmek herhangi bir kullanıcı için güvenli olarak tasarlanmış Web Bölümleri koleksiyonunu temsil eder.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Proje Öğeleri için Öğe Şablonları ve Proje Şablonları Oluşturma](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)  
  
  