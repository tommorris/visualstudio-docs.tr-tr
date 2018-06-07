---
title: Profil oluşturma kullanarak komut satırından Araçlar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- command line, performance tools
- command-line tools, performance tools
- profiling tools,command line
- tools, command-line
- command line, tools
ms.assetid: 6593fa82-181e-4009-a0ed-02aa24c2c063
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 62d15922404627b5b95f9782c46b70458fe14188
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34571565"
---
# <a name="use-the-profiling-tools-from-the-command-line"></a>Komut satırından profil oluşturma araçlarını kullanma
Komut satırı araçlarını kullanabilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturma araçları komut isteminden ve toplu iş dosyaları kullanılarak ve komut dosyası profil oluşturmayı otomatikleştirmek için profil uygulamaları için. Rapor dosyaları bir komut isteminde de oluşturabilirsiniz. Basit bağımsız profil oluşturucuyu olmayan bilgisayarlardaki verileri toplamak için kullanabileceğiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yüklü.  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Ortak görevler  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Simgelerin konumunu ayarlayın:** işlevler ve parametre adlarını görüntülemek için profil oluşturucu simgenin erişiminiz olmalıdır (. *pdb*) profili ikili dosyaları. Bu dosyalar, çözümleme, görüntülemek istediğiniz uygulamaları ve Microsoft işletim sistemi için simge dosyaları içermelidir. Doğru olduğundan emin olmak için genel Microsoft Simge Sunucusu'nu kullanabilirsiniz. *pdb* Microsoft ikili dosyaları.|-   [Nasıl yapılır: komut satırından simge dosyası konumlarını belirtin](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md)|  
|**Uygulamanıza profil:** komut satırı araçları ve bir hedef uygulama profil oluşturma yöntemi uygulama türüne bağlıdır profil için kullandığınız seçeneklerini ve hedef yönetilen veya yerel bir uygulama olup olmadığını.|-   [Komut satırından profil oluşturma yöntemlerini kullanma](../profiling/using-profiling-methods-to-collect-performance-data-from-the-command-line.md)<br />-   [Bağımsız uygulamalar profili](../profiling/command-line-profiling-of-stand-alone-applications.md)<br />-   [Profil ASP.NET web uygulamaları](../profiling/command-line-profiling-of-aspnet-web-applications.md)<br />-   [Profil Hizmetleri](../profiling/command-line-profiling-of-services.md)|  
|**.XML veya .csv raporları oluşturma:** komut isteminden profil oluşturma oluşturur arabirim için görüntülenebilir veri dosyalarını [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. De oluşturabilirsiniz. *xml* veya virgülle ayrılmış değer (. *CSV*) VSPerfReport komut satırı aracını kullanarak veri dosyaları.|-   [Komut satırından profil oluşturucu raporları oluşturma](../profiling/creating-profiler-reports-from-the-command-line.md)<br />-   [VSPerfReport](../profiling/vsperfreport.md)|  
|**Visual Studio bulunmayan bilgisayarlarda kodunun profilini oluşturma:** olmayan bilgisayarlardaki uygulamalarda verileri toplamak için profil oluşturma araçları bağımsız profil oluşturucuyu kullanabilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yüklü.|-   [Nasıl yapılır: bağımsız profil oluşturucuyu yükleme](../profiling/how-to-install-the-stand-alone-profiler.md)|  
  
## <a name="reference"></a>Başvuru  
 [Komut satırı profil araçları başvurusu](../profiling/command-line-profiling-tools-reference.md)  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Performans Gezgini](../profiling/performance-explorer.md)