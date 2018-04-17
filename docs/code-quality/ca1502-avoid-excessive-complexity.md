---
title: 'CA1502: aşırı karmaşıklıktan kaçının | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- AvoidExcessiveComplexity
- CA1502
helpviewer_keywords:
- CA1502
- AvoidExcessiveComplexity
ms.assetid: d735454b-2f8f-47ce-907d-f7a5a5391221
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 990a1336019325313c2152b38b7fa8525d52720a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1502-avoid-excessive-complexity"></a>CA1502: Aşırı karmaşıklıktan kaçının
|||  
|-|-|  
|TypeName|AvoidExcessiveComplexity|  
|CheckId|CA1502|  
|Kategori|Microsoft.Maintainability|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bir yöntemi aşırı cyclomatic karmaşıklık vardır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 *Cyclomatic karmaşıklık* sayısı ve karmaşıklığı koşullu dal tarafından belirlenir yöntemiyle doğrusal olarak bağımsız yollar sayısını ölçer. Düşük cyclomatic karmaşıklık genellikle anlamak, test ve korumak kolay bir yöntemi gösterir. Cyclomatic karmaşıklığı yönteminin denetim akışı grafikten hesaplanır ve aşağıdaki gibi verilir:  
  
 cyclomatic karmaşıklık = kenarları - düğüm sayısını + 1 sayısı  
  
 bir düğüm mantığı dal noktası ve kenar temsil ettiği bir satır düğümler arasında temsil eder.  
  
 Cyclomatic karmaşıklık 25'den fazla olduğunda kural ihlalinin bildirir.  
  
 Kod ölçümleri hakkında daha fazla bilgi edinebilirsiniz [ölçüm karmaşıklığı ve yönetilen kod bakımı](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md),  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için kendi cyclomatic karmaşıklığını azaltmak için yöntemini yeniden düzenleyin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan karmaşıklığını kolayca düşürülemiyor ve anlamak, test ve korumak kolay bir yöntemdir gizlemek güvenlidir. Özellikle, büyük bir içeren bir yöntem `switch` (`Select` içinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) dışlama aday bir ifadedir. Kod geliştirme döngüsü veya çalışma zamanı davranışı önceden sevk edilen kodda beklenmeyen bir değişiklik yapmanızı geç kodu yeniden düzenleme, bakım ağır basıyor tabanını destabilizing riskini.  
  
## <a name="how-cyclomatic-complexity-is-calculated"></a>Cyclomatic karmaşıklık nasıl hesaplanır  
 Cyclomatic karmaşıklık 1 aşağıdaki ekleyerek hesaplanır:  
  
-   Dalları sayısı (gibi `if`, `while`, ve `do`)  
  
-   Sayısı `case` deyimlerinde bir `switch`  
  
 Aşağıdaki örnekler değişen cyclomatic karmaşıklık sahip yöntemleri gösterir.  
  
## <a name="example"></a>Örnek  
 **1 Cyclomatic karmaşıklığı**  
  
 [!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_1.cpp)]
 [!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_1.vb)]
 [!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_1.cs)]  
  
## <a name="example"></a>Örnek  
 **2 Cyclomatic karmaşıklığı**  
  
 [!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_2.cpp)]
 [!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_2.vb)]
 [!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_2.cs)]  
  
## <a name="example"></a>Örnek  
 **3 Cyclomatic karmaşıklığı**  
  
 [!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_3.cpp)]
 [!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_3.vb)]
 [!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_3.cs)]  
  
## <a name="example"></a>Örnek  
 **8 Cyclomatic karmaşıklığı**  
  
 [!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_4.cpp)]
 [!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_4.vb)]
 [!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_4.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1501: Aşırı devralmadan kaçının](../code-quality/ca1501-avoid-excessive-inheritance.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen Kodun Ölçüm Karmaşıklığı ve Bakımı](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)