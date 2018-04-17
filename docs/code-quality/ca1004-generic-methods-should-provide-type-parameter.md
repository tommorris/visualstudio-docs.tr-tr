---
title: 'CA1004: Genel yöntemler tür parametresi sağlamalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1004
- GenericMethodsShouldProvideTypeParameter
helpviewer_keywords:
- GenericMethodsShouldProvideTypeParameter
- CA1004
ms.assetid: 38755f6a-fb45-4bf2-932e-0354ad826499
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f386530082f6bc44597dc33e5a034c71cbc17de9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1004-generic-methods-should-provide-type-parameter"></a>CA1004: Genel metotlar tür parametresi sağlamalıdır
|||  
|-|-|  
|TypeName|GenericMethodsShouldProvideTypeParameter|  
|CheckId|CA1004|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Dışarıdan görünür bir genel yöntem parametresi imzası tüm türü yönteminin parametreleri için karşılık gelen türlerine sahip değil.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Tip argümanının açıkça özelleştirilmesi yerine yöntemi geçen argüman tipiyle tanımlanan genel yöntemin nasıl tip argümanı olduğunun sonucudur. Çıkarımı etkinleştirmek için bir genel yöntem parametre imzası yöntem türü parametresi gibi aynı türde bir parametre içermelidir. Bu durumda, tip bağımsız değişkeninin belirtilmesine gerek yoktur. Çıkarım tüm türü parametrelerini kullandığınızda, genel ve nongeneric örnek yöntemleri çağırma söz dizimi aynıdır. Genel yöntemler kullanılabilirliğini basitleştirir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için tasarım yöntemi her tür parametresi için aynı türde parametre imzası içeren şekilde değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Genel türler anlamak ve kullanmak kolay bir sözdiziminde sağlama öğrenmek için gerekli olan ve yeni kitaplıklar benimseme oranı artırır süreyi azaltır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, iki genel yöntem çağırma sözdizimi gösterilmektedir. Tür bağımsız değişkeni için `InferredTypeArgument` algılanır ve tür bağımsız değişkeni için `NotInferredTypeArgument` açıkça belirtilmesi gerekir.  
  
 [!code-vb[FxCop.Design.Inference#1](../code-quality/codesnippet/VisualBasic/ca1004-generic-methods-should-provide-type-parameter_1.vb)]
 [!code-csharp[FxCop.Design.Inference#1](../code-quality/codesnippet/CSharp/ca1004-generic-methods-should-provide-type-parameter_1.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1005: Genel türlerde aşırı parametrelerden kaçının](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)  
  
 [CA1010: Koleksiyonlar genel arabirim uygulamalıdır](../code-quality/ca1010-collections-should-implement-generic-interface.md)  
  
 [CA1000: Genel türlerde statik üyeleri belirtme](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)  
  
 [CA1002: Genel listeleri gösterme](../code-quality/ca1002-do-not-expose-generic-lists.md)  
  
 [CA1006: Üye imzalarında genel türleri iç içe kullanmayın](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)  
  
 [CA1003: Genel olay işleyici örnekleri kullan](../code-quality/ca1003-use-generic-event-handler-instances.md)  
  
 [CA1007: Uygun yerlerde genel türler kullanın](../code-quality/ca1007-use-generics-where-appropriate.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel Türler](/dotnet/csharp/programming-guide/generics/index)