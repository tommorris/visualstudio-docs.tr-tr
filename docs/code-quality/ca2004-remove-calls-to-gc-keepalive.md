---
title: "CA2004: GC.KeepAlive'a çağrıları kaldırın"
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
helpviewer_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
ms.assetid: bc543b5b-23eb-4b45-abc2-9325cd254ac2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3845826ef1c88eaa40c8cf05936080eb320bdecc
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45546817"
---
# <a name="ca2004-remove-calls-to-gckeepalive"></a>CA2004: GC.KeepAlive'a çağrıları kaldırın
|||
|-|-|
|TypeName|RemoveCallsToGCKeepAlive|
|CheckId|CA2004|
|Kategori|Microsoft.Reliability|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Sınıfları kullanın `SafeHandle` ancak yine de çağrıları içeren `GC.KeepAlive`.

## <a name="rule-description"></a>Kural açıklaması
 İçin dönüştürüyorsanız `SafeHandle` kullanım, tüm çağrıları kaldırın `GC.KeepAlive` (nesne). Bu durumda, sınıflar çağrı yapmamalıdır `GC.KeepAlive`, bir sonlandırıcı olmayan ancak dayanır varsayılarak `SafeHandle` kendileri için işletim sistemini tamamlanması.  Ancak bir çağrıda bırakmanın maliyeti `GC.KeepAlive` ölçülen performans, perception Önemsiz olabilir, çağrı `GC.KeepAlive` gerekli ya da artık mevcut olabilecek bir sorunu kod için daha zor yapar bir ömrü çözmek yeterli korur.

## <a name="how-to-fix-violations"></a>İhlaller nasıl düzeltilir?
 Kaldırın `GC.KeepAlive`.

## <a name="when-to-suppress-warnings"></a>Uyarılar bastırıldığında
 Yalnızca dönüştürmek teknik olarak doğru değilse, bu uyarının gösterilmemesi `SafeHandle` sınıfınıza kullanımı.