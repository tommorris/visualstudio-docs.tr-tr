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
ms.openlocfilehash: 033c7a73c404a2bd5146a17a1a7b4f2fa8b9c540
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45545719"
---
# <a name="ca1601-do-not-use-timers-that-prevent-power-state-changes"></a>CA1601: Güç durumu değişikliklerini önleyen zamanlayıcılar kullanmayın
|||
|-|-|
|TypeName|DoNotUseTimersThatPreventPowerStateChanges|
|CheckId|CA1601|
|Kategori|Microsoft.Mobility|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Zamanlayıcı, saniye başına birden fazla kez gerçekleşecek şekilde ayarlanan bir aralığı vardır.

## <a name="rule-description"></a>Kural açıklaması
 İkinci ya da birden daha sık gerçekleşmesine kullanım zamanlayıcılar başına bir kez daha sık yoklama değil saniye başına zaman. Yüksek frekanslı dönemsel faaliyet CPU'yu meşgul tutar ve sabit diski gösteren güç tasarruflu zamanlayıcılarla müdahale edilir.

## <a name="how-to-fix-violations"></a>İhlaller nasıl düzeltilir?
 Zamanlayıcı aralıkları saniyede saatten daha az bir kez gerçekleşecek şekilde ayarlayın.

## <a name="when-to-suppress-warnings"></a>Uyarılar bastırıldığında
 Bu kural yalnızca saniye başına birden fazla kez Zamanlayıcı tetikleme gereklidir ve mobility konuları güvenle görmezden gelinebilir atlanması.