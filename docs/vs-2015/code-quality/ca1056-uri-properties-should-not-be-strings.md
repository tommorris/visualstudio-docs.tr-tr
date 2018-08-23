---
title: 'CA1056: URI özellikleri dize olmamalıdır | Microsoft Docs'
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
- UriPropertiesShouldNotBeStrings
- CA1056
helpviewer_keywords:
- UriPropertiesShouldNotBeStrings
- CA1056
ms.assetid: fdc99d29-0904-4a65-baa8-4f76833c953e
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 04e25e9ce01791db16403f72cfea39f40b7873a7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628756"
---
# <a name="ca1056-uri-properties-should-not-be-strings"></a>CA1056: URI özellikleri dizeler olmamalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1056: URI özellikleri dizeler olmamalıdır](https://docs.microsoft.com/visualstudio/code-quality/ca1056-uri-properties-should-not-be-strings).  
  
TypeName | UriPropertiesShouldNotBeStrings |  
| Checkıd | CA1056 |  
| Kategori | Microsoft.Design|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Bir tür adında "URI", "Uri", "urn", "Urn", "url" veya "Url" içeren bir dize özelliğini bildirir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural, Pascal casing standardına göre belirteçleri özellik adı ayıran ve her belirteç "URI", "Uri", "urn", "Urn", "url" veya "Url" eşit olup olmadığını denetler. Bir eşleşme varsa, kural, özelliğin Tekdüzen Kaynak Tanımlayıcısı (URI) temsil ettiğini varsayar. Bir URI'nın dize sunumu ayrıştırma ve hataları kodlama eğilimindedir ve güvenlik açıklarına yol açabilir. <xref:System.Uri?displayProperty=fullName> Sınıfı bu hizmetleri güvenli bir biçimde sunar.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için özelliğini değiştirin. bir <xref:System.Uri> türü.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Özelliği bir URI temsil etmiyorsa, bu kuraldan bir uyarıyı bastırmak güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir tür gösterir `ErrorProne`, bu kuralı ve bir tür ihlal `SaferWay`, bu kural karşılar.  
  
 [!code-cpp[FxCop.Design.UriNotString#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.UriNotString/cpp/FxCop.Design.UriNotString.cpp#1)]
 [!code-csharp[FxCop.Design.UriNotString#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.UriNotString/cs/FxCop.Design.UriNotString.cs#1)]
 [!code-vb[FxCop.Design.UriNotString#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.UriNotString/vb/FxCop.Design.UriNotString.vb#1)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1054: URI parametreleri dizeler olmamalıdır](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)  
  
 [CA1055: URI dönüş değerleri dizeler olmamalıdır](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)  
  
 [CA2234: Dizeler yerine System.Uri nesneleri gönderin](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)  
  
 [CA1057: Dize URI aşırı yüklemeleri System.Uri aşırı yüklemelerini çağırır](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)



