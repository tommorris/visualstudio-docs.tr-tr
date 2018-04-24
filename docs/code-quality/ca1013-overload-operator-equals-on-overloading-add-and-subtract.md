---
title: 'CA1013: Eşittir işlecini ekleme ve çıkarmayı aşırı yükleyerek aşırı yükleyin'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- OverrideOperatorEqualsOnOverridingAddAndSubtract
- OverrideOperatorEqualsOnOverloadingAddAndSubtract
- CA1013
- OverloadOperatorEqualsOnOverloadingAddAndSubtract
helpviewer_keywords:
- OverrideOperatorEqualsOnOverloadingAddAndSubtract
- OverrideOperatorEqualsOnOverridingAddAndSubtract
- CA1013
- OverloadOperatorEqualsOnOverloadingAddAndSubtract
ms.assetid: 5bd28d68-c179-49ff-af47-5250b8b18a10
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7fd43cc3077c037b70eaa8107563bd8f40b6a096
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1013-overload-operator-equals-on-overloading-add-and-subtract"></a>CA1013: Eşittir işlecini ekleme ve çıkarmayı aşırı yükleyerek aşırı yükleyin
|||
|-|-|
|TypeName|OverloadOperatorEqualsOnOverloadingAddAndSubtract|
|CheckId|CA1013|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Bir genel ya da korumalı tür eşitlik imlecini uygulamadan ekleme ya da çıkarma işleçlerini uygular.

## <a name="rule-description"></a>Kural Tanımı
 Toplama ve çıkarma gibi işlemleri kullanarak bir türün örneklerinin birleştirilebilir, neredeyse her zaman döndürülecek eşitlik tanımlarsınız `true` bağlı değerleri aynı olan iki örnekleri için.

 Varsayılan eşitlik işleci aşırı yüklenmiş bir eşitlik işleci uygulamasında kullanamazsınız. Bunun yapılması bir yığın taşması neden olur. Eşitlik işleci uygulamak için uygulamanızda Object.Equals yöntemini kullanın. Aşağıdaki örnekte bakın.

```vb
If (Object.ReferenceEquals(left, Nothing)) Then
    Return Object.ReferenceEquals(right, Nothing)
Else
    Return left.Equals(right)
End If
```

```csharp
if (Object.ReferenceEquals(left, null))
    return Object.ReferenceEquals(right, null);
return left.Equals(right);
```

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için böylece toplama ve çıkarma işleçlerle matematiksel tutarlı eşitlik işleci uygulayın.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural bir uyarıdan eşitlik işleci varsayılan uygulaması türü için doğru davranış sağladığında gizlemek güvenlidir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bir tür tanımlar (`BadAddableType`), bu kural ihlal ediyor. Bu tür test aynı alan değerleri olan iki örnekleri yapmak için eşitlik işleci uygulamalıdır `true` eşitlik için. Türü `GoodAddableType` düzeltilmiş uygulamasını gösterir. Bu tür ayrıca eşitsizlik işleci uygular ve geçersiz kılmalar Not <xref:System.Object.Equals%2A> diğer kurallar karşılamak için. Tam bir uygulama da uygulamak <xref:System.Object.GetHashCode%2A>.

 [!code-csharp[FxCop.Design.AddAndSubtract#1](../code-quality/codesnippet/CSharp/ca1013-overload-operator-equals-on-overloading-add-and-subtract_1.cs)]

## <a name="example"></a>Örnek
 Aşağıdaki örnek, varsayılan ve doğru davranış için eşitlik işleci göstermek için bu konudaki daha önceden tanımlanan türlerin örnekleri kullanarak eşitlik için test eder.

 [!code-csharp[FxCop.Design.TestAddAndSubtract#1](../code-quality/codesnippet/CSharp/ca1013-overload-operator-equals-on-overloading-add-and-subtract_2.cs)]

 Bu örnek şu çıkışı üretir.

 **Hatalı türü: {2,2} {2,2} eşit? Hayır**
**iyi türü: {3,3} {3,3} eşit? Evet**
**iyi türü: {3,3} == {3,3} misiniz?   Evet**
**hatalı türü: {2,2} {9,9} eşit? Hayır**
**iyi türü: {3,3} == {9,9} misiniz?   Yok**
## <a name="see-also"></a>Ayrıca Bkz.
 [Eşitlik İşleçleri](/dotnet/standard/design-guidelines/equality-operators)