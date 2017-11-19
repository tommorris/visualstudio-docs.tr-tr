---
title: Idiaenumsymbols | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumSymbols interface
ms.assetid: 649f7bfd-86ac-49a5-8533-aff77e1bc62e
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 372279d82f9f316edf0d1aed203be1ce4e48e236
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumsymbols"></a>IDiaEnumSymbols
Veri kaynağında bulunan çeşitli simgeleri numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaEnumSymbols : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaEnumSymbols`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Idiaenumsymbols::get__newenum](../../debugger/debug-interface-access/idiaenumsymbols-get-newenum.md)|Alır `IEnumVARIANT Interface` bu Sıralayıcı sürümü.|  
|[Idiaenumsymbols::get_Count](../../debugger/debug-interface-access/idiaenumsymbols-get-count.md)|Sembol sayısını alır.|  
|[Idiaenumsymbols::Item](../../debugger/debug-interface-access/idiaenumsymbols-item.md)|Bir dizin yoluyla bir simge alır.|  
|[Idiaenumsymbols::Next](../../debugger/debug-interface-access/idiaenumsymbols-next.md)|Belirtilen bir numaralandırma sırası sembolleri sayısını alır.|  
|[Idiaenumsymbols::Skip](../../debugger/debug-interface-access/idiaenumsymbols-skip.md)|Bir numaralandırma sırasını sembolleri belirtilen sayıda atlar.|  
|[Idiaenumsymbols::reset](../../debugger/debug-interface-access/idiaenumsymbols-reset.md)|Bir numaralandırma sırasını başlangıç durumuna sıfırlar.|  
|[Idiaenumsymbols::Clone](../../debugger/debug-interface-access/idiaenumsymbols-clone.md)|Geçerli Numaralandırıcı aynı numaralandırma duruma içeren bir numaralandırıcı oluşturur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim belirli bir sembol, örneğin, türüne göre gruplandırılmış simgeleri sağlar `SymTagUDT` (kullanıcı tanımlı türler) veya `SymTagBaseClass`. Adresine göre gruplandırılmış simgeleri ile çalışmak için kullanın [Idiaenumsymbolsbyaddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md) arabirimi.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim, aşağıdaki yöntemlerden çağırarak alın:  
  
-   [Idiasession::findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md)  
  
-   [Idiasymbol::findchildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)  
  
-   [Idiasourcefile::get_compilands](../../debugger/debug-interface-access/idiasourcefile-get-compilands.md)  
  
## <a name="example"></a>Örnek  
 Bu örnek nasıl alınacağını gösterir `IDiaEnumSymbols` arabirim ve o sabit listesi kullanıcı tanımlı türler (atama) için kullanın.  
  
> [!NOTE]
>  `CDiaBSTR`kaydırılan bir sınıf bir `BSTR` ve örnek oluşturma kapsam dışına çıktığında dize boşaltma otomatik olarak yönetir.  
  
```C++  
void ShowUDTs(IDiaSymbol *pGlobals)  
{  
    CComPtr<IDiaEnumSymbols> pEnum;  
    CComPtr<IDiaSymbol> pSymbol;  
    HRESULT hr;  
  
    hr = pGlobals->findChildren(SymTagUDT,  
                                NULL,  
                                nsfCaseInsensitive | nsfUndecoratedName,  
                                &pEnum);  
    if (hr == S_OK)  
    {  
        while ( SUCCEEDED( hr = pEnum->Next( 1, &pSymbol, &celt ) ) &&  
                celt == 1 )  
        {  
            CDiaBSTR name;  
            if ( pSymbol->get_name( &name ) != S_OK )  
                Fatal( "get_name" );  
            printf( "Found UDT: %ws\n", name );  
            pSymbol = 0;  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Dia2.h  
  
 Kitaplığı: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiasession::findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [Idiasourcefile::get_compilands](../../debugger/debug-interface-access/idiasourcefile-get-compilands.md)   
 [Idiasymbol::findchildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)