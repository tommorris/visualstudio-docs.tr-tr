---
title: "Şifreleme uyarıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d96723ea-a293-488d-b9db-adb437e50cdd
caps.latest.revision: "7"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4936482aea909938e135e8f61164955dacc9e20b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="cryptography-warnings"></a>Şifreleme uyarıları
Şifreleme uyarıları güvenli kitaplıklar ve şifreleme doğru kullanımı aracılığıyla uygulamaları destekler. Bu uyarılar, programınızdaki güvenlik açıklarını önlemeye yardımcı olur. Bu uyarılardan birini devre dışı bırakırsanız, bunun sebebini kodunuzda açıkça işaretlemelisiniz ve ayrıca geliştirme projeniz için güvenlik çalışanını bilgilendirmelisiniz.  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[CA5350: Zayıf şifreleme algoritmalarına kullanmayın](../code-quality/ca5350-do-not-use-weak-cryptographic-algorithms.md)|Zayıf şifreleme algoritmalarını ve karma İşlevler, birçok nedenden dolayı bugün kullanılır, ancak bunlar bütünlüğü korudukları verilerin ve gizliliği güvence altına almak için kullanılmamalıdır.        Kodda TripleDES, SHA1 veya RIPEMD160 algoritmaları bulduğunda bu kural tetikler.|  
|[CA5351 Bozuk şifreleme algoritmaları kullanmayın](../code-quality/ca5351-do-not-use-broken-cryptographic-algorithms.md)|Şifreleme bozuk algoritmaları güvenli kabul edilmez ve bunların kullanılması kesinlikle kaçının olması gerekir. Bu kod MD5 karma algoritma veya DES veya RC2 şifreleme algoritması bulduğunda bu kural tetikler.|