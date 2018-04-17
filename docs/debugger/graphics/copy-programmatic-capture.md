---
title: Kopyalama (programlı yakalama) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 30ec235a-0abb-44b9-8852-61bc9e67ce22
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a658f458b6f2dac48ad19f60e2491ad9d6e94406
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="copy-programmatic-capture"></a>Kopyalama (Programlı Yakalama)
Etkin Grafikler (.vsglog) günlük dosyasının içeriğini yeni bir dosyaya kopyalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
void Copy(  
  wchar_t const * szNewVSGLog  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `szNewVSGLog`  
 Yeni grafik günlük dosyasının dosya adı.  
  
## <a name="remarks"></a>Açıklamalar  
 Yeni bir dosyaya grafik bilgilerini kopyalamak için zaten bazı grafik bilgilerini yakalanan gerekir; Aksi takdirde, hiçbir şey olmaz.