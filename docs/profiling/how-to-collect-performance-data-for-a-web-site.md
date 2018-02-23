---
title: "Nasıl yapılır: bir Web sitesi için performans verilerini toplama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vsperf.url.url
- vsperf.chooseurl
- vs.performance.wizard.asppage
- vsperf.url.ok
- vsperf.url.cancel
helpviewer_keywords:
- Profiling Tools,profiling ASP.NET
- web sites, performance profiling
- ASP.NET, performance profilng
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: db9cefe31201a3b67ba176a56fed58bbe155bcf0
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2018
---
# <a name="how-to-collect-performance-data-for-a-web-site"></a>Nasıl yapılır: bir Web sitesi için performans verilerini topla

Kullanabileceğiniz **performans Sihirbazı** için performans verilerini toplamak için bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması. Visual Studio'da açık bir Web uygulaması profil ya da profil bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web sitesi, yerel bilgisayarınızda bulunan ve Visual Studio IDE içinde açık değil.

> [!NOTE]
> **Performans Sihirbazı** katman etkileşim (TIP) verileri, JScript performans verilerini ya da her ikisini toplanan profil oluşturma verileri eklemenize olanak tanır. İpucu seçeneği sunucu tarafı işlemlerini verileri toplar. JScript profil yerel veya uzak bir Web sitesinde çalışan betikler veri toplar. Çoğu durumda, seçeneklerden yalnızca birini seçmeniz gerekir.

 Bir yönetici kullanımına kullanıcı erişim izinleri ayarlarına bağlı olarak tek bir kullanıcı olabilir veya ASP.NET işleminin barındıran bilgisayarda bir profil oluşturucu oturumu oluşturmak için güvenlik izni olmayabilir. Aşağıdaki örneklerde kullanıcılar arasında olası farklar gösterilmektedir:

- Yönetici sürücü ve hizmeti başlatmak için ayarlanmış olduğunda bazı kullanıcılar Gelişmiş profil özellikleri erişebilir.

- Etki alanı kullanıcıları yalnızca örnek profil erişebilir.

- Bazı kullanıcılar için diğer tüm kullanıcıların profil oluşturma erişimini.

 Daha fazla bilgi için bkz: [profil oluşturma ve Windows Vista Güvenliği](../profiling/profiling-and-windows-vista-security.md) ve yönetim Seçenekleri'nde [VSPerfCmd](../profiling/vsperfcmd.md).

## <a name="to-profile-a-web-site-project"></a>Bir Web sitesi projesini profilini

1. Açık [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Visual Studio'da Web projesi.

2. Üzerinde **Çözümle** menüsünde, select **Performans Profil Oluşturucu**seçin **performans Gezgini**ve ardından **Başlat**.

3. Sihirbazın ilk sayfasında, profil için bir yöntem seçin ve ardından **sonraki**. Profil oluşturma yöntemlerini hakkında daha fazla bilgi için bkz: [anlama performans koleksiyon yöntemleri](../profiling/understanding-performance-collection-methods.md). Profil oluşturma yöntemi eşzamanlılık görselleştiricisi web uygulamaları için kullanılabilir olmadığını unutmayın.

4. İçinde **hangi uygulamanın profil oluşturma için hedef ister misiniz?** aşağı açılan listesinde, geçerli projenin seçili olduğundan emin olun ve ardından **sonraki**.

5. Sihirbazın üçüncü sayfasında katman etkileşim profil oluşturma (TIP) verileri, Web sayfaları veya her ikisini çalıştıran JavaScript verilerden eklemeyi seçebilirsiniz.

    - Katman etkileşimli toplamak için seçin **etkinleştirmek katman etkileşim profil** onay kutusu.

    - Web sayfalarında çalıştıran JavaScript veri toplamak için seçin **profil JavaScript** onay kutusu.

6. **İleri**'ye tıklayın.

7. Sihirbazının dördüncü sayfasında, tıklatın **son**.

8. Bir performans oturumu için oluşturulan [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] uygulaması ve Web sitesinin tarayıcıda başlatılır. Profil oluşturmayı istediğiniz işlevselliği uygular ve tarayıcıyı kapatın.

     Profil Oluşturucu veri dosyası oluşturur ve verileri Özet görünümünü görüntüler [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ana penceresi.

## <a name="to-profile-a-web-site-without-opening-a-project-in-visual-studio"></a>Visual Studio Proje açmadan bir Web sitesi profili oluşturmak üzere

1. Visual Studio'yu açın.

2. Üzerinde **Çözümle** menüsünde, select **Performans Profil Oluşturucu**seçin **performans Gezgini**ve ardından **Başlat**.

3. Sihirbazın ilk sayfasında, profil için bir yöntem seçin ve ardından **sonraki**. Daha fazla bilgi için bkz: [anlama performans koleksiyon yöntemleri](../profiling/understanding-performance-collection-methods.md).

4. Sihirbazın ikinci sayfasında seçin **bir ASP.NET veya JavaScript uygulamasını profil** seçeneğini ve ardından **sonraki**.

5. İçinde **hangi URL veya yol web uygulamanızın çalışacağı** kutusunda sihirbazın üçüncü sayfasında, uygulama giriş sayfası URL'sini girin ve ardından **sonraki**.

    - Sunucusu (IIS) Web sitesini tabanlı için bir URL gibi yazın **http://localhost/MySite/default.aspx**. Bu neden [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Sitem profili ve sayfa default.aspx oturumu başlatmak için Internet Explorer ' başlatılması için bu sitede uygulama kökü, yerel bilgisayarda uygulama.

    - Bir dosya tabanlı Web sitesi için dosya / / / gibi bir yol yazın**c:\WebSites\MySite\default.aspx**. Bu neden [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] c:\webSites\MySite profili ve sayfa oturumu başlatmak için Internet Explorer ' başlatılması http://localhost:nnnn/MySite/default.aspx bulunan uygulama.

    - JavaScript veri toplamak istediğiniz dış siteleri için örneğin, http://www.contoso.com URL'yi yazın.

     Daha fazla bilgi için özellik sayfaları görüntülemek bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] hedef ikili.

6. Sihirbazın üçüncü sayfasında katman etkileşim profil oluşturma (TIP) verileri, Web sayfaları veya her ikisini çalıştıran JavaScript verilerden eklemeyi seçebilirsiniz.

    - Katman etkileşimli toplamak için seçin **etkinleştirmek katman etkileşim profil** onay kutusu.

    - Web sayfalarında çalıştıran JavaScript veri toplamak için seçin **profil JavaScript** onay kutusu.

7. **İleri**'ye tıklayın.

8. Sihirbazının dördüncü sayfasında, tıklatın **son**.

9. Bir performans oturumu için ASP.NET uygulama oluşturulur ve Web sitesi tarayıcıda başlatılır. Profil oluşturmayı istediğiniz işlevselliği uygular ve tarayıcıyı kapatın.

     Profil Oluşturucu veri dosyası oluşturur ve verileri Özet görünümünü görüntüler [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ana penceresi.

## <a name="see-also"></a>Ayrıca bkz.

[Genel Bakışlar](../profiling/overviews-performance-tools.md)  
[Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)  
[İzleme veri değerlerini anlama](../profiling/understanding-instrumentation-data-values.md)  
[Örnekleme veri değerlerini anlama](../profiling/understanding-sampling-data-values.md)
