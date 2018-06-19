---
title: IDiaStackWalkHelper::put_registerValue | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::put_registerValue method
ms.assetid: 8f02ce54-ef59-455f-8aa6-dc26761c7aff
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2c094384fd4c1e01b28edcc809d58ab56b3bb225
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31463949"
---
# <a name="idiastackwalkhelperputregistervalue"></a>IDiaStackWalkHelper::put_registerValue
Bir kayıt değerini ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT put_registerValue (   
   DWORD     index,  
   ULONGLONG NewVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `index`  
 [in] Arasında bir değer [CV_HREG_e numaralandırması](../../debugger/debug-interface-access/cv-hreg-e.md) yazmak için Kaydet'i belirtme numaralandırması.  
  
 `NewVal`  
 [in] Yeni değer kaydedin.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Değer boyutu rağmen yalnızca ne kayıt normalde tutan uygulaması depolamanız gerekir. Örneğin, bir 8 bit kaydı yalnızca en düşük 8 bitlik verilen değer tutan.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [CV_HREG_e numaralandırması](../../debugger/debug-interface-access/cv-hreg-e.md)