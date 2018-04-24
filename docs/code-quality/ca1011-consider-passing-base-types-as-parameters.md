---
title: 'CA1011: Temel türleri parametre olarak geçirmeyi düşünün'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ConsiderPassingBaseTypesAsParameters
- CA1011
helpviewer_keywords:
- CA1011
- ConsiderPassingBaseTypesAsParameters
ms.assetid: ce1e1241-dcf4-419b-9363-1d5bc4989279
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ac73d2be980791d41b172ba0669387fd68a331fb
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1011-consider-passing-base-types-as-parameters"></a>CA1011: Temel türleri parametre olarak geçirmeyi düşünün
|||
|-|-|
|TypeName|ConsiderPassingBaseTypesAsParameters|
|CheckId|CA1011|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Yalnızca parametresinin temel türü üyeleri yöntemini çağırır ve türetilmiş bir tür olan bir biçimsel parametresi bir yöntem bildirimi içerir.

## <a name="rule-description"></a>Kural Tanımı
 Temel tür yöntem bildiriminde parametre olarak belirtildiğinde temel türünden türetilen herhangi bir tür yöntemine karşılık gelen bağımsız değişken olarak geçirilebilir. Bağımsız değişken yöntem gövdesi içinde kullanıldığında, yürütüldüğünde belirli yöntemi bağımsız değişkenin türüne bağlıdır. Türetilmiş türü tarafından sağlanan ek işlevsellik gerekli değilse, temel türü kullanımını yöntemi daha geniş kullanılmasına izin verir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için temel türünü parametrenin türünü değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural bir uyarıdan gizlemek güvenlidir

-   yöntem türetilen türü tarafından sağlanan belirli işlevleri gerektiriyorsa

     \- veya -

-   yalnızca türetilmiş bir tür ya da daha fazla türetilmiş bir tür, yönteme geçirilen zorlamak için.

 Bu durumlarda, kod derleyici ve çalışma zamanı tarafından sağlanan güçlü tür denetimi nedeniyle daha sağlam olacaktır.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bir yöntemi gösterir `ManipulateFileStream`, yalnızca kullanılabilir bir <xref:System.IO.FileStream> bu kuralını ihlal eden nesne. İkinci bir yöntem `ManipulateAnyStream`, kural değiştirerek karşılayan <xref:System.IO.FileStream> parametresini kullanarak bir <xref:System.IO.Stream>.

 [!code-csharp[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/CSharp/ca1011-consider-passing-base-types-as-parameters_1.cs)]
 [!code-cpp[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/CPP/ca1011-consider-passing-base-types-as-parameters_1.cpp)]
 [!code-vb[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1011-consider-passing-base-types-as-parameters_1.vb)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1059: Üyeler belli somut türleri göstermemelidir](../code-quality/ca1059-members-should-not-expose-certain-concrete-types.md)