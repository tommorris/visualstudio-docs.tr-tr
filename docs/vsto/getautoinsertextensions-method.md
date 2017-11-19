---
title: "Getautoınsertextensions yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
ms.assetid: 78388cce-7aae-4163-8db5-ce00d0a0c331
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1d222f7b6751381ceb4ebdb27bb6a6bf223616df
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
  
  