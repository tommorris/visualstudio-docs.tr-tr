---
title: "&lt;özelleştirme&gt; öğesi (Visual Studio'da Office Geliştirme) | Microsoft Docs"
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
helpviewer_keywords: application manifests [Office development in Visual Studio], <customization> element
ms.assetid: a3bf7f35-bd98-4530-9226-46489cd37bb1
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 922e68a676f1f8ceac547983436c76ac01facc3b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustomizationgt-element-office-development-in-visual-studio"></a>&lt;özelleştirme&gt; öğesi (Visual Studio'da Office Geliştirme)
  `customization` Öğesinin `vstov4` ad alanı, belirli bir Office çözümü açıklanmaktadır. Belge düzeyi özelleştirmeleri ve VSTO eklentileri için farklı alt öğeleridir.  
  
## <a name="syntax-for-document-level-customizations"></a>Belge düzeyi özelleştirmeleri için sözdizimi  
  
```  
<customization  
  id  
  <document  
    solutionId  
  />  
</customization>  
```  
  
## <a name="syntax-for-vsto-add-ins"></a>VSTO eklentileri için sözdizimi  
  
```  
<customization  
  id  
  <appAddin  
    application  
    loadBehavior  
    keyName>  
  <friendlyName></friendlyName>  
  <description></description>  
  <formRegions></formRegions>  
</customization>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `customization` Öğesi özelleştirme özgü bilgileri içerir. Bu öğe aşağıdaki ad alanında olması gerekir: `vstov4=urn:schemas-microsoft-com:vsto.v4`. Bir `customization` her Office çözümü için öğesi. Örneğin, birden çok proje dağıtımında üç Office çözümlerini dağıtma varsa üç `customization` uygulama bildiriminde öğeleri.  
  
 Bütünleştirilmiş kodun alt öğeleri de bu ad alanında olması gerekir.  
  
 `customization` Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`id`|Birden çok proje dağıtımı için gerekli. `id` Öğesi benzersiz olarak tanımlayan bir Office çözümü.|  
  
### <a name="document-level-customizations"></a>Belge Düzeyinde Özelleştirmeler  
 `customization` Öğesinin alt öğesi yok.  
  
#### <a name="document"></a>belge  
 `document` Öğesinde `vstov4` ad alanı tanımlanmış [&#60; belge &#62; Öğe &#40; Office geliştirme Visual Studio &#41; ](../vsto/document-element-office-development-in-visual-studio.md).  
  
### <a name="vsto-add-ins"></a>VSTO eklentileri  
 `customization` Öğesinin alt öğesi yok.  
  
#### <a name="appaddin"></a>appAddin  
 `appAddin` Öğesinde `vstov4` ad alanı tanımlanmış [&#60; appAddin &#62; Öğe &#40; Office geliştirme Visual Studio &#41; ](../vsto/appaddin-element-office-development-in-visual-studio.md).  
  
## <a name="example-of-a-document-level-customization"></a>Belge düzeyi özelleştirme örneği  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir `customization` öğesi için belge düzeyi özelleştirme. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kod  
  
```  
<vstov4:customization>  
  <vstov4:document   
    solutionId="73e" />  
</vstov4:customization>  
```  
  
## <a name="example-of-an-vsto-add-in"></a>VSTO eklenti örneği  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir `customization` öğesi için bir VSTO eklenti. Bir VSTO Outlook form bölgeleri içeren eklenti budur. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kod  
  
```  
<vstov4:customization>  
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
</vstov4:customization>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama Bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
  
  