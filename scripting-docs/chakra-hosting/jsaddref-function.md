---
title: JsAddRef işlevi | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsAddRef
helpviewer_keywords:
- JsAddRef function
ms.assetid: a7f3ed49-6a86-489a-abdf-c99428e79cae
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8e55ab6643dd949b8b41962161f76648dba926e8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788189"
---
# <a name="jsaddref-function"></a>JsAddRef İşlevi
Çöp toplanan nesnesine bir başvuru ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsAddRef(  
   _In_ JsRef ref,  
   _Out_opt_ unsigned int *count  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ref`  
 Bir başvuru eklenecek nesne.  
  
 `count`  
 Nesnenin yeni (boş değer geçirebilirsiniz) sayısı başvuru.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yalnızca üzerinde çağrılması gereken `JsRef` yığında yere depolanması için yapmayacağınız işler. Çağırma `JsAddRef` nesne sağlar `JsRef` başvurduğu kadar serbest bırakılmaz `JsRelease` olarak adlandırılır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)