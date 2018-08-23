---
title: 'CA2230: değişken bağımsız değişkenler için params kullanın | Microsoft Docs'
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
- UseParamsForVariableArguments
- CA2230
helpviewer_keywords:
- CA2230
- UseParamsForVariableArguments
ms.assetid: bf98b733-4855-4110-9f16-eba5a9e79421
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: b2e05b4d1dfd8c8b2a0f0e0cc461bcef8947b181
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694771"
---
# <a name="ca2230-use-params-for-variable-arguments"></a>CA2230: Değişken bağımsız değişkenler için params kullanın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2230: değişken bağımsız değişkenler için params kullanın](https://docs.microsoft.com/visualstudio/code-quality/ca2230-use-params-for-variable-arguments).  
  
TypeName | UseParamsForVariableArguments |  
| Checkıd | CA2230 |  
| Kategori | Microsoft.Usage|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Ortak veya korumalı tür kullanan bir ortak veya korumalı yöntem içerir `VarArgs` çağırma kuralı.  
  
## <a name="rule-description"></a>Kural Tanımı  
 `VarArgs` Çağırma kuralı değişik sayıda parametreyi almayan belirli yöntemi tanımları ile kullanılır. Yöntemini kullanarak `VarArgs` çağırma kuralı, ortak dil belirtimi (CLS) uyumlu değil ve programlama dillerini erişilebilir olmayabilir.  
  
 C# ' ta, `VarArgs` çağırma kuralı kullanılan bir yöntemin parametre listesi ile sona erdiğinde `__arglist` anahtar sözcüğü. Visual Basic desteklemiyor `VarArgs` elipsin kullanan yönetilmeyen kod içinde sağlayan kullanımı çağırma kuralı ve Visual C++ `...` gösterimi.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 C# ' de bu kural ihlalini düzeltmek için kullanın [params](http://msdn.microsoft.com/library/1690815e-b52b-4967-8380-5780aff08012) anahtar sözcüğü yerine `__arglist`.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, iki yöntem, kural ihlal eden diğeri kural karşılayan gösterir.  
  
 [!code-csharp[FxCop.Usage.UseParams#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.UseParams/cs/FxCop.Usage.UseParams.cs#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Reflection.CallingConventions?displayProperty=fullName>   
 [Dil Bağımsızlığı ve Dilden Bağımsız Bileşenler](http://msdn.microsoft.com/library/4f0b77d0-4844-464f-af73-6e06bedeafc6)



