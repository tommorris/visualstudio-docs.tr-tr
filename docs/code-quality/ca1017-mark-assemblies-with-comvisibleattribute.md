---
title: 'CA1017: Derlemeleri ComVisibleAttribute ile işaretleme'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1017
- MarkAssembliesWithComVisible
helpviewer_keywords:
- MarkAssembliesWithComVisible
- CA1017
ms.assetid: 4842cb49-8dd8-4e5d-a2d6-ceeaf6c6cf8e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 886de205e59ae7a10787dafe15f0ba726b99b465
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1017-mark-assemblies-with-comvisibleattribute"></a>CA1017: Derlemeleri ComVisibleAttribute ile işaretleme
|||
|-|-|
|TypeName|MarkAssembliesWithComVisible|
|CheckId|CA1017|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Bir derlemeyi yok <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> özniteliğinin.

## <a name="rule-description"></a>Kural Tanımı
 <xref:System.Runtime.InteropServices.ComVisibleAttribute> Özniteliği COM istemcileri yönetilen kod nasıl eriştiğini belirler. İyi tasarım derlemelerin açıkça COM görünürlüğünde gösterildiğini belirler. COM görünürlüğü için tam bir derleme ayarlayın ve ardından tek tek türleri ve tür üyeleri için geçersiz kılındı. Öznitelik yoksa, derleme içeriğini COM istemcileri için görünür durumdadır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için derlemeye özniteliğini ekleyin. Derleme COM istemcileri için görünür olmasını istemiyorsanız özniteliğini uygulayın ve değerini ayarlama `false`.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın. Derleme görünür olmasını istiyorsanız, özniteliğini uygulayın ve değerini ayarlama `true`.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bir derlemeye gösterir <xref:System.Runtime.InteropServices.ComVisibleAttribute> COM istemcileri için görünür olmasını engellemek için uygulanan öznitelik.

 [!code-cpp[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/CPP/ca1017-mark-assemblies-with-comvisibleattribute_1.cpp)]
 [!code-vb[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/VisualBasic/ca1017-mark-assemblies-with-comvisibleattribute_1.vb)]
 [!code-csharp[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/CSharp/ca1017-mark-assemblies-with-comvisibleattribute_1.cs)]

## <a name="see-also"></a>Ayrıca Bkz.
 [Yönetilmeyen kod ile birlikte](/dotnet/framework/interop/index) [birlikte çalışma için .NET türlerini niteleme](/dotnet/framework/interop/qualifying-net-types-for-interoperation)