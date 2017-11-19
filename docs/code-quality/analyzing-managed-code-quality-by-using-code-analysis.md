---
title: "Kod Analizi ile yönetilen kod kalitesini analiz etme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code analysis,managed code
- managed code analyis
ms.assetid: 68510a55-da51-4381-81a5-0feba76b8b4f
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 69cb1ed9c5c8da2ae511d73de45a0567d61236dd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="analyzing-managed-code-quality-by-using-code-analysis"></a>Kod Çözümlemesi ile Yönetilen Kod Kalitesini Çözümleme
Güvenli olmayan veri erişimi, kullanım ihlalleri ve tasarım sorunları gibi kodunuzda olası sorunları bulmak için Visual Studio'da kod çözümleme araçları kullanabilirsiniz. Kod Analizi, .NET Framework, yerel (C ve C++) ve veritabanı uygulamaları üzerinde çalışır. Yönetilen kod için Kod Analizi düzenler kurallarında *kural kümeleri* hedefleyen belirli sorunları kodlama.  
  
## <a name="common-tasks"></a>Ortak Görevler  
  
|Ortak Görevler|Destekleyici İçerik|  
|------------------|------------------------|  
|**Uygulamalı deneyim alın:** basit bir .NET Framework uygulamasında hataları düzelterek Kod Analizi temellerini öğrenin.|-   [İzlenecek yol: Yönetilen kodu analiz etme kod kusurları için](../code-quality/walkthrough-analyzing-managed-code-for-code-defects.md)|  
|**Projesi için kod analizini yapılandırma:** tarafından yönetilen kod, güvenlik ve tasarım gibi belirli alanlar hedef kural kümeleri halinde düzenlenir kuralları. Microsoft Standart kural ayarlar veya kendinizinkini oluşturun birini kullanabilirsiniz.|-   [Yönetilen kod genel bakış için Kod Analizi](../code-quality/code-analysis-for-managed-code-overview.md)<br />-   [Kod çözümleme kurallarını gruplandırmak için kural kullanarak ayarlar](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)<br />-   [SuppressMessage özniteliğini kullanarak uyarıları bastırma](../code-quality/suppress-warnings-by-using-the-suppressmessage-attribute.md)|  
|**Kod çözümleme çalıştırın:** bir proje yapılandırma yerleşik her zaman otomatik olarak çalıştırılacak Kod Analizi belirtebilirsiniz ve Kod Analizi bir proje üzerinde el ile çalıştırabilirsiniz.|-   [Nasıl yapılır: etkinleştirme ve devre dışı otomatik kod çözümleme](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)<br />-   [Nasıl yapılır: kod analizini elle çalıştırma](../code-quality/how-to-run-code-analysis-manually-for-managed-code.md)|  
|**Kod çözümleme sonuçlarını analiz:** Kod Analizi uyarıları ve hataları Kod Analizi penceresinde listelenir. Bir uyarı veya hata başlığı uyarı ile ilgili ek bilgileri görüntülemek için görüntülemek ve kural harekete kaynak kod satırı vurgulayın seçebilirsiniz. Bilgi ve sorunun nasıl çözüleceği örnekleri içerir MSDN Kitaplığı'nda ayrıntılı bilgileri görüntülemek için uyarı kimliği seçebilirsiniz.|-   [Nasıl yapılır: yönetilen kod kusurlarını görüntüleme](../code-quality/how-to-view-managed-code-defects.md)<br />-   [Yönetilen kod uyarıları için Kod Analizi](../code-quality/code-analysis-for-managed-code-warnings.md)<br />-   [Checkıd uyarıları](../code-quality/code-analysis-warnings-for-managed-code-by-checkid.md)<br />-   [Anonim yöntemler ve kod çözümleme](../code-quality/anonymous-methods-and-code-analysis.md)|  
|**Kod Analizi, geliştirme yaşam döngüsü ile tümleştirme:** iade ilkelerini [!INCLUDE[esprscc](../code-quality/includes/esprscc_md.md)] tüm iadeler kod emin olmak için etkinleştir geliştirme ekiplerinin karşılayan kod çözümleme standartları ortak bir dizi. Kod çözümleme kural ihlali için iş öğesi oluşturma hata listesi penceresini gerçekleştirebileceğiniz basit bir yordamdır.|-   [İade takım projesi ilkeleriyle kod kalitesini arttırma](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md)<br />-   [Nasıl yapılır: iade takım projesi ilkesiyle kod proje kural kümelerini eşitleme](../code-quality/how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy.md)<br />-   [Nasıl yapılır: yönetilen kod hatası için bir iş öğesi oluşturma](../code-quality/how-to-create-a-work-item-for-a-managed-code-defect.md)|