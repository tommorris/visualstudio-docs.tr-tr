---
title: 'CA1049: Yerel kaynaklara sahip olan türler atılabilir olmalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1049
- TypesThatOwnNativeResourcesShouldBeDisposable
helpviewer_keywords:
- TypesThatOwnNativeResourcesShouldBeDisposable
- CA1049
ms.assetid: 084e587d-0e45-4092-b767-49eed30d6a35
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 0f96f737274204018be3b30aaa4d85e07cc59f53
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1049-types-that-own-native-resources-should-be-disposable"></a>CA1049: Yerel kaynaklara sahip olan türler atılabilir olmalıdır
|||
|-|-|
|TypeName|TypesThatOwnNativeResourcesShouldBeDisposable|
|CheckId|CA1049|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Bir türüne başvuran bir <xref:System.IntPtr?displayProperty=fullName> alan, bir <xref:System.UIntPtr?displayProperty=fullName> alanında veya bir <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName> alan, ancak uygulamayan <xref:System.IDisposable?displayProperty=fullName>.

## <a name="rule-description"></a>Kural Tanımı
 Bu kural varsayar <xref:System.IntPtr>, <xref:System.UIntPtr>, ve <xref:System.Runtime.InteropServices.HandleRef> alanları yönetilmeyen kaynakları işaretçiler depolar. Yönetilmeyen kaynakları tahsis türleri uygulamanız gerekir <xref:System.IDisposable> isteğe bağlı olarak bu kaynakları serbest bırakır ve kaynakları tutun nesnelerin ömrü kısaltmak için arayanlara izin vermek için.

 Yönetilmeyen kaynakları temizlemek için önerilen tasarım deseni örtülü ve kullanarak bu kaynakları boşaltmak için açık bir şekilde sağlamaktır <xref:System.Object.Finalize%2A?displayProperty=fullName> yöntemi ve <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> yöntemi, sırasıyla. Çöp toplayıcı çağrıları <xref:System.Object.Finalize%2A> yöntemi nesnenin nesne artık erişilebilir olması belirlendikten sonra belirsiz bir süre. Sonra <xref:System.Object.Finalize%2A> çağrılır, ek bir atık toplama nesne serbest için gereklidir. <xref:System.IDisposable.Dispose%2A> Açıkça isteğe bağlı olarak, kaynaklar, atık toplayıcı bırakılırsa serbest ' den önceki kaynakları serbest bırakmak arayan bir yöntem sağlar. Yönetilmeyen kaynakları, temizler sonra <xref:System.IDisposable.Dispose%2A> çağırmalıdır <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> bilmesi için Atık toplayıcısının olanak yöntemi <xref:System.Object.Finalize%2A> çağrılacak; artık sahip bu ek çöp toplama gereksinimini ortadan kaldırır ve kısaltır nesne ömrü.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için uygulama <xref:System.IDisposable>.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Yönetilmeyen bir kaynak türü başvurmaması durumunda bu kural bir uyarıdan gizlemek güvenlidir. Aksi takdirde, bu kural bir uyarıdan çünkü engelleme uygulamak için hata <xref:System.IDisposable> yönetilmeyen kaynakları kullanılamıyor veya kapatacağı hale gelmesine neden olabilir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, uygulayan bir tür gösterir <xref:System.IDisposable> bir yönetilmeyen kaynak temizleme.

 [!code-csharp[FxCop.Design.UnmanagedResources#1](../code-quality/codesnippet/CSharp/ca1049-types-that-own-native-resources-should-be-disposable_1.cs)]
 [!code-vb[FxCop.Design.UnmanagedResources#1](../code-quality/codesnippet/VisualBasic/ca1049-types-that-own-native-resources-should-be-disposable_1.vb)]

## <a name="related-rules"></a>İlgili kuralları
 [CA2115: Yerel kaynaklar kullanırken GC.KeepAlive'ı çağırın](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)

 [CA1816: GC.SuppressFinalize öğesini doğru çağırın](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)

 [CA2216: Atılabilir türler sonlandırıcıyı bildirmelidir](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)

 [CA1001: Atılabilir alanlara sahip olan türler atılabilir olmalıdır](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)

## <a name="see-also"></a>Ayrıca Bkz.
 [Yönetilmeyen kaynakları Temizleme](/dotnet/standard/garbage-collection/unmanaged) [Dispose düzeni](/dotnet/standard/design-guidelines/dispose-pattern)