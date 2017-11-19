---
title: "CA2219: özel durumları durum yan tümceleri içinde yükseltmeyin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
helpviewer_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
ms.assetid: 7b9b0bee-4e8e-49a4-8c40-52142b49061f
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: da4b337ad0efb3a4876857bd07efb391dc040405
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2219-do-not-raise-exceptions-in-exception-clauses"></a>CA2219: Özel durum yan tümceleri içinde özel durum harekete geçirmeyin
|||  
|-|-|  
|TypeName|DoNotRaiseExceptionsInExceptionClauses|  
|CheckId|CA2219|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Sonu olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Gelen bir özel durum bir `finally`, filtre veya hataya yan tümcesi.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir özel durum yan tümcesinde bir özel durum oluştuğunda, hata ayıklama zorluk büyük ölçüde artırır.  
  
 Ne zaman bir özel durum oluşturulur içinde bir `finally` veya hataya yan tümcesi, yeni özel durum gizler etkin özel durum varsa. Bu özgün hata algılamak ve hata ayıklama zor hale getirir.  
  
 Bir filtre yan tümcesi içinde bir özel durum oluştuğunda, çalışma zamanı sessizce özel yakalar ve false olarak değerlendirmek filtre neden olur. False ve filtresi throw olan bir özel durum filtresi değerlendirme arasındaki farkı bildirmek için bir yolu yoktur. Bu, algılamak ve filtrenin mantık hataları hata ayıklamak sabit kolaylaştırır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural bu ihlal düzeltmek için açıkça bir özel durumundan yükseltmeyin bir `finally`, filtre veya hataya yan tümcesi.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural için bir uyarı bastırma değil. Altında bir özel durum yan tümcesinde yükseltilmiş bir özel durum yürütülen kod fayda sağlayan hiçbir senaryo vardır.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1065: beklenmedik konumlarda özel durumlar yükseltmeyin](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tasarım uyarıları](../code-quality/design-warnings.md)