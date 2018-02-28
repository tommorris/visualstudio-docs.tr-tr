---
title: "CA2204: Değişmez değerler doğru yazılmalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Literals should be spelled correctly
- CA2204
- LiteralsShouldBeSpelledCorrectly
helpviewer_keywords:
- CA2204
ms.assetid: b0bbcbb6-c92d-4c14-8ef7-9c8b38c791a6
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ad1fb951f17d223f248c678738070d1c5b70ae7d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2204-literals-should-be-spelled-correctly"></a>CA2204: Değişmez değerler doğru yazılmalıdır
|||  
|-|-|  
|TypeName|LiteralsShouldBeSpelledCorrectly|  
|CheckId|CA2204|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Hazır bir dize değeri, bir parametre veya yerelleştirilmiş dize ve değişmez değer dize gerektirir özelliği kullanılan bir yöntem geçişleri Microsoft Yazım kitaplığı tarafından tanınmayan bir veya daha fazla sözcükler içeriyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural bir parametre veya bir özellik için bir değer olarak geçirilen sabit değerli bir dize ya da daha fazla aşağıdaki durumlarda doğrudur:  
  
-   <xref:System.ComponentModel.LocalizableAttribute> Parametresi ya da özelliğin özniteliği true.  
  
-   Parametresi veya özellik adı "Metin", "İletisi" veya "Resim yazısı" içerir.  
  
-   Console.Write veya Console.WriteLine yönteme geçirilen dize parametresi "value" veya "biçim" adıdır.  
  
 Bu kural değişmez değer dize bileşik sözcüklerinin belirtece dönüştürmek sözcüklere ayrıştırır ve her word/token yazımını denetler. Ayrıştırma algoritması hakkında daha fazla bilgi için bkz: [CA1704: tanımlayıcılar yazıldığından](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).  
  
 Varsayılan olarak, yazım İngilizce (TR) sürümü kullanılır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için Word yazımı düzeltin veya sözcüğü özel sözlüğe ekleyin. Özel sözlük kullanma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Kod Analizi dizinini özelleştirme](../code-quality/how-to-customize-the-code-analysis-dictionary.md).  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Doğru yazılmış kelimeler yeni yazılım kitaplıkları için gerekli öğrenme eğrisini düşürebilir.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1704: Tanımlayıcılar doğru yazılmalıdır](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)  
  
 [CA1703: Kaynak dizeler doğru yazılmalıdır](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)