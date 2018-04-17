---
title: 'CA1309: sıralı StringComparison kullanın | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- UseOrdinalStringComparison
- CA1309
helpviewer_keywords:
- UseOrdinalStringComparison
- CA1309
ms.assetid: 19be0854-cb6e-4efd-a4c8-a5c1fc6f7a71
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 96718a9402b2bafcf8728004efb3df5e94da8126
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1309-use-ordinal-stringcomparison"></a>CA1309: Sıralı StringComparison kullanın
|||  
|-|-|  
|TypeName|UseOrdinalStringComparison|  
|CheckId|CA1309|  
|Kategori|Microsoft.Globalization|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Nonlinguistic bir dize karşılaştırma işlemi ayarlı değil <xref:System.StringComparison> ya da parametre **sıra** veya **Ordinalıgnorecase**.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Çoğu dize işlemleri, en önemli <xref:System.String.Compare%2A?displayProperty=fullName> ve <xref:System.String.Equals%2A?displayProperty=fullName> yöntemleri, artık kabul eden bir aşırı sağlayan bir <xref:System.StringComparison?displayProperty=fullName> bir parametre olarak numaralandırma değeri.  
  
 Belirttiğinizde ya da **StringComparison.Ordinal** veya **Stringcomparison.ordinalıgnorecase**, dize karşılaştırma nonlinguistic olacaktır. Diğer bir deyişle, karşılaştırma kararlar alındığında doğal dile özgü özellikleri göz ardı edilir. Bu kararlar basit bayt karşılaştırmaları üzerinde temel alır ve kültür tarafından parametreli büyük/küçük harf ya da eşdeğer tabloları yoksay anlamına gelir. Sonuç olarak ayarlayarak açıkça parametresi ya da **StringComparison.Ordinal** veya **Stringcomparison.ordinalıgnorecase**, kodunuzu genellikle kazanır hızı, doğruluk artırır ve olur daha güvenilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için kabul eden bir aşırı dize karşılaştırma yöntemini değiştirme <xref:System.StringComparison?displayProperty=fullName> sabit bir parametre olarak ya da belirtin **sıra** veya **Ordinalıgnorecase**. Örneğin, değiştirme `String.Compare(str1, str2)` için `String.Compare(str1, str2, StringComparison.Ordinal)`.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Kitaplığı veya uygulama sınırlı yerel izleyicisinin veya geçerli kültürü semantiği kullanılmalıdır yöneliktir olduğunda bir uyarı bu kuraldan bastırmak güvenlidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genelleştirme uyarıları](../code-quality/globalization-warnings.md)   
 [CA1307: StringComparison belirtin](../code-quality/ca1307-specify-stringcomparison.md)