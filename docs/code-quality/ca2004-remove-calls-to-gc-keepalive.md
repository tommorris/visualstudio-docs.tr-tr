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
ms.openlocfilehash: fa59c6797d81202637f44799327e6b2802d822eb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31917195"
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