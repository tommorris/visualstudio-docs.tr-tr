---
title: Idiadatasource::loaddatafromıstream | Microsoft Docs
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
- IDiaDataSource::loadDataFromIStream method
ms.assetid: 8fe33eea-1457-4b8c-ae19-f1ede5578483
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bba8ba990167872b9657c16b8b8620ddac96896d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674405"
---
# <a name="idiadatasourceloaddatafromistream"></a>IDiaDataSource::loadDataFromIStream
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiadatasource::loaddatafromıstream](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiadatasource-loaddatafromistream).  
  
Bir bellek içi veri akışı yoluyla erişilen bir program veritabanı (.pdb) dosyası içinde depolanan hata ayıklama verileri hazırlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT loadDataFromIStream (   
   IStream* pIStream  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pIStream  
 [in] Bir <xref:IStream> kullanılacak veri akışını temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Aşağıdaki tabloda, bu yöntem olası dönüş değerleri gösterir.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|E_PDB_FORMAT|Bir dosya biçimi geçersiz erişme girişiminde bulunuldu.|  
|E_INVALIDARG|Invalidparameter.|  
|E_UNEXPECTED|Veri kaynağı zaten hazırlandı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem bellekten alınabilmesi bir yürütülebilir dosya için hata ayıklama verileri sağlayan bir <xref:IStream> nesne.  
  
 Doğrulama olmadan bir .pdb dosyası yüklemek için kullanın [Idiadatasource::loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) yöntemi.  
  
 Belirli bir ölçüte göre .pdb dosyasını doğrulamak için kullanın [Idiadatasource::loadandvalidatedatafrompdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md) yöntemi.  
  
 (Bir geri dönüş mekanizması) veri yükleme işlemi için erişmek için kullandığı [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiadatasource](../../debugger/debug-interface-access/idiadatasource.md)   
 [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [Idiadatasource::loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)   
 [IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)



