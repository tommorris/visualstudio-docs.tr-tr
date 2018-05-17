---
title: CvLeaveSpan işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvLeaveSpan
helpviewer_keywords:
- CvLeaveSpan method
ms.assetid: 3bf65fdf-a471-4efd-ac7a-03e701bbae5d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e7f72b7cac16fa53e0f46aea60e914baf8333209
ms.sourcegitcommit: eefffa7ebe339d1297cdc12f51a813e7849d7e95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2018
---
# <a name="cvleavespan-function"></a>CvLeaveSpan İşlevi
Aralığın sonunu işaretler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C  
HRESULT CvLeaveSpan(  
   _In_ PCV_SPAN pSpan  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pSpan`  
 CvEnterSpan * önceki çağrı tarafından döndürülen nesne span. NULL olamaz.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İletiyi başarıyla yazıldığında S_OK. Hata kodu vardı herhangi bir hata durumunda. Hata koşulu denetlemek için başarılı/başarısız makroları kullanın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** cvmarkers.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Kitaplık Başvurusu](../profiling/cpp-library-reference.md)