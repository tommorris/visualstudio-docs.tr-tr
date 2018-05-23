---
title: Getautoınsertextensions yöntemi
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f8573576b40afabb5ec568a0c471e7b1d79560ba
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="getautoinsertextensions-method"></a>Getautoınsertextensions yöntemi
  Hata ayıklama sırasında otomatik olarak eklenmesini olan Office için uygulamalar hakkındaki bilgileri alır.  
  
 Bu yöntem, gelecekte kullanılmak üzere ayrılmış.  
  
## <a name="syntax"></a>Sözdizimi  
  
```c  
HRESULT GetAutoInsertExtensions(  
    [out, retval] SAFEARRAY(BSTR)* psaExtensionNames  
);  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*psaExtensionNames*|Office uygulamaları uzantısı adlarını.|  
  
## <a name="return-value"></a>Dönüş değeri  
 Yöntemi başarıyla tamamlanmış olup olmadığını belirten bir HRESULT değer.  
  
## <a name="remarks"></a>Açıklamalar  
 Her uygulama için eklenecek Office bir değere karşılık gelen bir Office uygulaması uzantı adı olarak döndürülür **HKEY_CURRENT_USER\Software\Microsoft\Office\WEF\Developer**. Konak, bu kayıt defteri değerlerini aramak ve uzantıları otomatik olarak ekler.  
  
  