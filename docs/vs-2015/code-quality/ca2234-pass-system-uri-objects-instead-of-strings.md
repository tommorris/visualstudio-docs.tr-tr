---
title: 'CA2234: Dizeler yerine System.Uri nesneleri | Microsoft Docs'
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
- PassSystemUriObjectsInsteadOfStrings
- CA2234
helpviewer_keywords:
- CA2234
- PassSystemUriObjectsInsteadOfStrings
ms.assetid: 14616b37-74c4-4286-b051-115d00aceb5f
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: cba04480cafc5aaed0ee31523d1a5f159cb6fe26
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902660"
---
# <a name="ca2234-pass-systemuri-objects-instead-of-strings"></a>CA2234: Dizeler yerine System.Uri nesneleri gönderin
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2234: dizeler yerine System.Uri geçirmek nesneleri](https://docs.microsoft.com/visualstudio/code-quality/ca2234-pass-system-uri-objects-instead-of-strings).

|||
|-|-|
|TypeName|PassSystemUriObjectsInsteadOfStrings|
|CheckId|CA2234|
|Kategori|Microsoft.Usage|
|Yeni Değişiklik|Bozucu olmayan|

## <a name="cause"></a>Sebep
 Adında "URI", "Uri", "urn", "Urn", "url" veya "Url" içeren bir dize parametresi olan bir yönteme bir çağrı yapılır. ve metodun bildirim türü olan bir aşırı yüklemeye uyan yöntemi içerir. bir <xref:System.Uri?displayProperty=fullName> parametresi.

## <a name="rule-description"></a>Kural Tanımı
 Parametre adları camel casing standardına göre belirteçleri bölün ve ardından her belirteç "URI", "Uri", "urn", "Urn", "url" veya "Url" eşit olup olmadığını görmek için denetlenir. Bir eşleşme varsa, parametre bir Tekdüzen Kaynak Tanımlayıcısı (URI) gösterdiği kabul edilir. Bir URI'nın dize sunumu ayrıştırma ve hataları kodlama eğilimindedir ve güvenlik açıklarına yol açabilir. <xref:System.Uri> Sınıfı bu hizmetleri güvenli bir biçimde sunar. URI ilgili yalnızca farklı iki aşırı yükler arasında bir seçim olduğunda kullanıcı alan aşırı yüklemesini seçmelidir bir <xref:System.Uri> bağımsız değişken.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlalini düzeltmek için alan aşırı yüklemesini çağırmak <xref:System.Uri> bağımsız değişken.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Dize parametresi bir URI temsil etmiyorsa, bu kuraldan bir uyarıyı bastırmak güvenlidir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek bir yöntemi gösterir `ErrorProne`, kural ve bir yöntem ihlal `SaferWay`, doğru bir şekilde çağıran <xref:System.Uri> aşırı yükleme.

 [!code-cpp[FxCop.Usage.PassUri#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Usage.PassUri/cpp/FxCop.Usage.PassUri.cpp#1)]
 [!code-csharp[FxCop.Usage.PassUri#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.PassUri/cs/FxCop.Usage.PassUri.cs#1)]
 [!code-vb[FxCop.Usage.PassUri#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.PassUri/vb/FxCop.Usage.PassUri.vb#1)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1057: Dize URI aşırı yüklemeleri System.Uri aşırı yüklemelerini çağırır](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)

 [CA1056: URI özellikleri dize olmamalıdır](../code-quality/ca1056-uri-properties-should-not-be-strings.md)

 [CA1054: URI parametreleri dizeler olmamalıdır](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)

 [CA1055: URI dönüş değerleri dizeler olmamalıdır](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)



