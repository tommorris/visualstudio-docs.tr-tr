---
title: 'CA1722: Tanımlayıcıların hatalı öneki olmalıdır değil | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- IdentifiersShouldNotHaveIncorrectPrefix
- CA1722
helpviewer_keywords:
- CA1722
- IdentifiersShouldNotHaveIncorrectPrefix
ms.assetid: c3313c51-d004-4f9a-a0d1-6c4c4a1fb1e6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5e95ef8daa7ed7fc7da4de4b99c677ef92559acb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1722-identifiers-should-not-have-incorrect-prefix"></a>CA1722: Tanımlayıcıların önekleri yanlış olmamalıdır
|||  
|-|-|  
|TypeName|IdentifiersShouldNotHaveIncorrectPrefix|  
|CheckId|CA1722|  
|Kategori|Microsoft.Naming|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Tanımlayıcı hatalı bir ön ekine sahip.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Kural gereği, programlama öğelerinin belirli bir önek ile başlayan adları vardır.  
  
 Tür adları belirli bir önek yoksa ve bir 'C' önüne değil. Bu kural ihlalleri 'CMyClass' gibi tür adları için raporlar ve 'Önbellek' gibi tür adları ihlali bildirmiyor.  
  
 Adlandırma kuralları hedefleyen ortak dil çalışma zamanı kitaplıkları için genel bir bakış sağlar. Bu, yeni yazılım kitaplıkları için gereklidir ve kitaplık geliştirme yönetilen kodda uzmanlığa sahip olan kişi tarafından geliştirilmiştir müşteri güvenini artırır öğrenme eğrisini azaltır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Önek tanımlayıcıdan kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1715: Tanımlayıcıların önekleri doğru olmalıdır](../code-quality/ca1715-identifiers-should-have-correct-prefix.md)