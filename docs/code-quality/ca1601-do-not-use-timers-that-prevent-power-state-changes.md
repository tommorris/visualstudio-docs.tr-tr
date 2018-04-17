---
title: 'CA1601: güç durumu değişikliklerini önleyen zamanlayıcılar kullanmayın | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
helpviewer_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
ms.assetid: b8028c92-0696-4c54-9773-0028f29bda9a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 270c030d4d4b829fb1e7d17308a4ae6f0ad17539
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1601-do-not-use-timers-that-prevent-power-state-changes"></a>CA1601: Güç durumu değişikliklerini önleyen zamanlayıcılar kullanmayın
|||  
|-|-|  
|TypeName|DoNotUseTimersThatPreventPowerStateChanges|  
|CheckId|CA1601|  
|Kategori|Microsoft.Mobility|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir süreölçeri saniye başına birden fazla kez gerçekleşecek şekilde ayarlanan bir aralığı vardır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 İkinci ya da birden fazla sıklıkla oluşuyor kullanım zamanlayıcılar başına bir kez daha sık yoklamak değil saniyede zaman. Yüksek frekanslı dönemsel faaliyet CPU'yu meşgul tutar ve sabit diski gösteren güç tasarruflu zamanlayıcılarla müdahale edilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Zamanlayıcı aralıkları saniye başına değerinden bir kez gerçekleşecek şekilde ayarlayın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural, yalnızca Zamanlayıcı saniye başına birden fazla kez tetikleme gereklidir ve mobility konuları güvenle yoksayılabilir gizlenen.