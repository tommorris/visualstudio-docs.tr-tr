---
title: VSG_DEFAULT_RUN_FILENAME | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: ea549d2f-c857-458c-93c7-bc5a2d11d15d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cb0853e51a5c56ed36babb3474d33adac480e8e4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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