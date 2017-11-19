---
title: "CA1701: Kaynak dize bileşik sözcüklerinin doğru ortası | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ResourceStringCompoundWordsShouldBeCasedCorrectly
- CA1701
helpviewer_keywords:
- CA1701
- ResourceStringCompoundWordsShouldBeCasedCorrectly
ms.assetid: 4ddbe09f-24b8-4c47-9373-a06f4487ca0d
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4dee5b21724944ea26e89c2cd1ace556f1377848
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1701-resource-string-compound-words-should-be-cased-correctly"></a>CA1701: Kaynak dize bileşik sözcüklerinin küçük/büyük harfleri doğru yazılmalıdır
|||  
|-|-|  
|TypeName|ResourceStringCompoundWordsShouldBeCasedCorrectly|  
|CheckId|CA1701|  
|Kategori|Microsoft.Naming|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Kaynak dizesi doğru ortası görünmüyor bileşik bir sözcük içeriyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Her sözcüğün kaynak dizesi büyük/küçük harf üzerinde temel belirteçler içine ayrılır. Her bir bitişik ikili-işaret kombinasyonu Microsoft yazım kitaplığı tarafından denetlenir. Tanınırsa, kelime kural ihlali üretir. "Sağlama" ve "Sağlama" ve "Multipart" sırasıyla ortası "MultiPart" bir ihlaline neden bileşik sözcüklerin örnekleridir. Önceki yaygın kullanım nedeniyle bazı özel durumlar kurala yerleşiktir ve "Araç" ve "iki ayrı sözcükleri ortası Filename" gibi birkaç tek sözcük işaretlenir. Bu örnekte, "Araç" ve "Dosya adı" bayrağı.  
  
 Adlandırma kuralları hedefleyen ortak dil çalışma zamanı kitaplıkları için genel bir bakış sağlar. Bu, yeni yazılım kitaplıkları için gereklidir ve kitaplık geliştirme yönetilen kodda uzmanlığa sahip olan kişi tarafından geliştirilmiştir müşteri güvenini artırır öğrenme eğrisini azaltır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Word doğru ortası şekilde değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan bileşik word kısımlarını yazım sözlüğüyle tanınır ve iki sözcükler kullanmayı hedefi ise gizlemek güvenlidir.  
  
 Özel sözlük yazım denetimi için bileşik sözcüklerin ekleyebilirsiniz. Özel sözlük sözcükleri ihlalleri neden olmaz. Daha fazla bilgi için bkz: [nasıl yapılır: Kod Analizi dizinini özelleştirme](../code-quality/how-to-customize-the-code-analysis-dictionary.md).  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1702: Bileşik sözcüklerin doğru ortası](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)  
  
 [CA1709: Tanımlayıcılar doğru ortası](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: Tanımlayıcılar örnekten daha fazla farklı olmalıdır](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Büyük/küçük harf kuralları](/dotnet/standard/design-guidelines/capitalization-conventions)   
 [Adlandırma yönergeleri](/dotnet/standard/design-guidelines/naming-guidelines)