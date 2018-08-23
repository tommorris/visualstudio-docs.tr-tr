---
title: CvReleaseProvider işlevi | Microsoft Docs
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
- cvmarkers/CvReleaseProvider
helpviewer_keywords:
- CvReleaseProvider method
ms.assetid: 8d74379e-295d-452b-bd5f-0769df387d4f
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8e62e897b56407ab985125361700da60d4e0fdcd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686122"
---
# <a name="cvreleaseprovider-function"></a>CvReleaseProvider İşlevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CvReleaseProvider işlevi](https://docs.microsoft.com/visualstudio/profiling/cvreleaseprovider-function).  
  
İşaretleyici sağlayıcısını yayınlar. İşaretleyici sağlayıcısını serbest bu sağlayıcı dizi önceden oluşturulmuş işaret etkilemez. İşaret serisi CvReleaseMarkerSeries çağrı tarafından ayrı ayrı serbest bırakılması gerekir. Sağlayıcı yayımlamayı hatası bellek sızıntısına neden olur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT CvReleaseProvider(  
   _In_ PCV_PROVIDER pProvider  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pProvider`  
 Sağlayıcı bağlamı. NULL olamaz.  
  
## <a name="return-value"></a>Dönüş Değeri  
 S_OK sağlayıcısı başarıyla serbest bırakıldı veya hata kodu var. durumda tüm hatalar. Hata koşulu denetleyen için başarılı/başarısız makroları kullanın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** cvmarkers.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Kitaplık Başvurusu](../profiling/cpp-library-reference.md)



