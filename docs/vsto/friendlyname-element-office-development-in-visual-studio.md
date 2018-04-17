---
title: "&lt;friendlyName&gt; öğesi (Visual Studio'da Office Geliştirme) | Microsoft Docs"
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
ms.openlocfilehash: 0cbf4438b72169218daa6814599fc8c7d11a15aa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ltfriendlynamegt-element-office-development-in-visual-studio"></a>&lt;friendlyName&gt; öğesi (Visual Studio'da Office Geliştirme)
  `friendlyName` Öğesinin `vstov4` ad alanı yüklü programlar listesinde görüntülenen adını depolar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<friendlyName>  
</friendlyName>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `friendlyName` Öğesidir içinde `vstov4` ad alanı. Değer, Microsoft Office uygulamalarının COM VSTO eklentileri iletişim kutusundan ve bilgisayarda yüklü programlar listesinde görünür.  
  
 `friendlyName` Öğeye sahip hiçbir öznitelik veya alt öğe.  
  
## <a name="vsto-add-in-example"></a>VSTO eklentileri örneği  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir `friendlyName` kullanılarak dağıtılan bir uygulama düzeyi çözümü öğesinde [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kod  
  
```  
<vstov4:friendlyName>  
  ContosoOutlookAddIn  
</vstov4:friendlyName>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama Bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
  
  