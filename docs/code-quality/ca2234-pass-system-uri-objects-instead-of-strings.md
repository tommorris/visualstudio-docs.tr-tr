---
title: 'CA2234: Dizeler yerine System.Uri nesneleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
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
ms.openlocfilehash: ec09fe58e7a30f6b554afbf275ef0d8663cb0abb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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