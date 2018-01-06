---
title: VSG_DEFAULT_RUN_FILENAME | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea549d2f-c857-458c-93c7-bc5a2d11d15d
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f7fe31b96911329089174772094784c0d0f3371c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="vsgdefaultrunfilename"></a>VSG_DEFAULT_RUN_FILENAME
Grafik günlük dosyası varsayılan dosya adını tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
#define VSG_DEFAULT_FILENAME filename  
```  
  
#### <a name="parameters"></a>Parametreler  
 `filename`  
 Grafik bilgilerini programla yakalandığında varsayılan olarak grafik günlük dosyasına verilen dosya adı.  
  
## <a name="value"></a>Değer  
 Günlük dosyası grafik dosya adını temsil eden bir dize. Varsayılan olarak, L"default.vsglog".  
  
```C++  
#define VSG_DEFAULT_FILENAME L"default.vsglog"  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa önişlemci sembolü `DONT_SAVE_VSGLOG_TO_TEMP` tanımlanan, ardından dosya adı yakalanan uygulama geçerli dizine göreli veya mutlak bir yol; Aksi takdirde, bu kullanıcının geçici dosyalar dizini göreli ve mutlak bir yol olamaz.  
  
 Eklediğiniz önce tanımlanan dosya adını değiştirmek için onu tanımlamalısınız `vsgcapture.h` programınızdaki.  
  
## <a name="example"></a>Örnek  
 Bu örnek yakalama dosyanın varsayılan dosya adını değiştirmek nasıl gösterir:  
  
```C++  
// Redefine the default capture filename before including vsgcapture.h  
#define VSG_DEFAULT_FILENAME L"capture.vsglog"  
  
#include <vsgcapture.h>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DONT_SAVE_VSGLOG_TO_TEMP](dont-save-vsglog-to-temp.md)