---
title: Idiaenumsegments | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumSegments interface
ms.assetid: 0c9edd5e-b9ce-43e1-a791-cd4c5d16d923
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d0f30e266389a3abfa3c0af1275cada34c9cfe11
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
|[Idiaenumsegments::get__newenum](../../debugger/debug-interface-access/idiaenumsegments-get-newenum.md)|Alır [IEnumVARIANT arabirimi](http://msdn.microsoft.com/en-us/139e3c93-faef-4003-9079-e0e94494db3e) bu Sıralayıcı sürümü.|  
|[Idiaenumsegments::get_Count](../../debugger/debug-interface-access/idiaenumsegments-get-count.md)|Bölümlerinin sayısını alır.|  
|[Idiaenumsegments::Item](../../debugger/debug-interface-access/idiaenumsegments-item.md)|Bir segment yoluyla bir dizin alır.|  
|[Idiaenumsegments::Next](../../debugger/debug-interface-access/idiaenumsegments-next.md)|Belirtilen bir numaralandırma sırası segmentlerinde sayısını alır.|  
|[Idiaenumsegments::Skip](../../debugger/debug-interface-access/idiaenumsegments-skip.md)|Bir numaralandırma sırası segmentlerinde belirtilen sayıda atlar.|  
|[Idiaenumsegments::reset](../../debugger/debug-interface-access/idiaenumsegments-reset.md)|Bir numaralandırma sırasını başlangıç durumuna sıfırlar.|  
|[Idiaenumsegments::Clone](../../debugger/debug-interface-access/idiaenumsegments-clone.md)|Geçerli Numaralandırıcı aynı numaralandırma duruma içeren bir numaralandırıcı oluşturur.|  
  
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
 [Idiasegment](../../debugger/debug-interface-access/idiasegment.md)