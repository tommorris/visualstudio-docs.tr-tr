---
title: 'CA2215: Atma yöntemleri taban sınıf atmayı çağırmalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2215
- DisposeMethodsShouldCallBaseClassDispose
- Dispose methods should call base class dispose
helpviewer_keywords:
- DisposeMethodsShouldCallBaseClassDispose
- CA2215
ms.assetid: c772e7a6-a87e-425c-a70e-912664ae9042
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d8eb5c56ab3affe6322a858dfcd34c3b138f26d7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 Varsa bir uyarı bu kuraldan gizlemek güvenlidir çağrısı `base`.<xref:System.IDisposable.Dispose%2A> Kural denetimleri daha derin bir arama düzeyinde gerçekleşir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir tür gösterir `TypeA` uygulayan <xref:System.IDisposable>.  
  
 [!code-csharp[FxCop.Usage.IDisposablePattern#1](../code-quality/codesnippet/CSharp/ca2215-dispose-methods-should-call-base-class-dispose_1.cs)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir tür gösterir `TypeB` türünden devralan `TypeA` ve doğru bir şekilde kendi <xref:System.IDisposable.Dispose%2A> yöntemi.  
  
 [!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../code-quality/codesnippet/VisualBasic/ca2215-dispose-methods-should-call-base-class-dispose_2.vb)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.IDisposable?displayProperty=fullName>   
 [Dispose Deseni](/dotnet/standard/design-guidelines/dispose-pattern)