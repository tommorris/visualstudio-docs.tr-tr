---
title: IDiaStackWalkHelper::pdataForVA | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::pdataByVA method
ms.assetid: fafc38fe-74dc-4726-9a51-eebf3a673d7f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9eb500539184d6ac5e7e3cb00e753a00f3585057
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
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