---
title: "Sabitler (arabirim erişimi SDK'SINDA hata ayıklama) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- constants, DIA SDK
- DIA SDK, constants
ms.assetid: aca4ec77-bc08-4cdd-a6ce-8d4a28ea5ea3
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 50b6533b1036087dc8d0cdfe59b653774d781f55
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="constants-debug-interface-access-sdk"></a>Sabitler (Arabirim Erişimi SDK'sında Hata Ayıklama)
Bu dize sabitleri, bir program hata ayıklama veritabanı (PDB) dosyası DIA SDK aracılığıyla çeşitli bölümlerini belirlemek için kullanılabilir.  
  
## <a name="constants"></a>Sabitler  
 Aşağıdaki C/C++ makroları olarak bildirilir.  
  
|Makrosu|Değer|  
|-----------|-----------|  
|`DiaTable_Symbols`|L "Simgeleri"|  
|`DiaTable_Sections`|L "Bölüm"|  
|`DiaTable_SrcFiles`|L "SourceFiles"|  
|`DiaTable_LineNums`|L "Lınenumbers"|  
|`DiaTable_SegMap`|L "SegmentMap"|  
|`DiaTable_Dbg`|L "Dbg"|  
|`DiaTable_InjSrc`|L "InjectedSource"|  
|`DiaTable_FrameData`|L "FrameData"|  
  
## <a name="example"></a>Örnek  
 Bu simgeleri birini kullanarak örnek aşağıda verilmiştir:  
  
```C++  
HRESULT GetSymbolTable(IDiaEnumTables *pEnumTables, IDiaTable **pTable)  
{  
    HRESULT hr;  
    VARIANT var;  
    var.vt      = VT_BSTR;  
    var.bstrVal = SysAllocString( DiaTable_Symbols );  
    hr = pEnumTables->Item( var, pTable );  
    return(hr);  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: dia2.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru](../../debugger/debug-interface-access/debug-interface-access-sdk-reference.md)   
 [Numaralandırmalar ve yapılar](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiaenumtables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md)