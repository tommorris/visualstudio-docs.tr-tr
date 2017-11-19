---
title: "Jsıdle işlevi | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsIdle
helpviewer_keywords: JsIdle function
ms.assetid: 372d1c62-8e19-4886-aa33-364cabc09bba
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ddffd4f37c0e10985a2dbca26558d8a94b21b2f7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jsidle-function"></a>JsIdle İşlevi
Yapmanız gereken herhangi bir boşta işlem yapmak için çalışma zamanı söyler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsIdle(  
   _Out_opt_ unsigned int *nextIdleTick  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nextIdleTick`  
 Olacaktır olduğunda yapmak için daha fazla boşta iş sonraki sistem değer çizgilerinin. Null olabilir. Burada ise çizgilerine üst sınırını Hayır yaklaşan döndürür boşta yapmak için çalışır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Boşta işleme için geçerli çalışma zamanı etkinleştirilmişse çağırma `JsIdle` geçerli çalışma zamanının konak boşta ve çalışma zamanı bellek temizleme görevlerini gerçekleştirebilir size bildirir.  
  
 `JsIdle`Ayrıca olacaktır kadar yapmak çalışma zamanı için daha fazla boşta iş sayısı sistem geri dönebilirsiniz. Çağırma `JsIdle` çizgilerine sayısı geçti önce hiçbir iş yapar.  
  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)