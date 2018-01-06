---
title: "Komut satırından profil oluşturucu raporları oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c886f8af-2014-4fec-9b24-d98b68ecafb7
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 474b7c0167b02665a5bc2ff5c1297f768facbc32
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-profiler-reports-from-the-command-line"></a>Komut Satırından Profil Oluşturma Raporları Oluşturma
**VSPerfReport** komut satırı aracı, veri (.vsp) dosyaları profil .xml veya virgülle ayrılmış değer (.csv) raporlar oluşturmanıza olanak sağlar. VSPerfReport rapor türleri arabirim için tablo tabanlı görünümlerini karşılayabilmesi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Yalnızca kodunuzun göstermek için ve profil oluşturma veri dosyası yalnızca bir parçasını göstermek için raporu filtreleyebilirsiniz. Daha fazla bilgi için bkz: [VSPerfReport](../profiling/vsperfreport.md).  
  
 Profil oluşturma veri dosyaları daha kolay .vsp dosyaları sembolleri katıştırma tarafından ve daha küçük ve açmak daha hızlı (.vsps) dosyalarını önceden çözümlenen raporu oluşturarak paylaşmak de yapabilirsiniz.  
  
## <a name="common-tasks"></a>Ortak Görevler  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Temel bir rapor oluşturun.** Tüm ya da alt kümesini VSPerfReport rapor türleri oluşturun.|-   [Temel raporlar oluşturma](../profiling/creating-basic-profiling-reports-from-the-command-line.md)|  
|**İki profil oluşturma veri dosyaları karşılaştırın.** Profil oluşturma veri dosyaları iki performans verilerini karşılaştırır "fark" rapor oluşturun.|-   [Nasıl yapılır: bir komut isteminden profil oluşturucu Karşılaştırma raporu oluşturma](../profiling/how-to-create-a-profiler-comparison-report-from-a-command-prompt.md)|  
|**Görünüm çağrı izleme ve olay izleme için Windows (ETW) verileri.** Her giriş ve çıkış noktası, uygulamanızın işlevlere ve diğer işlevleri işlevinizi tarafından her çağrı için zamanlama bilgileri listeleyen bir çağrı izleme raporu oluşturun. Veya bir profil çalıştırmada toplanmış olan tüm ETW olayları ayrıntılı bir listesini oluşturun.|-   [Nasıl yapılır: çağrı izleme raporu oluşturma](../profiling/how-to-create-a-profiling-tools-call-trace-report.md)|  
|**Bir raporu filtreleme.** Bir rapor yalnızca kodunuzda işlevleri veya profil oluşturma veri dosyası belirli bir zamanda sınırlayın.|-   [Nasıl yapılır: komut satırından raporları filtreleme](../profiling/how-to-filter-reports-from-the-command-line.md)|  
|**Taşınabilir profil oluşturma veri dosyaları oluşturun.** Profil oluşturma verilerini daha kolay paylaşımı yapmak için bir profil .vsp dosyasına çalıştırmak için simgeler eklenebilir. Daha küçük ve daha hızlı açmak önceden çözümlenen bir profil oluşturma veri (.vsps) dosyası da oluşturabilirsiniz.|-   [Taşınabilir profil oluşturma veri dosyaları oluşturma](../profiling/creating-portable-profiling-data-files-from-the-command-line.md)|