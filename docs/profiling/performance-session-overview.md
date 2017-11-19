---
title: "Performans oturumuna genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Profiling Tools, performance session
- performance sessions
ms.assetid: 35752f95-a57a-4def-b64d-cf4899669e99
caps.latest.revision: "35"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dff0b96bc40f857224df5222b43efac914de4f7c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="performance-session-overview"></a>Performans Oturumuna Genel Bakış
Bu genel bakışta profil temellerini açıklar. Performans çalışmaya yeni geliştiriciler görürsünüz nasıl [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturma araçları bunları hızla üretken ve kendi kod performansını artırmaya yardımcı olabilir. Profil deneyimli geliştiriciler belirli profil oluşturma araçları özellikleri ve süreçleri hakkında genel bir bakış elde edebilirler.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Profil oluşturma araçları yardımcı kaynak kodunda performans sorunlarını tanımlamak ve olası çözümlerini performansını karşılaştırır. Profil oluşturma araçları sihirbazlar ve varsayılan ayarları çoğu performans sorunu daha iyi verebilirsiniz. Özellikleri ve seçenekleri profil oluşturma araçları profil işlem üzerinde tam denetim sağlar. Bu denetim kesin hedefleme kod bölümleri, blok düzeyinde zamanlama bilgilerin toplanması ve eklenmesi, verilerinizde ek işlemci ve sistem performans verilerini içerir.  
  
 Aşağıdaki adımlar temel profil oluşturma araçlarını kullanma işlemini yapın:  
  
1.  Performans oturum koleksiyonu yöntemi ve toplamak istediğiniz verileri belirterek yapılandırın.  
  
2.  Performans oturumu uygulamayı çalıştırarak profil oluşturma veri toplayın.  
  
3.  Performans sorunu belirlemek için verileri analiz edin.  
  
4.  Kodda değişiklik [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamına (IDE) kod uygulama performansını artırır  
  
5.  Değiştirilen kod profil oluşturma verileri toplamak ve profil oluşturma verileri, özgün ve değiştirilen veriler karşılaştırın.  
  
6.  Performansı artırma belgeleri bir rapor oluşturun.  
  
 Profil oluşturma tarafından sağlanan bilgiler ile çalışmak için Sembol bilgilerini profil oluşturmayı istediğiniz ikili dosyaları ve Windows işletim sisteminin ikili dosyaları için kullanılabilir olmalıdır.  
  
## <a name="configure-the-performance-session"></a>Performans oturum yapılandırma  
 Profil oluşturma oturumu yapılandırmak için kullanmak istediğiniz profil oluşturma yöntemi ve toplamak istediğiniz verileri seçin. Profil oluşturma araçları **performans Sihirbazı** aracılığıyla temel yapılandırma yönlendirebilir ve diğer seçenekleri eklemek için Performans oturumunu özellik sayfalarını kullanabilirsiniz:  
  
-   Profil oluşturma yöntemleri örnekleme, izleme ve bellek ayırma içerir.  
  
-   Veri değerleri, saat, işlemci ve işletim sistemi performans sayaçları ve sayfa hataları ve çekirdek geçişler gibi uygulama olayları içerir.  
  
 Bir performans oturumda yapılandırabileceğiniz bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proje proje çözümün bir parçası ya da rasgele ikili dosyaları aracılığıyla profil [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE. Profil Oluşturma Sihirbazı'nı kullanabilirsiniz veya Performans oturumunu özellik sayfalarında oturum özellikleri belirtebilirsiniz.  
  
## <a name="collect-profiling-data"></a>Profil oluşturma verilerini topla  
 Profil oluşturma veri toplama başlatmak **performans Gezgini**. Duraklatma ve sürdürme topladığınız veri miktarını sınırlamak için profil oluşturma. Zaten çalışmakta olan bir işlem de ekleyebilirsiniz.  
  
 Uygulama başlar başlamaz **veri toplama denetimi** pencere görünür [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE. Gelen **veri toplama denetimi** penceresinde, profil, uygulamanızın belirli kısımlarını duraklatma ve sürdürme toplama işlemi. Aynı zamanda **veri toplama denetimi** toplanan verileri işaretleri eklemek için penceresi. İşaretleri profili görünümlerde görüntülenmesi ve profil oluşturma verileri filtrelemek için kullanılabilir kullanıcı tanımlı veri noktalarıdır.  
  
 Hedef uygulama kapatıldığında profil oluşturma araçları profil oluşturma veri dosyası (*.vsp) oluşturur ve Özet rapor görünümünde görüntüler [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE.  
  
## <a name="analyze-the-data-and-identify-performance-issues"></a>Verileri çözümlemek ve performans sorunlarını belirleyin  
 Bir çalıştırma profil sonlandırdığınızda, verileri analiz ve profil oluşturma araçları bir özeti gösterilir **performans raporu** windows görüntüleyin. Profil oluşturma verilerini çağrı yığını ve hedef uygulamanın tekil işlevler için toplanır. Rapor işlemler, iş parçacıkları, modüller, İşlevler ve uygulamanın kaynak kodu satır veri aralıkları için Performans Analizi görünümleri görüntüler. Profil oluşturma verilerini işlevi için değerler aşağıdakileri içerir:  
  
-   İşlev ve işlev (her ikisi de dahil değerler) tarafından çağrılan alt işlevleri harcanan toplam süreyi.  
  
-   (Özel değerler) işlevinde yalnızca kodu yürütme harcanan süre.  
  
 Üzerinde on iki farklı görünümleri en verimli şekilde profil oluşturma verileri çözümlemek etkinleştirin. Görünüm özelleştirmelerini filtrelemek ve performans sorunlarına neden işlevleri bulmak için verileri sıralamak etkinleştirin. Sık kullanılan yolu filtreleme çağrı ağacı ve modül görünümlerinde en etkin yol hemen vurgulama sağlar.  
  
## <a name="modify-the-application-code"></a>Uygulama kodu değiştirin  
 Bir veya daha fazla ilgili performans sorunlarını yalıtılmış sonra kullanarak kodu değiştirebilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE ve ardından veri değişiklikleri için profil oluşturma.  
  
## <a name="collect-profiling-data-again-and-compare-the-data-between-the-profiling-runs"></a>Yeniden profil oluşturma verilerini toplamak ve verileri profil çalıştırmaları arasında karşılaştırma  
 Profil oluşturma araçları karşılaştırma rapor görünümü modülü, işlev veya satır performans iki seçili profil oluşturma veri dosyaları arasındaki farkı görüntüler. Karşılaştırmak istediğiniz ve tek tek dosyaların görünümlerini ve karşılaştırma görünümü arasında geçiş yapabilirsiniz profil oluşturma veri değerlerini belirtebilirsiniz.  
  
## <a name="generate-a-report-of-the-results"></a>Sonuçları bir rapor oluşturun  
 E-postalar ve elektronik olarak herhangi bir performans raporu görünüm satırlarını yapıştırabilir ve bir veya daha fazla görünümler için verileri içeren raporlar oluşturabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel bakış](../profiling/overviews-performance-tools.md)   
 [İzlenecek yol: Performans sorunları tanımlama](../profiling/walkthrough-identifying-performance-problems.md)