---
title: 'CA1501: aşırı devralmadan kaçının | Microsoft Docs'
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
- CA1501
- AvoidExcessiveInheritance
helpviewer_keywords:
- AvoidExcessiveInheritance
- CA1501
ms.assetid: 9e934746-1a4d-492a-91e4-085201abafa4
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 29611b55a831cc8ccbc0d06dd2b7da33c79b4090
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633888"
---
# <a name="ca1501-avoid-excessive-inheritance"></a>CA1501: Aşırı devralmadan kaçın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1501: aşırı devralmadan kaçının](https://docs.microsoft.com/visualstudio/code-quality/ca1501-avoid-excessive-inheritance).  
  
TypeName | AvoidExcessiveInheritance |  
| Checkıd | CA1501 |  
| Kategori | Microsoft.Maintainability|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Devralma hiyerarşisinde düzeyleri dörtten fazla olan türdür.  
  
## <a name="rule-description"></a>Kural Tanımı  
 İç içe yuvalanmış hiyerarşileri izlemek, anlamak ve muhafaza etmek zor olabilir. Bu kural, aynı modülde hiyerarşileri analiz sınırlar.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için türü devralma hiyerarşisinde daha az ayrıntılı bir taban türünden türetilir veya Ara temel türlerinin bazılarını ortadan kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan bir uyarıyı bastırmak güvenlidir. Ancak, kod korumak daha zor olabilir. Temel türleri görünürlüğünü bağlı olarak, bu kuralın ihlallerini çözümleme bozucu değişiklikleri oluşturabilir, unutmayın. Örneğin, ortak temel türleri kaldırma bölünmesi farklıdır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kuralını ihlal eden bir tür gösterir.  
  
 [!code-csharp[FxCop.Maintainability.ExcessiveInheritance#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Maintainability.ExcessiveInheritance/cs/FxCop.Maintainability.ExcessiveInheritance.cs#1)]
 [!code-vb[FxCop.Maintainability.ExcessiveInheritance#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Maintainability.ExcessiveInheritance/vb/FxCop.Maintainability.ExcessiveInheritance.vb#1)]



