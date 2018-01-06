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
ms.workload: multiple
ms.openlocfilehash: dd6cc8b51ddd8f9e8813229cf66b9facb52e4668
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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