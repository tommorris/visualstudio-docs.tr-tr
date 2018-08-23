---
title: 'CA1061: taban sınıf yöntemlerini gizlemeyin | Microsoft Docs'
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
- CA1061
- DoNotHideBaseClassMethods
helpviewer_keywords:
- DoNotHideBaseClassMethods
- CA1061
ms.assetid: 0bda9dc8-87b4-4038-ab9d-563298387466
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 2f34307ea34741bd6ff4b2e04b7436555c25a4e3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683729"
---
# <a name="ca1061-do-not-hide-base-class-methods"></a>CA1061: Taban sınıf yöntemlerini gizlemeyin
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1061: taban sınıf yöntemlerini gizlemeyin](https://docs.microsoft.com/visualstudio/code-quality/ca1061-do-not-hide-base-class-methods).  
  
TypeName | DoNotHideBaseClassMethods |  
| Checkıd | CA1061 |  
| Kategori | Microsoft.Design|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Türetilmiş bir tür bir yöntem aynı ada sahip ve aynı parametre sayısı temel yöntemlerinden biri olarak bildirir; bir veya daha fazla parametre karşılık gelen temel yöntemin parametre temel türüdür; ve karşılık gelen temel yöntemin parametreleri özdeş türleri kalan parametreye sahip.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Türetilmiş yöntemin parametre imzası yalnızca türetilmiş türleri ve karşılık gelen temel yöntemin parametre imzası daha zayıf türlerine göre farklı olduğu durumlarda temel türde bir yöntemin türetilmiş türle aynı adlı bir yöntemi tarafından gizlenir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için kaldırmak veya metodu yeniden adlandırmak veya parametre imzası yöntem taban yöntemi gizlemez şekilde değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, kuralını ihlal eden bir yöntemi gösterir.  
  
 [!code-csharp[FxCop.Design.HideBaseMethod#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.HideBaseMethod/cs/FxCop.Design.HideBaseMethod.cs#1)]



