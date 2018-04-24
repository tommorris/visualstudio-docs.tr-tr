---
title: CvCreateDefaultMarkerSeriesOfDefaultProvider işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvCreateDefaultMarkerSeriesOfDefaultProvider
helpviewer_keywords:
- CvCreateDefaultMarkerSeriesOfDefaultProvider method
ms.assetid: 24eb80f8-8fca-4c47-93b5-bb1eb8ffdffd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 418acf8e296446785fb0cda5d0a97f52754050e2
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="cvcreatedefaultmarkerseriesofdefaultprovider-function"></a>CvCreateDefaultMarkerSeriesOfDefaultProvider İşlevi
Varsayılan bir sağlayıcı varsayılan işaret dizi oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT CvCreateDefaultMarkerSeriesOfDefaultProvider(  
   _Out_ PCV_PROVIDER* ppProvider,  
   _Out_ PCV_MARKERSERIES* ppMarkerSeries  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppProvider`  
 Sağlayıcı nesne değişkeni adresidir. Adres boş olamaz, değişkeni herhangi bir değer olabilir.  
  
 `ppMarkerSeries`  
 İşaretçi serisi nesne değişkeni adresidir. Adres boş olamaz, değişkeni herhangi bir değer olabilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Hem sağlayıcı hem de işaret serisi başarıyla oluşturulduğunda veya tüm hatalar oluştu. hata kodu var. durumda S_OK. Hata koşulu denetlemek için başarılı/başarısız makroları kullanın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** cvmarkers.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Kitaplık Başvurusu](../profiling/cpp-library-reference.md)