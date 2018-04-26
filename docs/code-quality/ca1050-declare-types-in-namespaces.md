---
title: 'CA1050: Ad alanlarında türleri bildirin'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1050
- DeclareTypesInNamespaces
helpviewer_keywords:
- DeclareTypesInNamespaces
- CA1050
ms.assetid: 1002748d-ac8d-404f-85dd-7a12d1ad3e05
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bf38fde258a033fd4050e93d3ad69015f365dc60
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1050-declare-types-in-namespaces"></a>CA1050: Ad alanlarında türleri bildirin
|||
|-|-|
|TypeName|DeclareTypesInNamespaces|
|CheckId|CA1050|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir genel ya da korumalı türü adlandırılmış bir ad alanı kapsamı dışında tanımlanır.

## <a name="rule-description"></a>Kural Tanımı
 Türleri ad çakışmaları önlemek için ad ve bir nesne hiyerarşisi ilgili türlerinde düzenlemek için bir yol olarak bildirilir. Herhangi bir adlandırılmış ad alanı dışında olan kodda başvurulamaz genel bir ad alanındaki türleridir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için bir ad alanındaki türü yerleştirin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural bir uyarıdan gizlemek hiçbir zaman sahip olsa da derlemeyi hiçbir zaman diğer derlemeler ile birlikte kullanılması durumunda bunu yapmak güvenlidir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, hatalı bir ad alanı dışında bildirilen bir türe sahip bir kitaplık ve bir ad alanında bildirilen aynı ada sahip bir tür gösterir.

 [!code-csharp[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_1.cs)]
 [!code-vb[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_1.vb)]

## <a name="example"></a>Örnek
 Aşağıdaki uygulama önceden tanımlanmış kitaplığını kullanır. Bir ad alanı dışında bildirilmiş türü ne zaman oluşturulduğunu unutmayın adı `Test` bir ad alanı tarafından yetkili değil. Erişim için ayrıca `Test` yazın `Goodspace`, ad alanı adı gereklidir.

 [!code-csharp[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_2.cs)]
 [!code-vb[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_2.vb)]