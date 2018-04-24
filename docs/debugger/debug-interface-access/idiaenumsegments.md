---
title: Idiaenumsegments | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSegments interface
ms.assetid: 0c9edd5e-b9ce-43e1-a791-cd4c5d16d923
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fa63e85a19a1aec5102d3f59b027e3cddf849a62
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaenumsegments"></a>IDiaEnumSegments
Veri kaynağında bulunan çeşitli kesimleri numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaEnumSegments : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaEnumSegments`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[IDiaEnumSegments::get__NewEnum](../../debugger/debug-interface-access/idiaenumsegments-get-newenum.md)|Alır [IEnumVARIANT arabirimi](http://msdn.microsoft.com/en-us/139e3c93-faef-4003-9079-e0e94494db3e) bu Sıralayıcı sürümü.|  
|[IDiaEnumSegments::get_Count](../../debugger/debug-interface-access/idiaenumsegments-get-count.md)|Bölümlerinin sayısını alır.|  
|[IDiaEnumSegments::Item](../../debugger/debug-interface-access/idiaenumsegments-item.md)|Bir segment yoluyla bir dizin alır.|  
|[IDiaEnumSegments::Next](../../debugger/debug-interface-access/idiaenumsegments-next.md)|Belirtilen bir numaralandırma sırası segmentlerinde sayısını alır.|  
|[IDiaEnumSegments::Skip](../../debugger/debug-interface-access/idiaenumsegments-skip.md)|Bir numaralandırma sırası segmentlerinde belirtilen sayıda atlar.|  
|[IDiaEnumSegments::Reset](../../debugger/debug-interface-access/idiaenumsegments-reset.md)|Bir numaralandırma sırasını başlangıç durumuna sıfırlar.|  
|[IDiaEnumSegments::Clone](../../debugger/debug-interface-access/idiaenumsegments-clone.md)|Geçerli Numaralandırıcı aynı numaralandırma duruma içeren bir numaralandırıcı oluşturur.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim çağırarak elde `QueryInterface` yöntemi bir [Idiatable](../../debugger/debug-interface-access/idiatable.md) nesnesi. Ayrıntılar için bkz.  
  
## <a name="example"></a>Örnek  
 Bu örnek nasıl alınacağını gösterir `IDiaEnumSections` bir tablodan arabirimi. Daha eksiksiz bir örnek kesimleri kullanarak bilgi için bkz [Idiasegment](../../debugger/debug-interface-access/idiasegment.md) arabirimi.  
  
```C++  
void ShowSegments(IDiaTable *pTable, IDiaSession *pSession)  
{  
    CComPtr<IDiaEnumSegments> pSegments;  
    if ( SUCCEEDED( pTable->QueryInterface(  
                                __uuidof( IDiaEnumSegments ),  
                                (void**)&pSegments )  
                  )  
       )  
    {  
        // Do something with this enumeration  
    }  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Dia2.h  
  
 Kitaplığı: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiatable](../../debugger/debug-interface-access/idiatable.md)   
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)