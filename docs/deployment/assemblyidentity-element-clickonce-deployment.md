---
title: "&lt;assemblyIdentity&gt; öğesi (ClickOnce dağıtımı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: urn:schemas-microsoft-com:asm.v2#assemblyIdentity
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords: <assemblyIdentity> element [ClickOnce deployment manifest]
ms.assetid: f4a3bb83-c800-47d0-9905-9a5ae2486838
caps.latest.revision: "23"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 51643b8db91c9f8c2961b319d47cdfb7789f6a4d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ltassemblyidentitygt-element-clickonce-deployment"></a>&lt;assemblyIdentity&gt; öğesi (ClickOnce dağıtımı)
Birincil derlemenin tanımlayan [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      <assemblyIdentity    
   name   
   version  
   publicKeyToken  
   processorArchitecture  
    type  
/>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `assemblyIdentity` Öğesi gereklidir. Hiçbir alt öğeleri içerir ve aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`name`|Gerekli. Bilgilendirme amaçlı okunabilir dağıtım adını tanımlar.<br /><br /> Varsa `name` özel karakterler içeren tek veya çift tırnak gibi etkinleştirmek uygulama başarısız olabilir.|  
|`version`|Gerekli. Şu biçimde derleme sürüm numarasını belirtir: `major.minor.build.revision`.<br /><br /> Bu değer, bir uygulama güncelleştirmesini tetiklemek için güncelleştirilmiş bir bildiriminde artırılır gerekir.|  
|`publicKeyToken`|Gerekli. Son 8 bayt altında dağıtım bildirimi imzalanan ortak anahtarı SHA-1 karma değeri temsil eden 16 karakter onaltılık dizeyi belirtir. İmzalamak için kullanılan ortak anahtar 2048 bit olmalı veya daha büyük.<br /><br /> Derleme imzalamayı önerilir ancak isteğe bağlı olsa da, bu öznitelik gereklidir. Bir derlemeyi imzalı değilse, bir değer otomatik olarak imzalanan bir derlemeden kopyalamak ya da sıfırlardan "kukla" değeri kullanın.|  
|`processorArchitecture`|Gerekli. İşlemci belirtir. Geçerli değerler `msil` tüm işlemciler için `x86` 32-bit Windows için `IA64` 64-bit Windows için ve `Itanium` Intel 64-bit Itanium işlemcilere için.|  
|`type`|Gerekli. Windows yan yana yükleme teknolojisi ile uyumluluk için. Yalnızca izin verilen değer `win32`.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği gösterilmektedir bir `assemblyIdentity` öğesinde bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım bildirimi. Bu kod örneği için sağlanan daha büyük bir örneğin parçasıdır [ClickOnce dağıtım bildirimi](../deployment/clickonce-deployment-manifest.md) konu.  
  
```  
<!-- Identify the deployment. -->  
<assemblyIdentity   
  name="My Application Deployment.app"  
  version="1.0.0.0"  
  publicKeyToken="43cb1e8e7a352766"  
  language="neutral"  
  processorArchitecture="x86"  
  xmlns="urn:schemas-microsoft-com:asm.v1" />  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce dağıtım bildirimi](../deployment/clickonce-deployment-manifest.md)   
 [\<assemblyIdentity > öğesi](../deployment/assemblyidentity-element-clickonce-application.md)