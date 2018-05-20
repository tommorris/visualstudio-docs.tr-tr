---
title: "&lt;appAddin&gt; öğesi (Visual Studio'da Office Geliştirme)"
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <appAddin> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0defe437e0778ee9d3c134148a3ca7e4b4cd2ef9
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="ltappaddingt-element-office-development-in-visual-studio"></a>&lt;appAddin&gt; öğesi (Visual Studio'da Office Geliştirme)
  **AppAddin** öğesinin `vstov4` ad alanı VSTO eklentileri için özelleştirme özgü bilgileri depolar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml 
<appAddin  
  application  
  loadBehavior  
  keyName>  
  <friendlyName>  
  <description>  
  <formRegions></formRegions>  
</appAddin>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 **AppAddin** öğesi gereklidir ve yer `vstov4` ad alanı. Yalnızca bir tane **appAddin** uygulama bildiriminde tanımlanan öğe.  
  
 **AppAddin** öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|**Uygulama**|Gerekli. Microsoft Office uygulamasının tanımlar. Değer şunlardan biri olabilir: Excel, InfoPath, Outlook, PowerPoint, proje, Visio veya Word.|  
|**LoadBehavior**|İsteğe bağlı. Varsayılan olarak, **loadBehavior** bu değeri ayarlamak etkinleştirilir. Hata ayıklama için VSTO eklentisi iki değerine ayarlayarak devre dışı bırakılabilir. LoadBehavior değerleri adlı tabloyu daha fazla bilgi için bkz: [VSTO eklentileri için kayıt defteri girişleri](../vsto/registry-entries-for-vsto-add-ins.md).|  
|**anahtar adı**|Gerekli. Bu değer uygulama tarafından VSTO eklenti yüklemek için kullanılan kayıt defteri anahtarı adını olur. Daha fazla bilgi için bkz: [VSTO eklentileri için kayıt defteri girişleri](../vsto/registry-entries-for-vsto-add-ins.md).|  
  
 **AppAddin** öğe aşağıdaki alt öğeleri vardır.  
  
### <a name="friendlyname"></a>FriendlyName  
 İsteğe bağlı. **FriendlyName** öğesi içinde açıklanan [ &#60;friendlyName&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/friendlyname-element-office-development-in-visual-studio.md).  
  
### <a name="description"></a>açıklama  
 İsteğe bağlı. **Açıklama** öğesi içinde açıklanan [ &#60;açıklama&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/description-element-office-development-in-visual-studio.md).  
  
### <a name="formregions"></a>formRegions  
 Yalnızca Outlook VSTO form bölgeleri içeren eklentileri için gereklidir. **FormRegions** öğesi içinde açıklanan [ &#60;formRegions&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/formregions-element-office-development-in-visual-studio.md).  
  
## <a name="vsto-add-in-example"></a>VSTO eklenti örneği  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir **appAddin** kullanılarak dağıtılan bir Outlook çözümü öğelerinde [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kod  
  
```xml  
<vstov4:appAddIn   
  application="Outlook"   
  loadBehavior="3"   
  keyName="ContosoOutlookAddIn">  
  <vstov4:friendlyName>  
    ContosoOutlookAddIn  
  </vstov4:friendlyName>  
  <vstov4:description>  
    ContosoOutlookAddIn - Outlook VSTO Add-in   
    created with Visual Studio Tools for Office  
  </vstov4:description>  
  <vstov4:formRegions>  
    <vstov4:formRegion  
        name="OutlookAddIn1.FormRegion1">  
      <vstov4:messageClass name="IPM.Note" />  
      <vstov4:messageClass name="IPM.Contact" />  
      <vstov4:messageClass name="IPM.Appointment" />  
    </vstov4:formRegion>  
  </vstov4:formRegions>  
</vstov4:appAddIn>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
  
  