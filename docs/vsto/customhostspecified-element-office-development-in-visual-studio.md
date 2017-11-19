---
title: "&lt;customHostSpecified&gt; öğesi (Visual Studio'da Office Geliştirme) | Microsoft Docs"
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
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <customHostSpecified> element
- <customHostSpecified> element
- customHostSpecified element
ms.assetid: 2212b7eb-bf94-4398-b9ea-0ab00203203b
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c7ad3bb1e62e2ea98f5afe1de5cc9eb49f711234
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ltcustomhostspecifiedgt-element-office-development-in-visual-studio"></a>&lt;customHostSpecified&gt; öğesi (Visual Studio'da Office Geliştirme)
  `customHostSpecified` Öğesi gösterir Bu çözüm bağımsız bir uygulama değil. Office çözümleri Microsoft Office uygulamalarında barındırılan bileşenleri içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<customHostSpecified />  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `customHostSpecified` Öğesi Office çözümleri için gereklidir. Bu öğe `co.v1` ad alanı ve bu dağıtım, özel bir konağın içinde dağıtılan bir bileşen içerdiğini belirtir ve tek başına bir uygulama değildir.  
  
 Bu öğenin ilk alt öğesidir `<entrypoint>` uygulama bildiriminde öğesi. Başka hiçbir alt öğe söz olabilir `<entrypoint>` öğesi veya [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] yükleme sırasında bir doğrulama hatası yükseltirsiniz.  
  
 Bu öğe özniteliklere ve alt öğeleri vardır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği gösterilmektedir `customHostSpecified` Office çözümü için uygulama bildiriminde öğesi. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
```  
<entryPoint>  
    <co.v1:customHostSpecified />  
</entryPoint>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
  
  