---
title: DONT_SAVE_VSGLOG_TO_TEMP | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f27ab0e6-9575-4ca0-9901-37d3e5c3a2f5
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a43bc90e0f40f8a7b9aa9c15c198ed3e82cf0685
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696055"
---
# <a name="dontsavevsglogtotemp"></a>DONT_SAVE_VSGLOG_TO_TEMP
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [DONT_SAVE_VSGLOG_TO_TEMP](https://docs.microsoft.com/visualstudio/debugger/graphics/dont-save-vsglog-to-temp).  
  
Grafik günlük dosyası, kullanıcı için geçici dosyalar dizini kaydedilip kaydedilmediğini kendi varlığı tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
#define DONT_SAVE_VSGLOG_TO_TEMP  
```  
  
## <a name="value"></a>Değer  
 Grafik günlük dosyası olup olmadığını belirler, kendi varlığı veya yokluğuna göre bir önişlemci sembolü kullanıcının geçici dosyalar dizinine kaydedilir. Bu simge tanımlanmadıysa sonra dosya adı tarafından tanımlanan `VSG_DEFAULT_RUN_FILENAME` yakalanan uygulamayı geçerli dizine göreli veya mutlak bir yol; Aksi takdirde, dosya adı tarafından tanımlanan `VSG_DEFAULT_RUN_FILENAME` ve kullanıcının geçici dosyalar dizini göreli olamaz mutlak bir yol.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanıcının ayrıcalıkları bağlı olarak, grafik günlük dosyasını rastgele bir konuma kaydedilmesi mümkün olmayabilir. Seçmek konumun kullanıcı tarafından yazılabilir olup emin değilseniz, grafik günlüklerini kullanıcının geçici dosyalar dizini veya bilinen iyi başka bir konuma kaydetmek tercih ettiğiniz öneririz.  
  
 Grafik günlük dosyası için geçici dosyalar dizini kaydedilmesini engellemek için gerekir tanımlanmış `DONT_SAVE_VSGLOG_TO_TEMP` dahil önce `vsgcapture.h`.  
  
## <a name="example"></a>Örnek  
 Bu örnek konak makinesi üzerinde mutlak bir yol için grafik günlük dosyasını kaydetmeyi nasıl gösterir.  
  
```  
// Define DONT_SAVE_VSGLOG_TO_TEMP and VSG_DEFAULT_RUN_FILENAME before including vsgcapture.h  
#define DONT_SAVE_VSGLOG_TO_TEMP  
#define VSG_DEFAULT_RUN_FILENAME L"C:\\Graphics Diagnostics Captures\\default.vsglog"  
  
#include <vsgcapture.h>  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSG_DEFAULT_RUN_FILENAME](../debugger/vsg-default-run-filename.md)



