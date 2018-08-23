---
title: İş parçacığı ve işlem eşzamanlılık verileri toplama | Microsoft Docs
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
- concurrency profiling method
- Profiling Tools, concurrency method
ms.assetid: fa03d381-a9ee-408c-876d-05111e29225b
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 935fbd89fa78ae7f05542eb0310f3e07673ee007
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687001"
---
# <a name="collecting-thread-and-process-concurrency-data"></a>İş Parçacığı ve İşlem Eşzamanlılık Verileri Toplama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [toplama iş parçacığı ve işlem eşzamanlılık verileri](https://docs.microsoft.com/visualstudio/profiling/collecting-thread-and-process-concurrency-data).  
  
[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Profil oluşturma araçları eşzamanlılık profili oluşturma yöntemi, bir işlev bir kaynağa erişim için beklenecek profillenen uygulamanın neden olan her eşitleme olay hakkında bilgiler içeren kaynak çekişmesi verisini toplamak olanak tanır.  
  
 **Gereksinimler**  
  
-   [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
 Aşağıdaki yordamlardan birini kullanarak profili oluşturma yöntemi eşzamanlılık belirtebilirsiniz:  
  
-   Profil Oluşturma Sihirbazı'nın ilk sayfasında, tıklayın **eşzamanlılık**  
  
-   Üzerinde **genel** sayfası için performans oturumu Özellikleri iletişim kutusu tıklayın **eşzamanlılık**.  
  
-   Üzerinde **performans Gezgini** araç penceresindeki **yöntemi** listesinde **eşzamanlılık**.  
  
## <a name="common-tasks"></a>Ortak Görevler  
 Ek seçenekler belirtebilirsiniz *performans oturumu *** özellik sayfaları** performans oturumunun iletişim kutusu. Bu iletişim kutusunu açmak için:  
  
-   İçinde **performans Gezgini**performans oturumu adına sağ tıklayın ve ardından **özellikleri**.  
  
 Aşağıdaki tabloda görevler belirleyebilirsiniz seçenekleri açıklanmıştır *performans oturumu *** özellik sayfaları** eşzamanlılık metodu kullanarak profil olduğunda iletişim kutusu.  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|Üzerinde **genel** sayfasında, oluşturulan profil oluşturma veri (.vsp) dosyasının adlandırma ayrıntıları belirtin.|-   [Nasıl yapılır: performans veri dosyası adlandırma seçeneklerini ayarlama](../profiling/how-to-set-performance-data-file-name-options.md)|  
|Üzerinde **başlatma** sayfasında, kod çözümünüz içinde birden çok .exe projeniz varsa başlatmak için bir uygulama belirtin.|-   [Nasıl yapılır: başlatma için ikili dosya belirtme](../profiling/how-to-specify-the-binary-to-start.md)|  
|Üzerinde **katman etkileşim** sayfasında, profil oluşturma çalışması için ADO.NET çağrı veri ekleyin.|-   [Katman etkileşim verileri toplama](../profiling/collecting-tier-interaction-data.md)|  
|Üzerinde **Windows sayaçları** sayfasında işaretleri olarak profil oluşturma verilerini eklemek için bir veya daha fazla işletim sistemi performans sayaçları belirtin.|-   [Nasıl yapılır: Windows sayaç verileri toplama](../profiling/how-to-collect-windows-counter-data.md)|  
|Üzerinde **Gelişmiş** sayfasında, uygulama modüllerinizi birden çok sürümü kullanıyorsanız, .NET Framework çalışma zamanı profili sürümünü belirtin. Varsayılan olarak yüklenen ilk sürüm profil oluşturulan.|-   [Nasıl yapılır: .NET Framework çalışma zamanını belirtin](../profiling/how-to-specify-the-dotnet-framework-runtime.md)|



