---
title: Idiasourcefile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSourceFile interface
ms.assetid: 6e9be757-797f-4960-ba62-c14092620bbd
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b742986d59024021eff5e85d54fc64247571df61
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasourcefile"></a>IDiaSourceFile
Kaynak dosyayı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaSourceFile : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaSourceFile`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Idiasourcefile::get_uniqueıd](../../debugger/debug-interface-access/idiasourcefile-get-uniqueid.md)|Bu görüntü için benzersiz bir basit tamsayı anahtar değeri alır.|  
|[Idiasourcefile::get_filename](../../debugger/debug-interface-access/idiasourcefile-get-filename.md)|Kaynak dosya adını alır.|  
|[Idiasourcefile::get_checksumtype](../../debugger/debug-interface-access/idiasourcefile-get-checksumtype.md)|Sağlama türünü alır.|  
|[Idiasourcefile::get_compilands](../../debugger/debug-interface-access/idiasourcefile-get-compilands.md)|Derlenecek dosyalar numaralandırması birlikte bu dosyayı başvuran satır numaralarını alır.|  
|[Idiasourcefile::get_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md)|Sağlama toplamı bayt alır.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim çağırarak elde [Idiaenumsourcefiles::Item](../../debugger/debug-interface-access/idiaenumsourcefiles-item.md) veya [Idiaenumsourcefiles::Next](../../debugger/debug-interface-access/idiaenumsourcefiles-next.md) yöntemleri. Ayrıntılar için bkz.  
  
## <a name="example"></a>Örnek  
 Bu işlev belirtilen tabloya katkıda bulunan tüm kaynak dosyaların adlarını görüntüler.  
  
```C++  
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
 Başlık: Dia2.h  
  
 Kitaplığı: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiaenumsourcefiles::Item](../../debugger/debug-interface-access/idiaenumsourcefiles-item.md)   
 [Idiaenumsourcefiles::Next](../../debugger/debug-interface-access/idiaenumsourcefiles-next.md)   
 [Idialinenumber::get_sourcefile](../../debugger/debug-interface-access/idialinenumber-get-sourcefile.md)   
 [Idiasession::findfilebyıd](../../debugger/debug-interface-access/idiasession-findfilebyid.md)   
 [Idiasession::findlines](../../debugger/debug-interface-access/idiasession-findlines.md)   
 [Idiasession::findlinesbylinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)