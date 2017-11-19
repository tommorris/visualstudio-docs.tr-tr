---
title: Idiadatasource::loaddataforexe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaDataSource::loadDataForExe method
ms.assetid: d94a1068-f53f-44b5-b6fb-00dec361a7f2
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 30890b66baf10f5000a9244e85a36000ea26c181
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiadatasourceloaddataforexe"></a>IDiaDataSource::loadDataForExe
Açılır ve.exe/.dll dosyayla ilişkili hata ayıklama veri hazırlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT loadDataForExe (  
   LPCOLESTR executable,  
   LPCOLESTR searchPath,  
   IUnknown* pCallback  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 yürütülebilir dosya  
 [in] .Exe veya .dll dosyasının yolu.  
  
 searchPath  
 [in] Hata ayıklama verileri için arama için alternatif yolu.  
  
 pCallback  
 [in] Bir `IUnknown` arabirimi hata ayıklama geri çağırma arabirimi gibi destekleyen bir nesne için [Idialoadcallback](../../debugger/debug-interface-access/idialoadcallback.md), [Idialoadcallback2](../../debugger/debug-interface-access/idialoadcallback2.md), [Idiareadexeatoffsetcallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md), ve/veya [Idiareadexeatrvacallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md) arabirimleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Aşağıdaki tabloda bu yöntem için olası hata kodları gösterilir.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|E_PDB_NOT_FOUND|Dosyayı açmak başarısız oldu veya dosya geçersiz bir biçime sahip.|  
|E_PDB_FORMAT|Bir dosya biçimi geçersiz erişme girişiminde bulunuldu.|  
|E_PDB_INVALID_SIG|İmza eşleşmiyor.|  
|E_PDB_INVALID_AGE|Geçerlilik süresi eşleşmiyor.|  
|E_INVALIDARG|Geçersiz parametre.|  
|E_UNEXPECTED|Veri kaynağı zaten hazırlandı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ayıklama üstbilgi.exe/.dll dosyasına ilişkili hata ayıklama veri konumu adları.  
  
 Bu yöntem hata ayıklama üst bilgisini okur ve ardından arar ve hata ayıklama veri hazırlar. Aramanın devam ediyor isteğe bağlı olarak, bildirilen ve geri çağırmalar aracılığıyla denetlenir. Örneğin, [Idialoadcallback::notifydebugdir](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md) olduğunda çağrılan `IDiaDataSource::loadDataForExe` yöntemi bulur ve hata ayıklama dizin işler.  
  
 [Idiareadexeatoffsetcallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md) ve [Idiareadexeatrvacallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md) arabirimleri izin yürütülebilir dosyadan veri okumak için alternatif yöntemler sağlamak için istemci uygulaması dosyası dosyası doğrudan standart dosya g/ç erişilemiyor.  
  
 Onaysız .pdb dosyasını yüklemek için kullanmak [Idiadatasource::loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) yöntemi.  
  
 Belirli bir ölçüte göre .pdb dosyasını doğrulamak için kullanın [Idiadatasource::loadandvalidatedatafrompdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md) yöntemi.  
  
 .Pdb dosyasını doğrudan bellekten yüklemek için kullanmak [Idiadatasource::loaddatafromıstream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md) yöntemi.  
  
## <a name="example"></a>Örnek  
  
```C++  
class MyCallBack: public IDiaLoadCallback  
{  
...  
};  
MyCallBack callback;  
...  
HRESULT hr = pSource->loadDataForExe( L"myprog.exe", L".\debug", (IUnknown*)&callback);  
if (FAILED(hr))  
{  
    // Report error  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiadatasource](../../debugger/debug-interface-access/idiadatasource.md)   
 [Idialoadcallback](../../debugger/debug-interface-access/idialoadcallback.md)   
 [Idialoadcallback2](../../debugger/debug-interface-access/idialoadcallback2.md)   
 [Idialoadcallback::notifydebugdir](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md)   
 [Idiareadexeatoffsetcallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)   
 [Idiareadexeatrvacallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)   
 [Idiadatasource::loaddatafrompdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)   
 [Idiadatasource::loadandvalidatedatafrompdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)   
 [Idiadatasource::loaddatafromıstream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)