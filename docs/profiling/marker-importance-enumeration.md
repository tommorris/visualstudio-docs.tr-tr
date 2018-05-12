---
title: marker_importance numaralandırması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::marker_importance
helpviewer_keywords:
- Concurrency::diagnostic::marker_importance enumeration
ms.assetid: d5524ea0-0227-4d8e-9122-332291042df5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9f4c87cfa1504c997cefdc68416dac9923fa10b4
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
---
# <a name="markerimportance-enumeration"></a>marker_importance Numaralandırması
Eşzamanlılık görselleştiricisi işaret önem düzeyini temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum marker_importance;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`critical_importance`|İşaretin kritik öneme sahip olduğunu belirtir.|  
|`high_importance`|İşaretin yüksek önem düzeyine sahip olduğunu belirtir.|  
|`low_importance`|İşaretin düşük önem olduğunu belirtir.|  
|`normal_importance`|İşaretin normal önem olduğunu belirtir.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** cvmarkersobj.h  
  
 **Namespace:** Concurrency::diagnostic  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tanılama Ad Alanı](../profiling/diagnostic-namespace.md)