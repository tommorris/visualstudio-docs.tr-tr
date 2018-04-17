---
title: Şifreleme uyarıları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
ms.assetid: d96723ea-a293-488d-b9db-adb437e50cdd
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ed273485df4e8bbd3b76dfd39fa38ec697052bb8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="cryptography-warnings"></a>Şifreleme uyarıları
Şifreleme uyarıları güvenli kitaplıklar ve şifreleme doğru kullanımı aracılığıyla uygulamaları destekler. Bu uyarılar, programınızdaki güvenlik açıklarını önlemeye yardımcı olur. Bu uyarılardan birini devre dışı bırakırsanız, bunun sebebini kodunuzda açıkça işaretlemelisiniz ve ayrıca geliştirme projeniz için güvenlik çalışanını bilgilendirmelisiniz.  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[CA5350: Zayıf Şifreleme Algoritmaları Kullanmayın](../code-quality/ca5350-do-not-use-weak-cryptographic-algorithms.md)|Zayıf şifreleme algoritmalarını ve karma İşlevler, birçok nedenden dolayı bugün kullanılır, ancak bunlar bütünlüğü korudukları verilerin ve gizliliği güvence altına almak için kullanılmamalıdır.        Kodda TripleDES, SHA1 veya RIPEMD160 algoritmaları bulduğunda bu kural tetikler.|  
|[CA5351: Bozuk Şifreleme Algoritmaları Kullanmayın](../code-quality/ca5351-do-not-use-broken-cryptographic-algorithms.md)|Şifreleme bozuk algoritmaları güvenli kabul edilmez ve bunların kullanılması kesinlikle kaçının olması gerekir. Bu kod MD5 karma algoritma veya DES veya RC2 şifreleme algoritması bulduğunda bu kural tetikler.|