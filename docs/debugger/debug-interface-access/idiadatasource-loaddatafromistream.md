---
title: "Idiadatasource::loaddatafromıstream | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::loadDataFromIStream method
ms.assetid: 8fe33eea-1457-4b8c-ae19-f1ede5578483
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5babf70c1f7b58e85b681956c44f1e387441b8b0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiadatasourceloaddatafromistream"></a>IDiaDataSource::loadDataFromIStream
Bellek içi veri akışı erişilen bir program veritabanı (.pdb) dosyasında depolanan hata ayıklama verileri hazırlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT loadDataFromIStream (   
   IStream* pIStream  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pIStream  
 [in] Bir <xref:IStream> kullanmak için veri akışı temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Aşağıdaki tabloda bu yöntem için olası dönüş değerleri gösterir.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|E_PDB_FORMAT|Bir dosya biçimi geçersiz erişme girişiminde bulunuldu.|  
|E_INVALIDARG|Invalidparameter.|  
|E_UNEXPECTED|Veri kaynağı zaten hazırlandı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem bellekten alınması için yürütülebilir bir dosya için hata ayıklama verilerin izin veren bir <xref:IStream> nesnesi.  
  
 Onaysız .pdb dosyasını yüklemek için kullanmak [Idiadatasource::loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) yöntemi.  
  
 Belirli bir ölçüte göre .pdb dosyasını doğrulamak için kullanın [Idiadatasource::loadandvalidatedatafrompdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md) yöntemi.  
  
 Veri yükleme işlemi (bir geri çağırma mekanizma) erişmek için kullandığı [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiadatasource](../../debugger/debug-interface-access/idiadatasource.md)   
 [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [Idiadatasource::loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)   
 [IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)