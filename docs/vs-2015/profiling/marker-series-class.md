---
title: marker_series sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::marker_series
helpviewer_keywords:
- Concurrency::diagnostic::marker_series class
ms.assetid: b8445ed0-c512-4f92-b6b4-3d05c044f939
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 18967d9f89f701dd02feb70670147db3f1275978
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633515"
---
# <a name="markerseries-class"></a>marker_series Sınıfı
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [marker_series sınıfı](https://docs.microsoft.com/visualstudio/profiling/marker-series-class).  
  
Tek bir sağlayıcı tarafından oluşturulan olayları seri bir kanalı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class marker_series;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[marker_series::marker_series Oluşturucusu](../profiling/marker-series-marker-series-constructor.md)|Yeni bir örneğini başlatır `marker_series` sınıfı.|  
|[marker_series::~marker_series Yok Edicisi](../profiling/marker-series-tilde-marker-series-destructor.md)|Marker_series nesnesini yok eder ve ayrılan tüm kaynakları serbest bırakır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[marker_series::is_enabled Metodu](../profiling/marker-series-is-enabled-method.md)|Tüm oturum sağlayıcısı etkin olmadığını belirler.|  
|[marker_series::write_alert Metodu](../profiling/marker-series-write-alert-method.md)|Bir uyarı eşzamanlılık görselleştiricisi izleme dosyasına yazar.|  
|[marker_series::write_flag Metodu](../profiling/marker-series-write-flag-method.md)|Bayrak eşzamanlılık görselleştiricisi izleme dosyasına yazar.|  
|[marker_series::write_message Metodu](../profiling/marker-series-write-message-method.md)|Eşzamanlılık görselleştiricisi izleme dosyasının bir ileti yazar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `marker_series`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** cvmarkersobj.h  
  
 **Namespace:** Concurrency::diagnostic  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tanılama Ad Alanı](../profiling/diagnostic-namespace.md)



