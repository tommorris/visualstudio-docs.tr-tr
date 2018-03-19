---
title: "Test denetleyicileri ve Test aracılarını Visual Studio sorunlarını giderme | Microsoft Docs"
ms.date: 10/20/2016
ms.topic: article
helpviewer_keywords:
- load tests, test controllers
- load tests, troubleshooting
- load tests, test agents
- troubleshooting, test controllers and agents in load tests
ms.assetid: 77329348-3a5d-43de-b6cb-90f93296a081
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 37ff6e82c61e55dc162287ce944008cc09e37204
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="strategies-for-troubleshooting-test-controllers-and-test-agents-in-load-tests"></a>Test Denetleyicileri ve Yükleme Testlerindeki Test Aracılarına İlişkin Sorun Giderme Stratejileri

Bu makalede, test denetleyicileri ve test aracılarını Visual Studio ile çalışırken, karşılaşabileceğiniz bazı yaygın sorunlar yer almaktadır.

##  <a name="unable-to-collect-performance-counters-on-test-agent-computer"></a>Test aracısı bilgisayarda performans sayaçları toplanamıyor.

 Bir yük testi çalıştırdığınızda, bir test aracısı bilgisayara bağlanmak ve performans sayaçlarını toplama çalıştığınızda hata alabilirsiniz. Uzak Kayıt Defteri hizmeti performans sayacı verilerini uzak bir bilgisayara sağlamak için sorumlu hizmetidir. Bazı işletim sistemlerinde, uzak kayıt defteri hizmeti otomatik olarak başlatılmaz. Bu sorunu gidermek için el ile uzak kayıt defteri hizmetini başlatın.

> [!NOTE]
>  Uzak Kayıt Defteri hizmetine erişim **Denetim Masası.** Seçin **Yönetimsel Araçlar** ve ardından **Hizmetleri**.

 Bu sorunun başka bir nedeni, performans sayaçlarını okumak için yeterli izinlere sahip değil ' dir. Yerel test çalıştırmalarında testi çalıştıran kullanıcı hesabı Power Users grubunun veya daha yüksek bir üyesi olmanız veya Performance Monitor Users grubunun bir üyesi olmanız gerekir. Uzaktan test denetleyicisi Power Users grubunun bir üyesi olarak çalıştırmak için yapılandırılmış veya sonrası, hesabı çalışır veya Performance Monitor Users grubunun bir üyesi olması için.

## <a name="setting-the-logging-level-on-a-test-controller-computer"></a>Bir Test denetleyicisi bilgisayarında günlüğe kaydetme düzeyini ayarlama
 Bir test denetleyicisi bilgisayarında günlüğe kaydetme düzeyini denetleyebilirsiniz. Bir ortamda bir yük testi çalıştırırken bir sorunu tanılamak çalışırken bu yararlı olur.

### <a name="to-set-the-logging-level-on-a-test-controller-computer"></a>Bir test denetleyicisi bilgisayarında günlüğe kaydetme düzeyi ayarlamak için

1.  Test denetleyicisi hizmetini durdurun. Bir komut isteminde `net stop vsttcontroller`.

2.  QTController.exe.config dosyasını açın. Bu dosya, denetleyici yükleme dizininde bulunur.

3.  Girişini Düzenle `EqtTraceLevel` dosya sistemi Tanılama bölümüne geçin. Kodunuzu şuna benzemelidir:

    ```
    <system.diagnostics>
        <trace autoflush="true" indentsize="4">
            <listeners>
                <add name="myListener" type="System.Diagnostics.TextWriterTraceListener" initializeData="d:\VSTestHost.log" />
            </listeners>
        </trace>
        <switches>
            <!-- You must use integral values for "value":
                    0 = off,
                    1 = error,
                    2 = warn,
                    3 = info,
                    4 = verbose. -->
            <add name="EqtTraceLevel" value="4" />
        </switches>
    </system.diagnostics>
    ```

4.  Dosyayı kaydedin.

5.  Denetleyici hizmetini başlatın. Bir komut isteminde `net start vsttcontroller`.

 Bu test denetleyicisi, test aracısı hizmeti ve test aracısı işlemi için geçerlidir. Tanılama sorunları olduğunda, tüm üç işlem günlüğü etkinleştirmek yararlıdır. Günlük düzeyini ayarlama yordamı test denetleyicisi için daha önce belirtildiği gibi her üç işlem için aynıdır. Hizmet ve aracı işlemi test aracısı için günlük düzeylerini ayarlamak için aşağıdaki yapılandırma dosyalarını kullanın:

-   **QTController.exe.config** Conttoller service

-   **QTAgentService.exe.config** Aracısı hizmeti

