---
title: CvCreateMarkerSeries işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvCreateMarkerSeriesA
- cvmarkers/CvCreateMarkerSeriesW
helpviewer_keywords:
- CvCreateMarkerSeriesA method
- CvCreateMarkerSeriesW method
ms.assetid: e280530b-137a-43a7-8643-aa514ab86ed7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3aa1acd52eeffe454dda3f081c97865290245644
ms.sourcegitcommit: eefffa7ebe339d1297cdc12f51a813e7849d7e95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2018
---
# <a name="cvcreatemarkerseries-function"></a>CvCreateMarkerSeries İşlevi
İşaretçi serisi için belirli bir sağlayıcı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C  
_Check_return_ HRESULT CvCreateMarkerSeriesW(  
    _In_ PCV_PROVIDER  pProvider,  
    _In_ LPCWSTR pSeriesName,  
    _Out_ PCV_MARKERSERIES* ppMarkerSeries);  
  
_Check_return_ HRESULT CvCreateMarkerSeriesA(  
    _In_ PCV_PROVIDER  pProvider,  
    _In_ LPCSTR pSeriesName,  
    _Out_ PCV_MARKERSERIES* ppMarkerSeries);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pProvider`  
 Cvınitprovider tarafından daha önce başlatılmış sağlayıcı nesnesi. NULL olamaz.  
  
 `pSeriesName`  
 İşaretçi seri adı. BOŞ olamaz, ancak boş dize izin verilir.  
  
 `ppMarkerSeries`  
 İşaretçi serisi bağlam depolayan bir çıkış değişkeninin adresi. NULL olamaz.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşaretçi serisi başarıyla oluşturulduğunda veya tüm hatalar oluştu. hata kodu var. durumda S_OK. Hata koşulu denetlemek için başarılı/başarısız makroları kullanın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** cvmarkers.h  
  
 **Unicode:** CvCreateMarkerSeriesW  
  
 **ANSI:** CvCreateMarkerSeriesA  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Kitaplık Başvurusu](../profiling/cpp-library-reference.md)