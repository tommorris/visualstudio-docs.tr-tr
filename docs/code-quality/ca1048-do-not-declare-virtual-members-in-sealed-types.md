---
title: 'CA1048: Korumalı türlerde sanal üyeleri bildirme'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotDeclareVirtualMembersInSealedTypes
- CA1048
helpviewer_keywords:
- DoNotDeclareVirtualMembersInSealedTypes
- CA1048
ms.assetid: 5dcf4a30-6f98-48a8-b8cc-7b89ea757262
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 38ba776cb423773ca6c5a4646bbf30531cd2d27f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31897362"
---
# <a name="ca1048-do-not-declare-virtual-members-in-sealed-types"></a>CA1048: Korumalı türlerde sanal üyeleri bildirme
|||
|-|-|
|TypeName|DoNotDeclareVirtualMembersInSealedTypes|
|CheckId|CA1048|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Ortak tür korumalı ve hem de bir yöntem bildirir `virtual` (`Overridable` Visual Basic'te) ve son değil. Bu kural ihlalleri bu deseni izlemelidir temsilci türleri için raporlamaz.

## <a name="rule-description"></a>Kural Tanımı
 Türler yöntemi sanal olarak bildirir, böylece devralan türler sanal yöntemin uygulanmasını geçersiz kılabilir. Tanımı gereği, sanal bir yöntem korumalı türüne anlamsız yapmadan korumalı bir türden devralır olamaz.

 Visual Basic ve C# Derleyicileri türleri bu kural ihlal izin vermez.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için yöntem sanal olmayan yaptığınızda veya türü devralınabilir.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın. Türü geçerli durumunda bırakarak bakım sorunlara neden olabilir ve tüm avantajları sağlamaz.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bu kural ihlal eden bir tür gösterir.

 [!code-cpp[FxCop.Design.SealedVirtual#1](../code-quality/codesnippet/CPP/ca1048-do-not-declare-virtual-members-in-sealed-types_1.cpp)]