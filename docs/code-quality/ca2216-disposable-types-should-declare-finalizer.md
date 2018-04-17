---
title: 'CA2216: Atılabilir türler sonlandırıcıyı bildirmelidir | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- DisposableTypesShouldDeclareFinalizer
- CA2216
helpviewer_keywords:
- CA2216
- DisposableTypesShouldDeclareFinalizer
ms.assetid: 0cabcc5e-b526-452b-8c2a-0cbe3b93c0ef
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3023967091c09610791f5032731772aa15b8bf6c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2216-disposable-types-should-declare-finalizer"></a>CA2216: Atılabilir türler sonlandırıcıyı bildirmelidir
|||  
|-|-|  
|TypeName|DisposableTypesShouldDeclareFinalizer|  
|CheckId|CA2216|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Uygulayan bir tür <xref:System.IDisposable?displayProperty=fullName>ve yönetilmeyen kaynakları kullanımını önermek alanları sahipse, bir Sonlandırıcısı tarafından açıklandığı şekilde uygulamıyor <xref:System.Object.Finalize%2A?displayProperty=fullName>.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Aşağıdaki türlerde alanları tek kullanımlık türü içeriyorsa, bu kural ihlal bildirdi:  
  
-   <xref:System.IntPtr?displayProperty=fullName>  
  
-   <xref:System.UIntPtr?displayProperty=fullName>  
  
-   <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName>  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için çağıran bir sonlandırıcı uygulamak, <xref:System.IDisposable.Dispose%2A> yöntemi.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan türü uygulamazsa gizlemek güvenlidir <xref:System.IDisposable> amacıyla yönetilmeyen kaynakları serbest bırakma.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bu kural ihlal eden bir tür gösterir.  
  
 [!code-csharp[FxCop.Usage.DisposeNoFinalize#1](../code-quality/codesnippet/CSharp/ca2216-disposable-types-should-declare-finalizer_1.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2115: Yerel kaynaklar kullanırken GC.KeepAlive'ı çağırın](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)  
  
 [CA1816: GC.SuppressFinalize öğesini doğru çağırın](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)  
  
 [CA1049: Yerel kaynaklara sahip olan türler atılabilir olmalıdır](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.IDisposable?displayProperty=fullName>   
 <xref:System.IntPtr?displayProperty=fullName>   
 <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName>   
 <xref:System.UIntPtr?displayProperty=fullName>   
 <xref:System.Object.Finalize%2A?displayProperty=fullName>   
 [Dispose Deseni](/dotnet/standard/design-guidelines/dispose-pattern)