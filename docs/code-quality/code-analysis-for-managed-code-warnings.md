---
title: "Yönetilen kod için uyarıları çözümleme kod | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.project.vcfxcoptool.enablefxcop
helpviewer_keywords:
- managed code analyis, warnings
- warnings, managed code analysis
- managed code analysis warnings
- code analysis,managed code
ms.assetid: 3c2741ff-0d3a-42e6-acd5-d42310bd03c4
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 64360c57f0d4b09f0dc7e8026208c7ec542709c4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="code-analysis-for-managed-code-warnings"></a>Yönetilen Kod için Kod Çözümleme Uyarıları
Yönetilen kod analizi aracı kuralı ihlallerini yönetilen kod kitaplıklarında belirtmek uyarılar sağlar. Uyarılar, tasarım, yerelleştirme, performans ve güvenlik gibi kural alanlar halinde düzenlenir. Her uyarı yönetilen kod analizi kural ihlal belirtir. Bu bölümde ayrıntılı tartışmalara ve örnekler için her yönetilen kod analizi uyarı sağlar.  
  
 Aşağıdaki tabloda her uyarı için sağlanan bilgi türünü gösterir.  
  
|Öğe|Açıklama|  
|----------|-----------------|  
|Tür|Kural için TypeName.|  
|CheckId|Kuralın benzersiz tanımlayıcısı. Checkıd ve kategoriyi bir uyarı kaynak gizleme için kullanılır.|  
|Kategori|Uyarı kategorisi.|  
|Yeni Değişiklik|Kural ihlal için düzeltmeyi önemli bir değişiklik olup olmadığı. Bir bağımlılık ihlali neden hedefe sahip bir derleme yeni derlenir değil değişiklik anlamına gelir ayırarak sürüm sabit veya çalışma zamanında değişikliği nedeniyle başarısız olabilir. Birden çok düzeltmeleri kullanılabilir durumda ve en az bir düzeltme önemli bir değişiklik ve bir düzeltme değil, hem 'Çiğnemekten' ve 'Olmayan çiğnemekten' belirtilir.|  
|Sebep|Bir uyarı oluşturmak kural neden belirli yönetilen kod.|  
|Açıklama|Uyarı arkasında sorunlarını ele alınmaktadır.|  
|İhlaller Nasıl Düzeltilir?|Kural karşılamak ve bir uyarı oluşturulmasını önlemek için kaynak kodunu değiştirmek açıklanmaktadır.|  
|Uyarılar Bastırıldığında|Bir kuraldan gizlemek güvenli olduğunda açıklar.|  
|Örnek kod|Kural ihlal ve kural karşılamak örnekler düzeltti örnekleri.|  
|İlgili uyarıları|İlgili uyarılar.|  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
|||  
|-|-|  
|[Checkıd uyarıları](../code-quality/code-analysis-warnings-for-managed-code-by-checkid.md)|Tüm checkıd listeler|  
|[Şifreleme uyarıları](../code-quality/cryptography-warnings.md)|Güvenli kitaplıklar ve şifreleme doğru kullanımı aracılığıyla uygulamaları destekleyen uyarılar.|  
|[Tasarım uyarıları](../code-quality/design-warnings.md)|Doğru kitaplık tasarımı belirtildiği gibi destek uyarıları [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] tasarım yönergeleri.|  
|[Genelleştirme uyarıları](../code-quality/globalization-warnings.md)|Dünya çapında kullanılmaya hazır kitaplıkları ve uygulamaları destekleyen uyarılar.|  
|[Birlikte çalışabilirlik uyarıları](../code-quality/interoperability-warnings.md)|COM istemcileri ile etkileşimi desteklemek uyarılar.|  
|[Bakım uyarıları](../code-quality/maintainability-warnings.md)|Kitaplık ve uygulama bakım destek uyarılar.|  
|[Taşınabilirlik uyarıları](../code-quality/mobility-warnings.md)|Destek verimli güç kullanımı uyarılar.|  
|[Adlandırma uyarıları](../code-quality/naming-warnings.md)|Adlandırma kuralları düzenlendi.%nÇözüm destek uyarıları [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] tasarım yönergeleri.|  
|[Performans uyarıları](../code-quality/performance-warnings.md)|Yüksek performanslı kitaplıkları ve uygulamaları destekleyen uyarılar.|  
|[Taşınabilirlik uyarıları](../code-quality/portability-warnings.md)|Farklı platformlarda taşınabilirlik destek uyarılar.|  
|[Güvenilirlik uyarıları](../code-quality/reliability-warnings.md)|Doğru bellek ve iş parçacığı kullanımı gibi kitaplığı ve uygulamanın güvenilirliğini destekleyen uyarılar.|  
|[Güvenlik Uyarıları](../code-quality/security-warnings.md)|Güvenli kitaplıklar ve uygulamaları destekleyen uyarılar.|  
|[Kullanım uyarıları](../code-quality/usage-warnings.md)|Uygun kullanımını destekleyen uyarıları [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].|  
|[Kod analiz İlkesi hataları](../code-quality/code-analysis-policy-errors.md)|Kod çözümleme İlkesi giriş sırasında değil sağlanıyorsa oluşan hatalar.|