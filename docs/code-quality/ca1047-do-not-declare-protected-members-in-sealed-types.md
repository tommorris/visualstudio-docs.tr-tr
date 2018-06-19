---
title: 'CA1047: Korumalı türlerde korunan üyeleri bildirmeyin'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: 079d330907981be11e0c07d44c83519975c17560
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31897718"
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