---
title: 'CA1802: Uygun yerlerde sabitleri kullan | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- UseLiteralsWhereAppropriate
- CA1802
helpviewer_keywords:
- UseLiteralsWhereAppropriate
- CA1802
ms.assetid: 2515e4cd-9e61-486d-b067-58ba1a743ce4
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c2e7841091d3ad5ca093b35b62cca1fdbe6b6a69
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1802-use-literals-where-appropriate"></a>CA1802: Uygun Yerlerde Sabitleri Kullan
|||  
|-|-|  
|TypeName|UseLiteralsWhereAppropriate|  
|CheckId|CA1802|  
|Kategori|Microsoft.Performance|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bir alan bildirilmiş `static` ve `readonly` (`Shared` ve `ReadOnly` içinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) ve derleme zamanında computable olan bir değer ile başlatıldı.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Değeri bir `static``readonly` alan bildiri türü statik Oluşturucusu çağrıldığında çalışma zamanında hesaplanır. Varsa `static``readonly` alan onu bildirilmiş ve bir statik Oluşturucu açıkça derleyicisi yayar alan başlatmak için statik bir oluşturucu bildirilmedi başlatılır.  
  
 Değeri bir `const` alan derleme zamanında hesaplanır ve için karşılaştırıldığında, çalışma zamanı performansı artırır meta verileri, depolanan bir `static``readonly` alan.  
  
 Hedeflenen alanına atanan değer derleme zamanında computable olduğundan, bildirimine değiştirme bir `const` derleme zamanında yerine çalışma zamanında hesaplanan değer böylece alan.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için yerini `static` ve `readonly` ile değiştiricileri `const` değiştiricisi.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Performans sorunu değilse bir uyarı bu kuraldan bastırmak veya kuralı devre dışı bırakmak daha güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir tür gösterir `UseReadOnly`, kural ve bir tür ihlal `UseConstant`, kural karşılar.  
  
 [!code-vb[FxCop.Performance.UseLiterals#1](../code-quality/codesnippet/VisualBasic/ca1802-use-literals-where-appropriate_1.vb)]
 [!code-csharp[FxCop.Performance.UseLiterals#1](../code-quality/codesnippet/CSharp/ca1802-use-literals-where-appropriate_1.cs)]