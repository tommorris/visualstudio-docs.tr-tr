---
title: 'CA1600: Boş işlem önceliğini kullanmayın'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotUseIdleProcessPriority
- CA1600
helpviewer_keywords:
- CA1600
- DoNotUseIdleProcessPriority
ms.assetid: 9b0d073b-78b6-41be-8ef3-14692a735283
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f3dcac11312b15049c743d596914b06819000801
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31915968"
---
# <a name="ca1600-do-not-use-idle-process-priority"></a>CA1600: Boş işlem önceliğini kullanmayın
|||
|-|-|
|TypeName|DoNotUseIdleProcessPriority|
|CheckId|CA1600|
|Kategori|Microsoft.Mobility|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 İşlemler ayarlamak bu kural oluşur `ProcessPriorityClass.Idle`.

## <a name="rule-description"></a>Kural Tanımı
 İşlem önceliğini Boşta olarak ayarlamayın. Bulunan işlemlerin `System.Diagnostics.ProcessPriorityClass.Idle` Aksi takdirde boş olacaktır ve bu nedenle bekleme engeller CPU kaplar.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Ayarlama işlemleri `ProcessPriorityClass.BelowNormal`.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural, yalnızca boş işlem önceliğini gereklidir ve mobility konuları güvenle yoksayılabilir gizlenen.