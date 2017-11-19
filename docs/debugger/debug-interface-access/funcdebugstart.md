---
title: FuncDebugStart | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- FuncDebugStart symbol
- debugging [DIA SDK], start point
ms.assetid: 1cbc6ca5-87d0-4c30-a39e-0a9dc62ce1a9
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b89d240980746a0a6a606bd43ff67f86e454bfdc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="funcdebugstart"></a>FuncDebugStart
Bir işlev hangi hata ayıklama sırasında tanımlanan noktası başlamak için noktası ile simgesiyle tanımlanır ise bir `SymTagFuncDebugStart` etiketi.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda bu simge türü için geçerli olan özellikleri gösterir.  
  
|Özellik|Veri türü|Açıklama|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_addressoffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|Uzaklık bölümü konumunun; Ayrıntılar için bkz [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_addresssection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|`DWORD`|Konum, bölüm parçası; Ayrıntılar için bkz [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md).|  
|[Idiasymbol::get_customcallingconvention](../../debugger/debug-interface-access/idiasymbol-get-customcallingconvention.md)|`BOOL`|`TRUE`işlev özel bir çağırma kuralı (yalnızca DIA SDK v8.0 veya sonrası) kullanıyorsa.|  
|[Idiasymbol::get_farreturn](../../debugger/debug-interface-access/idiasymbol-get-farreturn.md)|`BOOL`|`TRUE`işlev kadar dönüş (yalnızca DIA SDK v8.0 veya sonrası) uyguluyorsa.|  
|[Idiasymbol::get_interruptreturn](../../debugger/debug-interface-access/idiasymbol-get-interruptreturn.md)|`BOOL`|`TRUE`işlevi bir dönüş kesme (yalnızca DIA SDK v8.0 veya sonrası) içeriyorsa.|  
|[Idiasymbol::get_isstatic](../../debugger/debug-interface-access/idiasymbol-get-isstatic.md)|`BOOL`|`TRUE`(yalnızca DIA SDK v8.0 veya sonrası) işlevi static olarak işaretlenmişse.|  
|[Idiasymbol::get_lexicalparent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Kapsayan işlevi simgesi.|  
|[Idiasymbol::get_lexicalparentıd](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|Sözcük üst simge kimliği.|  
|[Idiasymbol::get_locationtype](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|Başlangıç noktaları statik konumları; yine de sahip istiyor musunuz? Ayrıntılar için bkz [simge konumları](../../debugger/debug-interface-access/symbol-locations.md).|  
|[Idiasymbol::get_noınline](../../debugger/debug-interface-access/idiasymbol-get-noinline.md)|`BOOL`|`TRUE`işlevi ile belirtildiyse, [noinline](/cpp/cpp/noinline) özniteliği (yalnızca DIA SDK v8.0 veya üzeri).|  
|[Idiasymbol::get_noreturn](../../debugger/debug-interface-access/idiasymbol-get-noreturn.md)|`BOOL`|`TRUE`işlevi ile belirtildiyse, [noreturn](/cpp/cpp/noreturn) özniteliği (yalnızca DIA SDK v8.0 veya üzeri).|  
|[Idiasymbol::get_notreached](../../debugger/debug-interface-access/idiasymbol-get-notreached.md)|`BOOL`|`TRUE`işlev hiçbir zaman (yalnızca DIA SDK v8.0 veya sonrası) çağrılırsa.|  
|[Idiasymbol::get_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|`LONG`|Bellekte simgenin uzaklığı; Ayrıntılar için bkz [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md), `LocIsRegRel`.|  
|[Idiasymbol::get_optimizedcodedebugınfo](../../debugger/debug-interface-access/idiasymbol-get-optimizedcodedebuginfo.md)|`BOOL`|`TRUE`kodu en iyi duruma getirilmiş kodu (yalnızca DIA SDK v8.0 veya sonrası) için hata ayıklama bilgileri varsa.|  
|[Idiasymbol::get_relativevirtualaddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|İşlev kendi bloğu içinde göreli konumunu.|  
|[Idiasymbol::get_symındexıd](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|Dizin kimliği simgesi.|  
|[Idiasymbol::get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Döndürür `SymTagFuncDebugStart` (birini [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md) değerleri).|  
|[Idiasymbol::get_virtualaddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|İşlev yürütülebilir dosya içinde konumu.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Simge türlerinin sözcük hiyerarşisi](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md)   
 [Simge konumları](../../debugger/debug-interface-access/symbol-locations.md)