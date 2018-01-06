---
title: "&lt;vstoRuntime&gt; öğesi (Visual Studio'da Office Geliştirme) | Microsoft Docs"
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
- application manifests [Office development in Visual Studio], <vstoRuntime> element
- <vstoRuntime> element
- vstoRuntime element
ms.assetid: e59a8a61-9ff2-4032-9983-4a1e289e70a7
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 13f5517e0bde4d5881acaf89640b01509cf19eb8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ltvstoruntimegt-element-office-development-in-visual-studio"></a>&lt;vstoRuntime&gt; öğesi (Visual Studio'da Office Geliştirme)
  `vstoRuntime` Öğesinin `vstav3` ad alanı, belirli bir Office çözümü için Office çalışma zamanı için Visual Studio Araçları desteklenen bir sürümünü içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<vstoRuntime  
    release  
    version  
    supportUrl />  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `vstoRuntime` Öğesi gereklidir ve yer `vstav3` ad alanı. Office çözümünü Office çalışma zamanı için Visual Studio Araçları iki sürümlerini destekliyorsa, var olan iki `vstoRuntime` uygulama bildiriminde öğeleri.  
  
 `vstoRuntime` Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`release`|Gerekli. Office çalışma zamanı için Visual Studio Araçları'nın sürümü.|  
|`version`|Gerekli. Office çalışma zamanı için Visual Studio Araçları sürüm numarası.|  
|`supportUrl`|İsteğe bağlı. Office çalışma zamanı için Visual Studio Araçları yükleme konumunu bağlayın.|  
  
 `vstoRuntime`hiç öğe yok.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği gösterilmektedir `vstoRuntime` kullanılarak dağıtılan Office çözümü için bir uygulama bildirimi öğesinde [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
```  
<vstav3:vstoRuntime  
    release="VSTOR40Beta1"  
    version="10.0.20303"  
    supportUrl="http://www.microsoft.com" />  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama Bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
  
  