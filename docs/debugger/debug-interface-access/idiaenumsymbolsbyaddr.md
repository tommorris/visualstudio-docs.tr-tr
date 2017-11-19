---
title: Idiaenumsymbolsbyaddr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumSymbolsbyAddr interface
ms.assetid: 37d3dcdf-e4fa-4354-b5e1-8843566b52ac
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4efdd5297b1a4b995ba7d3e45edc9b2c982f6ecd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumsymbolsbyaddr"></a>IDiaEnumSymbolsByAddr
Veri kaynağında bulunan çeşitli simgeleri adresine göre numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaEnumSymbolsByAddr : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaEnumSymbolsByAddr`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Idiaenumsymbolsbyaddr::symbolbyaddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyaddr.md)|Numaralayıcı bölümü ve uzaklık aramasından gerçekleştirerek yerleştirir.|  
|[Idiaenumsymbolsbyaddr::symbolbyrva](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyrva.md)|Numaralayıcı göreli sanal adres (RAV) tarafından bir araması gerçekleştirerek yerleştirir.|  
|[Idiaenumsymbolsbyaddr::symbolbyva](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyva.md)|Numaralayıcı sanal adres (VA) tarafından bir araması gerçekleştirerek yerleştirir.|  
|[Idiaenumsymbolsbyaddr::Next](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-next.md)|Sırayla sonraki simgeleri adresiyle alır. Numaralandırıcı konumu alınan öğeleri sayısına göre güncelleştirir.|  
|[Idiaenumsymbolsbyaddr::prev](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-prev.md)|Önceki simgeleri sırayla adresiyle alır. Numaralandırıcı konumu alınan öğeleri sayısına göre güncelleştirir.|  
|[Idiaenumsymbolsbyaddr::Clone](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-clone.md)|Bir nesne bir kopyasını oluşturur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim adresine göre gruplandırılmış simgeleri sağlar. Örneğin türüne göre gruplandırılmış simgeleri ile çalışmak için `SymTagUDT` (kullanıcı tanımlı tür) veya `SymTagBaseClass`, kullanın [Idiaenumsymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) arabirimi.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim çağırarak elde [Idiasession::getsymbolsbyaddr](../../debugger/debug-interface-access/idiasession-getsymbolsbyaddr.md) yöntemi.  
  
## <a name="example"></a>Örnek  
 Bu işlev, ad ve adres göreli sanal adresine göre sıralanmış tüm simgelerin görüntüler.  
  
```C++  
void ShowSymbolsByAddress(IDiaSession *pSession)  
{  
    CComPtr<IDiaEnumSymbolsByAddr> pEnumByAddr;  
    if ( FAILED( psession->getSymbolsByAddr( &pEnumByAddr ) ) )  
    {  
        Fatal( "getSymbolsByAddr" );  
    }  
    CComPtr<IDiaSymbol> pSym;  
    if ( FAILED( pEnumByAddr->symbolByAddr( 1, 0, &pSym ) ) )  
    {  
        Fatal( "symbolByAddr" );  
    }  
    DWORD rvaLast = 0;  
    if ( pSym->get_relativeVirtualAddress( &rvaLast ) == S_OK )  
    {  
        pSym = 0;  
        if ( FAILED( pEnumByAddr->symbolByRVA( rvaLast, &pSym ) ) )  
        {  
            Fatal( "symbolByAddr" );  
        }  
        printf( "Symbols in order\n" );  
        do  
        {   
            CDiaBSTR name;  
            if ( pSym->get_name( &name ) != S_OK )  
            {  
                printf( "\t0x%08X (%ws) <no name>\n", rvaLast );  
            }  
            else  
            {  
               printf( "\t0x%08X %ws\n", rvaLast, name );  
            }  
            pSym = 0;  
            celt = 0;  
            if ( FAILED( hr = pEnumByAddr->Next( 1, &pSym, &celt ) ) )  
            {  
                break;  
            }  
        } while ( celt == 1 );  
    }  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Dia2.h  
  
 Kitaplığı: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiasession::getsymbolsbyaddr](../../debugger/debug-interface-access/idiasession-getsymbolsbyaddr.md)   
 [Idiaenumsymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)