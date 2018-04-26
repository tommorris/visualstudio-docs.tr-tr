---
title: 'CA2220: Sonlandırıcılar taban tür sonlandırıcıları çağırmalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2220
- FinalizersShouldCallBaseClassFinalizer
helpviewer_keywords:
- CA2220
- FinalizersShouldCallBaseClassFinalizer
ms.assetid: 48329f42-170d-45ee-a381-e33f55a240c5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7f4fc620e55c2f8d5e32e2f2faa94a31d5fe271e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2220-finalizers-should-call-base-class-finalizer"></a>CA2220: Sonlandırıcılar taban tür sonlandırıcıları çağırmalıdır
|||
|-|-|
|TypeName|FinalizersShouldCallBaseClassFinalizer|
|CheckId|CA2220|
|Kategori|Microsoft.Usage|
|Yeni Değişiklik|Olmayan sonu|

## <a name="cause"></a>Sebep
 Geçersiz kılan bir türü <xref:System.Object.Finalize%2A?displayProperty=fullName> çağrılmayan <xref:System.Object.Finalize%2A> devralınabilir. taban sınıf yöntemi.

## <a name="rule-description"></a>Kural Tanımı
 Sonlandırılma, devralma hiyerarşisi aracılığıyla gönderilmelidir. Bu emin olmak için türleri bir temel sınıf'i çağırın <xref:System.Object.Finalize%2A> yönteminden kendi içinde <xref:System.Object.Finalize%2A> yöntemi. C# derleyici temel sınıf sonlandırıcıyı çağrısı otomatik olarak ekler.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için temel türün çağrısı <xref:System.Object.Finalize%2A> yönteminden, <xref:System.Object.Finalize%2A> yöntemi.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın. Ortak dil çalışma zamanı hedef bazı derleyicileri Microsoft Ara dile (MSIL) temel türün sonlandırıcıyı yapılan bir çağrı ekleyin. Bu kural bir uyarıdan bildirilirse, derleyici çağrı eklemez ve kodunuzu eklemeniz gerekir.

## <a name="example"></a>Örnek
 Aşağıdaki Visual Basic örnek bir türü gösterir `TypeB` doğru çağırır <xref:System.Object.Finalize%2A> devralınabilir. taban sınıf yöntemi.

 [!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../code-quality/codesnippet/VisualBasic/ca2220-finalizers-should-call-base-class-finalizer_1.vb)]

## <a name="see-also"></a>Ayrıca Bkz.
 [Dispose Deseni](/dotnet/standard/design-guidelines/dispose-pattern)