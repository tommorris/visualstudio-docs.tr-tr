---
title: "CA1056: URI özellikleri dizeler olmamalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- UriPropertiesShouldNotBeStrings
- CA1056
helpviewer_keywords:
- UriPropertiesShouldNotBeStrings
- CA1056
ms.assetid: fdc99d29-0904-4a65-baa8-4f76833c953e
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: cdfcce6ff0c9526508b5cf4088968a1a8081c822
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1056-uri-properties-should-not-be-strings"></a>CA1056: URI özellikleri dizeler olmamalıdır
|||  
|-|-|  
|TypeName|UriPropertiesShouldNotBeStrings|  
|CheckId|CA1056|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir tür adı "URI", "Uri", "urn", "Urn", "url" veya "Url" içeren bir dize özelliği bildirir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural Pascal büyük/küçük harf kuralına göre belirteçleri özellik adı ayıran ve her token "URI", "Uri", "urn", "Urn", "url" veya "Url" öğesine eşit olup olmadığını denetler. Bir eşleşme varsa, kural özelliği Tekdüzen Kaynak Tanımlayıcısı (URI) temsil eden varsayar. Bir URI'nın dize sunumu ayrıştırma ve hataları kodlama eğilimindedir ve güvenlik açıklarına yol açabilir. <xref:System.Uri?displayProperty=fullName> Sınıfı, güvenli ve güvenli bir şekilde bu hizmetleri sağlar.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için özelliği değiştirmek bir <xref:System.Uri> türü.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Özelliği bir URI temsil etmez, bu kural bir uyarıdan gizlemek güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir tür gösterir `ErrorProne`, bu kuralı ve bir tür ihlal `SaferWay`, kural karşılar.  
  
 [!code-csharp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CSharp/ca1056-uri-properties-should-not-be-strings_1.cs)]
 [!code-vb[FxCop.Design.UriNotString#1](../code-quality/codesnippet/VisualBasic/ca1056-uri-properties-should-not-be-strings_1.vb)]
 [!code-cpp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CPP/ca1056-uri-properties-should-not-be-strings_1.cpp)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1054: URI parametreleri dizeler olmamalıdır](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)  
  
 [CA1055: URI dönüş değerleri dizeler olmamalıdır](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)  
  
 [CA2234: Dizeler yerine System.Uri nesneleri gönderin](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)  
  
 [CA1057: Dize URI aşırı yüklemeleri System.Uri aşırı yüklemelerini çağırır](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)