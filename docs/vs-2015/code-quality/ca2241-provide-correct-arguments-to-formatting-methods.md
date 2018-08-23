---
title: 'CA2241: biçimlendirme yöntemlerine doğru bağımsız değişkenleri sağlayın | Microsoft Docs'
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
- CA2241
- Provide correct arguments to formatting methods
- ProvideCorrectArgumentsToFormattingMethods
helpviewer_keywords:
- ProvideCorrectArgumentsToFormattingMethods
- CA2241
ms.assetid: 83639bc4-4c91-4a07-a40e-dc5e49a84494
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: feb2181ac1b43affe69dadc8060c9b5a74ec2da1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693709"
---
# <a name="ca2241-provide-correct-arguments-to-formatting-methods"></a>CA2241: Biçimlendirme yöntemlerine doğru bağımsız değişkenleri sağlayın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2241: biçimlendirme yöntemlerine doğru bağımsız değişkenleri sağlayın](https://docs.microsoft.com/visualstudio/code-quality/ca2241-provide-correct-arguments-to-formatting-methods).  
  
TypeName | ProvideCorrectArgumentsToFormattingMethods |  
| Checkıd | CA2241 |  
| Kategori | Microsoft.Usage|  
| Yeni değişiklik | Olmayan yeni |  
  
## <a name="cause"></a>Sebep  
 `format` Dize gibi bir yönteme geçirilen bağımsız değişkenin <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, veya <xref:System.String.Format%2A?displayProperty=fullName> her nesne değişkeni veya tam tersi karşılık gelen bir biçim öğesi içermiyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Gibi yöntemlerinin bağımsız değişkenleri <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, ve <xref:System.String.Format%2A> birkaç tarafından izlenen bir biçim dizesi oluşur <xref:System.Object?displayProperty=fullName> örnekleri. Biçim dizesi metin ve ekli biçim öğesi formunun oluşur {dizini [, hizalama] [: formatString]}. 'dizin' Biçimlendirilecek nesneler gösteren sıfır tabanlı bir tamsayıdır. Bir nesne Biçim dizesinde karşılık gelen bir dizin yoksa, nesne göz ardı edilir. 'Dizin' tarafından belirtilen nesnede mevcut değilse bir <xref:System.FormatException?displayProperty=fullName> çalışma zamanında oluşturulur.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için bir biçim öğesi sağlamak için her bir nesne bağımsız ve her biçim öğesi için bir nesne bağımsız değişken sağlayın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, iki kural ihlalleri gösterir.  
  
 [!code-csharp[FxCop.Usage.FormattingArguments#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.FormattingArguments/cs/FxCop.Usage.FormattingArguments.cs#1)]
 [!code-vb[FxCop.Usage.FormattingArguments#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.FormattingArguments/vb/FxCop.Usage.FormattingArguments.vb#1)]



