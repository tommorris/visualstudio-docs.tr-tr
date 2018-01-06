---
title: "&lt;appAddin&gt; öğesi (Visual Studio'da Office Geliştirme) | Microsoft Docs"
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
helpviewer_keywords: application manifests [Office development in Visual Studio], <appAddin> element
ms.assetid: 6152fe5b-6af1-465d-aee7-19e4fd4d04c1
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: c099f73e98542c29718efc4158593da35d333abd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ltappaddingt-element-office-development-in-visual-studio"></a>&lt;appAddin&gt; öğesi (Visual Studio'da Office Geliştirme)
  `appAddin` Öğesinin `vstov4` ad alanı VSTO eklentileri için özelleştirme özgü bilgileri depolar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
 `appAddin` Öğesi gereklidir ve yer `vstov4` ad alanı. Yalnızca bir tane `appAddin` uygulama bildiriminde tanımlanan öğe.  
  
 `appAddin` Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`application`|Gerekli. Microsoft Office uygulamasının tanımlar. Değer şunlardan biri olabilir: Excel, InfoPath, Outlook, PowerPoint, proje, Visio veya Word.|  
|`loadBehavior`|İsteğe bağlı. Varsayılan olarak, `loadBehavior` bu değeri ayarlamak etkinleştirilir. Hata ayıklama için VSTO eklentisi iki değerine ayarlayarak devre dışı bırakılabilir. LoadBehavior değerleri adlı tabloyu daha fazla bilgi için bkz: [VSTO eklentileri için kayıt defteri girişleri](../vsto/registry-entries-for-vsto-add-ins.md).|  
|`keyName`|Gerekli. Bu değer uygulama tarafından VSTO eklenti yüklemek için kullanılan kayıt defteri anahtarı adını olur. Daha fazla bilgi için bkz: [VSTO eklentileri için kayıt defteri girişleri](../vsto/registry-entries-for-vsto-add-ins.md).|  
  
 `appAddin` Öğe aşağıdaki alt öğeleri vardır.  
  
### <a name="friendlyname"></a>FriendlyName  
 İsteğe bağlı. `friendlyName` Öğesi içinde açıklanan [&#60; friendlyName &#62; Öğe &#40; Office geliştirme Visual Studio &#41; ](../vsto/friendlyname-element-office-development-in-visual-studio.md).  
  
### <a name="description"></a>açıklama  
 İsteğe bağlı. `description` Öğesi içinde açıklanan [&#60; açıklama &#62; Öğe &#40; Office geliştirme Visual Studio &#41; ](../vsto/description-element-office-development-in-visual-studio.md).  
  
### <a name="formregions"></a>formRegions  
 Yalnızca Outlook VSTO form bölgeleri içeren eklentileri için gereklidir. `formRegions` Öğesi içinde açıklanan [&#60; formRegions &#62; Öğe &#40; Office geliştirme Visual Studio &#41; ](../vsto/formregions-element-office-development-in-visual-studio.md).  
  
## <a name="vsto-add-in-example"></a>VSTO eklentileri örneği  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir `appAddin` kullanılarak dağıtılan bir Outlook çözümü öğelerinde [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kod  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama Bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
  
  