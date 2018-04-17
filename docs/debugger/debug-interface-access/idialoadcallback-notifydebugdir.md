---
title: Idialoadcallback::notifydebugdir | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback::NotifyDebugDir method
ms.assetid: bd04e2f6-0dbf-4742-a556-96f2cd99aa19
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 006d507a2c77cf2cf3191ce639404ef84b7a7a46
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idialoadcallbacknotifydebugdir"></a>IDiaLoadCallback::NotifyDebugDir
Hata ayıklama dizin .exe dosyasında bulunan çağrılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT NotifyDebugDir (   
   BOOL  fExecutable,  
   DWORD cbData,  
   BYTE  data[]  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `fExecutable`  
 [in] `TRUE` debug dizinine bir yürütülebilir dosya (.dbg Dosya yerine) salt okunur ise.  
  
 `cbData`  
 [in] Hata ayıklama dizininde bulunan verileri bayt sayısı.  
  
 `data[]`  
 [in] Oturum debug dizinine doldurulmuş bir dizi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Dönüş kodu genellikle göz ardı edilir.  
  
## <a name="remarks"></a>Açıklamalar  
 [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) yürütülebilir dosyası işlenirken bir hata ayıklama dizin bulduğunda, bu geri çağırma yöntemini çağırır.  
  
 Bu yöntem .pdb dosyasında bulunan dışında hata ayıklama bilgileri desteklemek için ters mühendislik çalıştırılabilir ve/veya hata ayıklama dosya istemciye gereksinimini ortadan kaldırır. Bu verileri, istemci hata ayıklama bilgileri kullanılabilir türünü ve olup yürütülebilir dosya veya .dbg dosyasında bulunan tanıyabilirsiniz.  
  
 Çoğu istemcileri bu geri çağırma çünkü ihtiyacınız olmadığından `IDiaDataSource::loadDataForExe` yöntemi saydam .pdb ve .dbg dosyaları simgeleri hizmet için gerekli olduğunda açar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idialoadcallback2](../../debugger/debug-interface-access/idialoadcallback2.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)