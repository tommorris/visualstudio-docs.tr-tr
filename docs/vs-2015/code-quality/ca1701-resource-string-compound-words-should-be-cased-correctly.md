---
title: 'CA1701: Kaynak dize bileşik sözcüklerinin doğru yazılmalıdır | Microsoft Docs'
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
- ResourceStringCompoundWordsShouldBeCasedCorrectly
- CA1701
helpviewer_keywords:
- CA1701
- ResourceStringCompoundWordsShouldBeCasedCorrectly
ms.assetid: 4ddbe09f-24b8-4c47-9373-a06f4487ca0d
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: ccffe6561d461e52eb15f94a97a04c633d37abff
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629589"
---
# <a name="ca1701-resource-string-compound-words-should-be-cased-correctly"></a>CA1701: Kaynak dize bileşik sözcüklerinin küçük/büyük harfleri doğru yazılmalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1701: Kaynak dize bileşik sözcüklerinin büyük/küçük harfleri doğru](https://docs.microsoft.com/visualstudio/code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly).  
  
TypeName | ResourceStringCompoundWordsShouldBeCasedCorrectly |  
| Checkıd | CA1701 |  
| Kategori | Microsoft.Naming|  
| Yeni değişiklik | Bölünemez |  
  
## <a name="cause"></a>Sebep  
 Kaynak dizesi, büyük küçük harfleri doğru için görünmeyen bir bileşik sözcük içerir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Kaynak dizedeki her sözcüğün büyük/küçük harf üzerinde temel belirteçler içinde bölünür. Her bir bitişik ikili-işaret kombinasyonu Microsoft yazım kitaplığı tarafından denetlenir. Tanınırsa, kelime kural ihlali üretir. "CheckSum" ve "Checksum" ve "Multipart" sırasıyla yazılmalıdır "MultiPart" bir ihlaline neden bileşik sözcüklerin örnekleridir. Önceki ortak kullanımı nedeniyle kurala birkaç özel durum oluşturulur ve "Araç çubuğu" ve "iki ayrı sözcükleri yazılmalıdır Filename" gibi birden fazla tek sözcük işaretlenir. Bu örnekte, "Araç çubuğu" ve "Dosya adı" bayrak eklenmiş.  
  
 Adlandırma kuralları, ortak dil çalışma zamanını hedefleyen kitaplıkları için genel bir bakış sağlar. Bu, yeni yazılım kitaplıkları için gereklidir ve kitaplık geliştirme yönetilen kodda uzmanlığına sahip olan kişi tarafından geliştirilmiştir müşterilerinizin size olan güvenini artırır öğrenme eğrisini azaltır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Word'ün bu sözcüklerden şekilde değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bileşik sözcük kısımlarını yazım sözlüğüyle tanınır ve amacı iki kelimeye kullanmaktır. Bu kuraldan bir uyarıyı bastırmak güvenlidir.  
  
 Özel sözlük yazım denetimi için bileşik sözcüklerin ekleyebilirsiniz. Özel sözlük sözcükleri ihlallerine neden olmaz. Daha fazla bilgi için [nasıl yapılır: kod çözümleme dizinini özelleştirme](../code-quality/how-to-customize-the-code-analysis-dictionary.md).  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1702: Bileşik sözcüklerin küçük/büyük harfleri doğru yazılmalıdır](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)  
  
 [CA1709: Tanımlayıcıların büyük/küçük harfleri doğru yazılmalıdır](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: Tanımlayıcılar örnekten daha fazla farklı olmalıdır](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Büyük/küçük harf kuralları](http://msdn.microsoft.com/library/4c4ea526-9203-486f-b72d-29d61c5b3c6d)   
 [Adlandırma Kuralları](http://msdn.microsoft.com/library/fc076d66-9b5f-42d3-aa65-61d970c794a3)



