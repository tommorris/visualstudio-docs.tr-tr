---
title: Idiasymbol::get_undecoratednameex | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_undecoratedNameEx method
ms.assetid: 579aed0b-c57d-41a1-a94a-3bf665fd4a9d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d737ccfe9dbbcdf7a205fb847bb81344cd18ff0c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolgetundecoratednameex"></a>IDiaSymbol::get_undecoratedNameEx
Alır bölümünü veya tümünü bir C++ için ve bir ad (bağlantı) adı donatılmış.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_undecoratedNameEx(   
   DWORD undecorateOptions,  
   BSTR* pRetval  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `undecoratedOptions`  
 [in] Bayrak birleşimi ne döndürülür denetleyen belirtir. Belirli değerleri ve ne için Açıklamalar bölümüne bakın.  
  
 `pRetVal`  
 [out] C++ için ve ad ad donatılmış döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
> [!NOTE]
>  Dönüş değeri `S_FALSE` özelliğin simge için kullanılabilir olup olmadığı anlamına gelir.  
  
## <a name="remarks"></a>Açıklamalar  
 `undecorateOptions` Aşağıdaki bayraklar bir bileşimi olabilir.  
  
> [!NOTE]
>  Böylece kodunuzu bildirimi ekleyin ya da ham değerler kullanın gerek bayrağı adları DIA SDK içinde tanımlı değil.  
  
|Bayrağı|Değer|Açıklama|  
|----------|-----------|-----------------|  
|UNDNAME_COMPLETE|0x0000|Tam undecoration etkinleştirir.|  
|UNDNAME_NO_LEADING_UNDERSCORES|0x0001|Anahtar sözcükler genişletilmiş Microsoft'tan alt çizgi baştaki kaldırır.|  
|UNDNAME_NO_MS_KEYWORDS|0x0002|Anahtar sözcükler genişletilmiş Microsoft genişlemesi devre dışı bırakır.|  
|UNDNAME_NO_FUNCTION_RETURNS|0x0004|Genişletme birincil bildirimi için dönüş türü devre dışı bırakır.|  
|UNDNAME_NO_ALLOCATION_MODEL|0x0008|Genişletme bildirimi modelinin devre dışı bırakır.|  
|UNDNAME_NO_ALLOCATION_LANGUAGE|0x0010|Bildirim dil belirleyici genişlemesi devre dışı bırakır.|  
|UNDNAME_RESERVED1|0x0020|AYRILMIŞ.|  
|UNDNAME_RESERVED2|0x0040|AYRILMIŞ.|  
|UNDNAME_NO_THISTYPE|0x0060|Üzerindeki tüm değiştiricileri devre dışı bırakır `this` türü.|  
|UNDNAME_NO_ACCESS_SPECIFIERS|0x0080|Erişim tanımlayıcıları üyeleri için genişletilmesi devre dışı bırakır.|  
|UNDNAME_NO_THROW_SIGNATURES|0x0100|"Throw-imzaları" işlevler ve işlev işaretçileri genişlemesi devre dışı bırakır.|  
|UNDNAME_NO_MEMBER_TYPE|0x0200|Genişletme devre dışı bırakır `static` veya `virtual` üyeleri.|  
|UNDNAME_NO_RETURN_UDT_MODEL|0x0400|UDT döndürür Microsoft modelinin genişletme devre dışı bırakır.|  
|UNDNAME_32_BIT_DECODE|0x0800|32-bit düzenlenmiş adlar undecorates.|  
|UNDNAME_NAME_ONLY|0x1000|Yalnızca birincil bildirimi adını alır; yalnızca döndürür [kapsam::] adı.  Şablon parametreleri genişletir.|  
|UNDNAME_TYPE_ONLY|0x2000|Giriş kodlaması yalnızca bir türüdür; bir Özet bildirimcisi oluşturur.|  
|UNDNAME_HAVE_PARAMETERS|0x4000|Gerçek şablon parametreleri kullanılabilir.|  
|UNDNAME_NO_ECSU|0x8000|Enum/sınıfı/struct/union gizler.|  
|UNDNAME_NO_IDENT_CHAR_CHECK|0x10000|Geçerli bir tanımlayıcı karakterleri denetleme gizler.|  
|UNDNAME_NO_PTR64|0x20000|Ptr64 çıktısında içermez.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)