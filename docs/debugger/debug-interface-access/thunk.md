---
title: "Dönüştürücü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- thunk properties [DIA SDK]
- thunk symbol
ms.assetid: 01abb95f-d89a-465c-a4eb-8e8509598c95
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 514a0d7cea56158cbe15d59d2a809968b3c86979
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="thunk"></a>Dönüştürücü
Her `thunk` tarafından tanımlanan bir `SymTagThunk` etiketi.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda bu simge türü için geçerli olan özellikleri gösterir.  
  
|Özellik|Veri türü|Açıklama|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)|`DWORD`|Erişim değiştiricisi özniteliği, aşağıdakilerden birini [CV_access_e numaralandırması](../../debugger/debug-interface-access/cv-access-e.md) (yalnızca DIA SDK V8.0 veya değerleri daha sonra).|  
|[Idiasymbol::get_addressoffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|Uzaklık bölümü konumunun; Ayrıntılar için bkz [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasegment::get_addresssection](../../debugger/debug-interface-access/idiasegment-get-addresssection.md)|`DWORD`|Konum, bölüm parçası; Ayrıntılar için bkz [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_classparent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|Sınıf üst varsa (yalnızca DIA SDK V8.0 veya sonraki sürümlerinde) kapsayan.|  
|[Idiasymbol::get_classparentıd](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|Kimliği kapsayan sınıfı üst simgenin (yalnızca DIA SDK V8.0 veya üzeri).|  
|[Idiasymbol::get_consttype](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|Dönüştürücü (yalnızca DIA SDK V8.0 veya sonrası) sabit olarak işaretlenmiş ise TRUE.|  
|[Idiasymbol::get_intro](../../debugger/debug-interface-access/idiasymbol-get-intro.md)|`BOOL`|Dönüştürücü sanal işlev (yalnızca DIA SDK V8.0 içinde veya üstü) bir giriş ise TRUE|  
|[Idiasymbol::get_isstatic](../../debugger/debug-interface-access/idiasymbol-get-isstatic.md)|`BOOL`|Dönüştürücü (yalnızca DIA SDK V8.0 veya sonrası) statik kabul ediliyorsa TRUE.|  
|[Idiasymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`ULONGLONG`|Kod dönüştürücü bayt sayısı.|  
|[Idiasymbol::get_lexicalparent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Simge kapsayan derlenecek, blok veya işlevi için.|  
|[Idiasymbol::get_lexicalparentıd](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|Sözcük üst simge kimliği.|  
|[Idiasymbol::get_locationtype](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|Uç noktaları statik konumuna sahip; Ayrıntılar için bkz [simge konumları](../../debugger/debug-interface-access/symbol-locations.md) numaralandırması.|  
|[Idiasymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Dönüştürücü adı.|  
|[Idiasymbol::get_pure](../../debugger/debug-interface-access/idiasymbol-get-pure.md)|`BOOL`|(Dönüştürücü yalnızca DIA SDK V8.0 veya sonrası) tamamen sanal ise TRUE.|  
|[Idiasymbol::get_relativevirtualaddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|Bu dönüştürücü kendi modülü içinde göreli konumunu.|  
|[Idiasymbol::get_symındexıd](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|Dizin kimliği simgesi.|  
|[Idiasymbol::get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Döndürür `SymTagThunk` (birini [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md) değerleri).|  
|[Idiasymbol::get_targetoffset](../../debugger/debug-interface-access/idiasymbol-get-targetoffset.md)|`DWORD`|Dönüştürücü hedef konumu parçası uzaklık.|  
|[Idiasymbol::get_targetrelativevirtualaddress](../../debugger/debug-interface-access/idiasymbol-get-targetrelativevirtualaddress.md)|`DWORD`|Kendi kapsayan bloktaki dönüştürücü hedefinin göreli sanal adres.|  
|[Idiasymbol::get_targetsection](../../debugger/debug-interface-access/idiasymbol-get-targetsection.md)|`DWORD`|Dönüştürücü hedef bölüm bölümü.|  
|[Idiasymbol::get_targetvirtualaddress](../../debugger/debug-interface-access/idiasymbol-get-targetvirtualaddress.md)|`ULONGLONG`|Yürütülebilir görüntü dönüştürücü hedef konumu.|  
|[Idiasymbol::get_thunkordinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)|`DWORD`|Dönüştürücü türü tarafından tanımlanan [thunk_ordınal numaralandırması](../../debugger/debug-interface-access/thunk-ordinal.md).|  
|[Idiasymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|(Yalnızca DIA SDK V8.0 veya sonrası) Bu dönüştürücü türü.|  
|[Idiasymbol::get_typeıd](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|Tür simgesi (yalnızca DIA SDK V8.0 veya sonrası) kimliği.|  
|[Idiasymbol::get_unalignedtype](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`Dönüştürücü (yalnızca DIA SDK V8.0 veya daha sonra), hizalı değil|  
|[Idiasymbol::get_virtual](../../debugger/debug-interface-access/idiasymbol-get-virtual.md)|`BOOL`|`TRUE`(Dönüştürücü yalnızca DIA SDK V8.0 veya sonrası) sanal ise.|  
|[Idiasymbol::get_virtualaddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|Bu dönüştürücü yürütülebilir görüntü içindeki konumu.|  
|[Idiasymbol::get_virtualbaseoffset](../../debugger/debug-interface-access/idiasymbol-get-virtualbaseoffset.md)|`DWORD`|Bu dönüştürücü (yalnızca DIA SDK V8.0 veya sonrası) için sanal tablosundaki uzaklığı.|  
|[Idiasymbol::get_volatiletype](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`Dönüştürücü (yalnızca DIA SDK V8.0 veya sonrası) geçici işaretlenmişse.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Simge türlerinin sözcük hiyerarşisi](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md)   
 [Thunk_ordınal numaralandırması](../../debugger/debug-interface-access/thunk-ordinal.md)