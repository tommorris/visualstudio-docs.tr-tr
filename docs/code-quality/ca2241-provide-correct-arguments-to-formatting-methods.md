---
title: "CA2241: biçimlendirme yöntemlerine doğru bağımsız değişkenleri sağlayın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2241
- Provide correct arguments to formatting methods
- ProvideCorrectArgumentsToFormattingMethods
helpviewer_keywords:
- ProvideCorrectArgumentsToFormattingMethods
- CA2241
ms.assetid: 83639bc4-4c91-4a07-a40e-dc5e49a84494
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f5f71926705169d4ed7dc40318e83f265e8603f5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2241-provide-correct-arguments-to-formatting-methods"></a>CA2241: Biçimlendirme yöntemlerine doğru bağımsız değişkenleri sağlayın
|||  
|-|-|  
|TypeName|ProvideCorrectArgumentsToFormattingMethods|  
|CheckId|CA2241|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 `format` Dize gibi bir yönteme geçirilen bağımsız değişken <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, veya <xref:System.String.Format%2A?displayProperty=fullName> her nesne bağımsız değişkeni için veya tersi karşılık gelen bir biçim öğeyi içermiyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bağımsız değişkenler gibi yöntemler için <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, ve <xref:System.String.Format%2A> birkaç tarafından izlenen bir biçim dizesi oluşur <xref:System.Object?displayProperty=fullName> örnekleri. Metin ve form katıştırılmış biçimi öğelerinin biçim dizesi oluşur {dizin [, hizalama] [: formatString]}. 'dizini' biçimlendirmek için nesnelerin belirten sıfır tabanlı bir tamsayıdır. Bir nesne biçim dizesi içinde karşılık gelen bir dizin yoksa, nesne göz ardı edilir. 'Dizini' tarafından belirtilen nesne mevcut değilse, bir <xref:System.FormatException?displayProperty=fullName> çalışma zamanında atılır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için her nesne bağımsız değişkeni için bir biçim öğesi sağlar ve her biçim öğesi için bir nesne bağımsız değişken sağlayın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, iki kural ihlalleri gösterir.  
  
 [!code-vb[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/VisualBasic/ca2241-provide-correct-arguments-to-formatting-methods_1.vb)]
 [!code-csharp[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/CSharp/ca2241-provide-correct-arguments-to-formatting-methods_1.cs)]