---
title: Cvısenabled işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvIsEnabledEx
- cvmarkers/CvIsEnabled
helpviewer_keywords:
- CvIsEnabled method
- CvIsEnabledEx method
ms.assetid: 2e4fea6d-758d-4150-8744-6102a1d58c1c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 70448c74220c0643654b8cc951bba2d20fb5fdef
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="cvisenabled-function"></a>CvIsEnabled İşlevi
Herhangi bir oturumunda belirtilen ETW sağlayıcı etkin olup olmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT CvIsEnabled(  
   _In_ PCV_PROVIDER pProvider  
);  
HRESULT CvIsEnabledEx(  
   _In_ PCV_PROVIDER pProvider,  
   _In_ CV_IMPORTANCE level,  
   _In_ int category  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `category`  
 Kategori.  
  
 `level`  
 Önem düzeyi.  
  
 `pProvider`  
 Geçerli sağlayıcı nesnesi. NULL olamaz.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sağlayıcı etkinse S_OK. Sağlayıcı şu anda devre dışıysa S_FALSE. Hata kodu vardı herhangi bir hata durumunda. BAŞARISIZ makrosu S_OK/S_FALSE için denetleyin ve hata koşulu için denetlemek için kullanın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** cvmarkers.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Kitaplık Başvurusu](../profiling/cpp-library-reference.md)