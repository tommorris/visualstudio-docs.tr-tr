---
title: CV_CFL_LANG | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CV_CFL_LANG enumeration
ms.assetid: 4e8e0613-ad02-4de9-9f46-e4753c5b0251
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3ba4637baf2fa7aec7688648096cd34341442d05
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="cvcfllang"></a>CV_CFL_LANG
Uygulama veya bağlantılı modülü kaynak kod dilini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
typedef enum CV_CFL_LANG {   
   CV_CFL_C       = 0x00,  
   CV_CFL_CXX     = 0x01,  
   CV_CFL_FORTRAN = 0x02,  
   CV_CFL_MASM    = 0x03,  
   CV_CFL_PASCAL  = 0x04,  
   CV_CFL_BASIC   = 0x05,  
   CV_CFL_COBOL   = 0x06,  
   CV_CFL_LINK    = 0x07,  
   CV_CFL_CVTRES  = 0x08,  
   CV_CFL_CVTPGD  = 0x09,  
   CV_CFL_CSHARP  = 0x0A,  
   CV_CFL_VB      = 0x0B,  
   CV_CFL_ILASM   = 0x0C,  
   CV_CFL_JAVA    = 0x0D,  
   CV_CFL_JSCRIPT = 0x0E,  
   CV_CFL_MSIL    = 0x0F,  
   CV_CFL_HLSL    = 0x10  
} CV_CFL_LANG;  
```  
  
## <a name="elements"></a>Öğeleri  
 CV_CFL_C  
 C. uygulama dildir  
  
 CV_CFL_CXX  
 Uygulama, C++ dilidir.  
  
 CV_CFL_FORTRAN  
 Uygulama, FORTRAN dilidir.  
  
 CV_CFL_MASM  
 Uygulama, Microsoft makro derleyici dilidir.  
  
 CV_CFL_PASCAL  
 Uygulama, Pascal dilidir.  
  
 CV_CFL_BASIC  
 Uygulama, BASIC dilidir.  
  
 CV_CFL_COBOL  
 Uygulama, COBOL dilidir.  
  
 CV_CFL_LINK  
 Uygulama bir bağlayıcı tarafından oluşturulan bir modüldür.  
  
 CV_CFL_CVTRES  
 CVTRES aracıyla dönüştürülen bir kaynak modül uygulamasıdır.  
  
 CV_CFL_CVTPGD  
 Uygulama CVTPGD aracı ile oluşturulan bir en iyi duruma getirilmiş POGO modüldür.  
  
 CV_CFL_CSHARP  
 Uygulama C# dilidir.  
  
 CV_CFL_VB  
 Uygulama, Visual Basic dilidir.  
  
 CV_CFL_ILASM  
 Uygulama Ara dile derleme (diğer bir deyişle, ortak dil çalışma zamanı (CLR) derleme) dilidir.  
  
 CV_CFL_JAVA  
 Java uygulama dilidir.  
  
 CV_CFL_JSCRIPT  
 Uygulama, Jscript dilidir.  
  
 CV_CFL_MSIL  
 Uygulama dilidir bir bilinmeyen Microsoft Ara dili (MSIL), kullanarak büyük olasılıkla bir sonucu [/LTCG (bağlama zamanı kodu oluşturma)](/cpp/build/reference/ltcg-link-time-code-generation) geçin.  
  
 CV_CFL_HLSL  
 Uygulama, yüksek düzey gölgelendirici dil dilidir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu numaralandırma değerleri için yapılan bir çağrı tarafından döndürülen [Idiasymbol::get_language](../../debugger/debug-interface-access/idiasymbol-get-language.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: cvconst.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar ve yapılar](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_language](../../debugger/debug-interface-access/idiasymbol-get-language.md)