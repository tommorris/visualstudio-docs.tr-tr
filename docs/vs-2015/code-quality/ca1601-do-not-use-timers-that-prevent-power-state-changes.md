---
title: 'CA1601: güç durumu değişikliklerini önleyen zamanlayıcılar kullanmayın | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
helpviewer_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
ms.assetid: b8028c92-0696-4c54-9773-0028f29bda9a
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: de1b5e943274b80d8a46d05dcd0cdb8fe8b2b82a
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900560"
---
# <a name="ca1601-do-not-use-timers-that-prevent-power-state-changes"></a>CA1601: Güç durumu değişikliklerini önleyen zamanlayıcılar kullanmayın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1601: güç durumu değişikliklerini önleyen zamanlayıcılar kullanmayın](https://docs.microsoft.com/visualstudio/code-quality/ca1601-do-not-use-timers-that-prevent-power-state-changes).

|||
|-|-|
|TypeName|DoNotUseTimersThatPreventPowerStateChanges|
|CheckId|CA1601|
|Kategori|Microsoft.Mobility|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Zamanlayıcı, saniye başına birden fazla kez gerçekleşecek şekilde ayarlanan bir aralığı vardır.

## <a name="rule-description"></a>Kural Tanımı
 İkinci ya da birden daha sık gerçekleşmesine kullanım zamanlayıcılar başına bir kez daha sık yoklama değil saniye başına zaman. Yüksek frekanslı dönemsel faaliyet CPU'yu meşgul tutar ve sabit diski gösteren güç tasarruflu zamanlayıcılarla müdahale edilir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Zamanlayıcı aralıkları saniyede saatten daha az bir kez gerçekleşecek şekilde ayarlayın.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural yalnızca saniye başına birden fazla kez Zamanlayıcı tetikleme gereklidir ve mobility konuları güvenle görmezden gelinebilir atlanması.



