---
title: Idiasourcefile::get_checksum | Microsoft Docs
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
- IDiaSourceFile::get_checksum method
ms.assetid: aad63a7e-4e22-44e4-8a5b-81b5174ced1e
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f4c8ce89bd4cfe42be0fc67897a4545ecbe6a8a2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691219"
---
# <a name="idiasourcefilegetchecksum"></a>IDiaSourceFile::get_checksum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiasourcefile::get_checksum](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasourcefile-get-checksum).  
  
Sağlama toplamı bayt sayısını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT get_checksum (   
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cbData`  
 [in] Veri arabelleğin bayt cinsinden boyutu.  
  
 `pcbData`  
 [out] Sağlama toplamı bayt sayısını döndürür. Bu parametre olamaz `NULL`.  
  
 `data`  
 [out içinde] Sağlama toplamı bayt ile doldurulmuş bir arabellek. Bu parametre `NULL`, ardından `pcbData` gereken bayt sayısını döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Sağlama toplamı bayt oluşturmak için kullanılan sağlama toplamı algoritma türünü belirlemek için çağrı [Idiasourcefile::get_checksumtype](../../debugger/debug-interface-access/idiasourcefile-get-checksumtype.md) yöntemi.  
  
 Kaynak dosyadaki değişiklikler değişiklikleri sağlama toplamı bayt yansıtılması için sağlama toplamı genellikle kaynak dosyasının görüntüden oluşturulur. Sağlama toplamı bayt eşleşmiyorsa, dosyanın düşünülmesi gereken sonra dosya yüklenen görüntüden oluşturulan bir sağlama toplamı zarar görmüş veya değiştirilmiş.  
  
 Tipik sağlama toplamları hiçbir zaman boyutu 32 bayttan fazla olduğu ancak bir sağlama toplamı en büyük boyutu olan varsaymayın. Ayarlama `data` parametresi `NULL` sağlama toplamını almak için gereken bayt sayısını almak için. Ardından uygun boyutta bir arabellek ayırın ve bir kez daha yeni bir arabellek bu yöntemi çağırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasourcefile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSourceFile::get_checksumType](../../debugger/debug-interface-access/idiasourcefile-get-checksumtype.md)



