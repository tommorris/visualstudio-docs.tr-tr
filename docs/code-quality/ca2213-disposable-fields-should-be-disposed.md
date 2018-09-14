---
title: 'CA2213: Atılabilen alanlar atılmalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DisposableFieldsShouldBeDisposed
- CA2213
helpviewer_keywords:
- CA2213
- DisposableFieldsShouldBeDisposed
ms.assetid: e99442c9-70e2-47f3-b61a-d8ac003bc6e5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 143a094375871bf8073999f89d7fac5d6df01b4f
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551866"
---
# <a name="ca2213-disposable-fields-should-be-disposed"></a>CA2213: Atılabilen alanlar atılmalıdır

|||
|-|-|
|TypeName|DisposableFieldsShouldBeDisposed|
|CheckId|CA2213|
|Kategori|Microsoft.Usage|
|Yeni Değişiklik|Bozucu olmayan|

## <a name="cause"></a>Sebep
 Uygulayan bir tür <xref:System.IDisposable?displayProperty=fullName> ayrıca uygulayan türler alanlar bildirir <xref:System.IDisposable>. <xref:System.IDisposable.Dispose%2A> Alanının yöntemi çağrılmaz <xref:System.IDisposable.Dispose%2A> bildirim türü yöntemi.

## <a name="rule-description"></a>Kural açıklaması
 Bir tür için kendi yönetilmeyen tüm kaynaklarını atma sorumludur; Bu uygulama tarafından gerçekleştirilir <xref:System.IDisposable>. Tek kullanımlık bir tür olup olmadığını görmek için bu kural denetler `T` bir alan bildirir `F` atılabilir bir türün diğer bir deyişle bir örneğini `FT`. Her bir alan için `F`, kural için bir çağrı bulmaya çalışır `FT.Dispose`. Kural çağrılan yöntemler arar `T.Dispose`ve daha düşük bir düzey (çağrılan yöntemler tarafından çağrılan yöntemler `FT.Dispose`).

## <a name="how-to-fix-violations"></a>İhlaller nasıl düzeltilir?
 Bu kural ihlalini düzeltmek için çağrı <xref:System.IDisposable.Dispose%2A> uygulayan türler alanlar üzerinde <xref:System.IDisposable> sorumlu ve tutulan alanı tarafından yönetilmeyen kaynakları serbest bırakmak.

## <a name="when-to-suppress-warnings"></a>Uyarılar bastırıldığında
 Kaynağı serbest bırakarak alanı tarafından tutulan için sorumlu olduğunuz değil veya bu kuraldan bir uyarıyı bastırmak güvenlidir çağrısı <xref:System.IDisposable.Dispose%2A> kural denetimleri daha derin arama düzeyinde gerçekleşir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bir tür gösterir `TypeA` uygulayan <xref:System.IDisposable> (`FT` previosu tartışmada).

 [!code-csharp[FxCop.Usage.IDisposablePattern#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_1.cs)]

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bir tür gösterir `TypeB` , ihlal bu kural bir alan bildirerek `aFieldOfADisposableType` (`F` önceki tartışmada) tek kullanımlık bir tür olarak (`TypeA`) ve değil çağırma <xref:System.IDisposable.Dispose%2A> alanı. `TypeB` karşılık gelen `T` önceki tartışmada.

 [!code-csharp[FxCop.Usage.IDisposableFields#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_2.cs)]

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.IDisposable?displayProperty=fullName>
- [Dispose Deseni](/dotnet/standard/design-guidelines/dispose-pattern)