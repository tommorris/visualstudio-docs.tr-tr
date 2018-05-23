---
title: "&lt;friendlyName&gt; öğesi (Visual Studio'da Office Geliştirme)"
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <friendlyName> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 52a8a34e7469518f2d14bab00df46ce0997343bd
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="ltfriendlynamegt-element-office-development-in-visual-studio"></a>&lt;friendlyName&gt; öğesi (Visual Studio'da Office Geliştirme)
  `friendlyName` Öğesinin `vstov4` ad alanı yüklü programlar listesinde görüntülenen adını depolar.  
  
## <a name="syntax"></a>Sözdizimi  

XML  
```  
<friendlyName>  
</friendlyName>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `friendlyName` Öğesidir içinde `vstov4` ad alanı. Değer, Microsoft Office uygulamalarının COM VSTO eklentileri iletişim kutusundan ve bilgisayarda yüklü programlar listesinde görünür.  
  
 `friendlyName` Öğeye sahip hiçbir öznitelik veya alt öğe.  
  
## <a name="vsto-add-in-example"></a>VSTO eklenti örneği  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir `friendlyName` kullanılarak dağıtılan bir uygulama düzeyi çözümü öğesinde [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kod  
  
```xml  
<vstov4:friendlyName>  
  ContosoOutlookAddIn  
</vstov4:friendlyName>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
  