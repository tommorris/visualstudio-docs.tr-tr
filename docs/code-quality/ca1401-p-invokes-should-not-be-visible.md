---
title: 'CA1401: P çağırır görünür olmamalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- PInvokesShouldNotBeVisible
- CA1401
helpviewer_keywords:
- CA1401
- PInvokesShouldNotBeVisible
ms.assetid: 0f4d96c1-f9de-414e-b223-4dc7f691bee3
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c2aaadb0570e47e5ef41614925c20f8dc30f1620
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31900610"
---
# <a name="ca1401-pinvokes-should-not-be-visible"></a>CA1401: P/Invoke'lar görünür olmamalıdır
|||
|-|-|
|TypeName|PInvokesShouldNotBeVisible|
|CheckId|CA1401|
|Kategori|Microsoft.Interoperability|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Ortak tür genel ya da korumalı yönteminde sahip <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> özniteliği (Ayrıca tarafından uygulanan `Declare` in anahtar sözcüğü [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).

## <a name="rule-description"></a>Kural Tanımı
 İle işaretlenen yöntemleri <xref:System.Runtime.InteropServices.DllImportAttribute> özniteliği (veya kullanılarak tanımlanan yöntemler `Declare` anahtar sözcük [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) yönetilmeyen kod erişmek için Platform Başlatma Hizmetleri kullanın. Bu tür yöntemler açıkta kalmamalıdır. Bu yöntemler özel veya dahili tutarak kitaplığınıza arayanlar aksi arayamadı yönetilmeyen API'ler için erişime izin vererek güvenliği ihlal için kullanılamaz emin olun.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için yöntem erişim düzeyini değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bu kural ihlal eden bir yöntem bildirir.

 [!code-vb[FxCop.Interoperability.DllImports#1](../code-quality/codesnippet/VisualBasic/ca1401-p-invokes-should-not-be-visible_1.vb)]
 [!code-csharp[FxCop.Interoperability.DllImports#1](../code-quality/codesnippet/CSharp/ca1401-p-invokes-should-not-be-visible_1.cs)]