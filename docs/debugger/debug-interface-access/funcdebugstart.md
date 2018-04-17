---
title: FuncDebugStart | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- FuncDebugStart symbol
- debugging [DIA SDK], start point
ms.assetid: 1cbc6ca5-87d0-4c30-a39e-0a9dc62ce1a9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e61fd3d519c12ef001ec6db42e0b3bfc36370371
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="funcdebugstart"></a>FuncDebugStart
Bir işlev hangi hata ayıklama sırasında tanımlanan noktası başlamak için noktası ile simgesiyle tanımlanır ise bir `SymTagFuncDebugStart` etiketi.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda bu simge türü için geçerli olan özellikleri gösterir.  
  
|Özellik|Veri türü|Açıklama|  
|--------------|---------------|-----------------|  
|[IDiaSymbol::get_addressOffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|Uzaklık bölümü konumunun; Ayrıntılar için bkz [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md).|  
|[IDiaSymbol::get_addressSection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|`DWORD`|Konum, bölüm parçası; Ayrıntılar için bkz [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md).|  
|[IDiaSymbol::get_customCallingConvention](../../debugger/debug-interface-access/idiasymbol-get-customcallingconvention.md)|`BOOL`|`TRUE` işlev özel bir çağırma kuralı (yalnızca DIA SDK v8.0 veya sonrası) kullanıyorsa.|  
|[IDiaSymbol::get_farReturn](../../debugger/debug-interface-access/idiasymbol-get-farreturn.md)|`BOOL`|`TRUE` işlev kadar dönüş (yalnızca DIA SDK v8.0 veya sonrası) uyguluyorsa.|  
|[IDiaSymbol::get_interruptReturn](../../debugger/debug-interface-access/idiasymbol-get-interruptreturn.md)|`BOOL`|`TRUE` işlevi bir dönüş kesme (yalnızca DIA SDK v8.0 veya sonrası) içeriyorsa.|  
|[IDiaSymbol::get_isStatic](../../debugger/debug-interface-access/idiasymbol-get-isstatic.md)|`BOOL`|`TRUE` (yalnızca DIA SDK v8.0 veya sonrası) işlevi static olarak işaretlenmişse.|  
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Kapsayan işlevi simgesi.|  
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|Sözcük üst simge kimliği.|  
|[IDiaSymbol::get_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|Başlangıç noktaları statik konumları; yine de sahip istiyor musunuz? Ayrıntılar için bkz [simge konumları](../../debugger/debug-interface-access/symbol-locations.md).|  
|[IDiaSymbol::get_noInline](../../debugger/debug-interface-access/idiasymbol-get-noinline.md)|`BOOL`|`TRUE` işlevi ile belirtildiyse, [noinline](/cpp/cpp/noinline) özniteliği (yalnızca DIA SDK v8.0 veya üzeri).|  
|[IDiaSymbol::get_noReturn](../../debugger/debug-interface-access/idiasymbol-get-noreturn.md)|`BOOL`|`TRUE` işlevi ile belirtildiyse, [noreturn](/cpp/cpp/noreturn) özniteliği (yalnızca DIA SDK v8.0 veya üzeri).|  
|[IDiaSymbol::get_notReached](../../debugger/debug-interface-access/idiasymbol-get-notreached.md)|`BOOL`|`TRUE` işlev hiçbir zaman (yalnızca DIA SDK v8.0 veya sonrası) çağrılırsa.|  
|[IDiaSymbol::get_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|`LONG`|Bellekte simgenin uzaklığı; Ayrıntılar için bkz [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md), `LocIsRegRel`.|  
|[IDiaSymbol::get_optimizedCodeDebugInfo](../../debugger/debug-interface-access/idiasymbol-get-optimizedcodedebuginfo.md)|`BOOL`|`TRUE` kodu en iyi duruma getirilmiş kodu (yalnızca DIA SDK v8.0 veya sonrası) için hata ayıklama bilgileri varsa.|  
|[IDiaSymbol::get_relativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|İşlev kendi bloğu içinde göreli konumunu.|  
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|Dizin kimliği simgesi.|  
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Döndürür `SymTagFuncDebugStart` (birini [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md) değerleri).|  
|[IDiaSymbol::get_virtualAddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|İşlev yürütülebilir dosya içinde konumu.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Simge türlerinin sözcük hiyerarşisi](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [LocationType numaralandırması](../../debugger/debug-interface-access/locationtype.md)   
 [Simge Konumları](../../debugger/debug-interface-access/symbol-locations.md)