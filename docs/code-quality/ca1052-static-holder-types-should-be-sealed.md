---
title: 'CA1052: Statik tutucu türleri mühürlenmelidir'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- StaticHolderTypesShouldBeSealed
- CA1052
helpviewer_keywords:
- CA1052
- StaticHolderTypesShouldBeSealed
ms.assetid: 51a3165d-781e-4a55-aa0d-ea25fee7d4f2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9d20ed9ab4ed7fc47d601fb6edd6d38675d0ccec
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31897912"
---
# <a name="ca1052-static-holder-types-should-be-sealed"></a>CA1052: Statik tutucu türleri mühürlenmelidir
|||
|-|-|
|TypeName|StaticHolderTypesShouldBeSealed|
|CheckId|CA1052|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir genel ya da korumalı türü yalnızca statik üyeler içerir ve ile bildirilmemiş [korumalı](/dotnet/csharp/language-reference/keywords/sealed) ([NotInheritable](/dotnet/visual-basic/language-reference/modifiers/notinheritable)) değiştiricisi.

## <a name="rule-description"></a>Kural Tanımı
 Bu kural türü türetilen türde de kılınabilir herhangi bir işlevsellik sağlamadığından yalnızca statik üyeleri içeren bir türü devralınması için tasarlanmamıştır olduğunu varsayar. Devralma değiştirilmemelidir bir türü ile işaretlenmelidir `sealed` bir taban türü olarak kullanılmasını önlemek için değiştiricisi.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için türü olarak işaretlemek `sealed`. Hedefliyorsanız [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 2.0 veya sonraki sürümlerde, daha iyi bir tür olarak işaretlemek için yaklaşımdır `static`. Bu şekilde, sınıf oluşturulmasını önlemek için özel bir oluşturucuya bildirmek olmamasına özen gösterin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Türü yalnızca devralınacak şekilde tasarlanmıştır, bu kural bir uyarıdan engelleyin. Yokluğu `sealed` değiştiricisi öneren türü temel tür olarak yararlıdır.

## <a name="example-of-a-violation"></a>Bir ihlali örneği

### <a name="description"></a>Açıklama
 Aşağıdaki örnek kuralını ihlal eden bir tür gösterir.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_1.cs)]
 [!code-vb[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/VisualBasic/ca1052-static-holder-types-should-be-sealed_1.vb)]
 [!code-cpp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CPP/ca1052-static-holder-types-should-be-sealed_1.cpp)]

## <a name="fix-with-the-static-modifier"></a>Statik değiştirici ile Düzelt

### <a name="description"></a>Açıklama
 Aşağıdaki örnek türüyle işaretleyerek bu kural ihlal düzeltmek nasıl gösterir `static` değiştiricisi.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Design.StaticMembersFixed#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_2.cs)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1053: Statik tutucu türlerinde oluşturucular bulunmamalıdır](../code-quality/ca1053-static-holder-types-should-not-have-constructors.md)
