---
title: Idiadatasource::loadandvalidatedatafrompdb | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaDataSource::loadAndValidateDataFromPdb method
ms.assetid: d66712dd-6c24-4192-919a-cce262066f0e
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: bcd82116c7499d2a2289fc0c198a2be053226721
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiadatasourceloadandvalidatedatafrompdb"></a>IDiaDataSource::loadAndValidateDataFromPdb
Açılır ve program veritabanı (.pdb) dosyası sağlanan imza bilgileri eşleştiğini doğrular ve hata ayıklama veri kaynağı olarak .pdb dosyasını hazırlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT loadAndValidateDataFromPdb (   
   LPCOLESTR pdbPath,  
   GUID*     pcsig70,  
   DWORD     sig,  
   DWORD     age  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pdbPath`  
 [in] .Pdb dosyasının yolu.  
  
 `pcsig70`  
 [in] Karşı .pdb dosyasını imzayı doğrulamak için GUID imzası. Yalnızca .pdb dosyaları [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] ve daha sonra GUID imzalar.  
  
 `sig`  
 [in] Karşı .pdb dosyasını imzayı doğrulamak için 32-bit imzası.  
  
 `age`  
 [in] Doğrulamak için yaş değeri. Geçerlilik süresi herhangi bir bilinen saat değerine karşılık gelmiyor, .pdb dosyasını karşılık gelen bir .exe dosyası ile eşit olup olmadığını belirlemek için kullanılır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Aşağıdaki tabloda bu yöntem için olası dönüş değerleri gösterir.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|E_PDB_NOT_FOUND|Dosyayı açmak başarısız oldu veya dosya geçersiz bir biçime sahip.|  
|E_PDB_FORMAT|Bir dosya biçimi geçersiz erişme girişiminde bulunuldu.|  
|E_PDB_INVALID_SIG|İmza eşleşmiyor.|  
|E_PDB_INVALID_AGE|Geçerlilik süresi eşleşmiyor.|  
|E_INVALIDARG|Geçersiz parametre.|  
|E_UNEXPECTED|Veri kaynağı zaten hazırlandı.|  
  
## <a name="remarks"></a>Açıklamalar  
 .Pdb dosyasını imza ve yaş değerler içeriyor. Bu değerleri .pdb dosyasını eşleşen .exe veya .dll dosyasına çoğaltılır. Veri kaynağı hazırlamadan önce bu yöntem adlandırılmış .pdb dosyanın imza ve yaş sağlanan değerler eşleştiğini doğrular.  
  
 Onaysız .pdb dosyasını yüklemek için kullanmak [Idiadatasource::loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) yöntemi.  
  
 Veri yükleme işlemi (bir geri çağırma mekanizma) erişmek için kullandığı [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) yöntemi.  
  
 .Pdb dosyasını doğrudan bellekten yüklemek için kullanmak [Idiadatasource::loaddatafromıstream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md) yöntemi.  
  
## <a name="example"></a>Örnek  
  
```C++  
IDiaDataSource* pSource;  // Previously created data source.  
DEFINE_GUID(expectedGUIDSignature,0x1234,0x5678,0x01,0x02,0x03,0x04,0x05,0x06,0x07,0x08);  
DWORD expectedFileSignature = 0x12345678;  
DWORD expectedAge           = 128;  
  
HRESULT hr;  
hr = pSource->loadAndValidateDataFromPdb( L"yprog.pdb",  
                                          &expectedGUIDSignature,  
                                          expectedFileSignature,  
                                          expectedAge);  
if (FAILED(hr))  
{  
    // Report an error  
}  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiadatasource](../../debugger/debug-interface-access/idiadatasource.md)   
 [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [Idiadatasource::loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)   
 [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)