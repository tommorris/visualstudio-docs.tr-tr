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
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 048ad687b8754d09bd1e217e49bee2898d7791e3
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
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
  
  