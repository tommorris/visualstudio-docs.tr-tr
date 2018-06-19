---
title: 'CA1306: Veri türleri için yerel ayarları ayarlayın'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1306
- SetLocaleForDataTypes
helpviewer_keywords:
- CA1306
- SetLocaleForDataTypes
ms.assetid: 104297b2-5806-4de0-a8d9-c589380a796c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b9a7188f3679e04164411472fd2d53948466a30d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31900409"
---
# <a name="ca1306-set-locale-for-data-types"></a>CA1306: Veri türleri için yerel ayarları ayarlayın
|||
|-|-|
|TypeName|SetLocaleForDataTypes|
|CheckId|CA1306|
|Kategori|Microsoft.Globalization|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Bir yöntemi veya oluşturucusu oluşturulan bir veya daha fazla <xref:System.Data.DataTable?displayProperty=fullName> veya <xref:System.Data.DataSet?displayProperty=fullName> örnekleri ve açıkça locale özelliği ayarlamamış (<xref:System.Data.DataTable.Locale%2A?displayProperty=fullName> veya <xref:System.Data.DataSet.Locale%2A?displayProperty=fullName>).

## <a name="rule-description"></a>Kural Tanımı
 Yerel ayar sayısal değerleri, para birimi simgeleri ve sıralama için kullanılan biçimlendirme gibi verileri için kültüre özgü sunu öğelerini belirler. Oluştururken bir <xref:System.Data.DataTable> veya <xref:System.Data.DataSet>, yerel açıkça ayarlamanız gerekir. Varsayılan olarak, bu tür yerel geçerli kültürdür. Bir veritabanı veya dosya saklanır ve genel olarak paylaşılan veriler için yerel normalde sabit kültür olarak ayarlanmalıdır. (<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>). Veri arasında kültürler paylaşıldığında, varsayılan yerel ayar kullanarak içeriğini neden olabilir <xref:System.Data.DataTable> veya <xref:System.Data.DataSet> sunulan veya yanlış yorumlanır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için açıkça yerel ayarlamak <xref:System.Data.DataTable> veya <xref:System.Data.DataSet>.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural bir uyarıdan kitaplığı veya uygulama için sınırlı bir yerel İzleyici olduğunda, veri paylaşılmayan veya varsayılan ayarı tüm desteklenen senaryolar istenen davranış verir gizlemek güvenlidir.

## <a name="example"></a>Örnek
 Aşağıdaki örnekte iki oluşturur <xref:System.Data.DataTable> örnekleri.

 [!code-csharp[FxCop.Globalization.DataTable#1](../code-quality/codesnippet/CSharp/ca1306-set-locale-for-data-types_1.cs)]

## <a name="see-also"></a>Ayrıca Bkz.
 <xref:System.Data.DataTable?displayProperty=fullName> <xref:System.Data.DataSet?displayProperty=fullName> <xref:System.Globalization.CultureInfo?displayProperty=fullName> <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>