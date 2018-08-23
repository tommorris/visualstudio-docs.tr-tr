---
title: 'CA2243: Öznitelik dize harfleri doğru çözümlenmelidir | Microsoft Docs'
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
- CA2243
- AttributeStringLiteralsShouldParseCorrectly
helpviewer_keywords:
- AttributeStringLiteralsShouldParseCorrectly
- CA2243
ms.assetid: bfadb366-379d-4ee4-b17b-c4a09bf1106b
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f9224d458e6fd61e597b8ab51393e2e6feb7aaf9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686580"
---
# <a name="ca2243-attribute-string-literals-should-parse-correctly"></a>CA2243: Öznitelik dize harfleri doğru çözümlenmelidir
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2243: Öznitelik dize harfleri ayrıştırma doğru](https://docs.microsoft.com/visualstudio/code-quality/ca2243-attribute-string-literals-should-parse-correctly).  
  
TypeName | AttributeStringLiteralsShouldParseCorrectly |  
| Checkıd | CA2243 |  
| Kategori | Microsoft.Usage|  
| Yeni değişiklik | Olmayan yeni |  
  
## <a name="cause"></a>Sebep  
 Bir öznitelik dize literal parametresi, bir URL, GUID ya da sürüm için doğru ayrıştırmaz.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Öğesinden türetilen öznitelikler bu yana <xref:System.Attribute?displayProperty=fullName>ve öznitelikleri derleme zamanında kullanılan, yalnızca sabit değerler için oluşturucuları geçirilebilir. URL, GUID ve sürümleri temsil etmelidir öznitelik parametreleri olamaz yazılı olarak <xref:System.Uri?displayProperty=fullName>, <xref:System.Guid?displayProperty=fullName>, ve <xref:System.Version?displayProperty=fullName>, bu tür sabitleri temsil edilemez. Bunun yerine, dizeler gösterilmelidir.  
  
 Parametresi bir dize olarak yazıldığından, hatalı biçimlendirilmiş bir parametre derleme zamanında geçirilebilir mümkündür.  
  
 Bu kural, bir Tekdüzen Kaynak Tanımlayıcısı (URI) bir genel benzersiz tanıtıcısı (GUID) veya bir sürüm temsil eden parametreleri bulmak için bir adlandırma buluşsal kullanır ve geçirilen değerin doğru olduğunu doğrular.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Parametre dizesi düzgün biçimlendirilmiş bir URL, GUID veya sürüm değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 URL, GUID ya da sürüm parametresi temsil etmiyorsa bu kuraldan bir uyarıyı bastırmak güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bu kuralı ihlal AssemblyFileVersionAttribute için kod gösterir.  
  
 [!code-csharp[FxCop.Usage.AttributeStringLiteralsShouldParseCorrectly#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.AttributeStringLiteralsShouldParseCorrectly/cs/FxCop.Usage.AttributeStringLiteralsShouldParseCorrectly.cs#1)]  
  
 Kural aşağıdaki tarafından tetiklenir:  
  
-   'Version' içerir ve için System.Version nelze analyzovat parametreler.  
  
-   'GUID' içerir ve System.Guid için ayrıştırılamayan parametre.  
  
-   'Uri', 'urn' veya 'url' içerir ve System.Uri olarak ayrıştırılamıyor. parametreler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CA1054: URI parametreleri dizeler olmamalıdır](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)



