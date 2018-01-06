---
title: "Kural kümeleri kullanma kod çözümleme kurallarını gruplandırmak için | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.rulesets.learnmore
helpviewer_keywords: code analysis, rule sets
ms.assetid: ed0f3a2a-1516-42e2-92de-b8986dc75d42
caps.latest.revision: "36"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 51b282cb86ca83ecf2ace1e4b12c8444928b15e1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="using-rule-sets-to-group-code-analysis-rules"></a>Kod Çözümleme Kurallarını Gruplandırmak için Kural Kümeleri Kullanma
Kod Analizi yapılandırırken [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], veya [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)], Microsoft yerleşik listesinden seçebilirsiniz *kural kümeleri*. Bir kural kümesi hedeflenen sorunları ve belirli koşullar tanımlamak kod çözümleme kurallarını mantıksal bir gruplandırmasıdır. Örneğin, genel kullanıma açık API'ler kodu taramak için tasarlanmış bir kural kümesi uygulayabilir veya yalnızca kuralları önerilen en düşük içeren bir kural kümesi uygulayabilirsiniz. Tüm kuralları içeren bir kural kümesi de uygulayabilirsiniz.  
  
 Bir kural görünmesi ekleyerek veya kuralları silme veya değiştirme kurallarını kümesini özelleştirebilirsiniz **hata listesi** pencere uyarılar veya hatalar olarak. Özelleştirilmiş kural kümeleri belirli geliştirme ortamınızı gereksinimini karşılayabilir. Bir kural kümesi özelleştirdiğinizde, kural kümesi sayfası arama ve filtreleme süreçte yardımcı olacak araçlar sağlar.  
  
## <a name="common-tasks"></a>Ortak Görevler  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Uygulamalı deneyim alın:** özel bir kural belirtmek için kod çözümleme araçları kümesini bulmak ve basit bir .NET Framework uygulama sorunlarını düzeltmek için kullanın.|-   [İzlenecek yol: Yapılandırma ve özel bir kural kümesini kullanma](../code-quality/walkthrough-configuring-and-using-a-custom-rule-set.md)|  
|**Projesi için kod analizini yapılandırma:** proje, Web sitesi veya çözüm için mevcut bir kuralı seçme.|-   [Nasıl yapılır: yönetilen kod projesi için kod çözümlemesini yapılandırma](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)<br />-   [Çalıştırılacak C++ kurallarını belirtmek için kural kümeleri kullanma](../code-quality/using-rule-sets-to-specify-the-cpp-rules-to-run.md)<br />-   [Nasıl yapılır: bir ASP.NET Web uygulaması için kod çözümlemesini yapılandırma](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)<br />-   [Nasıl yapılır: bir çözümde birden çok proje için kural kümesi belirtme](../code-quality/how-to-specify-managed-code-rule-sets-for-multiple-projects-in-a-solution.md)|  
|**Bir kural kümesi özelleştirme:** projenize uygulamak için kuralları belirtin.|-   [Özel kural kümeleri oluşturma](../code-quality/creating-custom-code-analysis-rule-sets.md)|  
|**Yerleşik kural kümeleri anlama:** yerleşik kural kümelerini olun kod çözümleme kurallarını görüntüleyin.|-   [Kod çözümleme kural kümesi başvurusu](../code-quality/code-analysis-rule-set-reference.md)|  
|**Kod çözümleme Team Foundation Server ile tümleştirme:** [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)] ilkelerini etkinleştirmek tüm kod iadeler kod çözümleme standartları ortak bir dizi karşıladığından emin olmak geliştirme ekiplerinin iade.|-   [Nasıl yapılır: iade takım projesi ilkesiyle kod proje kural kümelerini eşitleme](../code-quality/how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy.md)|