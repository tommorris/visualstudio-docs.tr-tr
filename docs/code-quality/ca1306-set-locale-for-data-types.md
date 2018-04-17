---
title: 'CA1306: Veri türleri için yerel ayar ayarlama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
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
ms.openlocfilehash: 344b93f6c48ba1848c272522b4580b03ec4f0b5d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 <xref:System.Data.DataTable?displayProperty=fullName>   
 <xref:System.Data.DataSet?displayProperty=fullName>   
 <xref:System.Globalization.CultureInfo?displayProperty=fullName>   
 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>   
 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>