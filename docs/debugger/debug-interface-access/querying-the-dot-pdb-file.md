---
title: "Sorgulama. Pdb dosyası | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- PDB files
- .pdb files, querying
ms.assetid: 8da07d1c-2712-45f9-8fbf-f34040408a8a
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: da12d0cde9e8dae0d291985bc8bf88931ab35ec5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="querying-the-pdb-file"></a>.Pdb Dosyasını Sorgulama
Program veritabanı dosyası (uzantısı .pdb) türü ve derleme ve projesi bağlanıyor boyunca toplanan simgesel hata ayıklama bilgilerini içeren bir ikili dosyadır. PDB dosyası ile C/C++ programı derleme oluşturulduğunda **/zi** veya **/zı** veya [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)], [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)], veya [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)] ile program **/debug** seçeneği. Nesne dosyaları hata ayıklama bilgisi için .pdb dosyasına başvurular içeriyor. Pdb dosyaları hakkında daha fazla bilgi için bkz: [PDB dosyalarını](http://msdn.microsoft.com/en-us/1761c84e-8c2c-4632-9649-b5f99964ed3f). DIA uygulama çeşitli simgeler, nesneleri ve yürütülebilir görüntü içindeki veri öğeleri hakkındaki ayrıntıları almak için aşağıdaki genel adımları kullanabilirsiniz.  
  
### <a name="to-query-the-pdb-file"></a>.Pdb dosyasını sorgulama  
  
1.  Bir veri kaynağı oluşturarak elde bir [Idiadatasource](../../debugger/debug-interface-access/idiadatasource.md) arabirimi.  
  
    ```C++  
    CComPtr<IDiaDataSource> pSource;  
    hr = CoCreateInstance( CLSID_DiaSource,  
                           NULL,  
                           CLSCTX_INPROC_SERVER,  
                           __uuidof( IDiaDataSource ),  
                          (void **) &pSource);  
  
    if (FAILED(hr))  
    {  
        Fatal("Could not CoCreate CLSID_DiaSource. Register msdia80.dll." );  
    }  
    ```  
  
2.  Çağrı [Idiadatasource::loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) veya [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) hata ayıklama bilgileri yüklenemedi.  
  
    ```C++  
    wchar_t wszFilename[ _MAX_PATH ];  
    mbstowcs( wszFilename, szFilename, sizeof( wszFilename )/sizeof( wszFilename[0] ) );  
    if ( FAILED( pSource->loadDataFromPdb( wszFilename ) ) )  
    {  
        if ( FAILED( pSource->loadDataForExe( wszFilename, NULL, NULL ) ) )  
        {  
            Fatal( "loadDataFromPdb/Exe" );  
        }  
    }  
    ```  
  
3.  Çağrı [Idiadatasource::opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md) açmak için bir [Idiasession](../../debugger/debug-interface-access/idiasession.md) hata ayıklama bilgileri erişmek için.  
  
    ```C++  
    CComPtr<IDiaSession> psession;  
    if ( FAILED( pSource->openSession( &psession ) ) )   
    {  
        Fatal( "openSession" );  
    }  
    ```  
  
4.  Yöntemleri kullanın `IDiaSession` sorgulamak için veri kaynağındaki simgeler.  
  
    ```C++  
    CComPtr<IDiaSymbol> pglobal;  
    if ( FAILED( psession->get_globalScope( &pglobal) ) )  
    {  
        Fatal( "get_globalScope" );  
    }  
    ```  
  
5.  Kullanım `IDiaEnum*` hata ayıklama bilgileri saymak ve simgeler veya diğer öğeleri aracılığıyla taramak için arabirimleri.  
  
    ```C++  
    CComPtr<IDiaEnumTables> pTables;  
    if ( FAILED( psession->getEnumTables( &pTables ) ) )  
    {  
        Fatal( "getEnumTables" );  
    }  
    CComPtr< IDiaTable > pTable;  
    while ( SUCCEEDED( hr = pTables->Next( 1, &pTable, &celt ) ) && celt == 1 )  
    {  
         // Do something with each IDiaTable.  
    }  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)