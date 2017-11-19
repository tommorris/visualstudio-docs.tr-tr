---
title: "marker_importance numaralandırması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cvmarkersobj/Concurrency::diagnostic::marker_importance
helpviewer_keywords: Concurrency::diagnostic::marker_importance enumeration
ms.assetid: d5524ea0-0227-4d8e-9122-332291042df5
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d09138f90b94d3b37c4a20fbe53f311fa29a36e9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Tanılama Namespace](../profiling/diagnostic-namespace.md)