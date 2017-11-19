---
title: "&lt;Açıklama&gt; öğesi (ClickOnce dağıtımı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: urn:schemas-microsoft-com:asm.v2#description
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords: <description> element [ClickOnce deployment manifest]
ms.assetid: 18f6919e-a3ab-4942-a57d-167fabfac44e
caps.latest.revision: "19"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 41fd9fcee2d0ae954f5ec234bf23cbefd5ccd6da
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="ltdescriptiongt-element-clickonce-deployment"></a>&lt;Açıklama&gt; öğesi (ClickOnce dağıtımı)
Kabuk varlığı oluşturmak için kullanılan uygulama bilgilerini tanımlar ve bir **Program Ekle veya Kaldır** Denetim Masası.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      <description   
   publisher   
   product  
   suiteName  
   supportUrl  
/>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `description` Öğesi gereklidir ve yer `urn:schemas-microsoft-com:asm.v1` ad alanı. Hiçbir alt öğeleri içerir ve aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`publisher`|Gerekli. Windows simge yerleşimi için kullanılan şirket adını tanımlar **Başlat** menü ve **Program Ekle veya Kaldır** dağıtım yükleme için yapılandırıldığında, Denetim Masası,.|  
|`product`|Gerekli. Tam ürün adını tanımlar. Windows'ta yüklü simgesi için başlık olarak kullanılan **Başlat** menüsü.|  
|`suiteName`|İsteğe bağlı. İçinde bir alt tanımlayan `publisher` Windows klasöründe **Başlat** menüsü.|  
|`supportUrl`|İsteğe bağlı. Gösterilen destek URL'sini belirtir **Program Ekle veya Kaldır** Denetim Masası. Bu URL için bir kısayol ayrıca Windows uygulama desteği için oluşturulan **Başlat** dağıtım yükleme için yapılandırıldığında, menüsü.|  
  
## <a name="remarks"></a>Açıklamalar  
 Description öğesi tüm dağıtım yapılandırmaları gerekir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği gösterilmektedir bir `description` öğesinde bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım bildirimi. Bu kod örneği için sağlanan daha büyük bir örneğin parçasıdır [ClickOnce dağıtım bildirimi](../deployment/clickonce-deployment-manifest.md) konu.  
  
```  
<description   
  asmv2:publisher="My Company Name"  
  asmv2:product="My Application"  
  xmlns="urn:schemas-microsoft-com:asm.v1" />  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce dağıtım bildirimi](../deployment/clickonce-deployment-manifest.md)