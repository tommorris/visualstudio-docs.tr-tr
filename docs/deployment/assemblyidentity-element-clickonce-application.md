---
title: '&lt;assemblyIdentity&gt; öğesi (ClickOnce uygulaması) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assemblyIdentity
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assemblyIdentity> element [ClickOnce application manifest]
ms.assetid: f48e9531-efac-4d11-8166-f63a5ece1ac5
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 86a9aedcd3f21d4dbc1cc4f09106421542b188f8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ltassemblyidentitygt-element-clickonce-application"></a>&lt;assemblyIdentity&gt; öğesi (ClickOnce uygulaması)
Dağıtılan uygulamayı tanımlayan bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      <assemblyIdentity   
   name  
   version  
   publicKeyToken  
   processorArchitecture  
   language  
/>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `assemblyIdentity` Öğesi gereklidir. Hiçbir alt öğeleri içerir ve aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Name`|Gerekli. Uygulamanın adını tanımlar.<br /><br /> Varsa `Name` özel karakterler içeren tek veya çift tırnak gibi etkinleştirmek uygulama başarısız olabilir.|  
|`Version`|Gerekli. Uygulamanın sürüm numarasını şu biçimde belirtir: `major.minor.build.revision`|  
|`publicKeyToken`|İsteğe bağlı. Son 8 baytını temsil eden bir 16 karakter onaltılık dize belirtir `SHA-1` karma altında uygulama imzalanan derleme veya ortak anahtar değeri. Kataloğu imzalamak için kullanılan ortak anahtar 2048 bit olmalı veya daha büyük.<br /><br /> Derleme imzalamayı önerilir ancak isteğe bağlı olsa da, bu öznitelik gereklidir. Bir derlemeyi imzalı değilse, bir değer otomatik olarak imzalanan bir derlemeden kopyalamak ya da sıfırlardan "kukla" değeri kullanın.|  
|`processorArchitecture`|Gerekli. İşlemci belirtir. Geçerli değerler `msil` tüm işlemciler için `x86` 32-bit Windows için `IA64` 64-bit Windows için ve `Itanium` Intel 64-bit Itanium işlemcilere için.|  
|`language`|Gerekli. İki parçalı dil kodlarını tanımlar (örneğin, `en-US`) derlemenin. Bu öğe `asmv2` ad alanı. Belirtilmezse, varsayılan değer `neutral`.|  
  
## <a name="examples"></a>Örnekler  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir bir `assemblyIdentity` öğesinde bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirimi. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [ClickOnce Uygulama bildirimi](../deployment/clickonce-application-manifest.md).  
  
### <a name="code"></a>Kod  
  
```  
<asmv1:assemblyIdentity   
  name="My Application Deployment.exe"   
  version="1.0.0.0"   
  publicKeyToken="43cb1e8e7a352766"   
  language="neutral"   
  processorArchitecture="x86"   
  type="win32" />  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Uygulama bildirimi](../deployment/clickonce-application-manifest.md)   
 [\<assemblyIdentity > öğesi](../deployment/assemblyidentity-element-clickonce-deployment.md)