---
title: Şifreleme uyarıları
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: d96723ea-a293-488d-b9db-adb437e50cdd
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b36e174b577ccdb455e88b4bb10f061bfd2396a3
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="cryptography-warnings"></a>Şifreleme uyarıları
Şifreleme uyarıları güvenli kitaplıklar ve şifreleme doğru kullanımı aracılığıyla uygulamaları destekler. Bu uyarılar, programınızdaki güvenlik açıklarını önlemeye yardımcı olur. Bu uyarılardan birini devre dışı bırakırsanız, bunun sebebini kodunuzda açıkça işaretlemelisiniz ve ayrıca geliştirme projeniz için güvenlik çalışanını bilgilendirmelisiniz.

|Kural|Açıklama|
|----------|-----------------|
|[CA5350: Zayıf Şifreleme Algoritmaları Kullanmayın](../code-quality/ca5350-do-not-use-weak-cryptographic-algorithms.md)|Zayıf şifreleme algoritmalarını ve karma İşlevler, birçok nedenden dolayı bugün kullanılır, ancak bunlar bütünlüğü korudukları verilerin ve gizliliği güvence altına almak için kullanılmamalıdır.        Kodda TripleDES, SHA1 veya RIPEMD160 algoritmaları bulduğunda bu kural tetikler.|
|[CA5351: Bozuk Şifreleme Algoritmaları Kullanmayın](../code-quality/ca5351-do-not-use-broken-cryptographic-algorithms.md)|Şifreleme bozuk algoritmaları güvenli kabul edilmez ve bunların kullanılması kesinlikle kaçının olması gerekir. Bu kod MD5 karma algoritma veya DES veya RC2 şifreleme algoritması bulduğunda bu kural tetikler.|