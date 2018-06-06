---
title: ExtensionData öğesi | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ExtensionData element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e065c64445710e6ff0a99d3bcf8a27c71425879e
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34765719"
---
# <a name="extensiondata-element"></a>ExtensionData öğesi
  SharePoint proje öğesi ile ilişkili olan özel veri öğeleri koleksiyonunu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<ExtensionData>  
  <ExtensionDataItem.../>  
</ExtensionData>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve öğeler
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt öğeleri
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Extensiondataıtem](../sharepoint/extensiondataitem-element.md)|İsteğe bağlı öğe.<br /><br /> SharePoint proje öğesi anahtar/değer biçimi ile ilişkili bir özel veri öğesini temsil eder. Anahtar ve değer dize olmalıdır.|  
  
### <a name="parent-elements"></a>Üst öğeler
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[ProjectItem](../sharepoint/projectitem-element.md)|Bir SharePoint proje öğesi temsil eder. Bu öğe gerekli kök öğesi, `.spdata` dosya.|  
  
## <a name="remarks"></a>Açıklamalar  
 İlişkilendirdiğinizde özel verileri ile bir SharePoint proje öğesi kullanarak <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> özelliği bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> nesnesi, Visual Studio kaydeder verileri **ExtensionData** öğesinde `.spdata` proje dosyası öğe. Daha fazla bilgi için bkz: [SharePoint Proje sisteminin uzantılarında veri kaydetme](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md).  
  
## <a name="element-information"></a>Öğe bilgileri
  
|||  
|-|-|  
|**Namespace**|HTTP<nolink>: //schemas.microsoft.com/VisualStudio/<br>SharePointTools/2010/SharePointProjectItemModel|  
|**Şema adı**|SharePoint proje öğesi şeması|  
|**Dosya doğrulama**|ProjectItemModelSchema.xsd|  
|**Boş olamaz**|Hayır|  
  
## <a name="see-also"></a>Ayrıca bkz.
 [SharePoint Proje Öğesi Şema Başvurusu](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  
