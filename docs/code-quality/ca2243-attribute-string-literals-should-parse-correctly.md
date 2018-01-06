---
title: "CA2243: Öznitelik dize harfleri doğru ayrıştırması gereken | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2243
- AttributeStringLiteralsShouldParseCorrectly
helpviewer_keywords:
- AttributeStringLiteralsShouldParseCorrectly
- CA2243
ms.assetid: bfadb366-379d-4ee4-b17b-c4a09bf1106b
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 79ffda960d85c05648a0f1ea7d6c759fc9e76f78
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2243-attribute-string-literals-should-parse-correctly"></a>CA2243: Öznitelik dize harfleri doğru çözümlenmelidir
|||  
|-|-|  
|TypeName|AttributeStringLiteralsShouldParseCorrectly|  
|CheckId|CA2243|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Bir özniteliğin dize değişmez değer parametresi doğru bir URL, GUID veya sürüm için ayrıştırma değil.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Öznitelikleri türetilmiş beri <xref:System.Attribute?displayProperty=fullName>ve öznitelikleri derleme zamanında kullanılıyorsa, yalnızca sabit değerler kendi kurucusuna geçirilebilir. URL'ler, GUID'ler ve sürümleri temsil etmelidir özniteliği parametreleri olamaz yazılan olarak <xref:System.Uri?displayProperty=fullName>, <xref:System.Guid?displayProperty=fullName>, ve <xref:System.Version?displayProperty=fullName>, bu tür sabitleri temsil edilemez. Bunun yerine, dizeler gösterilmelidir.  
  
 Parametresi bir dize olarak yazıldığından, hatalı biçimlendirilmiş bir parametre derleme zamanında gönderilebilir mümkündür.  
  
 Bu kural bir Tekdüzen Kaynak Tanımlayıcısı (URI) bir genel benzersiz tanımlayıcı (GUID) veya bir sürüm temsil parametreleri bulmak için adlandırma buluşsal yöntemi kullanır ve geçirilen değerin doğru olduğunu doğrular.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Doğru biçimlendirilmiş bir URL, GUID veya sürüm parametre dizesini değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Parametresi, bir URL, GUID veya sürüm göstermiyor varsa bir uyarı bu kuraldan gizlemek güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kod için bu kuralı ihlal AssemblyFileVersionAttribute gösterir.  
  
 [!code-csharp[FxCop.Usage.AttributeStringLiteralsShouldParseCorrectly#1](../code-quality/codesnippet/CSharp/ca2243-attribute-string-literals-should-parse-correctly_1.cs)]  
  
 Kural aşağıdaki tarafından tetiklenir:  
  
-   'Version' içeren ve System.Version için ayrıştırılamıyor parametreleri.  
  
-   'Guid' içeren ve System.Guid için ayrıştırılamıyor parametreleri.  
  
-   İçin System.Uri ayrıştırılamaz ve 'uri', 'urn' veya 'URL'si' içeren parametreleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CA1054: URI parametreleri dizeler olmamalıdır](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)