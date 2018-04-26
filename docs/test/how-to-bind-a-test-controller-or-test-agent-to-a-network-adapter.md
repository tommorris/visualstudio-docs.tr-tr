---
title: Visual Studio'da bir ağ bağdaştırıcısına bir Test denetleyicisi veya Test aracısı bağlama
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- controllers, netwrok adapter
- agents, configuring
- agents, network adapter
- controllers, configuring
ms.assetid: 7eb9290a-f9f6-4e41-9caa-796fcfaf0610
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 051b7c7375c6b13a6f3805e358645eccdc0e33c3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-bind-a-test-controller-or-test-agent-to-a-network-adapter"></a>Nasıl yapılır: bir ağ bağdaştırıcısına bir test denetleyicisi veya test aracısı bağlama

Test denetleyicisi veya test aracısı yazılımı yüklü olduğu bir bilgisayara birden çok ağ bağdaştırıcısı varsa, bu test denetleyicisi veya test aracısı belirlemek için bilgisayar adı yerine IP adresi belirtmeniz gerekir.

> [!WARNING]
> Bir test aracınızı ayarlamaya çalıştığınızda, şu hatayı alabilirsiniz:
>
> **Hata 8110. Belirtilen denetleyici bilgisayara bağlantı kurulamadı veya denetleyicisi nesneye erişim**
>
> Birden fazla ağ bağdaştırıcısı olan bir bilgisayarda test denetleyicisi yükleyerek bu hataya neden. Aracıları başarıyla yüklemek ve test çalıştırma çalışana kadar bu sorunu karşılaşmamanız da mümkündür.

## <a name="binding-a-test-controller-to-a-specific-network-adapter"></a>Belirli bir ağ bağdaştırıcısı için bir Test denetleyicisi bağlama

### <a name="to-obtain-the-ip-addresses-of-the-network-adapters"></a>Ağ bağdaştırıcılarının IP adreslerini almak için

1.  Microsoft Windows'dan seçin **Başlat**, seçin **Aramaya Başla** kutusuna **cmd**ve ardından **Enter**.

2.  Tür **ipconfig/all**.

     Ağ bağdaştırıcılarınız için IP adresleri görüntülenir. Denetleyicinizi bağlamak istediğiniz ağ bağdaştırıcısının IP adresini kaydedin.

### <a name="to-bind-a-network-adapter-to-a-test-controller"></a>Bir ağ bağdaştırıcısı için bir Test denetleyicisi bağlamak için

1.  Microsoft Windows'dan seçin **Başlat**, seçin **Aramaya Başla** kutusuna **services.msc**ve ardından **Enter**.

     **Hizmetleri** iletişim kutusu görüntülenir.

2.  Sonuçlar bölmesinde altında **adı** sütun, sağ **Visual Studio Test denetleyicisi** hizmet ve ardından **durdurmak**.

     -veya-

     Yükseltilmiş bir komut istemi açın ve komut istemine aşağıdaki komutu çalıştırın:

     `net stop vsttcontroller`

3.  Açık *QTCcontroller.exe.config* bulunan XML yapılandırma dosyasını *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\\<edition>\Common7\IDE*.

4.  bulun `<appSettings>` etiketi.

    ```xml
    <appSettings>
      <add key="LogSizeLimitInMegs" value="20"/>
      <add key="AgentConnectionTimeoutInSeconds" value="120"/>
      <add key="AgentSyncTimeoutInSeconds" value="300"/>
      <add key="ControllerServicePort" value="6901"/>
      <add key="ControllerUsersGroup" value="TeamTestControllerUsers"/>
      <add key="ControllerAdminsGroup" value="TeamTestControllerAdmins"/>
      <add key="CreateTraceListener" value="no"/>
    </appSettings>
    ```

5.  Ekleme `BindTo` kullanmak için hangi ağ bağdaştırıcısı belirtmek için anahtar `<appSettings>` bölümü.

    ```xml
            <add key="BindTo" value="<YOUR IP ADDRESS>"/>
    </appSettings>
    ```

6.  Test denetleyicisi hizmetini başlatın. Bunu yapmak için bir komut isteminde aşağıdaki komutu çalıştırın:

    `net start vsttcontroller`

    > [!WARNING]
    > Test aracısı denetleyicisine yeniden bağlanmak için test aracısı yüklemesini çalıştırmanız gerekir. Bu süre, denetleyici adı yerine denetleyicisi için IP adresi belirtin.

     Bu denetleyici, aracı hizmetini ve aracı işlemi için geçerlidir. `BindTo` Özelliği, birden fazla ağ bağdaştırıcısı olan bir bilgisayarda çalışan her işlem için ayarlanmalıdır. Ayarlama yordamı `BindTo` özelliktir test denetleyicisi için bu konudaki daha önce belirtildiği gibi tüm üç işlemleri için aynı.

### <a name="to-bind-a-network-interface-card-to-a-test-agent"></a>Test aracısı için bir ağ arabirimi kartı bağlamak için

1.  Microsoft Windows'dan seçin **Başlat**, seçin **Aramaya Başla** kutusuna **services.msc**ve ardından **Enter**.

    **Hizmetleri** iletişim kutusu görüntülenir.

2.  Sonuçlar bölmesinde altında **adı** sütun, sağ **Visual Studio Test aracısı** hizmet ve ardından **durdurmak**.

     -veya-

     Yükseltilmiş bir komut istemi açın ve komut istemine aşağıdaki komutu çalıştırın:

     **net stop vsttagent**

3.  Açık *QTAgentService.exe.config* bulunan XML yapılandırma dosyasını *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\\<edition>\Common7\IDE*.

4.  bulun `<appSettings>` etiketi.

    ```xml
    <appSettings>
      <appSettings>
      <add key="LogSizeLimitInMegs" value="20"/>
      <add key="AgentServicePort" value="6910"/>
      <add key="ControllerConnectionPeriodInSeconds" value="30"/>
      <add key="StopTestRunCallTimeoutInSeconds" value="120"/>
      <add key="CreateTraceListener" value="no"/>
      <add key="GetCollectorDataTimeout" value="300"/>
    </appSettings>  </appSettings>
    ```

5.  Ekleme `BindTo` kullanmak için hangi ağ bağdaştırıcısı belirtmek için anahtar `<appSettings>` bölümü.

    ```xml
            <add key="BindTo" value="<YOUR IP ADDRESS>"/>
    </appSettings>
    ```

6.  Test aracısı hizmetini başlatın. Bunu yapmak için bir komut isteminde aşağıdaki komutu çalıştırın:

    `net start vsttagent`

## <a name="see-also"></a>Ayrıca bkz.

- [Test aracılarını yükleme ve yapılandırma](../test/lab-management/install-configure-test-agents.md)
- [Yük testi günlük oluşturma ayarlarını değiştirme](../test/modify-load-test-logging-settings.md)
- [Test denetleyicileri ve Test aracıları için bağlantı noktalarını yapılandırma](../test/configure-ports-for-test-controllers-and-test-agents.md)
- [Nasıl yapılır: günlük dosyası en büyük boyutu belirtin](../test/how-to-specify-the-maximum-size-for-the-log-file.md)
- [Nasıl yapılır: Test denetleyicileri ve Test aracıları için zaman aşımı sürelerini belirtme](../test/how-to-specify-timeout-periods-for-test-controllers-and-test-agents.md)