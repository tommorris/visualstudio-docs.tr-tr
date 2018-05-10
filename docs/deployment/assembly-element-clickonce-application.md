---
title: '&lt;derleme&gt; öğesi (ClickOnce uygulaması) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assembly
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assembly> element [ClickOnce application manifest]
ms.assetid: 51410569-10f9-4c0a-96b5-d39185edbefc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1c72dd684092784c88b1ef6dd76d410ac9ff84d5
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
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
  
## <a name="see-also"></a>Ayrıca bkz.  
 [ClickOnce Uygulama bildirimi](../deployment/clickonce-application-manifest.md)   
 [\<Assembly > öğesi](../deployment/assembly-element-clickonce-deployment.md)
