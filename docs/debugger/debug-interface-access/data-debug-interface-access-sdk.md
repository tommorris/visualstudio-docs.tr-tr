---
title: "Veriler (arabirim erişimi SDK'SINDA hata ayıklama) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- global variables [C++], as symbols
- local variables [C++], as symbols
- class members [C++], as symbols
- Data symbol
ms.assetid: 0f17e96a-2e06-42c9-a877-3e5e670ee0ef
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ea233e8bf26b3bbb9dd7b1e962e3729e172b5a7e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="data-debug-interface-access-sdk"></a>Veriler (Arabirim Erişimi SDK'sında Hata Ayıklama)
Parametreler, yerel değişkenleri, genel değişkenler ve sınıf üyeleri gibi tüm değişkenleri tarafından tanımlanan `SymTagData` simgeler. Sabit değerler (`LocIsConstant`) de bu türü ile tanımlanır.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda bu simge türü için geçerli olan özellikleri gösterir.  
  
|Özellik|Veri türü|Açıklama|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)|`DWORD`|Bir alanı varsa, ardından değerlerinin [CV_access_e numaralandırması](../../debugger/debug-interface-access/cv-access-e.md).|  
|[Idiasymbol::get_addressoffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|Uzaklık bölümü konumunun; Ayrıntılar için bkz [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_addresssection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|`DWORD`|Konum, bölüm parçası; Ayrıntılar için bkz [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_addresstaken](../../debugger/debug-interface-access/idiasymbol-get-addresstaken.md)|`BOOL`|`TRUE`Bu verinin adresi başka bir simgeyle başvurulduğunda.|  
|[Idiasymbol::get_bitposition](../../debugger/debug-interface-access/idiasymbol-get-bitposition.md)|`DWORD`|Konum konumunu bit; Ayrıntılar için bkz [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md) (DIA SDK v8.0 desteklenmez).|  
|[Idiasymbol::get_classparent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|Bu yapı, UNION veya sınıfı alanına ise sınıfı simgesi.|  
|[Idiasymbol::get_classparentıd](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|Sınıf üst simge kimliği.|  
|[Idiasymbol::get_compilergenerated](../../debugger/debug-interface-access/idiasymbol-get-compilergenerated.md)|`BOOL`|`TRUE`Veri derleyici tarafından oluşturulmuşsa.|  
|[Idiasymbol::get_consttype](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE`verileri sabit olduğu işaretlenmişse.|  
|[Idiasymbol::get_datakind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)|`DWORD`|Aşağıdakilerden birini [DataKind numaralandırması](../../debugger/debug-interface-access/datakind.md) değerleri.|  
|[Idiasymbol::get_isaggregated](../../debugger/debug-interface-access/idiasymbol-get-isaggregated.md)|`BOOL`|`TRUE`verileri bir toplanmış veri türü (yalnızca DIA SDK v8.0 ve daha sonra) bir parçası ise.|  
|[Idiasymbol::get_issplitted](../../debugger/debug-interface-access/idiasymbol-get-issplitted.md)|`BOOL`|`TRUE`veri toplama (yalnızca DIA SDK v8.0 ve daha sonra) birden çok simgelerin bölündü.|  
|[Idiasymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`ULONGLONG`|Saklayıcısında uzunluğu; Ayrıntılar için bkz [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_lexicalparent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Kapsayan derlenecek, işlev veya blok simgesi.|  
|[Idiasymbol::get_lexicalparentıd](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|Sözcük üst simge kimliği.|  
|[Idiasymbol::get_locationtype](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|İzin verilen konum türlerinden birini; Ayrıntılar için bkz [simge konumları](../../debugger/debug-interface-access/symbol-locations.md)|  
|[Idiasymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Değişkenin adı.|  
|[Idiasymbol::get_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|`LONG`|YAZMAÇ içeriği uzaklığı; Ayrıntılar için bkz [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_registerıd](../../debugger/debug-interface-access/idiasymbol-get-registerid.md)|`DWORD`|Konum Belirleyicisi kaydedin; Ayrıntılar için bkz [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_relativevirtualaddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|Göreli konumunu verilerini kendi bloğu içinde.|  
|[Idiasymbol::get_slot](../../debugger/debug-interface-access/idiasymbol-get-slot.md)|`DWORD`|Veri Yuva sayısını alır.|  
|[Idiasymbol::get_symındexıd](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|Dizin kimliği simgesi.|  
|[Idiasymbol::get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Döndürür `SymTagData` (birini [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md) değerleri).|  
|[Idiasymbol::get_token](../../debugger/debug-interface-access/idiasymbol-get-token.md)|`DWORD`|Verileri temsil eden meta veri simgesi.|  
|[Idiasymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|Değişken türü simgesi.|  
|[Idiasymbol::get_typeıd](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|Değişken türü simgenin kimliği.|  
|[Idiasymbol::get_unalignedtype](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`Hizalanmamış verisidir.|  
|[Idiasymbol::get_value](../../debugger/debug-interface-access/idiasymbol-get-value.md)|`VARIANT`|Sabit veri değeri.|  
|[Idiasymbol::get_virtualaddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|Yürütülebilir dosya içinde veri konumu.|  
|[Idiasymbol::get_volatiletype](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`veriler geçici işaretlenmişse.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CV_access_e numaralandırması](../../debugger/debug-interface-access/cv-access-e.md)   
 [DataKind numaralandırması](../../debugger/debug-interface-access/datakind.md)   
 [Simge türlerinin sözcük hiyerarşisi](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md)   
 [Simge konumları](../../debugger/debug-interface-access/symbol-locations.md)