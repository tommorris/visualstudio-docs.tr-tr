---
title: 'CA1033: Arabirim yöntemleri alt türler tarafından çağırılabilir olmalıdır'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- InterfaceMethodsShouldBeCallableByChildTypes
- CA1033
helpviewer_keywords:
- CA1033
- InterfaceMethodsShouldBeCallableByChildTypes
ms.assetid: 9f171497-a5e3-4769-a77b-7aed755b2662
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c41b19d9d4a82e25223a9cf7b04034b37c3f45fb
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1033-interface-methods-should-be-callable-by-child-types"></a>CA1033: Arabirim yöntemleri alt türler tarafından çağırılabilir olmalıdır
|||
|-|-|
|TypeName|InterfaceMethodsShouldBeCallableByChildTypes|
|CheckId|CA1033|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Ağzı açık dışarıdan görünen bir tür açık yöntem uygulaması ortak bir arabirim sağlar ve aynı ada sahip alternatif dışarıdan görünen bir yöntem sağlamaz.

## <a name="rule-description"></a>Kural Tanımı
 Açıkça ortak arabirim yöntemini kullanan bir taban türü göz önünde bulundurun. Taban türünden türeyen bir tür devralınan arabirim yöntemini yalnızca geçerli örneğine başvuru erişebilirsiniz (`this` C#) arabirimine atamalısınız. Türetilen türü (açıkça) devralınan arabirim yöntemini yeniden uygularsa, temel uygulamayı artık erişilebilir. Geçerli örnek başvuru çağrısıyla türetilmiş uygulamasına çağıracağı; Bu özyineleme ve nihai yığın taşması neden olur.

 Bu kural, açık bir uygulama için bir ihlali bildirmez <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> bir harici olarak görünür olduğunda `Close()` veya `System.IDisposable.Dispose(Boolean)` yöntemi sağlanır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için aynı işlevselliği sunar ve türetilmiş türler için görünür olan yeni bir yöntem veya açıkça verilmemiş bir uygulama değiştirin. Önemli bir değişiklik kabul edilebilir ise, bir alternatif korumalı türü olmasını sağlamaktır.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Açıkça gerçekleştirilen yöntem adından farklı ancak aynı işlevselliğe sahip sağlanan dışarıdan görünür bir yöntemi ise bir uyarı bu kuraldan gizlemek güvenlidir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bir tür gösterir `ViolatingBase`, kural ve bir tür ihlal `FixedBase`, ihlalin için bir düzeltme gösterir.

 [!code-csharp[FxCop.Design.ExplicitMethodImplementations#1](../code-quality/codesnippet/CSharp/ca1033-interface-methods-should-be-callable-by-child-types_1.cs)]

## <a name="see-also"></a>Ayrıca Bkz.
 [Arabirimler](/dotnet/csharp/programming-guide/interfaces/index)