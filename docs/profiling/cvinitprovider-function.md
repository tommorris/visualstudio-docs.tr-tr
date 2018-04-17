---
title: Cvınitprovider işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvInitProvider
helpviewer_keywords:
- CvInitProvider method
ms.assetid: ba1863ad-e35f-4d34-a2f2-5e68957d1915
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 00aa6f44fc33a4bbaf950b929a1b57a4a13eb6dd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="cvinitprovider-function"></a>CvInitProvider İşlevi
İşaretçi sağlayıcıyı başlatır. Diğer eşzamanlılık görselleştiricisi SDK işlevleri önce çağrılacak sahiptir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT CvInitProvider(  
   _In_ const GUID* pGuid,  
   _Out_ PCV_PROVIDER* ppProvider  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pGuid`  
 Sağlayıcı GUID. NULL olamaz.  
  
 `ppProvider`  
 Sağlayıcı içeriği depolayan bir çıkış değişkeninin adresi. NULL olamaz.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sağlayıcı başarıyla başlatıldı veya tüm hatalar oluştu. hata kodu var. durumda S_OK. Hata koşulu denetlemek için başarılı/başarısız makroları kullanın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** cvmarkers.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Kitaplık Başvurusu](../profiling/cpp-library-reference.md)