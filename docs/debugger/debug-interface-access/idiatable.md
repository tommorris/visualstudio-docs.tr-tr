---
title: Idiatable | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaTable interface
ms.assetid: c99a2c44-7b72-4e3c-b963-25fe3df3a555
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: be24edc89328f08199316df8bdedf2ab6391907b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiatable"></a>IDiaTable
DIA veri kaynağı tablosu numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaTable : IEnumUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaTable`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Idiatable::get__newenum](../../debugger/debug-interface-access/idiatable-get-newenum.md)|Alır [IEnumVARIANT arabirimi](http://msdn.microsoft.com/en-us/139e3c93-faef-4003-9079-e0e94494db3e) bu Sıralayıcı sürümü.|  
|[Idiatable::get_name](../../debugger/debug-interface-access/idiatable-get-name.md)|Tablonun adını alır.|  
|[Idiatable::get_Count](../../debugger/debug-interface-access/idiatable-get-count.md)|Tablosundaki öğelerin sayısını alır.|  
|[Idiatable::Item](../../debugger/debug-interface-access/idiatable-item.md)|Belirli giriş dizini için bir başvuru alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirimi uygulayan `IEnumUnknown` Microsoft.VisualStudio.OLE.Interop ad alanı numaralandırma yöntemleri. `IEnumUnknown` Numaralandırma arabirimidir İçindekiler üzerinde yineleme için çok daha verimli [Idiatable::get_Count](../../debugger/debug-interface-access/idiatable-get-count.md) ve [Idiatable::Item](../../debugger/debug-interface-access/idiatable-item.md) yöntemleri.  
  
 Yorumu `IUnknown` arabirimi tarafından döndürülen `IDiaTable::Item` yöntemi veya `Next` yöntemi (Microsoft.VisualStudio.OLE.Interop ad alanında) tablo türüne bağlıdır. Örneğin, varsa `IDiaTable` arabirimi temsil eder, eklenen kaynakların bir listesinde `IUnknown` arabirimi seçmeleri için [Idiaınjectedsource](../../debugger/debug-interface-access/idiainjectedsource.md) arabirimi.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim çağırarak elde [Idiaenumtables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md) veya [Idiaenumtables::Next](../../debugger/debug-interface-access/idiaenumtables-next.md) yöntemleri.  
  
 Aşağıdaki arabirimleri ile uygulanan `IDiaTable` arabirimi (diğer bir deyişle, sorgu `IDiaTable` aşağıdaki arabirimlerinden biri, arabirimin):  
  
-   [Idiaenumsymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)  
  
-   [Idiaenumsourcefiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)  
  
-   [Idiaenumlinenumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)  
  
-   [Idiaenumsectioncontribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)  
  
-   [Idiaenumsegments](../../debugger/debug-interface-access/idiaenumsegments.md)  
  
-   [Idiaenumınjectedsources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)  
  
-   [Idiaenumframedata](../../debugger/debug-interface-access/idiaenumframedata.md)  
  
## <a name="example"></a>Örnek  
 İlk işlev `ShowTableNames`, oturumda tüm tabloların adlarını görüntüler. İkinci işlev `GetTable`, belirtilen arabirimini uygulayan bir tablo için tabloların tümü arar. Üçüncü işlevi `UseTable`, nasıl kullanılacağını gösterir `GetTable` işlevi.  
  
> [!NOTE]
>  `CDiaBSTR`kaydırılan bir sınıf bir `BSTR` ve örnek oluşturma kapsam dışına çıktığında dize boşaltma otomatik olarak yönetir.  
  
```C++  
void ShowTableNames(IDiaSession *pSession)  
{  
    CComPtr<IDiaEnumTables> pTables;  
    if ( FAILED( psession->getEnumTables( &pTables ) ) )  
    {  
        Fatal( "getEnumTables" );  
    }  
    CComPtr< IDiaTable > pTable;  
    while ( SUCCEEDED( hr = pTables->Next( 1, &pTable, &celt ) )  
            && celt == 1 )  
    {  
        CDiaBSTR bstrTableName;  
        if ( pTable->get_name( &bstrTableName ) != 0 )  
        {  
            Fatal( "get_name" );  
        }  
        printf( "Found table: %ws\n", bstrTableName );  
    }  
  
// Searches the list of all tables for a table that supports  
// the specified interface.  Use this function to obtain an  
// enumeration interface.  
HRESULT GetTable(IDiaSession* pSession,  
                 REFIID       iid,  
                 void**       ppUnk)  
{  
    CComPtr<IDiaEnumTables> pEnumTables;  
    HRESULT hResult;  
  
    if (FAILED(pSession->getEnumTables(&pEnumTables)))  
        Fatal("getEnumTables");  
  
    CComPtr<IDiaTable> pTable;  
    ULONG celt = 0;  
    while (SUCCEEDED(hResult = pEnumTables->Next(1, &pTable, &celt)) &&  
           celt == 1)  
    {  
        if (pTable->QueryInterface(iid, (void**)ppUnk) == S_OK)  
        {  
            return S_OK;  
        }  
        pTable = NULL;  
    }  
  
    if (FAILED(hResult))  
        Fatal("EnumTables->Next");  
  
    return E_FAIL;  
}  
  
// This function shows how to use the GetTable function.  
void UseTable(IDiaSession *pSession)  
{  
    CComPtr<IDiaEnumSegments> pEnumSegments;  
    if (SUCCEEDED(GetTable(pSession, __uuidof(IDiaEnumSegments), &pEnumSegments)))  
    {  
        // Do something with pEnumSegments.  
    }  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Dia2.h  
  
 Kitaplığı: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiaenumtables](../../debugger/debug-interface-access/idiaenumtables.md)   
 [Idiaenumtables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md)   
 [Idiaenumtables::Next](../../debugger/debug-interface-access/idiaenumtables-next.md)