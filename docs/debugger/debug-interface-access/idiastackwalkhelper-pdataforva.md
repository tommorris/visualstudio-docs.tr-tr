---
title: IDiaStackWalkHelper::pdataForVA | Microsoft Docs
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
- IDiaStackWalkHelper2::pdataByVA method
ms.assetid: fafc38fe-74dc-4726-9a51-eebf3a673d7f
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 251b54ca712078e5252a4a55c9237545e14a7536
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idiastackwalkhelperpdataforva"></a>IDiaStackWalkHelper::pdataForVA
Sanal adres ile ilişkili PDATA veri bloğu döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT pdataForVA(   
   ULONGLONG  va,  
   DWORD      cbData,  
   DWORD*     pcbData,  
   BYTE*      pbData  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `va`  
 [in] Veri almak için sanal adresini belirtir.  
  
 `cbData`  
 [in] Veri almak için bayt cinsinden boyutu.  
  
 `pcbData`  
 [out] Gerçek veri boyutuna edinilen bayt cinsinden döndürür.  
  
 `pbData`  
 [içinde out] İstenen veri bilgileriyle doldurulan bir arabellek. Olamaz `NULL`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`. Döndürür `S_FALSE` belirtilen adresi için hiçbir PDATA ise. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 ("Ve.xdata'yı" adlı bölüm) PDATA derlenecek özel durum işleme için işlevleri hakkında bilgi içerir.  
  
 Arayan arayan için ne kadar veri kullanılabilir isteyin gerek nedenle döndürülecek ne kadar veri olduğunu bilir. Bu nedenle, bir hata durumunda döndürmek için bu yöntemi uygulaması için kabul edilebilir `pbData` parametresi `NULL`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)