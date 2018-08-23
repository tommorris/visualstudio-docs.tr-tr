---
title: CvCreateMarkerSeries işlevi | Microsoft Docs
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
- cvmarkers/CvCreateMarkerSeriesA
- cvmarkers/CvCreateMarkerSeriesW
helpviewer_keywords:
- CvCreateMarkerSeriesA method
- CvCreateMarkerSeriesW method
ms.assetid: e280530b-137a-43a7-8643-aa514ab86ed7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 332c7b54ca47334e1415c50751301b51912648f1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695074"
---
# <a name="cvcreatemarkerseries-function"></a>CvCreateMarkerSeries İşlevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CvCreateMarkerSeries işlevi](https://docs.microsoft.com/visualstudio/profiling/cvcreatemarkerseries-function).  
  
İşaret için belirli bir sağlayıcı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
 Cvınitprovider tarafından önceden başlatılan sağlayıcı nesnesi. NULL olamaz.  
  
 `pSeriesName`  
 İşaret seri adı. NULL olamaz, ancak boş dizeye izin verilir.  
  
 `ppMarkerSeries`  
 İşaret serisi bağlam depolayacak bir çıkış değişkeni adresi. NULL olamaz.  
  
## <a name="return-value"></a>Dönüş Değeri  
 S_OK işaret serisi başarıyla oluşturulduğunda veya hata kodu var. durumda tüm hatalar. Hata koşulu denetleyen için başarılı/başarısız makroları kullanın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** cvmarkers.h  
  
 **Unicode:** CvCreateMarkerSeriesW  
  
 **ANSI:** CvCreateMarkerSeriesA  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Kitaplık Başvurusu](../profiling/cpp-library-reference.md)



