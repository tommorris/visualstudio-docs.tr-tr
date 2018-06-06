---
title: "&lt;Güncelleştirme&gt; öğesi (Visual Studio'da Office Geliştirme)"
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- update element
- <update> element
- application manifests [Office development in Visual Studio], <update> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c51a7f79165d421f080d05088418d02a48680b66
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767614"
---
# <a name="ltupdategt-element-office-development-in-visual-studio"></a>&lt;Güncelleştirme&gt; öğesi (Visual Studio'da Office Geliştirme)
  `update` Öğesi çözüm denetleyecek güncelleştirmelere yönelik aralığı belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<update  
  enabled>  
  <expiration  
    maximumAge  
    unit  
  />  
</update>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `update` Öğesi gereklidir ve yer `vstav3` ad alanı.  
  
 `update` Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`enabled`|Gerekli. Aşağıdaki değerlerden biri için etkinleştirilmiş ayarlayın:<br /><br /> -   **doğru** güncelleştirmeleri denetlemek için.<br />-   **yanlış** güncelleştirmeleri denetleniyor önlemek için.|  
  
 `update` Öğe aşağıdaki alt öğeleri vardır.  
  
### <a name="expiration"></a>süre sonu  
 `expiration` Öğesi gereklidir ve yer `vstav3` ad alanı. Bu öğe, çözüm denetler aralığını güncelleştirmeleri belirtir.  
  
 `expiration` Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`maximumAge`|   Gerekli. Bu, bir tamsayıya eşit ayarlayın.|  
|`unit`|Gerekli. Ayarlama `unit` aşağıdaki değerlerden birine:<br /><br /> -   **Saatleri**<br />-   **gün**<br />-   **Hafta**|  
  
## <a name="example-of-always-checking-for-updates"></a>Her zaman güncelleştirmeleri denetleniyor örneği  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir bir `update` her zaman Office çözümlerinde güncelleştirmeleri denetlemek için ayarlanmış öğesi.  
  
### <a name="code"></a>Kod  
  
```xml  
<vstav3:update enabled="true" />  
```  
  
## <a name="example-of-setting-a-default-update-interval"></a>Bir varsayılan güncelleştirme aralığı ayarlama örneği  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir bir `update` Office çözümleri için uygulama bildiriminde öğesi. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kod  
  
```xml  
<vstav3:update enabled="true">  
    <vstav3:expiration maximumAge="7" unit="days" />  
</vstav3:update>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [ClickOnce kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
  
  