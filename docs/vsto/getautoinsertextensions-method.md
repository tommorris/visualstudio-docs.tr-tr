---
title: Getautoınsertextensions yöntemi | Microsoft Docs
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
ms.openlocfilehash: 67f6bfcb0ee38acf9abb604f28fa95eeaa605fde
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="getautoinsertextensions-method"></a>GetAutoInsertExtensions Metodu
  Hata ayıklama sırasında otomatik olarak eklenmesini olan Office için uygulamalar hakkındaki bilgileri alır.  
  
 Bu yöntem, gelecekte kullanılmak üzere ayrılmış.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetAutoInsertExtensions(  
    [out, retval] SAFEARRAY(BSTR)* psaExtensionNames  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*psaExtensionNames*|Office uygulamaları uzantısı adlarını.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yöntemi başarıyla tamamlanmış olup olmadığını belirten bir HRESULT değer.  
  
## <a name="remarks"></a>Açıklamalar  
 Her uygulama için eklenecek Office HKEY_CURRENT_USER\Software\Microsoft\Office\WEF\Developer altındaki bir değere karşılık gelen bir Office uygulaması uzantı adı olarak döndürülür. Konak, bu kayıt defteri değerlerini aramak ve uzantıları otomatik olarak ekler.  
  
  