---
title: Sabitler (arabirim erişimi SDK'SINDA hata ayıklama) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- constants, DIA SDK
- DIA SDK, constants
ms.assetid: aca4ec77-bc08-4cdd-a6ce-8d4a28ea5ea3
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ff1b473f7e5fdddbb1706d54e44692df3a6022e2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42681404"
---
# <a name="constants-debug-interface-access-sdk"></a>Sabitler (Arabirim Erişimi SDK'sında Hata Ayıklama)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [sabitler (arabirim erişimi SDK'ı hata ayıklama)](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/constants-debug-interface-access-sdk).  
  
Bu dize sabitleri, program hata ayıklama veritabanı (PDB) dosyası DIA SDK'sı aracılığıyla çeşitli bölümlerini belirlemek için kullanılabilir.  
  
## <a name="constants"></a>Sabitler  
 Aşağıdaki C/C++ makroları olarak bildirilir.  
  
|Makrosu|Değer|  
|-----------|-----------|  
|`DiaTable_Symbols`|L "Simge"|  
|`DiaTable_Sections`|L "Bölümler"|  
|`DiaTable_SrcFiles`|L "Kaynakdosyalar"|  
|`DiaTable_LineNums`|L "Lınenumbers"|  
|`DiaTable_SegMap`|L "SegmentMap"|  
|`DiaTable_Dbg`|L "Dbg"|  
|`DiaTable_InjSrc`|L "InjectedSource"|  
|`DiaTable_FrameData`|L "FrameData"|  
  
## <a name="example"></a>Örnek  
 Şu simgelerden birini kullanarak bir örnek aşağıda verilmiştir:  
  
```cpp#  
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
 Üstbilgi: dia2.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru](../../debugger/debug-interface-access/debug-interface-access-sdk-reference.md)   
 [Sabit listeleri ve yapıları](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaEnumTables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md)



