---
title: 'CA2002: zayıf kimliği olan nesneleri kilitlemeyin | Microsoft Docs'
ms.custom: ''
ms.date: 01/31/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- DoNotLockOnObjectsWithWeakIdentity
- CA2002
helpviewer_keywords:
- CA2002
- DoNotLockOnObjectsWithWeakIdentity
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: d509de487bd81b4401195a8e3564c165a2d50f0a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2002-do-not-lock-on-objects-with-weak-identity"></a>CA2002: Zayıf kimliği olan nesneleri kilitlemeyin

|||
|-|-|
|TypeName|DoNotLockOnObjectsWithWeakIdentity|
|CheckId|CA2002|
|Kategori|Microsoft.Reliability|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep

Bir iş parçacığı, zayıf bir kimliğe sahip bir nesne üzerinde bir kilit almayı dener.

## <a name="rule-description"></a>Kural açıklaması

Bir nesneye uygulama etki alanları arasından erişilebiliyorsa o nesnenin zayıf bir kimliğe sahip olduğu söylenir. Zayıf kimliğe sahip bir nesne üzerinde kilit almayı deneyen iş parçacığı aynı nesne üzerinde bir kilide sahip olan farklı uygulama etki alanı içindeki ikinci iş parçacığı tarafından engellenebilir.

Aşağıdaki türler zayıf bir kimliğe sahip ve kural tarafından işaretlenen:

- <xref:System.String>

- Değer türleri dahil olmak üzere, dizilerin [tam sayı türleri](/dotnet/csharp/language-reference/keywords/integral-types-table), [kayan nokta türleri](/dotnet/csharp/language-reference/keywords/floating-point-types-table), ve <xref:System.Boolean>.

- <xref:System.MarshalByRefObject>

- <xref:System.ExecutionEngineException>

- <xref:System.OutOfMemoryException>

- <xref:System.StackOverflowException>

- <xref:System.Reflection.MemberInfo>

- <xref:System.Reflection.ParameterInfo>

- <xref:System.Threading.Thread>

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?

Bu kural ihlal düzeltmek için nesneyi Açıklama bölümündeki listesinde olmayan türünden kullanın.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında

Bu kuraldan uyarıyı bastırmayın.

## <a name="related-rules"></a>İlgili kuralları

[CA2213: Atılabilen alanlar atılmalıdır](../code-quality/ca2213-disposable-fields-should-be-disposed.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek kural ihlal bazı nesne kilitleri gösterir.

[!code-vb[FxCop.Reliability.LockWeakObjects#1](../code-quality/codesnippet/VisualBasic/ca2002-do-not-lock-on-objects-with-weak-identity_1.vb)]
[!code-csharp[FxCop.Reliability.LockWeakObjects#1](../code-quality/codesnippet/CSharp/ca2002-do-not-lock-on-objects-with-weak-identity_1.cs)]

## <a name="see-also"></a>Ayrıca bkz.

<xref:System.Threading.Monitor>  
<xref:System.AppDomain>  
[lock deyimi (C#)](/dotnet/csharp/language-reference/keywords/lock-statement)  
[SyncLock deyimi (Visual Basic)](/dotnet/visual-basic/language-reference/statements/synclock-statement)