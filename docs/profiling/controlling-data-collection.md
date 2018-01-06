---
title: Veri toplama denetimi | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- advanced tasks for profiling tools
- profiling tools, advanced tasks
ms.assetid: e713ad63-b948-46f3-8db9-59b30922ebe5
caps.latest.revision: "27"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8cbbbb2ce9002512eeba4e838edf0d4d960b38c8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="controlling-data-collection"></a>Veri Toplama Denetimi
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Profil Oluşturma Araçları, bir performans oturumu sırasında profil oluşturma verilerinin ne zaman toplanacağını kontrol etmenizi ve profillenen işlevleri belirtmenizi sağlar. Bu bölümde, veri koleksiyonunu durdurmak ve başlatmak açıklar **performans Gezgini** ve **veri toplama denetimi** windows ve kendisi için profil oluşturma verilerini toplanır nesneleri sınırlandırmak nasıl.  
  
## <a name="common-tasks"></a>Ortak Görevler  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Profil oluşturma durdurup başlatın:** uygulama başlatıldığında bir uygulamayı veya iliştirebilirsiniz profil oluşturucu zaten çalışan bir işlemin profili başlayabilirsiniz. Hedef uygulama çalışırken, veri toplamayı duraklatabilir ve devam ettirebilirsiniz. Hedef uygulamayı kapatarak veya profil oluşturucuyu çalışan bir işlemden ayırarak bir profil oluşturma oturumunu sonlandırabilirsiniz. |-   [Nasıl yapılır: Başlangıç ve bitiş performans verileri toplama](../profiling/how-to-start-and-end-performance-data-collection.md)<br />-   [Nasıl yapılır: ekleme ve ayırma işlemleri çalıştırmanın performans araçları](../profiling/how-to-attach-and-detach-performance-tools-to-running-processes.md)<br />-   [Nasıl yapılır: duraklatma ve sürdürme performans verileri toplama](../profiling/how-to-pause-and-resume-performance-data-collection.md)|  
|**Toplanan verileri sınırlamak için profil oluşturma Araçları'nı yapılandırın:** izleme metodunu kullanın çalıştırmalarının profil toplanan verileri sınırlamak için performans oturumu yapılandırma özelliklerini kullanabilirsiniz. Belirli .dll dosyalarını, ad alanlarını, sınıfları ve işlevleri dahil edebilir veya hariç tutabilirsiniz. Ayrıca, belirttiğiniz bir boyut eşiğini karşılamayan işlevleri çıkarabilirsiniz.|-   [Nasıl yapılır: belirli DLL'ler için araçları sınırlama](../profiling/how-to-limit-instrumentation-to-specific-dlls.md)<br />-   [Nasıl yapılır: belirli işlevler için araçları sınırlama](../profiling/how-to-limit-instrumentation-to-specific-functions.md)<br />-   [Nasıl yapılır: hariç tutma veya kısa işlevleri izlemeden içerir](../profiling/how-to-exclude-or-include-short-functions-from-instrumentation.md)|  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans Gezgini](../profiling/performance-explorer.md)