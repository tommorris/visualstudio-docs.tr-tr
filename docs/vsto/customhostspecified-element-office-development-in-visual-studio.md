---
title: "&lt;customHostSpecified&gt; öğesi (Visual Studio'da Office Geliştirme) | Microsoft Docs"
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <customHostSpecified> element
- <customHostSpecified> element
- customHostSpecified element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9d74dac27e4d4a5735dc73ebb069d985d17022d4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 [ClickOnce Uygulama Bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
  
  