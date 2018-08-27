---
title: 'CA1600: boş işlem önceliğini kullanmayın | Microsoft Docs'
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
- DoNotUseIdleProcessPriority
- CA1600
helpviewer_keywords:
- CA1600
- DoNotUseIdleProcessPriority
ms.assetid: 9b0d073b-78b6-41be-8ef3-14692a735283
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: b211c1ab646d27cf32290d3c5c306719ba7decff
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902570"
---
# <a name="ca1600-do-not-use-idle-process-priority"></a>CA1600: Boş işlem önceliğini kullanmayın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1600: boş işlem önceliğini kullanmayın](https://docs.microsoft.com/visualstudio/code-quality/ca1600-do-not-use-idle-process-priority).

|||
|-|-|
|TypeName|DoNotUseIdleProcessPriority|
|CheckId|CA1600|
|Kategori|Microsoft.Mobility|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bu kural işlemleri ayarlandığından oluşur `ProcessPriorityClass.Idle`.

## <a name="rule-description"></a>Kural Tanımı
 İşlem önceliğini Boşta olarak ayarlamayın. Sahip işlemler `System.Diagnostics.ProcessPriorityClass.Idle` Aksi durumda boş olacak ve bu nedenle beklemeyi engeller, CPU dolduracaktır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Ayarlama işlemleri `ProcessPriorityClass.BelowNormal`.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural yalnızca boş işlem önceliğini gereklidir ve mobility konuları güvenle görmezden gelinebilir atlanması.



