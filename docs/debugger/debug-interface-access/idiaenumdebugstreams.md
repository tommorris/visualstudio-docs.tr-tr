---
title: Idiaenumdebugstreams | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumDebugStreams interface
ms.assetid: 611caf4f-7a5f-4aa4-b909-52feeb3cc752
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 023cb5f92abb9c67a94eeaf0f7202c95f097248d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumdebugstreams"></a>IDiaEnumDebugStreams
Veri kaynağında bulunan çeşitli hata ayıklama akışlar numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaEnumDebugStreams : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaEnumDebugStreams`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Idiaenumdebugstreams::get__newenum](../../debugger/debug-interface-access/idiaenumdebugstreams-get-newenum.md)|Alır `IEnumVARIANT` bu Sıralayıcı sürümü.|  
|[Idiaenumdebugstreams::get_Count](../../debugger/debug-interface-access/idiaenumdebugstreams-get-count.md)|Hata ayıklama akış sayısını alır.|  
|[Idiaenumdebugstreams::Item](../../debugger/debug-interface-access/idiaenumdebugstreams-item.md)|Hata ayıklama akışı yoluyla bir dizin alır.|  
|[Idiaenumdebugstreams::Next](../../debugger/debug-interface-access/idiaenumdebugstreams-next.md)|Belirtilen bir numaralandırma sırası hata ayıklama akış sayısını alır.|  
|[Idiaenumdebugstreams::Skip](../../debugger/debug-interface-access/idiaenumdebugstreams-skip.md)|Bir numaralandırma sırasını hata ayıklama akış belirtilen sayıda atlar.|  
|[Idiaenumdebugstreams::reset](../../debugger/debug-interface-access/idiaenumdebugstreams-reset.md)|Bir numaralandırma sırasını başlangıç durumuna sıfırlar.|  
|[Idiaenumdebugstreams::Clone](../../debugger/debug-interface-access/idiaenumdebugstreams-clone.md)|Geçerli Numaralandırıcı aynı numaralandırma duruma içeren bir numaralandırıcı oluşturur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ayıklama akışları içeriğini uygulama bağlıdır ve veri biçimleri belgelenmemiş.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrı [Idiasession::getenumdebugstreams](../../debugger/debug-interface-access/idiasession-getenumdebugstreams.md) elde etmek için yöntemi bir `IDiaEnumDebugStreams` nesnesi.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, kullanılabilir veri akışlarını bu arabirimden erişim gösterilmektedir. Bkz: [Idiaenumdebugstreamdata](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md) arabirim uygulaması için `PrintStreamData` işlevi.  
  
```C++  
void DumpAllDebugStreams( IDiaSession* pSession)  
{  
    IDiaEnumDebugStreams* pEnumStreams;  
  
    wprintf(L"\n\n*** DEBUG STREAMS\n\n");  
    // Retrieve an enumerated sequence of debug data streams  
    if(pSession->getEnumDebugStreams(&pEnumStreams) == S_OK)  
    {  
        IDiaEnumDebugStreamData* pStream;  
        ULONG celt = 0;  
  
        for(; pEnumStreams->Next(1, &pStream, &celt) == S_OK; pStream = NULL)  
        {  
            PrintStreamData(pStream);  
            pStream->Release();  
        }  
        pEnumStreams->Release();  
    }  
    else  
    {  
      wprintf(L"Failed to get any debug streams!\n");  
    }  
    wprintf(L"\n");  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Dia2.h  
  
 Kitaplığı: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiaenumdebugstreamdata](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)   
 [Idiasession::getenumdebugstreams](../../debugger/debug-interface-access/idiasession-getenumdebugstreams.md)