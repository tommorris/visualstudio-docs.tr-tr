---
title: 'CA1716: Tanımlayıcılar anahtar sözcüklerle eşleşmemelidir'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
helpviewer_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
ms.assetid: 900cc8a1-1089-4069-a4ce-10b109ac4fab
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 079a3502b35807fed39070b59c6ded2e554bf511
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1716-identifiers-should-not-match-keywords"></a>CA1716: Tanımlayıcılar anahtar sözcüklerle eşleşmemelidir
|||
|-|-|
|TypeName|IdentifiersShouldNotMatchKeywords|
|CheckId|CA1716|
|Kategori|Microsoft.Naming|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir ad alanı, bir tür veya viritual veya arabirim üye adı ayrılmış bir anahtar sözcük bir programlama dili eşleşir.

## <a name="rule-description"></a>Kural Tanımı
 Ad alanlarını, türleri için tanımlayıcıları ve sanal ve arabirim üyeleri olmayan ortak dil çalışma zamanı hedef dilleri tarafından tanımlanan anahtar sözcükleri eşleşmelidir. Kullanılan dil ve anahtar sözcüğü bağlı olarak, derleyici hataları ve belirsizlikleri kitaplığı kullanmak zorlaştırabilir.

 Bu kural, anahtar sözcükler aşağıdaki dillerde karşı denetler:

-   Visual Basic

-   C#

-   C++/CLI

 Büyük küçük harf duyarsız karşılaştırma için kullanıldığından [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] anahtar sözcükleri ve büyük küçük harfe duyarlı karşılaştırma diğer diller için kullanılır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Anahtar sözcükler listesinde görünmeyen bir ad seçin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Tanımlayıcı API kullanıcılarının karıştırır değil ve kitaplık tüm kullanılabilir dilde kullanılabilir olduğunu ikna varsa bir uyarı bu kuraldan gizleyebilirsiniz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].