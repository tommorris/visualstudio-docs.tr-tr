---
title: 'CA1816: GC.SuppressFinalize öğesini doğru çağırın'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1816
- DisposeMethodsShouldCallSuppressFinalize
helpviewer_keywords:
- DisposeMethodsShouldCallSuppressFinalize
- CA1816
ms.assetid: 47915fbb-103f-4333-b157-1da16bf49660
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e3c3b7a7dd5e7c9ed8e5b713578dd682384dbf30
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31916122"
---
# <a name="ca1816-call-gcsuppressfinalize-correctly"></a>CA1816: GC.SuppressFinalize öğesini doğru çağırın
|||
|-|-|
|TypeName|CallGCSuppressFinalizeCorrectly|
|CheckId|CA1816|
|Kategori|Microsoft. Kullanım|
|Yeni Değişiklik|Olmayan sonu|

## <a name="cause"></a>Sebep

-   Öğesinin bir uygulamasıdır bir yöntem <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> çağrılmayan <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.

-   Uygulaması olmayan bir yöntem <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> çağrıları <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.

-   Bir yöntemi çağırır <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> ve bu (Me Visual Basic'te) dışında bir şey geçirir.

## <a name="rule-description"></a>Kural Tanımı
 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> Yöntemi çöp koleksiyonu için kullanılabilir hale nesne önce herhangi bir zamanda kaynakları serbest bırakmak kullanıcıların olanak tanır. Varsa <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> yöntemi çağrıldığında, nesnenin kaynakları serbest bırakır. Bu, sonlandırma gereksiz kılar. <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> çağırmalıdır <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> atık toplayıcı nesnesi sonlandırıcıyı çağırmaz şekilde.

 Türetilen türlerin sonlandırıcılar ile yeniden uygulamak bırakılmasını engellemek için <xref:System.IDisposable> ve onu aramak için korumasız türleri sonlandırıcılar olmadan hala çağırmalıdır <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için:

 Yöntem uygulaması ise <xref:System.IDisposable.Dispose%2A>, bir çağrı ekleyin <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.

 Yöntemin bir uygulaması, değilse <xref:System.IDisposable.Dispose%2A>, çağrıyı kaldırın ya da <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> veya tipinin taşıma <xref:System.IDisposable.Dispose%2A> uygulaması.

 Tüm çağrıları değiştirmek <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> bu (Me Visual Basic'te) geçirmek için.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Kullanarak deliberating, yalnızca bir bu kuraldan gizlemek <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> diğer nesnelerin ömrü denetlemek için. Uygulaması, bu kural bir uyarıdan engelleme <xref:System.IDisposable.Dispose%2A> çağrılmayan <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>. Bu durumda, sonlandırma gizlemek başarısız olan performansı düşürür ve hiçbir fayda sağlar.

## <a name="example"></a>Örnek
 Aşağıdaki örnek bir yöntem çağrıları bu yanlış gösterir <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.

 [!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../code-quality/codesnippet/VisualBasic/ca1816-call-gc-suppressfinalize-correctly_1.vb)]
 [!code-csharp[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../code-quality/codesnippet/CSharp/ca1816-call-gc-suppressfinalize-correctly_1.cs)]

## <a name="example"></a>Örnek
 Aşağıdaki örnek bir yöntem çağrıları, doğru bir şekilde gösterir <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.

 [!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../code-quality/codesnippet/VisualBasic/ca1816-call-gc-suppressfinalize-correctly_2.vb)]
 [!code-csharp[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../code-quality/codesnippet/CSharp/ca1816-call-gc-suppressfinalize-correctly_2.cs)]

## <a name="related-rules"></a>İlgili kuralları
 [CA2215: Atma yöntemleri taban sınıf atmayı çağırmalıdır](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)

 [CA2216: Atılabilir türler sonlandırıcıyı bildirmelidir](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)

## <a name="see-also"></a>Ayrıca Bkz.
 [Dispose Deseni](/dotnet/standard/design-guidelines/dispose-pattern)