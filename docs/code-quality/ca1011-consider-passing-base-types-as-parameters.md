---
title: "CA1011: temel türleri parametre olarak geçirmeyi düşünün | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ConsiderPassingBaseTypesAsParameters
- CA1011
helpviewer_keywords:
- CA1011
- ConsiderPassingBaseTypesAsParameters
ms.assetid: ce1e1241-dcf4-419b-9363-1d5bc4989279
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ae6923e369d0f4245759bff2c66dc931dc51baf8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
  
     \-veya -  
  
-   yalnızca türetilmiş bir tür ya da daha fazla türetilmiş bir tür, yönteme geçirilen zorlamak için.  
  
 Bu durumlarda, kod derleyici ve çalışma zamanı tarafından sağlanan güçlü tür denetimi nedeniyle daha sağlam olacaktır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir yöntemi gösterir `ManipulateFileStream`, yalnızca kullanılabilir bir <xref:System.IO.FileStream> bu kuralını ihlal eden nesne. İkinci bir yöntem `ManipulateAnyStream`, kural değiştirerek karşılayan <xref:System.IO.FileStream> parametresini kullanarak bir <xref:System.IO.Stream>.  
  
 [!code-csharp[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/CSharp/ca1011-consider-passing-base-types-as-parameters_1.cs)]
 [!code-cpp[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/CPP/ca1011-consider-passing-base-types-as-parameters_1.cpp)]
 [!code-vb[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1011-consider-passing-base-types-as-parameters_1.vb)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1059: Üyeler belli somut türleri göstermemelidir](../code-quality/ca1059-members-should-not-expose-certain-concrete-types.md)