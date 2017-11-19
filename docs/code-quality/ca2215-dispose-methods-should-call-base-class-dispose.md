---
title: "CA2215: Atma yöntemleri taban sınıf atmayı çağırmalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2215
- DisposeMethodsShouldCallBaseClassDispose
- Dispose methods should call base class dispose
helpviewer_keywords:
- DisposeMethodsShouldCallBaseClassDispose
- CA2215
ms.assetid: c772e7a6-a87e-425c-a70e-912664ae9042
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0659b9ec82353e3c658f1ba89f07fad197dd8670
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2215-dispose-methods-should-call-base-class-dispose"></a>CA2215: Atma yöntemleri taban sınıf atmayı çağırmalıdır
|||  
|-|-|  
|TypeName|DisposeMethodsShouldCallBaseClassDispose|  
|CheckId|CA2215|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Uygulayan bir tür <xref:System.IDisposable?displayProperty=fullName> de uygulayan bir türden devralır <xref:System.IDisposable>. <xref:System.IDisposable.Dispose%2A> Türetilen türünün yöntemi çağırmaz <xref:System.IDisposable.Dispose%2A> üst türü yöntemi.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir tür bir seferlik türünden devralan varsa çağırmalıdır <xref:System.IDisposable.Dispose%2A> yöntemi kendi içinde temel türün <xref:System.IDisposable.Dispose%2A> yöntemi. Temel türü yönteminin çağrılması Dispose öğesini temel türü tarafından oluşturulan tüm kaynakları serbest bırakılır sağlar.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için arama `base`.<xref:System.IDisposable.Dispose%2A> içinde <xref:System.IDisposable.Dispose%2A> yöntemi.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Varsa bir uyarı bu kuraldan gizlemek güvenlidir çağrısı `base`.<xref:System.IDisposable.Dispose%2A> kural denetimleri daha derin bir arama düzeyinde gerçekleşir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir tür gösterir `TypeA` uygulayan <xref:System.IDisposable>.  
  
 [!code-csharp[FxCop.Usage.IDisposablePattern#1](../code-quality/codesnippet/CSharp/ca2215-dispose-methods-should-call-base-class-dispose_1.cs)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir tür gösterir `TypeB` türünden devralan `TypeA` ve doğru bir şekilde kendi <xref:System.IDisposable.Dispose%2A> yöntemi.  
  
 [!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../code-quality/codesnippet/VisualBasic/ca2215-dispose-methods-should-call-base-class-dispose_2.vb)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.IDisposable?displayProperty=fullName>   
 [Desen dispose](/dotnet/standard/design-guidelines/dispose-pattern)