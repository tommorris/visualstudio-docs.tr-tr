---
title: 'CA1001: Atılabilir alanlara sahip olan türler atılabilir olmalıdır'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1001
- TypesThatOwnDisposableFieldsShouldBeDisposable
helpviewer_keywords:
- CA1001
- TypesThatOwnDisposableFieldsShouldBeDisposable
ms.assetid: c85c126c-2b16-4505-940a-b5ddf873fb22
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d3def21cf32dd45c006045a5301293da2a5d0f70
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1001-types-that-own-disposable-fields-should-be-disposable"></a>CA1001: Atılabilir alanlara sahip olan türler atılabilir olmalıdır
|||
|-|-|
|TypeName|TypesThatOwnDisposableFieldsShouldBeDisposable|
|CheckId|CA1001|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Bölünemez - türü dışında derleme görünür değilse.<br /><br /> Derlemenin dışından türü görünmüyorsa - kesiliyor.|

## <a name="cause"></a>Sebep
 Bir sınıf bildirir ve bir örnek alanındaki uygulayan bir <xref:System.IDisposable?displayProperty=fullName> türü ve sınıf uygulamıyor <xref:System.IDisposable>.

## <a name="rule-description"></a>Kural Tanımı
 Bir sınıf uygular <xref:System.IDisposable> sahibi yönetilmeyen kaynaklarını silmek için arabirim. Bir örnek alanındaki bir <xref:System.IDisposable> türünü gösteren alan bir yönetilmeyen kaynağına sahip. Bildiren bir sınıf bir <xref:System.IDisposable> alan dolaylı bir yönetilmeyen kaynağın sahibi ve uygulamalıdır <xref:System.IDisposable> arabirimi. Sınıfın doğrudan yönetilmeyen kaynakları sahip olmadığından, bir sonlandırıcı uygulamalıdır değil.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için uygulama <xref:System.IDisposable> ve <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> yöntem çağrısı <xref:System.IDisposable.Dispose%2A> alanının yöntemi.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, kural ihlal eden bir ve kural uygulayarak karşılayan bir sınıfı gösterir <xref:System.IDisposable>. Sınıfın doğrudan tüm yönetilmeyen kaynaklar kendisine ait değil çünkü sınıfı bir sonlandırıcı uygulamıyor.

 [!code-vb[FxCop.Design.DisposableFields#1](../code-quality/codesnippet/VisualBasic/ca1001-types-that-own-disposable-fields-should-be-disposable_1.vb)]
 [!code-csharp[FxCop.Design.DisposableFields#1](../code-quality/codesnippet/CSharp/ca1001-types-that-own-disposable-fields-should-be-disposable_1.cs)]

## <a name="related-rules"></a>İlgili kuralları
 [CA2213: Atılabilen alanlar atılmalıdır](../code-quality/ca2213-disposable-fields-should-be-disposed.md)

 [CA2216: Atılabilir türler sonlandırıcıyı bildirmelidir](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)

 [CA2215: Atma yöntemleri taban sınıf atmayı çağırmalıdır](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)

 [CA1049: Yerel kaynaklara sahip olan türler atılabilir olmalıdır](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)