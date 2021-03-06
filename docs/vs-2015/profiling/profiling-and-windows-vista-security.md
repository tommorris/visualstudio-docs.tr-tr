---
title: Profil oluşturma ve Windows Vista güvenliği | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Profiling Tools,security
- performance tools, security
ms.assetid: 842112fc-b886-4801-8cd7-a25b314b0393
caps.latest.revision: 24
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 736e7a04813a6c56d6cab6d1886171e321d583cb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689802"
---
# <a name="profiling-and-windows-vista-security"></a>Profil Oluşturma Windows Vista Güvenliği
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [profil oluşturma ve Windows Vista Güvenliği](https://docs.microsoft.com/visualstudio/profiling/profiling-and-windows-vista-security).  
  
Yapılandırmanıza bağlı olarak [!INCLUDE[wiprlhext](../includes/wiprlhext-md.md)] bilgisayar yöneticisi kullanılabilir hale getirdiği kullanıcı erişimi izinleri ayarları, bireysel bir kullanıcı bu bilgisayarda bir işlem profili için güvenlik izni olabilir. Aşağıdaki örneklerde kullanıcılar arasındaki olası farklar gösterilmektedir:  
  
-   Yöneticisi hizmetinin başlatılmasını ve sürücü ayarladığınızda, bazı kullanıcılar Gelişmiş profil oluşturma özelliklerine erişebilir.  
  
-   Etki alanı kullanıcıları yalnızca örnek profil oluşturma erişebilir.  
  
-   Bazı kullanıcılar, diğer tüm kullanıcılar için profil oluşturma için erişim reddedebilir.  
  
 Daha fazla bilgi için yönetim seçenekleri görmek [VSPerfCmd](../profiling/vsperfcmd.md).  
  
## <a name="cross-session-profiling"></a>Çapraz oturum profil oluşturma  
 *Çapraz oturum profil oluşturma* farklı oturumda çalışan bir işlemi profil yeteneğidir. Örneğin, çoğu Hizmetleri 0 oturumunda çalıştırın ve kullanıcıların 0. oturumunda doğrudan çalıştıramazsınız. Kullanarak **iliştirme** performans Gezgini araç çubuğundan veya / komut satırı aracının VSPerfCmd seçenek ekleme, çoğu işlemleri farklı oturum açılışlarında profil oluşturabilirsiniz.  
  
 Çapraz işlem profil görünürlüğü seçeneklerini ayarlayarak kullanılabilir işlem listesini görebilirsiniz. Bu seçenekler kullanılabilir **iliştirme** tıkladığınızda görüntülenen penceresi **iliştirme**:  
  
-   **Tüm kullanıcıların işlemlerini göster**  
  
     Bu seçenek, yalnızca geçerli kullanıcıya ait işlemler listede görüntülenir. Zaman **tüm kullanıcıların işlemlerini göster** olduğu belirlenirse, tüm kullanıcıların işlemlerini listesini görüntüler.  
  
-   **Tüm oturumlardaki işlemleri göster**  
  
     Bu seçenek seçilmezse, listenin geçerli oturumda işlemleri görüntüler. Bu seçenek belirlendiğinde, listenin tüm oturumlardaki işlemleri görüntüler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel bakış](../profiling/overviews-performance-tools.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Nasıl yapılır: bir çalışan işleme ekleme](http://msdn.microsoft.com/en-us/636d0a52-4bfd-48d2-89ad-d7b9ca4dc4f4)



