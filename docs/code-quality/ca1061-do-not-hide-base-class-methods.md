---
title: 'CA1061: taban sınıf yöntemlerini gizlemeyin | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1061
- DoNotHideBaseClassMethods
helpviewer_keywords:
- DoNotHideBaseClassMethods
- CA1061
ms.assetid: 0bda9dc8-87b4-4038-ab9d-563298387466
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f3119a088c0dfa7a976a12f0c6abb45e409da8d2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1061-do-not-hide-base-class-methods"></a>CA1061: Taban sınıf yöntemlerini gizlemeyin
|||  
|-|-|  
|TypeName|DoNotHideBaseClassMethods|  
|CheckId|CA1061|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Türetilmiş bir tür aynı ada sahip ve aynı sayıda parametreleri temel yöntemlerinden biri ile bir yöntem bildirir; bir veya daha fazla parametre karşılık gelen bir parametre temel yönteminde temel bir türde değil; ve kalan herhangi bir parametre parametrelerini temel yöntemi ilgili özdeş türlerine sahip.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Türetilen yönteminin parametre imzası türetilmiş temel yöntemi parametre imzası içinde karşılık gelen türlerine daha daha zayıf olan türlerine göre farklı olduğu durumlarda bir taban türü yönteminde türetilmiş bir tür aynı adlı bir yöntemi tarafından gizlenir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için kaldırmak veya yöntemi yeniden adlandırın veya parametre imzası yöntemi temel yöntemi gizlemez şekilde değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kuralını ihlal eden bir yöntemi gösterir.  
  
 [!code-csharp[FxCop.Design.HideBaseMethod#1](../code-quality/codesnippet/CSharp/ca1061-do-not-hide-base-class-methods_1.cs)]