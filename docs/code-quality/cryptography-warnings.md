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
ms.workload: multiple
ms.openlocfilehash: 5270a9b2cb2801d80dc9a087821e73d6c54bfe1c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="cryptography-warnings"></a>Şifreleme uyarıları
Şifreleme uyarıları güvenli kitaplıklar ve şifreleme doğru kullanımı aracılığıyla uygulamaları destekler. Bu uyarılar, programınızdaki güvenlik açıklarını önlemeye yardımcı olur. Bu uyarılardan birini devre dışı bırakırsanız, bunun sebebini kodunuzda açıkça işaretlemelisiniz ve ayrıca geliştirme projeniz için güvenlik çalışanını bilgilendirmelisiniz.  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[CA5350: Zayıf Şifreleme Algoritmaları Kullanmayın](../code-quality/ca5350-do-not-use-weak-cryptographic-algorithms.md)|Zayıf şifreleme algoritmalarını ve karma İşlevler, birçok nedenden dolayı bugün kullanılır, ancak bunlar bütünlüğü korudukları verilerin ve gizliliği güvence altına almak için kullanılmamalıdır.        Kodda TripleDES, SHA1 veya RIPEMD160 algoritmaları bulduğunda bu kural tetikler.|  
|[CA5351: Bozuk Şifreleme Algoritmaları Kullanmayın](../code-quality/ca5351-do-not-use-broken-cryptographic-algorithms.md)|Şifreleme bozuk algoritmaları güvenli kabul edilmez ve bunların kullanılması kesinlikle kaçının olması gerekir. Bu kod MD5 karma algoritma veya DES veya RC2 şifreleme algoritması bulduğunda bu kural tetikler.|