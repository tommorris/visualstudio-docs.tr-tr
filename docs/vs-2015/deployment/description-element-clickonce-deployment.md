---
title: '&lt;Açıklama&gt; öğesi (ClickOnce dağıtımı) | Microsoft Docs'
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
- urn:schemas-microsoft-com:asm.v2#description
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <description> element [ClickOnce deployment manifest]
ms.assetid: 18f6919e-a3ab-4942-a57d-167fabfac44e
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 473ebf814ab65c34ee99cab0cf2cc239e0d013eb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633263"
---
# <a name="ltdescriptiongt-element-clickonce-deployment"></a>&lt;Açıklama&gt; öğesi (ClickOnce dağıtımı)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ &lt;açıklama&gt; öğesi (ClickOnce dağıtımı)](https://docs.microsoft.com/visualstudio/deployment/description-element-clickonce-deployment).  
  
Bir kabuk varlığı oluşturmak için kullanılan uygulama bilgilerini tanımlar ve bir **Program Ekle veya Kaldır** Denetim Masası'ndaki öğesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      <description   
   publisher   
   product  
   suiteName  
   supportUrl  
/>  
```  
  
## <a name="elements-and-attributes"></a>Öğeler ve öznitelikler  
 `description` Öğesi gereklidir ve içinde `urn:schemas-microsoft-com:asm.v1` ad alanı. Alt öğe içerir ve aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`publisher`|Gerekli. Windows simge yerleşimi için kullanılan şirket adını tanımlayan **Başlat** menü ve **Program Ekle veya Kaldır** Denetim Masası, yükleme için dağıtım yapılandırıldığında.|  
|`product`|Gerekli. Tam ürün adını tanımlar. Windows yüklü simgesi başlığı olarak kullanılan **Başlat** menüsü.|  
|`suiteName`|İsteğe bağlı. Bir alt klasörde tanımlayan `publisher` Windows klasöründe **Başlat** menüsü.|  
|`supportUrl`|İsteğe bağlı. Gösterilen destek URL'sini belirtir **Program Ekle veya Kaldır** Denetim Masası'ndaki öğesi. Windows uygulama desteği için bu URL için bir kısayol da oluşturulur **Başlat** dağıtım yüklemesi için yapılandırıldığında menüsü.|  
  
## <a name="remarks"></a>Açıklamalar  
 Description öğesi tüm dağıtım yapılandırmaları gerekir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde gösterilmiştir bir `description` öğesinde bir [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] dağıtım bildirimi. Bu kod örneği için sağlanan daha büyük bir örneğin parçasıdır [ClickOnce dağıtım bildirimi](../deployment/clickonce-deployment-manifest.md) konu.  
  
```  
<description   
  asmv2:publisher="My Company Name"  
  asmv2:product="My Application"  
  xmlns="urn:schemas-microsoft-com:asm.v1" />  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Dağıtım Bildirimi](../deployment/clickonce-deployment-manifest.md)



