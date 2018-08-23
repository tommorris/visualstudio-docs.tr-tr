---
title: 'CA1703: Kaynak dizeler doğru yazılmalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- ResourceStringsShouldBeSpelledCorrectly
- CA1703
helpviewer_keywords:
- CA1703
- ResourceStringsShouldBeSpelledCorrectly
ms.assetid: 693f4970-f512-40cb-ae3b-a0f3a5c6d6f1
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 017b0d2e12e990c1cb0c056182552983387820af
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691268"
---
# <a name="ca1703-resource-strings-should-be-spelled-correctly"></a>CA1703: Kaynak dizeler doğru yazılmalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1703: kaynak dizeler yazıldığından](https://docs.microsoft.com/visualstudio/code-quality/ca1703-resource-strings-should-be-spelled-correctly).  
  
TypeName | ResourceStringsShouldBeSpelledCorrectly |  
| Checkıd | CA1703 |  
| Kategori | Microsoft.Naming|  
| Yeni değişiklik | Bölünemez |  
  
## <a name="cause"></a>Sebep  
 Kaynak dizesi, Microsoft Yazım kitaplığı tarafından tanınmayan bir veya birkaç sözcük içerir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural kaynak dizesi (bileşik sözcüklerin) kelimelere ayrıştırır ve her kelimenin/belirtecin yazımını denetler. Ayrıştırma algoritma hakkında daha fazla bilgi için bkz. [CA1704: tanımlayıcılar yazıldığından](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).  
  
 Varsayılan olarak, yazım denetimcisi (TR) İngilizce sürümü kullanılır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için sözcüklerin bir özel sözlüğüne ekleyin ya da doğru yazıldığından tam sözcük kullanın. Özel sözlükler kullanma hakkında daha fazla bilgi için bkz: [CA1704: tanımlayıcılar yazıldığından](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Doğru bir şekilde yazılmış kelimeler yeni yazılım kitaplıkları öğrenmek için gereken süreyi azaltın.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1701: Kaynak dize bileşik sözcüklerinin küçük/büyük harfleri doğru yazılmalıdır](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)  
  
 [CA1704: Tanımlayıcılar doğru yazılmalıdır](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)  
  
 [CA2204: Değişmez değerler doğru yazılmalıdır](../code-quality/ca2204-literals-should-be-spelled-correctly.md)



