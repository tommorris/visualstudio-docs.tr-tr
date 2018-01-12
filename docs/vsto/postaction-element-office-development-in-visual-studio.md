---
title: "&lt;postAction&gt; öğesi (Visual Studio'da Office Geliştirme) | Microsoft Docs"
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
- application manifests [Office development in Visual Studio], <postAction> element
- <postAction> element
- postAction element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 63e15e2a02ac58ee385e38d5ed2d435c0e80dddb
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="ltpostactiongt-element-office-development-in-visual-studio"></a>&lt;postAction&gt; öğesi (Visual Studio'da Office Geliştirme)
  `postAction` Öğesinin `vstav3` ad alanında `entrypoint` öğeleri ve tüm `postActionData` Office çözümleri yüklendikten sonra çalıştırmak dağıtım sonrası eylemleri ile ilişkili olan öğeler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<postAction>  
  <entryPoint>  
  </entryPoint>  
  <postActionData>  
  </postActionData>  
</postAction>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `postAction` Öğe isteğe bağlı ve olarak `vstav3` ad alanı. Bir `postAction` her dağıtım sonrası eylemi için uygulama bildiriminde tanımlanan öğe.  
  
 `postAction` Öğesi özniteliklere sahip değildir.  
  
 `postAction`Aşağıdaki öğeler vardır.  
  
### <a name="entrypoint"></a>EntryPoint  
 İsteğe bağlı. Rolü `entryPoint` öğesinde `vstav3` ad alanı tanımlanmış [&#60; giriş noktaları &#62; Öğe &#40; Office geliştirme Visual Studio &#41; ](../vsto/entrypoints-element-office-development-in-visual-studio.md).  
  
### <a name="postactiondata"></a>postActionData  
 İsteğe bağlı. Rolü `postActionData` öğesinde `vstav3` ad alanı tanımlanmış [&#60; postActionData &#62; Öğe &#40; Office geliştirme Visual Studio &#41; ](../vsto/postactiondata-element-office-development-in-visual-studio.md).  
  
## <a name="post-deployment-action-example"></a>Dağıtım sonrası eylemi örneği  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir `postAction` kullanılarak dağıtılan Office çözümü için bir uygulama bildirimi öğesinde [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kod  
  
```  
<vstav3:postAction>  
  <vstav3:entryPoint   
    class="PostDeploymentAction.PostDeploymentActionSample">  
    <assemblyIdentity   
      name="PostDeploymentAction"   
      version="1.0.0.0"   
      language="neutral"   
      processorArchitecture="msil" />  
  </vstav3:entryPoint>  
  <vstav3:postActionData>  
  </vstav3:postActionData>  
</vstav3:postAction>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama Bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
  
  