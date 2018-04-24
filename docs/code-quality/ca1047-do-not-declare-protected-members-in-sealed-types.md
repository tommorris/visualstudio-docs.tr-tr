---
title: 'CA1047: Korumalı türlerde korunan üyeleri bildirmeyin'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotDeclareProtectedMembersInSealedTypes
- CA1047
helpviewer_keywords:
- CA1047
- DoNotDeclareProtectedMembersInSealedTypes
ms.assetid: 829033b5-a9d8-4f26-a719-45494c9dd035
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f25af4cf9ddd86bd28b5909242ab55f35a467438
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1047-do-not-declare-protected-members-in-sealed-types"></a>CA1047: Korumalı türlerde korunan üyeleri bildirmeyin
|||
|-|-|
|TypeName|DoNotDeclareProtectedMembersInSealedTypes|
|CheckId|CA1047|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Genel bir tür `sealed` (`NotInheritable` Visual Basic'te) ve korumalı üye ya da korumalı bir iç içe geçmiş tür bildirir. Bu kural ihlali bildirmez <xref:System.Object.Finalize%2A> bu deseni izlemelidir yöntemleri.

## <a name="rule-description"></a>Kural Tanımı
 Türler, devralmasına erişebileceğiniz veya üyeyi geçersiz kılmak için korunan üyelerin türlerini bildirir. Tanımı gereği, yöntemlere korumalı türlerde korunan anlamına adlı bir korumalı türünden devralan olamaz.

 C# Derleyici, bu hata için bir uyarı verir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için üyenin erişim düzeyini özel değiştirmek veya türü devralınabilir olun.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın. Türü geçerli durumunda bırakarak bakım sorunlara neden olabilir ve tüm avantajları sağlamaz.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bu kural ihlal eden bir tür gösterir.

 [!code-vb[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/VisualBasic/ca1047-do-not-declare-protected-members-in-sealed-types_1.vb)]
 [!code-csharp[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/CSharp/ca1047-do-not-declare-protected-members-in-sealed-types_1.cs)]