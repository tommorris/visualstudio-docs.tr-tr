---
title: Idialinenumber | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaLineNumber interface
ms.assetid: 1071f7d0-1f8c-4384-933f-c49c7eb930bd
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 45996e66500ebf275154553774d5116c6075af0f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idialinenumber"></a>IDiaLineNumber
Bir kaynak dosya satır numarası bayt görüntü metin bloğunu eşleme işlemini açıklar bilgilere erişir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaLineNumber : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaLineNumber`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Idialinenumber::get_compiland](../../debugger/debug-interface-access/idialinenumber-get-compiland.md)|Görüntü metnin bayt katkıda derlenecek dosya simgesi için bir başvuru alır.|  
|[Idialinenumber::get_sourcefile](../../debugger/debug-interface-access/idialinenumber-get-sourcefile.md)|Kaynak dosya nesnesine başvuru alır.|  
|[Idialinenumber::get_linenumber](../../debugger/debug-interface-access/idialinenumber-get-linenumber.md)|Kaynak dosya satır numarasını alır.|  
|[Idialinenumber::get_linenumberend](../../debugger/debug-interface-access/idialinenumber-get-linenumberend.md)|Sona ereceği deyiminin veya ifadesinin kaynak tabanlı satır numarasını alır.|  
|[Idialinenumber::get_columnnumber](../../debugger/debug-interface-access/idialinenumber-get-columnnumber.md)|İfade veya deyimin başladığı sütun sayısını alır.|  
|[Idialinenumber::get_columnnumberend](../../debugger/debug-interface-access/idialinenumber-get-columnnumberend.md)|İfade veya deyimin bittiği sütun sayısını alır.|  
|[Idialinenumber::get_addresssection](../../debugger/debug-interface-access/idialinenumber-get-addresssection.md)|Bir blok başladığı bellek adresi bölüm parçası alır.|  
|[Idialinenumber::get_addressoffset](../../debugger/debug-interface-access/idialinenumber-get-addressoffset.md)|Bir blok başladığı bellek adresi uzaklık parçası alır.|  
|[Idialinenumber::get_relativevirtualaddress](../../debugger/debug-interface-access/idialinenumber-get-relativevirtualaddress.md)|Görüntü göreli sanal adres (RVA) bloğunun alır.|  
|[Idialinenumber::get_virtualaddress](../../debugger/debug-interface-access/idialinenumber-get-virtualaddress.md)|Bir blok sanal adres (VA) alır.|  
|[Idialinenumber::get_length](../../debugger/debug-interface-access/idialinenumber-get-length.md)|Bir blok bayt sayısını alır.|  
|[Idialinenumber::get_sourcefileıd](../../debugger/debug-interface-access/idialinenumber-get-sourcefileid.md)|Bu satırı katkıda bulunan kaynak dosya için bir benzersiz kaynak dosya tanımlayıcı alır.|  
|[Idialinenumber::get_statement](../../debugger/debug-interface-access/idialinenumber-get-statement.md)|Bu satır bilgileri program kaynak deyiminde başlangıcını açıklar belirten bir bayrak alır.|  
|[Idialinenumber::get_compilandıd](../../debugger/debug-interface-access/idialinenumber-get-compilandid.md)|Bu satırı katkıda derlenecek için benzersiz tanımlayıcıyı alır.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim çağırarak elde [Idiaenumlinenumbers::Item](../../debugger/debug-interface-access/idiaenumlinenumbers-item.md) veya [Idiaenumlinenumbers::Next](../../debugger/debug-interface-access/idiaenumlinenumbers-next.md) yöntemleri.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki işlevi bir işlevde kullanılan satır numaralarını görüntüler (tarafından temsil edilen `pSymbol`).  
  
```C++  
void dumpFunctionLines( IDiaSymbol* pSymbol, IDiaSession* pSession )  
{  
    ULONGLONG length = 0;  
    DWORD     isect  = 0;  
    DWORD     offset = 0;  
  
    pSymbol->get_addressSection( &isect );  
    pSymbol->get_addressOffset( &offset );  
    pSymbol->get_length( &length );  
    if ( isect != 0 && length > 0 )  
    {  
        CComPtr< IDiaEnumLineNumbers > pLines;  
        if ( SUCCEEDED( pSession->findLinesByAddr(  
                                      isect,  
                                      offset,  
                                      static_cast<DWORD>( length ),  
                                      &pLines)  
                      )  
           )  
        {  
            CComPtr< IDiaLineNumber > pLine;  
            DWORD celt      = 0;  
            bool  firstLine = true;  
  
            while ( SUCCEEDED( pLines->Next( 1, &pLine, &celt ) ) &&  
                    celt == 1 )  
            {  
                DWORD offset;  
                DWORD seg;  
                DWORD linenum;  
                CComPtr< IDiaSymbol >     pComp;  
                CComPtr< IDiaSourceFile > pSrc;  
  
                pLine->get_compiland( &pComp );  
                pLine->get_sourceFile( &pSrc );  
                pLine->get_addressSection( &seg );  
                pLine->get_addressOffset( &offset );  
                pLine->get_lineNumber( &linenum );  
                printf( "\tline %d at 0x%x:0x%x\n", linenum, seg, offset );  
                pLine = NULL;  
                if ( firstLine )  
                {  
                    // sanity check  
                    CComPtr< IDiaEnumLineNumbers > pLinesByLineNum;  
                    if ( SUCCEEDED( pSession->findLinesByLinenum(  
                                                  pComp,  
                                                  pSrc,  
                                                  linenum,  
                                                  0,  
                                                  &pLinesByLineNum)  
                                  )  
                       )  
                    {  
                        CComPtr< IDiaLineNumber > pLine;  
                        DWORD celt;  
                        while ( SUCCEEDED( pLinesByLineNum->Next( 1, &pLine, &celt ) ) &&  
                                celt == 1 )  
                        {  
                            DWORD offset;  
                            DWORD seg;  
                            DWORD linenum;  
  
                            pLine->get_addressSection( &seg );  
                            pLine->get_addressOffset( &offset );  
                            pLine->get_lineNumber( &linenum );  
                            printf( "\t\tfound line %d at 0x%x:0x%x\n", linenum, seg, offset );  
                            pLine = NULL;  
                       }  
                    }  
                    firstLine = false;  
                }  
            }  
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
 [Idiaenumlinenumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [Idiaenumlinenumbers::Item](../../debugger/debug-interface-access/idiaenumlinenumbers-item.md)   
 [Idiaenumlinenumbers::Next](../../debugger/debug-interface-access/idiaenumlinenumbers-next.md)