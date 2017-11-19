---
title: "İşlevi (hata ayıklama arabirimi Erişim SDK'sı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Function symbol
ms.assetid: 458dc91c-b78b-4427-84f4-615d89e26760
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 39d3871fcfbd3702e2ad198f2061be41dc51ac18
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="function-debug-interface-access-sdk"></a>İşlev (Arabirim Erişimi SDK'sında Hata Ayıklama)
Her işlevi tarafından tanımlanan bir `SymTagFunction` simgesi.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda bu simge türü için geçerli olan özellikleri gösterir.  
  
|Özellik|`Data type`|Açıklama|  
|--------------|-----------------|-----------------|  
|[Idiasymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)|`DWORD`|Değerlerden [CV_access_e numaralandırması](../../debugger/debug-interface-access/cv-access-e.md), üye işlevi işlevdir.|  
|[Idiasymbol::get_addressoffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|Uzaklık bölümü konumunun; Ayrıntılar için bkz [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_addresssection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|`DWORD`|Konum, bölüm parçası; Ayrıntılar için bkz [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_classparent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|İşlev üye işlevi ise sınıfı simgesi.|  
|[Idiasymbol::get_classparentıd](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|Sınıf üst simge kimliği.|  
|[Idiasymbol::get_consttype](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE`Eğer işlevi bir sabit değer olarak işaretlenmiş.|  
|[Idiasymbol::get_customcallingconvention](../../debugger/debug-interface-access/idiasymbol-get-customcallingconvention.md)|`BOOL`|`TRUE`işlev özel bir çağırma kuralı (yalnızca DIA SDK V8.0 veya sonrası) kullanıyorsa.|  
|[Idiasymbol::get_farreturn](../../debugger/debug-interface-access/idiasymbol-get-farreturn.md)|`BOOL`|`TRUE`işlev kadar dönüş (yalnızca DIA SDK V8.0 veya sonrası) uyguluyorsa.|  
|[Idiasymbol::get_hasalloca](../../debugger/debug-interface-access/idiasymbol-get-hasalloca.md)|`BOOL`|`TRUE`bir işlev ayrılmış bellek işlevi kullanıyorsa (yalnızca uinnder DIA SDK V8.0 veya üstü).|  
|[Idiasymbol::get_haseh](../../debugger/debug-interface-access/idiasymbol-get-haseh.md)|`BOOL`|`TRUE`işlev stili C++ özel durum (yalnızca DIA SDK V8.0 veya sonrası) işleme içeriyorsa.|  
|[Idiasymbol::get_haseha](../../debugger/debug-interface-access/idiasymbol-get-haseha.md)|`BOOL`|`TRUE`işlevi (yalnızca DIA SDK V8.0 veya sonrası) zaman uyumsuz özel durum işleme içeriyorsa.|  
|[Idiasymbol::get_hasınlasm](../../debugger/debug-interface-access/idiasymbol-get-hasinlasm.md)|`BOOL`|`TRUE`işlev satır içi derleme (yalnızca DIA SDK V8.0 veya sonrası) içeriyorsa.|  
|[Idiasymbol::get_haslongjump](../../debugger/debug-interface-access/idiasymbol-get-haslongjump.md)|`BOOL`|`TRUE`işlev içeriyorsa bir [longjmp](/cpp/c-runtime-library/reference/longjmp) (yalnızca DIA SDK V8.0 veya sonrası) çağırın.|  
|[Idiasymbol::get_hassecuritychecks](../../debugger/debug-interface-access/idiasymbol-get-hassecuritychecks.md)|`BOOL`|`TRUE`işlev güvenlik denetimlerini (yalnızca DIA SDK V8.0 veya sonrası) içeriyorsa.|  
|[Idiasymbol::get_hasseh](../../debugger/debug-interface-access/idiasymbol-get-hasseh.md)|`BOOL`|`TRUE`işlev Win32 stili yapılandırılmış özel durum (yalnızca DIA SDK V8.0 veya sonrası) işleme içeriyorsa.|  
|[Idiasymbol::get_hassetjump](../../debugger/debug-interface-access/idiasymbol-get-hassetjump.md)|`BOOL`|`TRUE`işlev içeriyorsa bir [setjmp](/cpp/c-runtime-library/reference/setjmp) (yalnızca DIA SDK V8.0 veya sonrası) çağırın.|  
|[Idiasymbol::get_interruptreturn](../../debugger/debug-interface-access/idiasymbol-get-interruptreturn.md)|`BOOL`|`TRUE`işlevi bir dönüş kesme (yalnızca DIA SDK V8.0 veya sonrası) varsa.|  
|[Idiasymbol::get_intro](../../debugger/debug-interface-access/idiasymbol-get-intro.md)|`BOOL`|`TRUE`bir işlev giriş sanal ise.|  
|[Idiasymbol::get_ınlspec](../../debugger/debug-interface-access/idiasymbol-get-inlspec.md)|`BOOL`|`TRUE`işlev biri ile işaretlendiyse [satır içi, __inline, \__forceinline](/cpp/cpp/inline-functions-cpp.md) öznitelikleri.|  
|[Idiasymbol::get_isnaked](../../debugger/debug-interface-access/idiasymbol-get-isnaked.md)|`BOOL`|`TRUE`işlevi ile işaretlenmişse [naked](/cpp/cpp/naked-cpp) özniteliği (yalnızca DIA SDK V8.0 veya üzeri).|  
|[Idiasymbol::get_isstatic](../../debugger/debug-interface-access/idiasymbol-get-isstatic.md)|`BOOL`|`TRUE`(işlevi yalnızca DIA SDK V8.0 veya sonrası) statik ise.|  
|[Idiasymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`ULONGLONG`|İşlev kodunun, konumundan başlayarak bayt sayısı.|  
|[Idiasymbol::get_lexicalparent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Kapsayan derlenecek dosya simgesi.|  
|[Idiasymbol::get_lexicalparentıd](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|Sözcük üst simge kimliği.|  
|[Idiasymbol::get_locationtype](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|İşlev statik veya meta veri konumları olabilir; Ayrıntılar için bkz [simge konumları](../../debugger/debug-interface-access/symbol-locations.md).|  
|[Idiasymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|İşlevin adı.|  
|[Idiasymbol::get_noınline](../../debugger/debug-interface-access/idiasymbol-get-noinline.md)|`BOOL`|`TRUE`işlev satır içi işlev değilse (yalnızca n DIA SDK V8.0 veya üstü).|  
|[Idiasymbol::get_notreached](../../debugger/debug-interface-access/idiasymbol-get-notreached.md)|`BOOL`|`TRUE`işlevi (yalnızca DIA SDK V8.0 veya sonrası) erişilebilir durumda değilse.|  
|[Idiasymbol::get_noreturn](../../debugger/debug-interface-access/idiasymbol-get-noreturn.md)|`BOOL`|`TRUE`işlevi (yalnızca DIA SDK V8.0 içinde veya üstü) bir değer döndürmezse.|  
|[Idiasymbol::get_nostackordering](../../debugger/debug-interface-access/idiasymbol-get-nostackordering.md)|`BOOL`|`TRUE`işlev arabellek güvenlik denetimleri ile derlenen ancak hiçbir yığın sıralama yapılabilir değilse.|  
|[Idiasymbol::get_optimizedcodedebugınfo](../../debugger/debug-interface-access/idiasymbol-get-optimizedcodedebuginfo.md)|`BOOL`|`TRUE`kodu en iyi duruma getirilmiş kodu (yalnızca DIA SDK V8.0 veya sonrası) için hata ayıklama bilgileri varsa.|  
|[Idiasymbol::get_pure](../../debugger/debug-interface-access/idiasymbol-get-pure.md)|`BOOL`|`TRUE`işlev saf olup olmadığını sanal.|  
|[Idiasymbol::get_relativevirtualaddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|Bu işlev, modül içinde göreli konumunu.|  
|[Idiasymbol::get_symındexıd](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|Dizin kimliği simgesi.|  
|[Idiasymbol::get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Döndürür `SymTagFunction` (birini [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md) değerleri).|  
|[Idiasymbol::get_token](../../debugger/debug-interface-access/idiasymbol-get-token.md)|`DWORD`|İşlev için meta veri simgesi.|  
|[Idiasymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|İşlev imzası simgesi.|  
|[Idiasymbol::get_typeıd](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|Tür simgesi kimliği.|  
|[Idiasymbol::get_unalignedtype](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`işlev hizalanmamış ise.|  
|[Idiasymbol::get_undecoratedname](../../debugger/debug-interface-access/idiasymbol-get-undecoratedname.md)|`BSTR`|İşlev adı (yalnızca DIA SDK v8.0 veya sonrası) ve formu|  
|[Idiasymbol::get_undecoratednameex](../../debugger/debug-interface-access/idiasymbol-get-undecoratednameex.md)|`BSTR`|Kısmını veya tamamını işlev adı (yalnızca DIA SDK v8.0 veya sonrası) ve biçimidir.|  
|[Idiasymbol::get_virtual](../../debugger/debug-interface-access/idiasymbol-get-virtual.md)|`BOOL`|`TRUE`bir sanal işlev durumunda.|  
|[Idiasymbol::get_virtualaddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|Bu işlev yürütülebilir görüntü içindeki konumu.|  
|[Idiasymbol::get_virtualbaseoffset](../../debugger/debug-interface-access/idiasymbol-get-virtualbaseoffset.md)|`DWORD`|Bir sanal işlev, ardından sanal işlev tablosundaki uzaklığı.|  
|[Idiasymbol::get_volatiletype](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`Eğer işlevi geçici işaretlenmiş.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CV_access_e numaralandırması](../../debugger/debug-interface-access/cv-access-e.md)   
 [Simge türlerinin sözcük hiyerarşisi](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md)   
 [Simge konumları](../../debugger/debug-interface-access/symbol-locations.md)