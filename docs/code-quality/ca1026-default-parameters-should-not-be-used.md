---
title: "CA1026: Varsayılan parametreler kullanılmamalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1026
- DefaultParametersShouldNotBeUsed
helpviewer_keywords:
- CA1026
- DefaultParametersShouldNotBeUsed
ms.assetid: 09643415-36ef-4d0f-9411-5721e14e2512
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 43f83bf88e017da06ee3653019aa91807229d55e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1026-default-parameters-should-not-be-used"></a>CA1026: Varsayılan parametreler kullanılmamalıdır
|||  
|-|-|  
|TypeName|DefaultParametersShouldNotBeUsed|  
|CheckId|CA1026|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Harici olarak görünen bir türü varsayılan bir parametre kullanan dışarıdan görünür yöntemi içerir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Varsayılan parametreleri kullanan yöntemleri ortak dil belirtimi (CLS) altında izin verilir; Ancak, bu parametreler için atanmış olan değerleri yok sayın derleyicileri CLS sağlar. Varsayılan parametre değerleri yok sayın derleyicileri için yazılan kod, açıkça her varsayılan parametresi için bağımsız değişkenleri belirtmeniz gerekir. Programlama dilleri arasında istediğiniz davranışı sağlamak için varsayılan parametreleri kullanan yöntemleri varsayılan parametreleri sağlamak yöntemi aşırı yüklemeleri ile değiştirilmelidir.  
  
 Yönetilen kod eriştiğinde derleyici C++ için yönetilen uzantısı için varsayılan parametre değerlerini yoksayar. Visual Basic derleyici kullanan varsayılan parametrelere sahip yöntemlerini destekler [isteğe bağlı](/dotnet/visual-basic/language-reference/modifiers/optional) anahtar sözcüğü.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için varsayılan parametrelerini yöntemi aşırı yüklemeleri ile varsayılan parametreleri kullanan yöntem değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, varsayılan parametreleri kullanan bir yöntem, eşdeğer bir işlevselliği sağlayan ve aşırı yüklenmiş yöntemleri gösterir.  
  
 [!code-vb[FxCop.Design.DefaultParameters#1](../code-quality/codesnippet/VisualBasic/ca1026-default-parameters-should-not-be-used_1.vb)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1025: Tekrarlanan bağımsız değişkenleri params dizisi ile değiştirin](../code-quality/ca1025-replace-repetitive-arguments-with-params-array.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dil Bağımsızlığı ve Dilden Bağımsız Bileşenler](/dotnet/standard/language-independence-and-language-independent-components)