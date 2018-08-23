---
title: '&lt;derleme&gt; öğesi (ClickOnce dağıtımı) | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assembly
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assembly> element [ClickOnce deployment manifest]
ms.assetid: b8e3362a-f821-4696-b98d-571d4bbfe431
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 96978ec8329ddf31b2cc641bf02d2b38a9e98f4a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675771"
---
# <a name="ltassemblygt-element-clickonce-deployment"></a>&lt;derleme&gt; öğesi (ClickOnce dağıtımı)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ &lt;derleme&gt; öğesi (ClickOnce dağıtımı)](https://docs.microsoft.com/visualstudio/deployment/assembly-element-clickonce-deployment).  
  
Dağıtım bildirimi için üst düzey öğe.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      <assembly    
   manifestVersion  
/>  
```  
  
## <a name="elements-and-attributes"></a>Öğeler ve öznitelikler  
 `assembly` Öğesi kök öğe ve gereklidir. Alt ilk bağımsız öğe olmalıdır bir `assemblyIdentity` öğesi. Bildirim öğeler aşağıdaki alanlarında olmalıdır: `urn:schemas-microsoft-com:asm.v1`, `urn:schemas-microsoft-com:asm.v2`, ve `http://www.w3.org/2000/09/xmldsig#`. Derlemenin alt öğeleri, bu ad alanlarında, devralma veya etiketleme tarafından da olması gerekir.  
  
 `assembly` Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`manifestVersion`|Gerekli. Bu öznitelik ayarlanmalıdır `1.0`.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde gösterilmiştir bir `assembly` kullanılarak dağıtılan bir uygulama için bir dağıtım bildirimi öğesinde [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]. Bu kod örneği için sağlanan daha büyük bir örneğin parçasıdır [ClickOnce dağıtım bildirimi](../deployment/clickonce-deployment-manifest.md) konu.  
  
```  
<asmv1:assembly   
  xsi:schemaLocation="urn:schemas-microsoft-com:asm.v1 assembly.adaptive.xsd"  
  manifestVersion="1.0"  
  xmlns:asmv3="urn:schemas-microsoft-com:asm.v3"  
  xmlns:dsig=http://www.w3.org/2000/09/xmldsig#  
  xmlns:co.v1="urn:schemas-microsoft-com:clickonce.v1"  
  xmlns:co.v2="urn:schemas-microsoft-com:clickonce.v2"  
  xmlns="urn:schemas-microsoft-com:asm.v2"  
  xmlns:asmv1="urn:schemas-microsoft-com:asm.v1"  
  xmlns:asmv2="urn:schemas-microsoft-com:asm.v2"  
  xmlns:xrml="urn:mpeg:mpeg21:2003:01-REL-R-NS"  
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce dağıtım bildirimi](../deployment/clickonce-deployment-manifest.md)   
 [\<derleme > öğesi](../deployment/assembly-element-clickonce-application.md)



