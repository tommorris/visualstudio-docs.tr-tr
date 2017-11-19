---
title: "CA1703: Kaynak dizeler doğru yazılmalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ResourceStringsShouldBeSpelledCorrectly
- CA1703
helpviewer_keywords:
- CA1703
- ResourceStringsShouldBeSpelledCorrectly
ms.assetid: 693f4970-f512-40cb-ae3b-a0f3a5c6d6f1
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9c7828aa218933208408a285510e998921d6f032
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1703-resource-strings-should-be-spelled-correctly"></a>CA1703: Kaynak dizeler doğru yazılmalıdır
|||  
|-|-|  
|TypeName|ResourceStringsShouldBeSpelledCorrectly|  
|CheckId|CA1703|  
|Kategori|Microsoft.Naming|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Kaynak dizesi, Microsoft Yazım kitaplığı tarafından tanınmayan bir veya birkaç sözcük içerir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural kaynak dizesi (bileşik sözcüklerin belirtece dönüştürmek) sözcüklere ayrıştırır ve her word/token yazımını denetler. Ayrıştırma algoritması hakkında daha fazla bilgi için bkz: [CA1704: tanımlayıcılar yazıldığından](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).  
  
 Varsayılan olarak, yazım İngilizce (TR) sürümü kullanılır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için doğru yazıldığından veya özel bir sözlüğe sözcükler ekleme tam sözcükler kullanın. Özel sözlük kullanma hakkında daha fazla bilgi için bkz: [CA1704: tanımlayıcılar yazıldığından](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Doğru yazılmış kelimeler yeni yazılım kitaplıkları öğrenmek için gereken süreyi azaltmak.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1701: Kaynak dize bileşik sözcüklerinin doğru ortası](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)  
  
 [CA1704: Tanımlayıcılar doğru yazılmalıdır](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)  
  
 [CA2204: Değişmez değerler doğru yazılmalıdır](../code-quality/ca2204-literals-should-be-spelled-correctly.md)