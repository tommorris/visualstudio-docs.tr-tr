---
title: DONT_SAVE_VSGLOG_TO_TEMP | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f27ab0e6-9575-4ca0-9901-37d3e5c3a2f5
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5a98081aa73d11d9a2edea9293804d6c83a211d4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="dontsavevsglogtotemp"></a>DONT_SAVE_VSGLOG_TO_TEMP
Grafik günlük dosyası için kullanıcının geçici dosyalar dizini kaydedilip kaydedilmediğini tarafından varlığını tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
#define DONT_SAVE_VSGLOG_TO_TEMP  
```  
  
## <a name="value"></a>Değer  
 Kendi varlığı veya yokluğuna göre grafik günlük dosyası olup olmadığını belirleyen bir önişlemci sembol kullanıcının geçici dosyalar dizinine kaydedilir. Bu simgenin tanımlanan sonra dosya adı tarafından tanımlanan `VSG_DEFAULT_RUN_FILENAME` yakalanan uygulama geçerli dizin göreli veya mutlak bir yol; Aksi halde, dosya adı tarafından tanımlanan `VSG_DEFAULT_RUN_FILENAME` göre kullanıcının geçici dosyalar dizini ve olamaz mutlak bir yol.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanıcının ayrıcalıklarına bağlı olarak, grafik günlük dosyası rasgele bir konuma kaydedilmesi mümkün olmayabilir. Konumun seçmeniz kullanıcı tarafından yazılabilir mi emin değilseniz, grafik günlükleri kullanıcının geçici dosyalar dizini veya başka bir bilinen iyi konuma kaydetmek tercih ettiğiniz öneririz.  
  
 Geçici dosyalar dizini kaydedilen grafik günlük dosyası önlemek için gereken tanımlanan `DONT_SAVE_VSGLOG_TO_TEMP` dahil önce `vsgcapture.h`.  
  
## <a name="example"></a>Örnek  
 Bu örnek, grafik günlük dosyası konak makinesi üzerinde mutlak bir yol kaydetmek gösterilmiştir.  
  
```  
// Define DONT_SAVE_VSGLOG_TO_TEMP and VSG_DEFAULT_RUN_FILENAME before including vsgcapture.h  
#define DONT_SAVE_VSGLOG_TO_TEMP  
#define VSG_DEFAULT_RUN_FILENAME L"C:\\Graphics Diagnostics Captures\\default.vsglog"  
  
#include <vsgcapture.h>  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSG_DEFAULT_RUN_FILENAME](vsg-default-run-filename.md)