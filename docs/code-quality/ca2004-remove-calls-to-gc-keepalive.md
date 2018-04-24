---
title: "CA2004: GC.KeepAlive'a çağrıları kaldırın"
ms.date: 11/04/2016
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
ms.openlocfilehash: e2f05764f5147a064815cdb744420686fb6a5a7c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2004-remove-calls-to-gckeepalive"></a>CA2004: GC.KeepAlive'a çağrıları kaldırın
|||
|-|-|
|TypeName|RemoveCallsToGCKeepAlive|
|CheckId|CA2004|
|Kategori|Microsoft.Reliability|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Sınıfları kullanım `SafeHandle` ancak hala çağrıları içeren `GC.KeepAlive`.

## <a name="rule-description"></a>Kural Tanımı
 İçin dönüştürüyorsanız `SafeHandle` kullanımı, tüm çağrıları kaldırın `GC.KeepAlive` (nesne). Bu durumda, sınıfları çağırmak olmaması gereken `GC.KeepAlive`, bir sonlandırıcı yoksa ancak Bel varsayılarak `SafeHandle` işletim sistemi işleci için bunları tamamlamak için.  Rağmen bir çağrı bırakarak maliyetini `GC.KeepAlive` performans, algısına ölçülen Önemsiz olabilir, çağrı `GC.KeepAlive` gerekli ya da artık mevcut olabilecek sorunu kodu için daha zor yapar bir ömrü çözmek yeterli korur.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Çağrıları kaldırın `GC.KeepAlive`.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Yalnızca dönüştürmek teknik olarak doğru değilse, bu uyarıyı gizleyebilirsiniz `SafeHandle` sınıfınızda kullanımı.