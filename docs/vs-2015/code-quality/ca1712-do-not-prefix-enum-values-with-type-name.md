---
title: 'CA1712: numaralandırma değerleri tür adıyla önek kullanmayın | Microsoft Docs'
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
- CA1712
- DoNotPrefixEnumValuesWithTypeName
helpviewer_keywords:
- CA1712
- DoNotPrefixEnumValuesWithTypeName
ms.assetid: df0e3a12-67bf-48f1-a10b-2ef60484a5c7
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: eed58446407af6178b6f42caaa48df620878b201
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633003"
---
# <a name="ca1712-do-not-prefix-enum-values-with-type-name"></a>CA1712: Numaralandırma değerleri için tür adıyla önek kullanmayın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1712: numaralandırma değerleri için tür adıyla önek kullanmayın](https://docs.microsoft.com/visualstudio/code-quality/ca1712-do-not-prefix-enum-values-with-type-name).  
  
TypeName | DoNotPrefixEnumValuesWithTypeName |  
| Checkıd | CA1712 |  
| Kategori | Microsoft.Naming|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Bir sabit listesi adı numaralandırma türü adı ile başlayan bir üye içeriyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Tür bilgilerini geliştirme araçları tarafından sağlanacak beklendiğinden numaralandırma üyelerinin adları tür adıyla öneklenmemiştir.  
  
 Adlandırma kuralları, ortak dil çalışma zamanını hedefleyen kitaplıkları için genel bir bakış sağlar. Bu, yeni bir yazılım kitaplığı öğrenmek için gereklidir ve kitaplık geliştirme yönetilen kodda uzmanlığına sahip olan kişi tarafından geliştirilmiştir müşterilerinizin size olan güvenini artırır süreyi azaltır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için sabit listesi üyesi türü adı ön eki kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, düzeltilmiş sürümü tarafından izlenen bir yanlış adlandırılmış bir numaralandırmayı gösterir.  
  
 [!code-cpp[FxCop.Naming.EnumValues#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Naming.EnumValues/cpp/FxCop.Naming.EnumValues.cpp#1)]
 [!code-csharp[FxCop.Naming.EnumValues#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Naming.EnumValues/cs/FxCop.Naming.EnumValues.cs#1)]
 [!code-vb[FxCop.Naming.EnumValues#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Naming.EnumValues/vb/FxCop.Naming.EnumValues.vb#1)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1711: Tanımlayıcıların sonekleri yanlış olmamalıdır](../code-quality/ca1711-identifiers-should-not-have-incorrect-suffix.md)  
  
 [CA1027: Numaralandırmaları FlagsAttribute ile işaretleyin](../code-quality/ca1027-mark-enums-with-flagsattribute.md)  
  
 [CA2217: Numaralandırmaları FlagsAttribute ile işaretlemeyin](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Enum?displayProperty=fullName>



