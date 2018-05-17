---
title: CvCreateMarkerSeriesWithCodePageA işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmakers/CvCreateMarkerSeriesWithCodePageA
helpviewer_keywords:
- CvCreateMarkerSeriesWithCodePageA method
ms.assetid: 3d7ed601-2222-4be9-a557-f217db008753
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4f79c85714ca27846c77529859789cc4465eb3ac
ms.sourcegitcommit: eefffa7ebe339d1297cdc12f51a813e7849d7e95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2018
---
# <a name="cvcreatemarkerserieswithcodepagea-function"></a>CvCreateMarkerSeriesWithCodePageA İşlevi
Belirtilen sağlayıcı ve belirtilen kod sayfası için işaret serisi oluşturur. Bu işlev, açıkça işaret API ANSI işlevleri tarafından yazılan metin kod sayfası belirlemek için kullanılabilir. İzleme yakalanan ve daha sonra farklı yerel ayarlara/dilleri ile farklı makinelerde analiz durumda kod sayfası ayarı yararlı olabilir. Varsayılan olarak GetACP() işlevi tarafından döndürülen kod sayfası kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C  
HRESULT CvCreateMarkerSeriesWithCodePageA(  
   _In_ PCV_PROVIDER pProvider,  
   _In_ LPCSTR pSeriesName,  
   _In_ UINT nTextCodePage,  
   _Out_ PCV_MARKERSERIES* ppMarkerSeries  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pProvider`  
 Cvınitprovider tarafından daha önce başlatılmış sağlayıcı nesnesi. NULL olamaz.  
  
 `pSeriesName`  
 İşaretçi seri adı. BOŞ olamaz, ancak boş dize izin verilir.  
  
 `nTextCodePage`  
 Geçerli kod sayfası.  
  
 `ppMarkerSeries`  
 İşaretçi serisi bağlam depolayan bir çıkış değişkeninin adresi. NULL olamaz.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşaretçi serisi başarıyla oluşturulduğunda veya tüm hatalar oluştu. hata kodu var. durumda S_OK. Hata koşulu denetlemek için başarılı/başarısız makroları kullanın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** cvmarkers.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Kitaplık Başvurusu](../profiling/cpp-library-reference.md)