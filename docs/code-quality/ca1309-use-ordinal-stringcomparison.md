---
title: "CA1309: sıralı StringComparison kullanın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- UseOrdinalStringComparison
- CA1309
helpviewer_keywords:
- UseOrdinalStringComparison
- CA1309
ms.assetid: 19be0854-cb6e-4efd-a4c8-a5c1fc6f7a71
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ba777ea4cd272a1392413a2ecbb52b9f45a3d71b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [CA1307: StringComparison belirtme](../code-quality/ca1307-specify-stringcomparison.md)