---
title: CvReleaseProvider işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvReleaseProvider
helpviewer_keywords:
- CvReleaseProvider method
ms.assetid: 8d74379e-295d-452b-bd5f-0769df387d4f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9e4620a4322fedb7fb6337c3f4fd7cb7e22b39df
ms.sourcegitcommit: eefffa7ebe339d1297cdc12f51a813e7849d7e95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2018
---
# <a name="cvreleaseprovider-function"></a>CvReleaseProvider İşlevi
Sürümler işaret sağlayıcısı. Bu sağlayıcı önceden oluşturulmuş işaret dizi işaret sağlayıcısı serbest etkilemez. İşaretçi serisi sürüm CvReleaseMarkerSeries çağrısı tarafından ayrı ayrı olması gerekir. Sağlayıcı yayımlamayı hatası bellek sızıntısı neden olur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C  
HRESULT CvReleaseProvider(  
   _In_ PCV_PROVIDER pProvider  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pProvider`  
 Sağlayıcı bağlamı. NULL olamaz.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sağlayıcı başarıyla yayınlandığı veya tüm hatalar oluştu. hata kodu var. durumda olduğunda S_OK. Hata koşulu denetlemek için başarılı/başarısız makroları kullanın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** cvmarkers.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Kitaplık Başvurusu](../profiling/cpp-library-reference.md)