---
title: "CA1720: Tanımlayıcılar tür adları içermemelidir | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1720
- IdentifiersShouldNotContainTypeNames
helpviewer_keywords:
- IdentifiersShouldNotContainTypeNames
- CA1720
ms.assetid: c95ee48f-f23a-45f0-ac9e-a3c1ecfabdea
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ac50c390ca7a45cf5ef28f2d82d1f75fc5e2c1a0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1720-identifiers-should-not-contain-type-names"></a>CA1720: Tanımlayıcılar tür adları içermemelidir
|||  
|-|-|  
|TypeName|IdentifiersShouldNotContainTypeNames|  
|CheckId|CA1720|  
|Kategori|Microsoft.Naming|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Dışarıdan görünür bir üye içindeki bir parametre adı bir veri türü adı içeriyor.  
  
 veya  
  
 Dile özgü veri türü adı dışarıdan görünür bir üyenin adını içerir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Parametreleri ve üyeleri adlarını daha iyi geliştirme araçları tarafından sağlanacak beklenen tipine açıklamak üzere daha anlamları iletişim kurmak için kullanılır. Veri türü adı kullanılmalıdır üyelerin adları için dile özgü bir yerine bir dilden bağımsız adını kullanın. Örneğin, C# türü adı 'int yerine', Int32 dilden bağımsız veri türü adı kullanın.  
  
 Her ayrık belirteç parametresi veya üye adına aşağıdaki dile özgü veri türü adları karşı büyük küçük harf duyarsız bir biçimde denetlenir:  
  
-   bool  
  
-   WChar  
  
-   int8  
  
-   UInt8  
  
-   kısa  
  
-   UShort  
  
-   int  
  
-   UInt  
  
-   Tamsayı  
  
-   Uınteger  
  
-   uzun  
  
-   ULong  
  
-   İmzasız  
  
-   İmzalı  
  
-   Kayan nokta  
  
-   Float32  
  
-   Float64  
  
 Ayrıca, bir parametre adları büyük küçük harf duyarsız bir biçimde da aşağıdaki dilden bağımsız veri türü adları karşı denetlenir:  
  
-   Nesne  
  
-   Obj  
  
-   Boole değeri  
  
-   Char  
  
-   Dize  
  
-   SByte  
  
-   Bayt  
  
-   UByte  
  
-   Int16  
  
-   UInt16  
  
-   Int32  
  
-   UInt32  
  
-   Int64  
  
-   UInt64  
  
-   IntPtr  
  
-   PTR  
  
-   İşaretçi  
  
-   UInptr  
  
-   UPtr  
  
-   UPointer  
  
-   Tek  
  
-   Çift  
  
-   Ondalık  
  
-   Guid  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 **Bir parametre karşı harekete ise:**  
  
 Veri türü tanımlayıcısı parametresi adına daha iyi anlamlarını açıklar bir terim veya 'value' gibi daha genel bir terim değiştirin.  
  
 **Üye karşı harekete ise:**  
  
 Bunun anlamı, bir dilden bağımsız eşdeğeri ya da 'value' gibi daha genel bir terim daha iyi tanımlayan bir terim dile özgü veri türü tanımlayıcısı üyenin adını değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Tür tabanlı parametre ve üye adları ara sıra kullanılmasını uygun olabilir. Ancak, yeni geliştirme, hiçbir bilinen için senaryolar ortaya burada bu kuraldan bir uyarı bastırma. Önceki sevk sahip kitaplıkları için bu kural bir uyarıdan bastırmak gerekebilir.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1709: Tanımlayıcıların büyük/küçük harfleri doğru yazılmalıdır](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: Tanımlayıcılar örnekten daha fazla farklı olmalıdır](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
 [CA1707: Tanımlayıcılar alt çizgi içermemelidir](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)  
  
 [CA1719: Parametre adları üye adlarıyla eşleşmemelidir](../code-quality/ca1719-parameter-names-should-not-match-member-names.md)