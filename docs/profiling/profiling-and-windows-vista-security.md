---
title: Profil oluşturma ve Windows Vista güvenliği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools,security
- performance tools, security
ms.assetid: 842112fc-b886-4801-8cd7-a25b314b0393
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f64483ff7c296e8a428d845018ac9630419c037e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="profiling-and-windows-vista-security"></a>Profil Oluşturma Windows Vista Güvenliği
Bağlı olarak [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)] bilgisayar yöneticisi kullanılabilir hale getirdiği kullanıcı erişimi izinleri ayarları, tek bir kullanıcı bu bilgisayarda bir işlemi profil için güvenlik izni olabilir. Aşağıdaki örneklerde kullanıcılar arasında olası farklar gösterilmektedir:  
  
-   Yönetici sürücü ve hizmeti başlatmak için ayarlanmış olduğunda bazı kullanıcılar Gelişmiş profil özellikleri erişebilir.  
  
-   Etki alanı kullanıcıları yalnızca örnek profil erişebilir.  
  
-   Bazı kullanıcılar için diğer tüm kullanıcıların profil oluşturma erişimini.  
  
 Daha fazla bilgi için yönetici bkz [VSPerfCmd](../profiling/vsperfcmd.md).  
  
## <a name="cross-session-profiling"></a>Profil oluşturma oturumu arası  
 *Profil oluşturma oturumu arası* farklı bir oturumda çalışan bir işlemi profil yeteneğidir. Örneğin, çoğu Hizmetleri 0 oturumunda çalıştırın ve kullanıcıların doğrudan oturum 0 çalıştıramazsınız. Kullanarak **ekleme işlemi için** performans Gezgini araç çubuğunda veya / VSPerfCmd komut satırı aracı seçeneği bağlayın, çoğu işlemleri farklı oturum açma oturumlarında profil.  
  
 Çapraz işlem profil görünürlük seçeneklerini ayarlayarak kullanılabilir işlemlerin bir listesini görebilirsiniz. Bu seçenekler mevcuttur **ekleme işlemi için** tıkladığınızda görüntülenen penceresi **ekleme işlemi için**:  
  
-   **Tüm kullanıcıların işlemlerini göster**  
  
     Bu seçenek belirlenmediğinde, geçerli kullanıcı tarafından sahip olunan işlemlerin listesini görüntüler. Zaman **işlemleri tüm kullanıcıları göster** olduğunu belirlenirse, tüm kullanıcıların işlemlerini görüntüler.  
  
-   **Tüm oturumları işlemlerini göster**  
  
     Bu seçenek belirlenmediğinde işlemleri geçerli oturumdaki görüntüler. Bu seçenek belirlendiğinde, listenin tüm oturumları işlemleri görüntüler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel bakış](../profiling/overviews-performance-tools.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Nasıl yapılır: bir çalışan işlem ekleme](http://msdn.microsoft.com/en-us/636d0a52-4bfd-48d2-89ad-d7b9ca4dc4f4)