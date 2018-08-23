---
title: '&lt;publisherIdentity&gt; öğesi (ClickOnce dağıtımı) | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publisherIdentity Element [ClickOnce deployment manifest], introduction
- required element for signed manifests [ClickOnce], publisherIdentity Element
- publisherIdentity Element [ClickOnce deployment manifest], syntax, elements, and attributes
ms.assetid: 34c579db-d2f2-4b66-b9c8-47207f33d950
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 4c11e8ed9a3e0b4341708fc849462fbc476dc395
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42697271"
---
# <a name="ltpublisheridentitygt-element-clickonce-deployment"></a>&lt;publisherIdentity&gt; öğesi (ClickOnce dağıtımı)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ &lt;publisherIdentity&gt; öğesi (ClickOnce dağıtımı)](https://docs.microsoft.com/visualstudio/deployment/publisheridentity-element-clickonce-deployment).  
  
Bu dağıtım bildirimi imzalayan yayımcı hakkında bilgi içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<publisherIdentity  
   name  
   issuerKeyHash  
/>  
```  
  
## <a name="elements-and-attributes"></a>Öğeler ve öznitelikler  
 `publisherIdentity` Öğesi imzalı bildirimler için gereklidir. Aşağıdaki tabloda, öznitelikleri gösterir `publisherIdentity` öğeyi destekler.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`name`|Gerekli. Bu uygulamayı yayımlayan taraf kimliğini açıklar.|  
|`issuerKeyHash`|Gerekli. Ortak anahtar sertifika verenin SHA-1 karması içerir.|  
  
#### <a name="parameters"></a>Parametreler  
  
## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
  
## <a name="exceptions"></a>Özel Durumlar  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="requirements"></a>Gereksinimler  
  
## <a name="subhead"></a>Alt başlık



