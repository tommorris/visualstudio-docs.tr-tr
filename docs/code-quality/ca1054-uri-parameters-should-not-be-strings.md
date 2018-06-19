---
title: 'CA1054: URI parametreleri dizeler olmamalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1054
- UriParametersShouldNotBeStrings
helpviewer_keywords:
- CA1054
- UriParametersShouldNotBeStrings
ms.assetid: 8e99d72b-a658-47a7-8dd5-9784ce2c30b8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 740a3354b9b14bb62dee259c6534ce8065162894
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31900036"
---
# <a name="ca1054-uri-parameters-should-not-be-strings"></a>CA1054: URI parametreleri dizeler olmamalıdır
|||
|-|-|
|TypeName|UriParametersShouldNotBeStrings|
|CheckId|CA1054|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir tür adı "URI", "Uri", "urn", "Urn", "url" veya "Url" içeren bir dize parametresi yöntemiyle bildirir ve türü alır karşılık gelen bir aşırı bildirmiyor bir <xref:System.Uri?displayProperty=fullName> parametresi.

## <a name="rule-description"></a>Kural Tanımı
 Bu kural parametre adı ortası büyük/küçük harf kuralına göre belirteçler içine böler ve her token "URI", "Uri", "urn", "Urn", "url" veya "Url" öğesine eşit olup olmadığını denetler. Bir eşleşme varsa, kural parametre Tekdüzen Kaynak Tanımlayıcısı (URI) temsil eden varsayar. Bir URI'nın dize sunumu ayrıştırma ve hataları kodlama eğilimindedir ve güvenlik açıklarına yol açabilir. Bir yöntem bir URI dize gösterimini sürerse örneğini alan sağlanan karşılık gelen bir aşırı olmalıdır <xref:System.Uri> güvenli ve güvenli bir şekilde bu hizmetleri sağlayan sınıf.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için parametre değiştirme bir <xref:System.Uri> yazın; önemli bir değişiklik budur. Alternatif olarak, alan yöntemin bir aşırı yüklemesini sağlayan bir <xref:System.Uri> parametresi; bu bölünemez bir değişikliktir.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Parametresi bir URI temsil etmez, bu kural bir uyarıdan gizlemek güvenlidir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bir tür gösterir `ErrorProne`, bu kuralı ve bir tür ihlal `SaferWay`, kural karşılar.

 [!code-csharp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CSharp/ca1054-uri-parameters-should-not-be-strings_1.cs)]
 [!code-vb[FxCop.Design.UriNotString#1](../code-quality/codesnippet/VisualBasic/ca1054-uri-parameters-should-not-be-strings_1.vb)]
 [!code-cpp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CPP/ca1054-uri-parameters-should-not-be-strings_1.cpp)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1056: URI özellikleri dize olmamalıdır](../code-quality/ca1056-uri-properties-should-not-be-strings.md)

 [CA1055: URI dönüş değerleri dizeler olmamalıdır](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)

 [CA2234: Dizeler yerine System.Uri nesneleri gönderin](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)

 [CA1057: Dize URI aşırı yüklemeleri System.Uri aşırı yüklemelerini çağırır](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)