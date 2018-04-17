---
title: 'CA2213: Atılabilen alanlar atılmalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- DisposableFieldsShouldBeDisposed
- CA2213
helpviewer_keywords:
- CA2213
- DisposableFieldsShouldBeDisposed
ms.assetid: e99442c9-70e2-47f3-b61a-d8ac003bc6e5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 89f861db9c6e22492a8720a5890020cce26a4f43
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2213-disposable-fields-should-be-disposed"></a>CA2213: Atılabilen alanlar atılmalıdır
|||  
|-|-|  
|TypeName|DisposableFieldsShouldBeDisposed|  
|CheckId|CA2213|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Uygulayan bir tür <xref:System.IDisposable?displayProperty=fullName> de tür alanları bildirir <xref:System.IDisposable>. <xref:System.IDisposable.Dispose%2A> Alanının yöntemi çağrılmaz <xref:System.IDisposable.Dispose%2A> yöntemi bildiri türü.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir tür, kendi yönetilmeyen tüm kaynaklarını atma sorumludur; Bu uygulama tarafından gerçekleştirilir <xref:System.IDisposable>. Bu kural, bir seferlik türü olup olmadığını görmek için denetler `T` bir alan bildirir `F` diğer bir deyişle bir seferlik türünün örneği `FT`. Her bir alan için `F`, kural için bir çağrı bulmayı dener `FT.Dispose`. Kural çağrılan yöntemler arar `T.Dispose`ve daha düşük bir düzey (çağrılan yöntemler tarafından çağrılan yöntemler `FT.Dispose`).  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için arama <xref:System.IDisposable.Dispose%2A> uygulayan türleridir alanlar <xref:System.IDisposable> tahsis etmek için sorumludur ve tutulan alanı tarafından yönetilmeyen kaynakları serbest bırakma.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan kaynak serbest alanın taşıdığı için sorumlu değilseniz veya gizlemek güvenlidir çağrısı <xref:System.IDisposable.Dispose%2A> kural denetimleri daha derin bir arama düzeyinde gerçekleşir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir tür gösterir `TypeA` uygulayan <xref:System.IDisposable> (`FT` previosu tartışma içinde).  
  
 [!code-csharp[FxCop.Usage.IDisposablePattern#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_1.cs)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir tür gösterir `TypeB` , ihlal bu kural bir alan bildirerek `aFieldOfADisposableType` (`F` Önceki tartışmaya) tek kullanımlık bir tür olarak (`TypeA`) ve değil çağırma <xref:System.IDisposable.Dispose%2A> alanı. `TypeB` karşılık gelen `T` önceki tartışma içinde.  
  
 [!code-csharp[FxCop.Usage.IDisposableFields#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_2.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.IDisposable?displayProperty=fullName>   
 [Dispose Deseni](/dotnet/standard/design-guidelines/dispose-pattern)