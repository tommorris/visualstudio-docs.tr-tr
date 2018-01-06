---
title: "CA1819: Özellikler diziler döndürmemelidir | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
helpviewer_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
ms.assetid: 85fcf312-57f8-438a-8b10-34441fe0bdeb
caps.latest.revision: "22"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: cc11a71b9f6a68db2d795694af0326561b235f8c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1819-properties-should-not-return-arrays"></a>CA1819: Özellikler diziler döndürmemelidir
|||  
|-|-|  
|TypeName|PropertiesShouldNotReturnArrays|  
|CheckId|CA1819|  
|Kategori|Microsoft.Performance|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Ortak tür genel ya da korumalı bir özelliğinde bir dizi döndürür.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Salt okunur özelliği olsa bile, özellik tarafından döndürülen dizi yazma korumalı değildir. Dizi değiştirilmeye kanıt tutulacak özellik dizisinin bir kopyasını döndürmelidir. Tipik olarak, kullanıcılar bu tür bir özellik aramanın performans üzerindeki olumsuz etkilerini anlamayacaktır. Özellikle, bunlar bir dizin oluşturulmuş özellik olarak özelliğini kullanabilirsiniz.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için özelliği bir yöntem olun ya da bir koleksiyon döndürmek için özelliğini değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Öznitelikler diziler döndüren özellikleri içerebilir, ancak koleksiyonları döndüren özellikleri içeremez. Türetilen bir özniteliğin bir özellik için yükseltilmiş bir uyarı gizleyebilirsiniz <xref:System.Attribute> sınıfı. Aksi takdirde, bu kural bir uyarıdan engelleme.  
  
## <a name="example-violation"></a>Örnek ihlali  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnekte bu kuralını ihlal eden bir özelliği gösterir.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_1.cs)]
 [!code-vb[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_1.vb)]  
  
### <a name="comments"></a>Açıklamalar  
 Bu kural ihlal düzeltmek için özelliği bir yöntem olun ya da bir koleksiyonu bir dizi yerine döndürülecek özelliğini değiştirin.  
  
## <a name="change-the-property-to-a-method-example"></a>Bir yöntemi örneği özelliğini değiştirin  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek, bir yönteme özelliğini değiştirerek ihlali giderir.  
  
### <a name="code"></a>Kod  
 [!code-vb[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_2.vb)]
 [!code-csharp[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_2.cs)]  
  
## <a name="return-a-collection-example"></a>Bir koleksiyon örnek Döndür  
  
### <a name="description"></a>Açıklama  
 Döndürülecek özelliğini değiştirerek aşağıdaki örnekte ihlali düzeltmeler bir  
  
 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_3.cs)]
 [!code-vb[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_3.vb)]  
  
## <a name="allowing-users-to-modify-a-property"></a>Bir özelliği değiştirmek kullanıcılara izin verme  
  
### <a name="description"></a>Açıklama  
 Bir özelliği değiştirmek tüketici sınıfının izin vermek isteyebilirsiniz. Aşağıdaki örnekte bu kuralını ihlal eden bir okuma/yazma özelliği gösterir.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_4.cs)]
 [!code-vb[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_4.vb)]  
  
### <a name="comments"></a>Açıklamalar  
 Döndürülecek özelliğini değiştirerek aşağıdaki örnekte ihlali düzeltmeler bir <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>.  
  
### <a name="code"></a>Kod  
 [!code-vb[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_5.vb)]
 [!code-csharp[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_5.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1024: Uygun yerlerde özellikler kullanın](../code-quality/ca1024-use-properties-where-appropriate.md)