-   **QTDCAgent (32).exe.config** 32 bitlik bir mimari için aracı veri bağdaştırıcısı işlemi.

-   **QTDCAgent (64).exe.config** 64 bitlik bir mimari için aracı veri bağdaştırıcısı işlemi.

-   **QTAgent (32).exe.config** 32 bitlik bir mimari için aracı test işlemi.

-   **QTAgent (64).exe.config** 64 bitlik bir mimari için aracı test işlemi.

## <a name="binding-a-test-controller-to-a-network-adapter"></a>Bir ağ bağdaştırıcısına bir Test denetleyicisi bağlama
 Bir test aracınızı ayarlamaya çalıştığınızda, şu hatayı alabilirsiniz:

 **Hata 8110. Belirtilen denetleyici bilgisayara bağlantı kurulamadı veya denetleyicisi nesneye erişim.**

 Birden fazla ağ bağdaştırıcısı olan bir bilgisayarda test denetleyicisi yükleyerek bu hataya neden.

> [!NOTE]
>  Test aracıları başarıyla yüklemek ve test çalıştırma çalışana kadar bu sorunu karşılaşmamanız da mümkündür.

 Bu hatayı düzeltmek için test denetleyicisi ağ bağdaştırıcılarından birine bağlamanız gerekir. Ayarlamak sahip `BindTo` özelliği test denetleyicisi ve test aracısı başvurmak için değiştirin test denetleyicisi tarafından IP adresi yerine ada göre. Aşağıdaki yordamlardaki adımları sağlanır.

### <a name="to-obtain-the-ip-address-of-the-network-adapter"></a>Ağ bağdaştırıcısının IP adresi elde etmek için

1.  Seçin **Başlat**ve ardından **çalıştırmak**.

     **Çalıştırmak** iletişim kutusu görüntülenir.

2.  Tür `cmd` ve ardından **Tamam**.

     Bir komut istemi açılır.

3.  Türü `ipconfig /all`.

     Ağ bağdaştırıcılarınız için IP adresleri görüntülenir. Denetleyicinizi bağlamak istediğiniz ağ bağdaştırıcısının IP adresini kaydedin.

### <a name="to-bind-a-test-controller-to-a-network-adapter"></a>Bir ağ bağdaştırıcısına bir test denetleyicisi bağlamak için

1.  Test denetleyicisi hizmetini durdurun. Bir komut isteminde `net stop vsttcontroller`.

2.  QTController.exe.config dosyasını açın. Bu dosya, % ProgramFiles(x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE bulunur.

3.  İçin bir giriş eklemek `BindTo` uygulama ayarları için özellik. Denetleyiciyi bağlamak istediğiniz ağ bağdaştırıcısının IP adresi belirtin. Kodunuzu şuna benzemelidir:

    ```xml
    <appSettings>
        <add key="LogSizeLimitInMegs" value="20" />
        <add key="AgentSyncTimeoutInSeconds" value="120" />
        <add key="ControllerServicePort" value="6901" />
        <add key="ControllerUsersGroup" value="TeamTestControllerUsers" />
        <add key="ControllerAdminsGroup" value="TeamTestControllerAdmins" />
        <add key="CreateTraceListener" value="no" />
        <add key="BindTo" value="<YOUR IP ADDRESS>" />
    </appSettings>
    ```

4.  Dosyayı kaydedin.

5.  Test denetleyicisi hizmetini başlatın. Bir komut isteminde `net start vsttcontroller`.

### <a name="to-connect-a-test-agent-to-a-bound-controller"></a>Test aracısı bağlama denetleyicisine bağlanmak için

-   Test aracısı yüklemeyi yeniden çalıştırın. Bu süre, test denetleyicisi adı yerine test denetleyicisi için IP adresi belirtin.

 Bu test denetleyicisi, test aracısı hizmeti ve test aracısı işlemi için geçerlidir. `BindTo` Özelliği, birden fazla ağ bağdaştırıcısı olan bir bilgisayarda çalışan her işlem için ayarlanmalıdır. Ayarlama yordamı `BindTo` özelliktir test denetleyicisi için daha önce belirtildiği gibi tüm üç işlemleri için aynı. Test aracısı hizmeti ve test aracısı işlemi için günlüğe kaydetme düzeyini ayarlamak için listelenen yapılandırma dosyalarını kullanmak [bir Test denetleyicisi bilgisayarında günlüğe kaydetme düzeyini ayarlama](#Logging).

## <a name="see-also"></a>Ayrıca bkz.

- [Test denetleyicileri ve test aracıları](../test/configure-test-agents-and-controllers-for-load-tests.md)