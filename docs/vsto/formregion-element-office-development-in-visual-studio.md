---
title: "&lt;formRegion&gt; öğesi (Visual Studio'da Office Geliştirme) | Microsoft Docs"
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <formRegion> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: af7dd4f3472692def9f05a937297d54d13c6f0d6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ltformregiongt-element-office-development-in-visual-studio"></a>&lt;formRegion&gt; öğesi (Visual Studio'da Office Geliştirme)
  `formRegion` Öğesinin `vstov4` ad alanı VSTO eklenti ile ilişkilendirilen bir Microsoft Office Outlook form bölgesi tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<formRegion  
  name>  
  <messageClass  
    name/>  
</formRegion>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `formRegion` Öğesinin `vstov4` ad alanı Outlook VSTO eklenti ile ilişkili bir form bölgesi tanımlar. Yalnızca Outlook VSTO form bölgeleri içeren eklentileri için gereklidir.  
  
 Birden çok da olabilir `formRegion` içinde tanımlanan öğeleri bir `formRegions` öğesi için tek bir VSTO eklentisi.  
  
 `formRegion` Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`name`|Gerekli. Form bölgesi adı tanımlar.|  
  
 `formRegion` Öğe aşağıdaki alt öğeleri vardır.  
  
### <a name="messageclass"></a>iletisınıfı  
 `messageClass` Öğesi form bölgesiyle ilişkilendirilen Outlook form tanımlar.  
  
 `messageClass` Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`name`|Gerekli. Form bölgesiyle ilişkilendirilen form tanımlar.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği gösterilmektedir bir `formRegion` Outlook VSTO kullanılarak dağıtılan eklenti için bir uygulama bildirimi öğesinde [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Bu bir form bölgesini ile ilişkili üç ileti sınıfları vardır. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
```  
<vstov4:formRegion  
    name="OutlookAddIn1.FormRegion1">  
  <vstov4:messageClass name="IPM.Note" />  
  <vstov4:messageClass name="IPM.Contact" />  
  <vstov4:messageClass name="IPM.Appointment" />  
</vstov4:formRegion>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md)   
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama Bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
  
  