---
title: JsSerializeScript işlevi | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSerializeScript
helpviewer_keywords:
- JsSerializeScript function
ms.assetid: ca42c194-e1c1-407d-b542-b9d494e3ac4e
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 92bc6c1de0f2cd43dfe9566413fb64188fd5a382
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788561"
---
# <a name="jsserializescript-function"></a>JsSerializeScript İşlevi
Yeniden kullanılabilir daha ayrıştırılmış bir komut dosyası bir arabelleğe serileştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsSerializeScript(  
   _In_z_ const wchar_t *script,  
   _Out_writes_to_opt_(*bufferSize,  
   *bufferSize) BYTE *buffer,  
   _Inout_ unsigned long *bufferSize  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `script`  
 Seri hale getirmek için komut dosyası.  
  
 `buffer`  
 Serileştirilmiş betiğe put arabelleği. Null olabilir.  
  
 `bufferSize`  
 Girişte arabelleğin bayt cinsinden boyutu; Çıkışta serileştirilmiş betik tutmak için gereken bayt cinsinden arabellek boyutu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 `JsSerializeScript`bir komut dosyası ayrıştırır ve ardından komut dosyasının ayrıştırılmış form bir çalışma zamanı bağımsız biçimde depolar. Serileştirilmiş betik sonra tüm çalışma zamanında yeniden ayrıştırılmış olması için komut dosyası gerek kalmadan seri durumdan çıkarılabiliyorsa.  
  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)