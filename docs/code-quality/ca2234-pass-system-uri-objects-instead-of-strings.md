---
title: 'CA2234: Dizeler yerine System.Uri nesneleri gönderin'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- PassSystemUriObjectsInsteadOfStrings
- CA2234
helpviewer_keywords:
- CA2234
- PassSystemUriObjectsInsteadOfStrings
ms.assetid: 14616b37-74c4-4286-b051-115d00aceb5f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 086f902aeb89d8ee3cc63fc21a3364cfcb480266
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2234-pass-systemuri-objects-instead-of-strings"></a>CA2234: Dizeler yerine System.Uri nesneleri gönderin
|||
|-|-|
|TypeName|PassSystemUriObjectsInsteadOfStrings|
|CheckId|CA2234|
|Kategori|Microsoft.Usage|
|Yeni Değişiklik|Olmayan sonu|

## <a name="cause"></a>Sebep
 "URI", "Uri", "urn", "Urn", "url" veya "Url"; adını içeren bir dize parametresi olan bir yöntemine bir çağrı yapılır. ve sahip karşılık gelen bir yöntemi aşırı yüklemesini yöntemi bildiri türü içeren bir <xref:System.Uri?displayProperty=fullName> parametresi.

## <a name="rule-description"></a>Kural Tanımı
 Bir parametre adı ortası büyük/küçük harf kuralına göre belirteçleri bölün ve ardından her belirteç "URI", "Uri", "urn", "Urn", "url" veya "Url" eşit olup olmadığını görmek için denetlenir. Bir eşleşme varsa, parametre Tekdüzen Kaynak Tanımlayıcısı (URI) temsil eden varsayılır. Bir URI'nın dize sunumu ayrıştırma ve hataları kodlama eğilimindedir ve güvenlik açıklarına yol açabilir. <xref:System.Uri> Sınıfı, güvenli ve güvenli bir şekilde bu hizmetleri sağlar. Bir URI gösterimini ilgili yalnızca farklı iki aşırı arasında bir seçim olduğunda, kullanıcının alan aşırı seçmesi gereken bir <xref:System.Uri> bağımsız değişkeni.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için alan aşırı yüklemesini çağırın <xref:System.Uri> bağımsız değişkeni.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Dize parametresi bir URI temsil etmez, bu kural bir uyarıdan gizlemek güvenlidir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bir yöntemi gösterir `ErrorProne`, kural ve bir yöntem ihlal `SaferWay`, doğru çağıran <xref:System.Uri> aşırı yükleme.

 [!code-vb[FxCop.Usage.PassUri#1](../code-quality/codesnippet/VisualBasic/ca2234-pass-system-uri-objects-instead-of-strings_1.vb)]
 [!code-cpp[FxCop.Usage.PassUri#1](../code-quality/codesnippet/CPP/ca2234-pass-system-uri-objects-instead-of-strings_1.cpp)]
 [!code-csharp[FxCop.Usage.PassUri#1](../code-quality/codesnippet/CSharp/ca2234-pass-system-uri-objects-instead-of-strings_1.cs)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1057: Dize URI aşırı yüklemeleri System.Uri aşırı yüklemelerini çağırır](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)

 [CA1056: URI özellikleri dize olmamalıdır](../code-quality/ca1056-uri-properties-should-not-be-strings.md)

 [CA1054: URI parametreleri dizeler olmamalıdır](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)

 [CA1055: URI dönüş değerleri dizeler olmamalıdır](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)