---
title: "&lt;formRegions&gt; öğesi (Visual Studio'da Office Geliştirme)"
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- formRegions element
- <formRegions> element
- application manifests [Office development in Visual Studio], <formRegions> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 36741e5e3bcd39dbb6e4ea0746e1877acc581e70
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="ltformregionsgt-element-office-development-in-visual-studio"></a>&lt;formRegions&gt; öğesi (Visual Studio'da Office Geliştirme)
  `formRegions` Öğesinin `vstov4` ad alanı, VSTO eklenti ile ilişkili Microsoft Office Outlook form bölgeleri içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<formRegions>  
  <formRegion>  
  </formRegion>  
</formRegions>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `formRegions` Öğesinin `vstov4` ad alanı içeren tüm `formRegion` bir Outlook VSTO eklenti için öğeleri. Yalnızca Outlook VSTO form bölgeleri içeren eklentileri için gereklidir.  
  
 Yalnızca bir olabilir `formRegions` uygulama bildiriminde tanımlanan öğe.  
  
 `formRegions` Öğesi özniteliklere sahip değildir.  
  
 `formRegions` Öğesinin öğesi yok.  
  
### <a name="formregion"></a>formRegion  
 Outlook VSTO form bölgeleri içeren eklentileri için gereklidir. `formRegion` Öğesi tanımlanmış [ &#60;formRegion&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/formregion-element-office-development-in-visual-studio.md).  
  
## <a name="vsto-add-in-example"></a>VSTO eklenti örneği  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir bir `formRegions` kullanarak dağıtılmış uygulama düzeyi Office çözümü için bir uygulama bildirimi öğesinde [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kod  
  
```xml  
<vstov4:formRegions>  
  <vstov4:formRegion  
      name="OutlookAddIn1.FormRegion1">  
    <vstov4:messageClass name="IPM.Note" />  
    <vstov4:messageClass name="IPM.Contact" />  
    <vstov4:messageClass name="IPM.Appointment" />  
  </vstov4:formRegion>  
</vstov4:formRegions>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
  
  