---
title: "&lt;customErrorReporting&gt; öğesi (ClickOnce dağıtımı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords: <customErrorReporting> element [ClickOnce deployment manifest]
ms.assetid: 7d31816e-c692-46b5-9cc9-753284b3bcda
caps.latest.revision: "6"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 238e4c0c0fe9021424b48963eac7d21bf6f9a049
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="ltcustomerrorreportinggt-element-clickonce-deployment"></a>&lt;customErrorReporting&gt; öğesi (ClickOnce dağıtımı)
Bir hata oluştuğunda göstermek için bir URI belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<customErrorReporting  
   uri  
/>  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu öğe isteğe bağlıdır. Bu olmadan, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] özel durum yığını gösteren bir hata iletişim kutusu görüntüler. Varsa `customErrorReporting` öğesi mevcutsa, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] tarafından gösterilen URI'yi bunun yerine görüntülenir `uri` parametresi. Hedef URI parametreleri olarak dış özel durum sınıfı, iç özel durum sınıfı ve iç özel durum iletisi içerir.  
  
 Hata Raporlama işlevselliği, uygulamanıza eklemek için bu öğeyi kullanın. Üretilen URI hata türü ile ilgili bilgi içeren olduğundan, Web sitenizi bilgileri ve görüntüyü, örneğin, uygun bir sorun giderme ekranı ayrıştıramıyor.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod parçacığında gösterildiği `customErrorReporting` onu verebilir üretilen URI ile birlikte öğesi.  
  
```  
<customErrorReporting uri=http://www.contoso.com/applications/error.asp />  
  
Example Generated Error:  
http://www.contoso.com/applications/error.asp? outer=System.Deployment.Application.InvalidDeploymentException&&inner=System.Deployment.Application.InvalidDeploymentException&&msg=The%20application%20manifest%20is%20signed,%20but%20the%20deployment%20manifest%20is%20unsigned.%20Both%20manifests%20must%20be%20either%20signed%20or%20unsigned.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce dağıtım bildirimi](../deployment/clickonce-deployment-manifest.md)