---
title: "Idiaenumınjectedsources | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumInjectedSources interface
ms.assetid: f97e2392-22e1-48da-b7ce-ad94c8b684b0
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: efc5773f3cadaaf2c2a4a57c3fd8b381ca3f5d43
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenuminjectedsources"></a>IDiaEnumInjectedSources
Veri kaynağında bulunan çeşitli eklenen kaynakları numaralandırılamıyor.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaEnumInjectedSources : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaEnumInjectedSources`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Idiaenumınjectedsources::get__newenum](../../debugger/debug-interface-access/idiaenuminjectedsources-get-newenum.md)|Alır [IEnumVARIANT arabirimi](http://msdn.microsoft.com/en-us/139e3c93-faef-4003-9079-e0e94494db3e) bu Sıralayıcı sürümü.|  
|[Idiaenumınjectedsources::get_Count](../../debugger/debug-interface-access/idiaenuminjectedsources-get-count.md)|Eklenen kaynağı sayısını alır.|  
|[Idiaenumınjectedsources::Item](../../debugger/debug-interface-access/idiaenuminjectedsources-item.md)|Eklenen bir kaynak dizin yoluyla alır.|  
|[Idiaenumınjectedsources::Next](../../debugger/debug-interface-access/idiaenuminjectedsources-next.md)|Belirtilen bir numaralandırma sırası eklenen kaynaklarında sayısını alır.|  
|[Idiaenumınjectedsources::Skip](../../debugger/debug-interface-access/idiaenuminjectedsources-skip.md)|Bir numaralandırma sırasını eklenen kaynaklarında belirtilen sayıda atlar.|  
|[Idiaenumınjectedsources::reset](../../debugger/debug-interface-access/idiaenuminjectedsources-reset.md)|Bir numaralandırma sırasını başlangıç durumuna sıfırlar.|  
|[Idiaenumınjectedsources::Clone](../../debugger/debug-interface-access/idiaenuminjectedsources-clone.md)|Geçerli Numaralandırıcı aynı numaralandırma duruma içeren bir numaralandırıcı oluşturur.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim çağırılarak alınır [Idiasession::findınjectedsource](../../debugger/debug-interface-access/idiasession-findinjectedsource.md) yöntemini çağırarak ya da belirli kaynak dosyasının adıyla [Idiasession::getenumtables](../../debugger/debug-interface-access/idiasession-getenumtables.md) GUID ile yöntemi `IDiaEnumInjectedSources` arabirimi.  
  
## <a name="example"></a>Örnek  
 Bu örnek nasıl alınacağını gösterir ( `GetEnumInjectedSources` işlevi) ve kullanma ( `DumpAllInjectedSources` işlevi) `IDiaEnumInjectedSources` arabirimi. Bkz: [Idiapropertystorage](../../debugger/debug-interface-access/idiapropertystorage.md) arabirim uygulaması için `PrintPropertyStorage` işlevi. Alternatif bir çıktı için bkz: [Idiaınjectedsource](../../debugger/debug-interface-access/idiainjectedsource.md) arabirimi.  
  
```C++  
  
IDiaEnumInjectedSources* GetEnumInjectedSources(IDiaSession *pSession)  
{  
    IDiaEnumInjectedSources* pUnknown    = NULL;  
    REFIID                   iid         = __uuidof(IDiaEnumInjectedSources);  
    IDiaEnumTables*          pEnumTables = NULL;  
    IDiaTable*               pTable      = NULL;  
    ULONG                    celt        = 0;  
  
    if (pSession->getEnumTables(&pEnumTables) != S_OK)  
    {  
        wprintf(L"ERROR - GetTable() getEnumTables\n");  
        return NULL;  
    }  
    while (pEnumTables->Next(1, &pTable, &celt) == S_OK && celt == 1)  
    {  
        // There is only one table that matches the given iid  
        HRESULT hr = pTable->QueryInterface(iid, (void**)&pUnknown);  
        pTable->Release();  
        if (hr == S_OK)  
        {  
            break;  
        }  
    }  
    pEnumTables->Release();  
    return pUnknown;  
}  
  
void DumpAllInjectedSources( IDiaSession* pSession)  
{  
    IDiaEnumInjectedSources* pEnumInjSources;  
  
    pEnumInjSources = GetEnumInjectedSources(pSession);  
    if (pEnumInjSources != NULL)  
    {  
        IDiaInjectedSource* pInjSource;  
        ULONG celt = 0;  
  
        while(pEnumInjSources->Next(1, &pInjSource, &celt) == S_OK &&  
              celt == 1)  
        {  
            IDiaPropertyStorage *pPropertyStorage;  
            if (pInjSource->QueryInterface(__uuidof(IDiaPropertyStorage),  
                                           (void **)&pPropertyStorage) == S_OK)  
            {  
                PrintPropertyStorage(pPropertyStorage);  
                pPropertyStorage->Release();  
            }  
            pInjSource->Release();  
        }  
        pEnumInjSources->Release();  
    }  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Dia2.h  
  
 Kitaplığı: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiasession::findınjectedsource](../../debugger/debug-interface-access/idiasession-findinjectedsource.md)   
 [Idiasession::getenumtables](../../debugger/debug-interface-access/idiasession-getenumtables.md)   
 [Idiapropertystorage](../../debugger/debug-interface-access/idiapropertystorage.md)   
 [Idiaınjectedsource](../../debugger/debug-interface-access/idiainjectedsource.md)