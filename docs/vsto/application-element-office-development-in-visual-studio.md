---
title: "&lt;Uygulama&gt; öğesi (Visual Studio'da Office Geliştirme)"
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <application> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0d513ce5d9439ffa55a32d5210669162c0a21e2e
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35255830"
---
# <a name="ltapplicationgt-element-office-development-in-visual-studio"></a>&lt;Uygulama&gt; öğesi (Visual Studio'da Office Geliştirme)
  `application` Öğesinin `vstav3` ad alanı Office çözümleri açıklaması sarmalar. Belge düzeyi özelleştirmeleri ve VSTO eklentileri için farklı alt öğeleridir.  
  
## <a name="syntax-for-document-level-customizations"></a>Belge düzeyi özelleştirmeleri için sözdizimi  
  
```xml  
<application>  
  <customization  
    id  
    <document  
      solutionId  
    />  
  </customization>  
</application>  
```  
  
## <a name="syntax-for-application-level-add-ins"></a>Uygulama düzeyi eklentileri için sözdizimi  
  
```xml
<application>  
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
</application>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `application` Öğesinin `vstav3` ad alanıdır bulunan tüm özelleştirme özgü bilgileri sarmalar düğümü `vstov4` ad alanı.  
  
 `application` Öğesi özniteliklere sahip değildir.  
  
 `application` Öğesinin öğesi yok.  
  
### <a name="customization"></a>Özelleştirme  
 Rolü `customization` öğesinde `vstov3` ad alanı tanımlanmış [ &#60;özelleştirme&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/customization-element-office-development-in-visual-studio.md).  
  
## <a name="document-level-customization-example"></a>Belge düzeyi özelleştirme örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir bir `application` kullanılarak dağıtılan bir belge düzeyi Office çözümü öğesinde [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kod  
  
```xml  
<vstav3:application>  
  <vstov4:customizations   
    xmlns:vstov4="urn:schemas-microsoft-com:vsto.v4">  
    <vstov4:customization>  
      <vstov4:document   
        solutionId="73e" />  
    </vstov4:customization>  
  </vstov4:customizations>  
</vstav3:application>  
```  
  
## <a name="vsto-add-in-example"></a>VSTO eklenti örneği  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir bir `application` kullanarak dağıtılmış uygulama düzeyi Office çözümünü öğesinde [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kod  
  
```xml  
<vstav3:application>  
  <vstov4:customizations   
    xmlns:vstov4="urn:schemas-microsoft-com:vsto.v4">  
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
  </vstov4:customizations>  
</vstav3:application>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
  
  