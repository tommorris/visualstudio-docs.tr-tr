---
title: 'CA1601: Güç durumu değişikliklerini önleyen zamanlayıcılar kullanmayın'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
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
ms.openlocfilehash: 669f0ffc2e61d67bd57e965a4030b17af1eb1bb2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31914594"
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