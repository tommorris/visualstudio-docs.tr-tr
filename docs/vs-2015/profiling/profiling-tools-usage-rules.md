---
title: Profil Araçları Kullanım Kuralları | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: afa7db3b-8c1d-473a-81ac-24ede112a17f
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6d508fdfe1845a75f0ef7e0ba36730afbaa4e157
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686565"
---
# <a name="profiling-tools-usage-rules"></a>Profil Araçları Kullanım Kuralları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [profil oluşturma araçları kullanım kuralları](https://docs.microsoft.com/visualstudio/profiling/profiling-tools-usage-rules).  
  
Performans kuralları profil oluşturma araçları kullanım kategorisinde en etkili bir şekilde veri toplamak için profil oluşturucu kullanmaya yönelik rehberlik sağlar.  
  
|||  
|-|-|  
|[DA0002: VSPerfCorProf.dll eksik](../profiling/da0002-vsperfcorprof-dll-is-missing.md)|Komut satırı profil oluşturma için eksik veri içerebilir [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] ikili dosyaları. Bu doğru ortam değişkenlerini ayarlanmaması kaynaklanıyor olabilir.|  
|[DA0003: Pek çok çekirdek örneği](../profiling/da0003-many-kernel-samples.md)|Hedef ikili yürütülmesini dışında gerçekleşen çok sayıda profil oluşturma örneğinden kaydedilmiş. Daha doğru veriler toplamak için izleme metodunu kullanarak göz önünde bulundurun.|  
|[DA0004: Yüksek işlemci kullanımı](../profiling/da0004-high-processor-usage.md)|Profil oluşturma verilerini, profil oluşturma sırasında işlemci sürekli olarak meşgul önerir. Daha doğru veriler toplamak için örnekleme metodu kullanılarak göz önünde bulundurun.|  
|[DA0008: Toplanan örnek az](../profiling/da0008-few-samples-collected.md)|Profil oluşturma çalışmasında toplanan örnek sayısı, istatistiksel açıdan anlamlı olması yeterince yüksek değil. Yeniden profil oluşturma ve uygulama için daha uzun süre çalışan göz önünde bulundurun. Ayrıca, veri toplamak için izleme metodunu kullanarak göz önünde bulundurun.|  
|[DA0026: Aşırı çekirdek CPU süresi işleme](../profiling/da0026-excessive-kernel-cpu-time-processing.md)|Profil oluşturma çalışma zamanında önemli miktarda işlemci çekirdek modunda oluştu. Örnekleme ölçüm zaman ölçümü kullanmak yerine sistem çağrıları kullanarak göz önünde bulundurun.|  
|[DA0029: Desteklenmeyen CLR Sürümü](../profiling/da0029-unsupported-clr-version.md)|Profili oluşturulan ikili bir sürümünü kullanıyor [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] Profil Oluşturucu tarafından desteklenmiyor. Profil Oluşturucu raporları sembol adı çözümlenemiyor.|  
|[DA0030: Veritabanı projeleri için Katman Etkileşim ölçümlerini topla](../profiling/da0030-gather-tier-interaction-measurements-for-database-projects.md)|Çok sayıda yöntemlere çağrıları <xref:System.Data?displayProperty=fullName> ad alanı toplandı. Veritabanı çağrıları ile ilgili verileri içerecek şekilde profilinizde katman etkileşim verileri toplama çalışır göz önünde bulundurun.|



