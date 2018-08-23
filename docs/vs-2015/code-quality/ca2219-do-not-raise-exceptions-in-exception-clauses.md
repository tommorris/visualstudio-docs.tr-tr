---
title: 'CA2219: özel durum yan tümceleri içinde özel durum harekete geçirmeyin | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
helpviewer_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
ms.assetid: 7b9b0bee-4e8e-49a4-8c40-52142b49061f
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: dc951b8cfcefefe473eb7f5b19648da298b40792
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674982"
---
# <a name="ca2219-do-not-raise-exceptions-in-exception-clauses"></a>CA2219: Özel durum yan tümceleri içinde özel durum harekete geçirmeyin
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2219: özel durum yan tümceleri içinde özel durum harekete geçirmeyin](https://docs.microsoft.com/visualstudio/code-quality/ca2219-do-not-raise-exceptions-in-exception-clauses).  
  
TypeName | DoNotRaiseExceptionsInExceptionClauses |  
| Checkıd | CA2219 |  
| Kategori | Microsoft.Usage|  
| Yeni değişiklik | Olmayan yeni, bozucu |  
  
## <a name="cause"></a>Sebep  
 Bir özel durum bir `finally`, filtre ya da arıza yan tümcesi.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir özel durum yan tümcesinde bir özel durum oluştuğunda, hata ayıklamayı büyük ölçüde artırır.  
  
 Ne zaman bir neden bir `finally` ya da arıza yan tümcesine yeni istisna aktif istisnayı, varsa. Bu özgün hata algılama ve hata ayıklamayı sabit hale getirir.  
  
 Filtre yan tümcesinde bir özel durum oluştuğunda, çalışma zamanı sessizce özel durumu yakalar ve filtre false olarak değerlendirilecek neden olur. False ve filtresi throw olan bir özel durum filtresi değerlendirme arasındaki farkı bildirmek için hiçbir yolu yoktur. Bu algılama ve filtre mantığındaki hataların hata ayıklamayı zorlaştırır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kuralın ihlalini düzeltmek için açıkça adresinden bir özel durum harekete geçirmeyin bir `finally`, filtre ya da arıza yan tümcesi.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural için bir uyarıyı bastırmayın. Altında oluşturulan bir özel durum yan tümcesinde bir özel durum kodu yürütürken bir avantaj sağlayan senaryo vardır.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1065: Beklenmedik konumlarda özel durumlar tetiklemeyin](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tasarım Uyarıları](../code-quality/design-warnings.md)



