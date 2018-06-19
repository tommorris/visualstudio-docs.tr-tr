---
title: Idiadatasource::loaddatafrompdb | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::loadDataFromPdb method
ms.assetid: 02159073-8144-47f8-a0b0-aa0edcb92b5b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1910d54ad1a9d2964869beb4854ea97600569b7c
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31468365"
---
# <a name="idiadatasourceloaddatafrompdb"></a>IDiaDataSource::loadDataFromPdb
Açılır ve hata ayıklama veri kaynağı olarak program veritabanı (.pdb) dosyası hazırlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT loadDataFromPdb (  
   LPCOLESTR pdbPath  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pdbPath  
 [in] .Pdb dosyasının yolu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Aşağıdaki tabloda bu yöntem için olası dönüş değerleri gösterir.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|E_PDB_NOT_FOUND|Dosyayı açmak için başarısız oldu veya dosyanın biçimi geçersiz olduğunu belirledi.|  
|E_PDB_FORMAT|Bir dosya biçimi geçersiz erişme girişiminde bulunuldu.|  
|E_INVALIDARG|Geçersiz parametre.|  
|E_UNEXPECTED|Veri kaynağı zaten hazırlandı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, hata ayıklama verileri doğrudan .pdb dosyasından yükler.  
  
 Belirli bir ölçüte göre .pdb dosyasını doğrulamak için kullanın [Idiadatasource::loadandvalidatedatafrompdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md) yöntemi.  
  
 Veri yükleme işlemi (bir geri çağırma mekanizma) erişmek için kullandığı [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) yöntemi.  
  
 .Pdb dosyasını doğrudan bellekten yüklemek için kullanmak [Idiadatasource::loaddatafromıstream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md) yöntemi.  
  
## <a name="example"></a>Örnek  
  
```C++  
HRESULT hr = pSource->loadDataFromPdb( L"myprog.pdb" );  
if (FAILED(hr))  
{  
    // report error  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiadatasource](../../debugger/debug-interface-access/idiadatasource.md)   
 [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [Idiadatasource::loadandvalidatedatafrompdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)   
 [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)