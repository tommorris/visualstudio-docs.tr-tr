---
title: Idiadatasource | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaDataSource interface
ms.assetid: 6260ac76-4f9d-4144-ba22-32f8620b32c2
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9b6ddb2ba2cc568b8f07e6643dcaeb93c0dec8ff
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiadatasource"></a>IDiaDataSource
Hata ayıklama simgeleri ın kaynak erişimi başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaDataSource : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaDataSource`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Idiadatasource::get_lasterror](../../debugger/debug-interface-access/idiadatasource-get-lasterror.md)|Son yükleme hatası için dosya adını alır.|  
|[Idiadatasource::loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)|Açılır ve hata ayıklama veri kaynağı olarak program veritabanı (.pdb) dosyası hazırlar.|  
|[Idiadatasource::loadandvalidatedatafrompdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)|Açılır ve program veritabanı (.pdb) dosyası sağlanan imza bilgileri eşleştiğini doğrular; hata ayıklama veri kaynağı olarak .pdb dosyasını hazırlar.|  
|[Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)|Açılır ve.exe/.dll dosyayla ilişkili hata ayıklama veri hazırlar.|  
|[Idiadatasource::loaddatafromıstream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)|Bellek içi veri akışı erişilen bir program veritabanı (.pdb) dosyasında depolanan hata ayıklama verileri hazırlar.|  
|[Idiadatasource::opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md)|Simgeler sorgulama için bir oturum açar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yükleme yöntemlerinden birini çağrısına `IDiaDataSource` arabirimi simgesi Kaynak açılır. Başarılı bir çağrı [Idiadatasource::opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md) yöntemi döndürür bir [Idiasession](../../debugger/debug-interface-access/idiasession.md) veri kaynağı sorgulanırken destekleyen arabirimi. Load yöntemi dosya ile ilgili bir hata verirse sonra [Idiadatasource::get_lasterror](../../debugger/debug-interface-access/idiadatasource-get-lasterror.md) yöntemi dönüş değeri şu hata ile ilişkilendirilmiş dosya adını içerir.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim çağırılarak alınır `CoCreateInstance` sınıf tanımlayıcısı işleviyle `CLSID_DiaSource` ve arabirim kimliği `IID_IDiaDataSource`. Bu örnek, bu arabirimin nasıl elde gösterir.  
  
## <a name="example"></a>Örnek  
  
```C++  
  
      IDiaDataSource* pSource;  
HRESULT hr = CoCreateInstance(CLSID_DiaSource,  
                              NULL,  
                              CLSCTX_INPROC_SERVER,  
                              IID_IDiaDataSource,  
                              (void**) &pSource);  
if (FAILED(hr))  
{  
    // Report error and exit  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Dia2.h  
  
 Kitaplığı: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)