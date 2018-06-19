---
title: DONT_SAVE_VSGLOG_TO_TEMP | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: f27ab0e6-9575-4ca0-9901-37d3e5c3a2f5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b70ddf2933b8bd2d96db1636612cb35a6a759a1a
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31473812"
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