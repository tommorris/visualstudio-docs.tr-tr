---
title: "Oluşturma ve kod çözümleme iade ilkelerini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: code analysis, check-in policies
ms.assetid: 3fa5a849-e05f-4e31-8ba3-b014c889d94d
caps.latest.revision: "39"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b16b7e9f4dba55babfc7ad2ad90affe0ca93c508
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-and-using-code-analysis-check-in-policies"></a>Kod Çözümleme İade İlkeleri Oluşturma ve Kullanma
Team Foundation sürüm denetimi (TFVC'yi) kullandığınızda, bir takım projesi yerel (C/C++) kod projelerinde ve .NET Framework için bir kod çözümleme iade ilkesi oluşturabilirsiniz. Kod çözümleme iade ilkesi denetlemek ve kod temeli denetlenir kod kalitesini artırmak için kullanabilirsiniz.  
  
 İlkeyi Yerel yapıyı güncel olduğunda ve Kod Analizi en son kaynak dosyalarda Çalıştır geçirir. En azından, kod projesinde etkin kod çözümleme kurallarını takım projesi iade ilkede tanımlanan olanlarla aynı kuralları içermesi gerekir. Takım projesi ayarlarında hata olarak belirtilen kuralları de kod projesinde hata olarak belirtilmesi gerekir  
  
> [!IMPORTANT]
>  Kod çözümleme iade ilkeleri web sitesi projelerine uygulanamaz. Web uygulama projeleri için uygulanabilir.  
  
 Takım projesi ayarlarını kullanarak kod çözümleme iade ilkeleri oluşturma [!INCLUDE[esprscc](../code-quality/includes/esprscc_md.md)]. İade ilkeleri belirtilir ve bir takım projesi için zorunlu ancak kod çözümleme çalıştırır yapılandırılmış ve kod projeleri için yerel geliştirme bilgisayarlarında çalıştırabilir. Bu bölümde, bir takım projesi için kod çözümleme iade ilkeleri belirtin ve yönetilen kod için özel kod çözümleme ilkelerini uygulamak açıklar.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Nasıl yapılır: oluştur veya güncelleştir standart kod çözümleme iade ilkeleri](../code-quality/how-to-create-or-update-standard-code-analysis-check-in-policies.md)  
 Ayarlamak ve bir takım projesi için kod çözümleme İlkesi değiştirmek için kullanma adımları açıklanmaktadır.  
  
 [Yönetilen kod için özel iade ilkelerini uygulama](../code-quality/implementing-custom-code-analysis-check-in-policies-for-managed-code.md)  
 Özel bir kural için bir takım projesi iade ilkesi kümesini oluşturmak ve kod projeleri takım projesi iade ilkesiyle eşitleme için kullanma adımları açıklanmaktadır.  
  
 [Kod çözümleme iade ilkeleri için sürüm uyumluluğu](../code-quality/version-compatibility-for-code-analysis-check-in-policies.md)  
 Kod Analizi iade uyumluluk sorunlarını sürümleri arasında açıklar [!INCLUDE[vstsLong](../code-quality/includes/vstslong_md.md)].  
  
 [Nasıl yapılır: Kod Analizi dizinini özelleştirme](../code-quality/how-to-customize-the-code-analysis-dictionary.md)  
 Sözcükler ve belirteçleri kod çözümleme adlandırma kuralları başvurulan sözlük nasıl ekleneceğini açıklar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Kalite kapıları ayarlama ve uygulama](http://msdn.microsoft.com/Library/bdc5666e-6cf0-45b2-a0a1-133c3f61e852)  
  
 [İade takım projesi ilkeleriyle kod kalitesini arttırma](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md)