---
title: "CA2004: GC çağrıları kaldırın. KeepAlive | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
helpviewer_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
ms.assetid: bc543b5b-23eb-4b45-abc2-9325cd254ac2
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: edb47391872da6754e39a27d2e8a50dc61293af1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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