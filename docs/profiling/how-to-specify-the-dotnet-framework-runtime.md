---
title: "Nasıl yapılır: .NET Framework çalışma zamanı belirtin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Profiling Tools, .NET Framework versions
- .NET Framework versions,profililng
ms.assetid: d39f3579-719a-4f47-a97d-5b4232fe4c64
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 894d3f137787617de88ddcd2bed586c64dd22117
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-specify-the-net-framework-runtime"></a>Nasıl yapılır: .NET Framework çalışma zamanı belirtin
Sürümü ile [!INCLUDE[net_v40_long](../code-quality/includes/net_v40_long_md.md)], uygulamaları, farklı sürümleri kullanılarak oluşturulan modüllerin birleştirilebilen [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] çalıştırma. Varsayılan olarak, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturma araçları profil uygulama tarafından yüklenen ilk çalışma zamanı. Bir uygulamaya Profil Oluşturucu ile başladığınızda ve zaten çalışan bir uygulamaya profil oluşturucu ekleme, profil için çalışma zamanı belirtebilirsiniz.  
  
 **Gereksinimler**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
### <a name="to-specify-the-net-framework-run-time-to-profile-when-starting-an-application-with-the-profiler"></a>.NET Framework çalışma zamanı profili için bir uygulama ile profil oluşturucu başlatılırken belirtmek için  
  
1.  İçinde **performans Gezgini**, performans oturumunu sağ tıklayın, **özellikleri**ve ardından **Gelişmiş**.  
  
     **Hedef CLR sürümü** liste kutusunu görüntüler **otomatik** ve sürümleri [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] bilgisayarda yüklü olan çalışma zamanı.  
  
2.  Aşağıdaki adımlardan birini uygulayın:  
  
    -   Profil oluşturmayı istediğiniz CLR sürümü'ı tıklatın.  
  
    -   Tıklatın **otomatik** uygulama tarafından yüklenen ilk sürüm profilini.  
  
### <a name="to-specify-the-net-framework-run-time-to-profile-when-attaching-the-profiler-to-an-application"></a>.NET Framework çalışma zamanı profili için bir uygulamaya profil oluşturucu eklerken belirtmek için  
  
1.  Çözümle menüsünde için profil oluşturucu, sonra Attach/Detach'yi tıklatın.  
  
2.  Attach profil oluşturucu üzerinde işlem iletişim kutusu, profil oluşturmayı istediğiniz işlemi'ı tıklatın.  
  
     **Hedef CLR sürümü** liste kutusu s **otomatik** ve sürümleri [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] bilgisayarda yüklü olan çalışma zamanı.  
  
3.  Aşağıdaki adımlardan birini uygulayın:  
  
    -   Profil oluşturmayı istediğiniz CLR sürümü'ı tıklatın.  
  
    -   Tıklatın **otomatik** uygulamaya profil oluşturucu ekler, yüklenen sürüm profilini.