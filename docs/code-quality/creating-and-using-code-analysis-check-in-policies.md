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
ms.openlocfilehash: a7d8ab4732938721da8e72c5a4c5f7387a4e67e2
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/12/2017
---
# <a name="creating-and-using-code-analysis-check-in-policies"></a>Kod Çözümleme İade İlkeleri Oluşturma ve Kullanma
Team Foundation sürüm denetimi (TFVC'yi) kullandığınızda, bir takım projesi yerel (C/C++) kod projelerinde ve .NET Framework için bir kod çözümleme iade ilkesi oluşturabilirsiniz. Kod çözümleme iade ilkesi denetlemek ve kod temeli denetlenir kod kalitesini artırmak için kullanabilirsiniz.  
  
 İlkeyi Yerel yapıyı güncel olduğunda ve Kod Analizi en son kaynak dosyalarda Çalıştır geçirir. En azından, kod projesinde etkin kod çözümleme kurallarını takım projesi iade ilkede tanımlanan olanlarla aynı kuralları içermesi gerekir. Takım projesi ayarlarında hata olarak belirtilen kuralları de kod projesinde hata olarak belirtilmesi gerekir  
  
> [!IMPORTANT]
>  Kod çözümleme iade ilkeleri web sitesi projelerine uygulanamaz. Web uygulama projeleri için uygulanabilir.  
  
 Takım projesi ayarlarını kullanarak kod çözümleme iade ilkeleri oluşturma [!INCLUDE[esprscc](../code-quality/includes/esprscc_md.md)]. İade ilkeleri belirtilir ve bir takım projesi için zorunlu ancak kod çözümleme çalıştırır yapılandırılmış ve kod projeleri için yerel geliştirme bilgisayarlarında çalıştırabilir. Bu bölümde, bir takım projesi için kod çözümleme iade ilkeleri belirtin ve yönetilen kod için özel kod çözümleme ilkelerini uygulamak açıklar.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Nasıl yapılır: Standart Kod Çözümleme İade İlkeleri Oluşturma veya Güncelleme](../code-quality/how-to-create-or-update-standard-code-analysis-check-in-policies.md)  
 Ayarlamak ve bir takım projesi için kod çözümleme İlkesi değiştirmek için kullanma adımları açıklanmaktadır.  
  
 [Yönetilen kod için özel iade ilkelerini uygulama](../code-quality/implementing-custom-code-analysis-check-in-policies-for-managed-code.md)  
 Özel bir kural için bir takım projesi iade ilkesi kümesini oluşturmak ve kod projeleri takım projesi iade ilkesiyle eşitleme için kullanma adımları açıklanmaktadır.  
  
 [Kod Çözümleme İade İlkeleri için Sürüm Uyumluluğu](../code-quality/version-compatibility-for-code-analysis-check-in-policies.md)  
 Kod Analizi iade uyumluluk sorunlarını sürümleri arasında açıklar [!INCLUDE[vstsLong](../code-quality/includes/vstslong_md.md)].  
  
 [Nasıl yapılır: Kod Çözümleme Dizinini Özelleştirme](../code-quality/how-to-customize-the-code-analysis-dictionary.md)  
 Sözcükler ve belirteçleri kod çözümleme adlandırma kuralları başvurulan sözlük nasıl ekleneceğini açıklar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Takım Projesi İade İlkeleriyle Kod Kalitesini Arttırma](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md)