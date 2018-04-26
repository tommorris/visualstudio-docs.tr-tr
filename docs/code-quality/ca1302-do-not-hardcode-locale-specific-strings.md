---
title: 'CA1302: Yerel özel dizeleri doğrudan programın içine gömmeyin'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotHardcodeLocaleSpecificStrings
- CA1302
helpviewer_keywords:
- DoNotHardcodeLocaleSpecificStrings
- CA1302
ms.assetid: 05ed134a-837d-43d7-bf97-906edeac44ce
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a00f78739a9287c996e87f182ca34ecba6d484c7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1302-do-not-hardcode-locale-specific-strings"></a>CA1302: Yerel özel dizeleri doğrudan programın içine gömmeyin
|||
|-|-|
|TypeName|DoNotHardcodeLocaleSpecificStrings|
|CheckId|CA1302|
|Kategori|Microsoft.Globalization|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Bir yöntem belirli sistem klasörlerinin yolu temsil eden bir dize sabit değeri kullanır.

## <a name="rule-description"></a>Kural Tanımı
 <xref:System.Environment.SpecialFolder?displayProperty=fullName> Numaralandırma özel sistem klasörlerine başvuran üyeleri içerir. Bu klasör konumlarını farklı işletim sistemleri üzerinde farklı değerlere sahip olabilir, kullanıcı konumları bazılarını değiştirebilir ve konumları yerelleştirilmiş. Özel bir klasör "C:\WINDOWS\system32" olan sistem klasörü üzerinde örneğidir [!INCLUDE[winxp](../code-quality/includes/winxp_md.md)] ancak üzerinde "C:\WINNT\system32" [!INCLUDE[win2kfamily](../code-quality/includes/win2kfamily_md.md)]. <xref:System.Environment.GetFolderPath%2A?displayProperty=fullName> Yöntemi ile ilişkili konumlarını döndürür <xref:System.Environment.SpecialFolder> numaralandırması. Tarafından döndürülen konumları <xref:System.Environment.GetFolderPath%2A> yerelleştirilir ve şu anda çalışan bilgisayar için uygun.

 Bu kuralı kullanarak alınabilecek klasör yollarını tokenizes <xref:System.Environment.GetFolderPath%2A> ayrı bir dizini düzeylere yöntemi. Her dize sabit değeri belirteçleri karşılaştırılır. Bir eşleşme bulunursa, yöntem belirteçle ilişkilendirilen sistem konuma başvuran bir dize oluşturuyor varsayılır. Taşınabilirlik ve yerelleştirme için kullanmak <xref:System.Environment.GetFolderPath%2A> dize değişmez değerleri kullanmak yerine özel sistem klasörleri konumlarını alma yöntemi.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için konumun kullanarak almak <xref:System.Environment.GetFolderPath%2A> yöntemi.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Dize sabit değeri ile ilişkili sistem konumlardan birine başvurmak için kullanılmıyorsa bu kuraldan bir uyarı bastırma güvenlidir <xref:System.Environment.SpecialFolder> numaralandırması.

## <a name="example"></a>Örnek
 Aşağıdaki örnekte bu kuraldan üç uyarıları oluşturur ortak uygulama veri klasörünün yolunu oluşturur. Ardından, kullanarak örnek yolunu alır <xref:System.Environment.GetFolderPath%2A> yöntemi.

 [!code-csharp[FxCop.Globalization.HardcodedLocaleStrings#1](../code-quality/codesnippet/CSharp/ca1302-do-not-hardcode-locale-specific-strings_1.cs)]
 [!code-vb[FxCop.Globalization.HardcodedLocaleStrings#1](../code-quality/codesnippet/VisualBasic/ca1302-do-not-hardcode-locale-specific-strings_1.vb)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1303: Harfleri yerelleştirilmiş parametreler olarak göndermeyin](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)