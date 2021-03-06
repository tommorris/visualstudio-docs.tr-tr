---
title: 'CA1819: Özellikler diziler döndürmemelidir'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
helpviewer_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
ms.assetid: 85fcf312-57f8-438a-8b10-34441fe0bdeb
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 68f64d37a7616f095a86452353edc498d2d27f28
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45549423"
---
# <a name="ca1819-properties-should-not-return-arrays"></a>CA1819: Özellikler diziler döndürmemelidir

|||
|-|-|
|TypeName|PropertiesShouldNotReturnArrays|
|CheckId|CA1819|
|Kategori|Microsoft.Performance|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Ortak türde ortak veya korumalı bir özellik, bir dizi döndürür.

## <a name="rule-description"></a>Kural açıklaması
 Özellik salt okunur olsa bile özellikleri tarafından döndürülen dizi yazma korumalı değildir. Dizi değiştirilmeye kanıt tutulacak özellik dizisinin bir kopyasını döndürmelidir. Tipik olarak, kullanıcılar bu tür bir özellik aramanın performans üzerindeki olumsuz etkilerini anlamayacaktır. Özellikle, bunlar bir dizinlenmiş özellik olarak özelliğini kullanabilirsiniz.

## <a name="how-to-fix-violations"></a>İhlaller nasıl düzeltilir?
 Bu kural ihlalini düzeltmek için özelliği bir yöntem yapın veya özelliği bir koleksiyon döndürecek şekilde değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarılar bastırıldığında
 Öznitelikler, dizi döndüren özellikler içerebilir, ancak koleksiyon döndüren özellikler içeremez. Türetilen bir özniteliğin bir özellik için oluşturulan bir uyarıyı bastırmak <xref:System.Attribute> sınıfı. Aksi takdirde, bu kuraldan bir uyarıyı bastırmayın.

## <a name="example-violation"></a>Örnek ihlali

### <a name="description"></a>Açıklama
 Aşağıdaki örnek bu kuralı ihlal eden bir özellik gösterilmiştir.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_1.cs)]
 [!code-vb[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_1.vb)]

### <a name="comments"></a>Açıklamalar
 Bu kural ihlalini düzeltmek için özelliği bir yöntem yapın veya özelliği bir dizi yerine bir koleksiyon döndürecek şekilde değiştirin.

## <a name="change-the-property-to-a-method-example"></a>Özelliğini yöntemi örneği

### <a name="description"></a>Açıklama
 Aşağıdaki örnek, bir yönteme özelliğini değiştirerek ihlali düzeltir.

### <a name="code"></a>Kod
 [!code-vb[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_2.vb)]
 [!code-csharp[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_2.cs)]

## <a name="return-a-collection-example"></a>Bir koleksiyon örneği döndürür.

### <a name="description"></a>Açıklama
 Aşağıdaki örnek, döndürülecek özelliği değiştirilerek ihlali giderir bir

 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_3.cs)]
 [!code-vb[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_3.vb)]

## <a name="allowing-users-to-modify-a-property"></a>Kullanıcıların bir özelliği değiştirmek için

### <a name="description"></a>Açıklama
 Bir özelliği değiştirmek tüketici sınıfı izin vermek isteyebilirsiniz. Aşağıdaki örnek bu kuralı ihlal eden bir okuma/yazma özelliği gösterir.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_4.cs)]
 [!code-vb[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_4.vb)]

### <a name="comments"></a>Açıklamalar
 Aşağıdaki örnek, döndürülecek özelliği değiştirilerek ihlali giderir bir <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>.

### <a name="code"></a>Kod
 [!code-vb[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_5.vb)]
 [!code-csharp[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_5.cs)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1024: Uygun yerlerde özellikler kullanın](../code-quality/ca1024-use-properties-where-appropriate.md)