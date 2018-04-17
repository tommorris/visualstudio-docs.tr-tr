---
title: '&lt;derleme&gt; öğesi (ClickOnce uygulaması) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assembly
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assembly> element [ClickOnce application manifest]
ms.assetid: 51410569-10f9-4c0a-96b5-d39185edbefc
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 58d169ff230b5b6e5dd93190190d9a15beec2f14
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ltassemblygt-element-clickonce-application"></a>&lt;derleme&gt; öğesi (ClickOnce uygulaması)
Uygulama bildirimi için üst düzey öğesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      <assembly  
   manifestVersion  
/>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `assembly` Öğesi kök öğe ve gereklidir. İçinde ilk öğe olmalıdır bir `assemblyIdentity` öğesi. Bildirim öğeleri şu ad alanlarından birinde olmalıdır:  
  
 `urn:schemas-microsoft-com:asm.v1`  
  
 `urn:schemas-microsoft-com:asm.v2`  
  
 `http://www.w3.org/2000/09/xmldsig#`  
  
 Bütünleştirilmiş kodun alt öğeleri de kalıtım veya etiketleme yoluyla bu ad alanları olması gerekir.  
  
 `assembly` Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`manifestVersion`|Gerekli. `manifestVersion` Özniteliği ayarlanmalıdır `1.0`.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği gösterilmektedir bir `assembly` için bir uygulama bildirimi öğesinde bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [ClickOnce Uygulama bildirimi](../deployment/clickonce-application-manifest.md).  
  
```  
<asmv1:assembly   
  xsi:schemaLocation="urn:schemas-microsoft-com:asm.v1 assembly.adaptive.xsd"   
  manifestVersion="1.0"   
  xmlns:asmv3="urn:schemas-microsoft-com:asm.v3"  
  xmlns:dsig=http://www.w3.org/2000/09/xmldsig#  
  xmlns:co.v2="urn:schemas-microsoft-com:clickonce.v2"  
  xmlns="urn:schemas-microsoft-com:asm.v2"  
  xmlns:asmv1="urn:schemas-microsoft-com:asm.v1"  
  xmlns:asmv2="urn:schemas-microsoft-com:asm.v2"  
  xmlns:xsi=http://www.w3.org/2001/XMLSchema-instance  
  xmlns:co.v1="urn:schemas-microsoft-com:clickonce.v1">  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Uygulama bildirimi](../deployment/clickonce-application-manifest.md)   
 [\<Assembly > öğesi](../deployment/assembly-element-clickonce-deployment.md)