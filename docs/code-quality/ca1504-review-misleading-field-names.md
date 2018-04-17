---
title: 'CA1504: yanlış alan adlarını gözden geçirin. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- ReviewMisleadingFieldNames
- CA1504
helpviewer_keywords:
- CA1504
- ReviewMisleadingFieldNames
ms.assetid: 94136ff1-4aaf-4dc2-9170-48c171ab7499
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 592fc516dad51db10e80cdcbdf652cbf4329f4ec
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1504-review-misleading-field-names"></a>CA1504: Yanlış alan adlarını gözden geçirin
|||  
|-|-|  
|TypeName|ReviewMisleadingFieldNames|  
|CheckId|CA1504|  
|Kategori|Microsoft.Maintainability|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bir örnek alanın adını başlatır "s_" veya adı ile bir `static` (`Shared` içinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) alanı "m_" ile başlar.  
  
## <a name="rule-description"></a>Kural Tanımı  
 "S_" ile başlayan alan adları statik verilerle birden çok kullanıcı tarafından ilişkilendirilir. Benzer şekilde, "m_" ile başlayan alan adlarını örneği (üye) verileriyle ilişkilendirilir. Daha kolay tutulan kodunu adları genellikle kullanılan kuralları izlemelidir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için uygun önek kullanarak alanı'nı yeniden adlandırın. Alternatif olarak, geçerli sonekiyle ekleyerek veya kaldırarak kabul alan yapmak `static` değiştiricisi.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.