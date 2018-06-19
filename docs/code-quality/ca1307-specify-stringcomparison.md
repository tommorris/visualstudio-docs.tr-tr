---
title: 'CA1307: StringComparison belirtme'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1307
- SpecifyStringComparison
helpviewer_keywords:
- CA1307
- SpecifyStringComparison
ms.assetid: 9b0d5e71-1683-4a0d-bc4a-68b2fbd8af71
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dac870bde757d77e1d0025a1b387f54ca928a5f1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31900861"
---
# <a name="ca1307-specify-stringcomparison"></a>CA1307: StringComparison belirtme
|||
|-|-|
|TypeName|SpecifyStringComparison|
|CheckId|CA1307|
|Kategori|Microsoft.Globalization|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Dize karşılaştırma işlemi ayarlı değil yöntemi aşırı yüklemesini kullanır bir <xref:System.StringComparison> parametresi.

## <a name="rule-description"></a>Kural Tanımı
 Çoğu dize işlemleri, en önemli <xref:System.String.Compare%2A> ve <xref:System.String.Equals%2A> yöntemleri sağlayan kabul eden bir aşırı bir <xref:System.StringComparison> bir parametre olarak numaralandırma değeri.

 Her bir aşırı var. Bu alır bir <xref:System.StringComparison> parametresi, bu parametre almayan aşırı yerine kullanılmalıdır. Bu parametre açıkça ayarlayarak kodunuzun clearer yapılmış ve sürdürmek daha kolay görülür.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için kabul aşırı dize karşılaştırma yöntemlerini değiştirme <xref:System.StringComparison> bir parametre olarak numaralandırması. Örneğin: değiştirme `String.Compare(str1, str2)` için `String.Compare(str1, str2, StringComparison.Ordinal)`.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Kitaplığı veya uygulama için sınırlı bir yerel kitleye yöneliktir ve bu nedenle değil yerelleştirilmiş olabilir olduğunda bir uyarı bu kuraldan bastırmak güvenlidir.

## <a name="see-also"></a>Ayrıca Bkz.
 [Genelleştirme uyarıları](../code-quality/globalization-warnings.md) [CA1309: sıralı StringComparison kullanın](../code-quality/ca1309-use-ordinal-stringcomparison.md)