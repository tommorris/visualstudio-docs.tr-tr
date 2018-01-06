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
ms.workload: dotnet
ms.openlocfilehash: 689fe39cfb8a7719efbba15b412800d9dfa78361
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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
|[Şifreleme Uyarıları](../code-quality/cryptography-warnings.md)|Güvenli kitaplıklar ve şifreleme doğru kullanımı aracılığıyla uygulamaları destekleyen uyarılar.|  
|[Tasarım Uyarıları](../code-quality/design-warnings.md)|Doğru kitaplık tasarımı belirtildiği gibi destek uyarıları [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] tasarım yönergeleri.|  
|[Genelleştirme Uyarıları](../code-quality/globalization-warnings.md)|Dünya çapında kullanılmaya hazır kitaplıkları ve uygulamaları destekleyen uyarılar.|  
|[Birlikte Çalışabilirlik Uyarıları](../code-quality/interoperability-warnings.md)|COM istemcileri ile etkileşimi desteklemek uyarılar.|  
|[Bakım Uyarıları](../code-quality/maintainability-warnings.md)|Kitaplık ve uygulama bakım destek uyarılar.|  
|[Hareketlilik Uyarıları](../code-quality/mobility-warnings.md)|Destek verimli güç kullanımı uyarılar.|  
|[Adlandırma Uyarıları](../code-quality/naming-warnings.md)|Adlandırma kuralları düzenlendi.%nÇözüm destek uyarıları [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] tasarım yönergeleri.|  
|[Performans Uyarıları](../code-quality/performance-warnings.md)|Yüksek performanslı kitaplıkları ve uygulamaları destekleyen uyarılar.|  
|[Taşınabilirlik Uyarıları](../code-quality/portability-warnings.md)|Farklı platformlarda taşınabilirlik destek uyarılar.|  
|[Güvenilirlik Uyarıları](../code-quality/reliability-warnings.md)|Doğru bellek ve iş parçacığı kullanımı gibi kitaplığı ve uygulamanın güvenilirliğini destekleyen uyarılar.|  
|[Güvenlik Uyarıları](../code-quality/security-warnings.md)|Güvenli kitaplıklar ve uygulamaları destekleyen uyarılar.|  
|[Kullanım Uyarıları](../code-quality/usage-warnings.md)|Uygun kullanımını destekleyen uyarıları [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].|  
|[Kod Çözümleme İlkesi Hataları](../code-quality/code-analysis-policy-errors.md)|Kod çözümleme İlkesi giriş sırasında değil sağlanıyorsa oluşan hatalar.|