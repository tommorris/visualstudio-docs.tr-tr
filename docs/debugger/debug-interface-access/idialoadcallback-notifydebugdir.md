---
title: Idialoadcallback::notifydebugdir | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaLoadCallback::NotifyDebugDir method
ms.assetid: bd04e2f6-0dbf-4742-a556-96f2cd99aa19
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3bc5150146953dc99970da82747c6e608660b104
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)