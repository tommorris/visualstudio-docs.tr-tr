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
ms.openlocfilehash: 4b193ff33d979917342679e115cdb973cb3b7ad5
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="markerimportance-enumeration"></a>marker_importance Numaralandırması
Eşzamanlılık görselleştiricisi işaret önem düzeyini temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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