---
title: Idiasourcefile | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile interface
ms.assetid: 6e9be757-797f-4960-ba62-c14092620bbd
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8b43eeda2111052eda355f3b04fa0e2c5087dc07
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688138"
---
# <a name="idiasourcefile"></a>IDiaSourceFile
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiasourcefile](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasourcefile).  
  
Bir kaynak dosyasını temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaSourceFile : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaSourceFile`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[IDiaSourceFile::get_uniqueId](../../debugger/debug-interface-access/idiasourcefile-get-uniqueid.md)|Bu görüntü için benzersiz olan bir basit tamsayı anahtar değeri alır.|  
|[IDiaSourceFile::get_fileName](../../debugger/debug-interface-access/idiasourcefile-get-filename.md)|Kaynak dosya adını alır.|  
|[IDiaSourceFile::get_checksumType](../../debugger/debug-interface-access/idiasourcefile-get-checksumtype.md)|Sağlama türünü alır.|  
|[IDiaSourceFile::get_compilands](../../debugger/debug-interface-access/idiasourcefile-get-compilands.md)|Bu dosya başvuran satır numaraları ile derleme, bir numaralandırıcı alır.|  
|[IDiaSourceFile::get_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md)|Sağlama toplamı bayt sayısını alır.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim çağırarak elde [Idiaenumsourcefiles::Item](../../debugger/debug-interface-access/idiaenumsourcefiles-item.md) veya [Idiaenumsourcefiles::Next](../../debugger/debug-interface-access/idiaenumsourcefiles-next.md) yöntemleri. Ayrıntılar için örneğe bakın.  
  
## <a name="example"></a>Örnek  
 Bu işlev belirtilen tabloya katkıda bulunan tüm kaynak dosyalarının adlarını görüntüler.  
  
```cpp#  
void ShowSourceFiles(IDiaTable *pTable)  
{  
    CComPtr<IDiaEnumSourceFiles> pSourceFiles;  
    if ( SUCCEEDED( pTable->QueryInterface(  
                                _uuidof( IDiaEnumSourceFiles ),  
                               (void**)&pSourceFiles )  
                  )  
       )  
    {  
        CComPtr<IDiaSourceFile> pSourceFile;  
        while ( SUCCEEDED( hr = pSourceFiles->Next( 1, &pSourceFile, &celt ) ) &&  
                celt == 1 )  
        {  
            CDiaBSTR fileName;  
            if ( pSourceFile->get_fileName( &fileName) == S_OK )  
            {  
                printf( "file name: %ws\n", fileName );  
            }  
            pSourceFile = NULL;  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Dia2.h  
  
 Kitaplık: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiaenumsourcefiles::Item](../../debugger/debug-interface-access/idiaenumsourcefiles-item.md)   
 [Idiaenumsourcefiles::Next](../../debugger/debug-interface-access/idiaenumsourcefiles-next.md)   
 [Idialinenumber::get_sourcefile](../../debugger/debug-interface-access/idialinenumber-get-sourcefile.md)   
 [Idiasession::findfilebyıd](../../debugger/debug-interface-access/idiasession-findfilebyid.md)   
 [Idiasession::findlines](../../debugger/debug-interface-access/idiasession-findlines.md)   
 [IDiaSession::findLinesByLinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)



