---
title: 'CA1506: aşırı sınıf bağlantısından Kaçın | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- AvoidExcessiveClassCoupling
- CA1506
helpviewer_keywords:
- AvoidExcessiveClassCoupling
- CA1506
ms.assetid: 9f0943c0-e802-4e3f-8798-2ab8653ddc80
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 018abf05181be812bcf01fc9cb910745dc085bcf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1506-avoid-excessive-class-coupling"></a>CA1506: Aşırı sınıf bağlantısından kaçın
|||  
|-|-|  
|TypeName|AvoidExcessiveClassCoupling|  
|CheckId|CA1506|  
|Kategori|Microsoft.Maintainability|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Türü veya yöntemi diğer birçok ile birleştirilmiştir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural türü veya yöntemini içeren benzersiz türde başvuru sayısı belirlenerek eşlenmesiyle sınıfı ölçer.  
  
 Türleri ve sınıf yüksek derecede sahip yöntemleri korumak zor olabilir. Türler ve düşük bağ ve yüksek cohesion sergiler yöntemler için iyi bir uygulamadır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu ihlali düzeltmek için türü veya yöntemi bağlı türleri sayısını azaltmak için yeniden tasarlayabilir deneyin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu uyarı türü veya yöntemi yine, sayıda diğer türleri bağımlılıkları rağmen sürdürülebilir olarak kabul edildiğinde dışlayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bakım uyarıları](../code-quality/maintainability-warnings.md)   
 [Yönetilen Kodun Ölçüm Karmaşıklığı ve Bakımı](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)