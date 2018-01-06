---
title: "CA1707: Tanımlayıcılar alt çizgi içermemelidir | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IdentifiersShouldNotContainUnderscores
- CA1707
helpviewer_keywords:
- CA1707
- IdentifiersShouldNotContainUnderscores
ms.assetid: 5fb539ef-c304-4323-90c0-b14386da9774
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 582b7c95663633a4aada6a479a17306354c16b7f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1707-identifiers-should-not-contain-underscores"></a>CA1707: Tanımlayıcılar alt çizgi içermemelidir
|||  
|-|-|  
|TypeName|IdentifiersShouldNotContainUnderscores|  
|CheckId|CA1707|  
|Kategori|Microsoft.Naming|  
|Yeni Değişiklik|-Derlemelerini oluştuğunda kesme<br /><br /> Tür parametreleri oluştuğunda bölünemez-|  
  
## <a name="cause"></a>Sebep  
 Tanımlayıcı adı alt çizgi (_) karakterini içeriyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Kural gereği, tanımlayıcı adlar alt çizgi (_) karakterini içermez. Kural ad alanlarını, türleri, üyeleri ve parametreleri denetler.  
  
 Adlandırma kuralları hedefleyen ortak dil çalışma zamanı kitaplıkları için genel bir bakış sağlar. Bu, yeni yazılım kitaplıkları için gereklidir ve kitaplık geliştirme yönetilen kodda uzmanlığa sahip olan kişi tarafından geliştirilmiştir müşteri güvenini artırır öğrenme eğrisini azaltır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Tüm alt çizgi karakterleri adından kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1709: Tanımlayıcıların büyük/küçük harfleri doğru yazılmalıdır](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: Tanımlayıcılar örnekten daha fazla farklı olmalıdır](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)