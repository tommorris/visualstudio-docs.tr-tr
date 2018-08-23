---
title: Şifreleme uyarıları | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d96723ea-a293-488d-b9db-adb437e50cdd
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 947721de606cb6117ed2fd5f84bbc51e20e08203
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686652"
---
# <a name="cryptography-warnings"></a>Şifreleme Uyarıları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [şifreleme uyarıları](https://docs.microsoft.com/visualstudio/code-quality/cryptography-warnings).  
  
Şifreleme uyarıları daha güvenli kütüphaneleri ve şifreleme aracılığıyla doğru uygulamaları destekler. Bu uyarılar, programınızdaki güvenlik açıklarını önlemeye yardımcı olur. Bu uyarılardan birini devre dışı bırakırsanız, bunun sebebini kodunuzda açıkça işaretlemelisiniz ve ayrıca geliştirme projeniz için güvenlik çalışanını bilgilendirmelisiniz.  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[CA5350: Zayıf Şifreleme Algoritmaları Kullanmayın](../code-quality/ca5350-do-not-use-weak-cryptographic-algorithms.md)|Zayıf şifreleme algoritmalarını ve karma işlevler bir dizi nedenden ötürü bugün kullanılır, ancak bunlar bunların koruduğu veri bütünlüğü ve gizliliği güvence altına almak için kullanılmamalıdır.        Kodda TripleDES, SHA1 veya RIPEMD160 algoritmaları bulduğunda bu kural tetiklenir.|  
|[CA5351: Bozuk Şifreleme Algoritmaları Kullanmayın](../code-quality/ca5351-do-not-use-broken-cryptographic-algorithms.md)|Bozuk şifreleme algoritmaları güvenli kabul edilmeyen ve bunların kullanılması kesinlikle önerilmez. Bu kodda DES veya RC2 şifreleme algoritmaları ve MD5 karma algoritması bulduğunda bu kural tetikler.|



