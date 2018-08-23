---
title: 'CA1309: sıralı StringComparison kullanın | Microsoft Docs'
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
- UseOrdinalStringComparison
- CA1309
helpviewer_keywords:
- UseOrdinalStringComparison
- CA1309
ms.assetid: 19be0854-cb6e-4efd-a4c8-a5c1fc6f7a71
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: e18bd9d15b9b17268e4002268394cf6149722b0a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686518"
---
# <a name="ca1309-use-ordinal-stringcomparison"></a>CA1309: Sıralı StringComparison kullanın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1309: sıralı StringComparison kullanın](https://docs.microsoft.com/visualstudio/code-quality/ca1309-use-ordinal-stringcomparison).  
  
TypeName | UseOrdinalStringComparison |  
| Checkıd | CA1309 |  
| Kategori | Microsoft.Globalization|  
| Yeni değişiklik | Bölünemez |  
  
## <a name="cause"></a>Sebep  
 Nonlinguistic bir dize karşılaştırma işlemi ayarlı değil <xref:System.StringComparison> ya da parametre **sıra** veya **Ordinalıgnorecase**.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Çoğu dize işlemleri, en önemli <xref:System.String.Compare%2A?displayProperty=fullName> ve <xref:System.String.Equals%2A?displayProperty=fullName> yöntemleri artık kabul eden bir aşırı sağlayan bir <xref:System.StringComparison?displayProperty=fullName> numaralandırma değeri olarak bir parametre.  
  
 Belirttiğinizde ya da **StringComparison.Ordinal** veya **Stringcomparison.ordinalıgnorecase**, dize karşılaştırması nonlinguistic olacaktır. Diğer bir deyişle, karşılaştırma kararlar verildiğinde doğal dile özgü özellikleri göz ardı edilir. Bu kararların basit bayt karşılaştırmalarını temel alır ve kültür tarafından parametre haline getirilen büyük/küçük harf ya da denklik tabloları yoksay anlamına gelir. Sonuç olarak, açıkça ya da parametre ayarı tarafından **StringComparison.Ordinal** veya **Stringcomparison.ordinalıgnorecase**, kodunuzu genellikle hız kazandığı doğruluğu artırır ve olur daha güvenilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için dize karşılaştırma yöntemini kabul eden bir aşırı değiştirin <xref:System.StringComparison?displayProperty=fullName> , parametre olarak numaralandırması belirtin **sıra** veya **Ordinalıgnorecase**. Örneğin, değiştirme `String.Compare(str1, str2)` için `String.Compare(str1, str2, StringComparison.Ordinal)`.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Sınırlı bir yerel hedef kitle için veya geçerli kültürü semantiği kullanılmalıdır kitaplık veya uygulamanın amaçlanan bu kuraldan bir uyarıyı bastırmak güvenlidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genelleştirme uyarıları](../code-quality/globalization-warnings.md)   
 [CA1307: StringComparison belirtin](../code-quality/ca1307-specify-stringcomparison.md)



