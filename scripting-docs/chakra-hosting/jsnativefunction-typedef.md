---
title: Jsnativefunction tür | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 56ef6cdf-4ca9-4f7c-b953-e661addb1a8e
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 33cf475dd6a17434ea132647b7d8bde833f0de9e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788324"
---
# <a name="jsnativefunction-typedef"></a>JsNativeFunction Tür Tanımı
Bir işlev geri çağırma.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef _Ret_maybenull_ JsValueRef (CALLBACK * JsNativeFunction)(  
   _In_ JsValueRef callee,  
   _In_ bool isConstructCall,  
   _In_ JsValueRef *arguments,  
   _In_ unsigned short argumentCount  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 çağırılan  
 Çağırılan işlevi temsil eden bir `Function` nesnesi.  
  
 isConstructCall  
 Bunun normal bir çağrı mı yoksa 'yeni' bir çağrı mı olduğunu gösterir.  
  
 bağımsız değişkenler  
 Arama için bağımsız değişkenler.  
  
 Bağımsız Değişken Sayısı  
 Bağımsız değişkenlerin sayısı  
  
## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 Varsa çağrı sonucunu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)