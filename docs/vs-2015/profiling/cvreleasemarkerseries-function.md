---
title: CvReleaseMarkerSeries işlevi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- cvmarkers/CvReleaseMarkerSeries
helpviewer_keywords:
- CvReleaseMarkerSeries method
ms.assetid: 3b4711ee-e534-411d-9128-f69cd7932a48
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a8df22a27f23395ac3de6bb3b4f28c7746dd10ba
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684516"
---
# <a name="cvreleasemarkerseries-function"></a>CvReleaseMarkerSeries İşlevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CvReleaseMarkerSeries işlevi](https://docs.microsoft.com/visualstudio/profiling/cvreleasemarkerseries-function).  
  
İşaret serisi serbest bırakır. Aksi takdirde uygulama serbest çökebilir sonra işaret serisi nesnesi kullanmayın. İşaret serisi yayımlamayı hatası bellek sızıntısına neden olur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT CvReleaseMarkerSeries(  
   _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pMarkerSeries`  
 Nesne değişkeni sağlayıcı adresi. Adresi boş olamaz, değişken herhangi bir değere sahip olabilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 S_OK işaret serisi başarıyla serbest bırakıldı veya hata kodu var. durumda tüm hatalar. Hata koşulu denetleyen için başarılı/başarısız makroları kullanın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** cvmarkers.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Kitaplık Başvurusu](../profiling/cpp-library-reference.md)



