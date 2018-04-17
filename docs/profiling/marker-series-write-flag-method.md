---
title: marker_series::write_flag yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkersojb/Concurrency::diagnostic::marker_series::write_flag
helpviewer_keywords:
- Concurrency::diagnostic::marker_series::write_flag method
ms.assetid: ca07f388-e5d5-46fd-b991-fe6e9029a68f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c979a2c37f786a4766952189cb300f32beff363c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="markerserieswriteflag-method"></a>marker_series::write_flag Yöntemi
Bir bayrak eşzamanlılık görselleştiricisi izleme dosyasına yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void write_flag(  
   _In_ LPCTSTR _Format,  
   ...  
);  
void write_flag(  
   marker_importance _Importance,  
   _In_ LPCTSTR _Format,  
   ...  
);  
void write_flag(  
   int _Category,  
   _In_ LPCTSTR _Format,  
   ...  
);  
void write_flag(  
   marker_importance _Importance,  
   int _Category,  
   _In_ LPCTSTR _Format,  
   ...  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `_Format`  
 Metin içeren bileşik biçim dizesi bağımsız değişken listesinde nesnelere karşılık gelen, sıfır veya daha fazla biçimi öğeleri ile intermixed.  
  
 `_Importance`  
 Önem düzeyi.  
  
 `_Category`  
 Kategori.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** cvmarkersobj.h  
  
 **Namespace:** Concurrency::diagnostic  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [marker_series Sınıfı](../profiling/marker-series-class.md)