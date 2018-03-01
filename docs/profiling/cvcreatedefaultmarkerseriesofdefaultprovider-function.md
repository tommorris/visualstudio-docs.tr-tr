---
title: "CvCreateDefaultMarkerSeriesOfDefaultProvider işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cvmarkers/CvCreateDefaultMarkerSeriesOfDefaultProvider
helpviewer_keywords:
- CvCreateDefaultMarkerSeriesOfDefaultProvider method
ms.assetid: 24eb80f8-8fca-4c47-93b5-bb1eb8ffdffd
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3fae064fab478de88f6b5f66c41df7e4e57d4ead
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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