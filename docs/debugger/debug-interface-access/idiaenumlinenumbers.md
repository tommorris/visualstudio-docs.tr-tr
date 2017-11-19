---
title: Idiaenumlinenumbers | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumLineNumbers interface
ms.assetid: cdf07b4f-19e4-4dcd-8af8-c2dbca586a7c
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 92d257749e12605fb02c4c25a57b1862880d9a5c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumlinenumbers"></a>IDiaEnumLineNumbers
Veri kaynağında bulunan çeşitli satır numaralarını numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaEnumLineNumbers : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaEnumLineNumbers`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Idiaenumlinenumbers::get__newenum](../../debugger/debug-interface-access/idiaenumlinenumbers-get-newenum.md)|Alır [IEnumVARIANT arabirimi](http://msdn.microsoft.com/en-us/139e3c93-faef-4003-9079-e0e94494db3e) bu Sıralayıcı sürümü.|  
|[Idiaenumlinenumbers::get_Count](../../debugger/debug-interface-access/idiaenumlinenumbers-get-count.md)|Satır numaraları sayısını alır.|  
|[Idiaenumlinenumbers::Item](../../debugger/debug-interface-access/idiaenumlinenumbers-item.md)|Bir satır sayısı bir dizin yoluyla alır.|  
|[Idiaenumlinenumbers::Next](../../debugger/debug-interface-access/idiaenumlinenumbers-next.md)|Belirtilen bir numaralandırma sırası satır numaralarını sayısını alır.|  
|[Idiaenumlinenumbers::Skip](../../debugger/debug-interface-access/idiaenumlinenumbers-skip.md)|Belirtilen sayıda satır numaralarını bir numaralandırma sırasını atlar.|  
|[Idiaenumlinenumbers::reset](../../debugger/debug-interface-access/idiaenumlinenumbers-reset.md)|Bir numaralandırma sırasını başlangıç durumuna sıfırlar.|  
|[Idiaenumlinenumbers::Clone](../../debugger/debug-interface-access/idiaenumlinenumbers-clone.md)|Geçerli Numaralandırıcı aynı numaralandırma duruma içeren bir numaralandırıcı oluşturur.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim, aşağıdaki yöntemlerden birini çağırılarak alınır [Idiasession](../../debugger/debug-interface-access/idiasession.md) arabirimi:  
  
-   [Idiasession::findlines](../../debugger/debug-interface-access/idiasession-findlines.md)  
  
-   [Idiasession::findlinesbyaddr](../../debugger/debug-interface-access/idiasession-findlinesbyaddr.md)  
  
-   [Idiasession::findlinesbyrva](../../debugger/debug-interface-access/idiasession-findlinesbyrva.md)  
  
-   [Idiasession::findlinesbyva](../../debugger/debug-interface-access/idiasession-findlinesbyva.md)  
  
-   [Idiasession::findlinesbylinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)  
  
## <a name="example"></a>Örnek  
 Bu örnek nasıl alınacağını gösterir `IDiaEnumLineNumbers` oturumundan arabirimi. Bu durumda, örnek bir işlev için satır numarası numaralandırması alma gösterir (tarafından temsil edilen `pSymbol`). Satır numaraları kullanarak daha kapsamlı örneği için bkz [Idialinenumber](../../debugger/debug-interface-access/idialinenumber.md) arabirimi.  
  
```C++  
void dumpFunctionLines( IDiaSymbol* pSymbol, IDiaSession* pSession )  
{  
    ULONGLONG length = 0;  
    DWORD isect = 0;  
    DWORD offset = 0;  
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
                                      &pLines )  
                      )  
           )  
        {  
            // Do something with the enumeration  
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
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasession::findlinesbylinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)   
 [Idiasession::findlinesbyrva](../../debugger/debug-interface-access/idiasession-findlinesbyrva.md)   
 [Idiasession::findlinesbyva](../../debugger/debug-interface-access/idiasession-findlinesbyva.md)   
 [Idiasession::findlines](../../debugger/debug-interface-access/idiasession-findlines.md)   
 [Idiasession::findlinesbyaddr](../../debugger/debug-interface-access/idiasession-findlinesbyaddr.md)