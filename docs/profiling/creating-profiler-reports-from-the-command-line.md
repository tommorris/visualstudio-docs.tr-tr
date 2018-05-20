---
title: Komut satırından profil oluşturucu raporları oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: c886f8af-2014-4fec-9b24-d98b68ecafb7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d925e2c20a304239c8b510bf9ecc1fba123c4dfa
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="create-profiler-reports-from-the-command-line"></a>Komut satırından profil oluşturucu raporları oluşturma
**VSPerfReport** komut satırı aracı, veri (.vsp) dosyaları profil .xml veya virgülle ayrılmış değer (.csv) raporlar oluşturmanıza olanak sağlar. VSPerfReport rapor türleri arabirim için tablo tabanlı görünümlerini karşılayabilmesi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Yalnızca kodunuzun göstermek için ve profil oluşturma veri dosyası yalnızca bir parçasını göstermek için raporu filtreleyebilirsiniz. Daha fazla bilgi için bkz: [VSPerfReport](../profiling/vsperfreport.md).  
  
 Profil oluşturma veri dosyaları daha kolay .vsp dosyaları sembolleri katıştırma tarafından ve daha küçük ve açmak daha hızlı (.vsps) dosyalarını önceden çözümlenen raporu oluşturarak paylaşmak de yapabilirsiniz.  
  
## <a name="common-tasks"></a>Ortak görevler
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Temel bir rapor oluşturun.** Tüm ya da alt kümesini VSPerfReport rapor türleri oluşturun.|-   [Temel raporlar oluşturma](../profiling/creating-basic-profiling-reports-from-the-command-line.md)|  
|**İki profil oluşturma veri dosyaları karşılaştırın.** Profil oluşturma veri dosyaları iki performans verilerini karşılaştırır "fark" rapor oluşturun.|-   [Nasıl yapılır: bir komut isteminden profil oluşturucu Karşılaştırma raporu oluşturma](../profiling/how-to-create-a-profiler-comparison-report-from-a-command-prompt.md)|  
|**Görünüm çağrı izleme ve olay izleme için Windows (ETW) verileri.** Her giriş ve çıkış noktası, uygulamanızın işlevlere ve diğer işlevleri işlevinizi tarafından her çağrı için zamanlama bilgileri listeleyen bir çağrı izleme raporu oluşturun. Veya bir profil çalıştırmada toplanmış olan tüm ETW olayları ayrıntılı bir listesini oluşturun.|-   [Nasıl yapılır: çağrı izleme raporu oluşturma](../profiling/how-to-create-a-profiling-tools-call-trace-report.md)|  
|**Bir raporu filtreleme.** Bir rapor yalnızca kodunuzda işlevleri veya profil oluşturma veri dosyası belirli bir zamanda sınırlayın.|-   [Nasıl yapılır: komut satırından raporları filtreleme](../profiling/how-to-filter-reports-from-the-command-line.md)|  
|**Taşınabilir profil oluşturma veri dosyaları oluşturun.** Profil oluşturma verilerini daha kolay paylaşımı yapmak için bir profil .vsp dosyasına çalıştırmak için simgeler eklenebilir. Daha küçük ve daha hızlı açmak önceden çözümlenen bir profil oluşturma veri (.vsps) dosyası da oluşturabilirsiniz.|-   [Taşınabilir profil oluşturma veri dosyaları oluşturma](../profiling/creating-portable-profiling-data-files-from-the-command-line.md)|