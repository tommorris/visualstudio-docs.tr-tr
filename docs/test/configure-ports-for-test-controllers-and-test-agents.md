---
title: "Test denetleyicileri ve Test aracılarını Visual Studio için bağlantı noktalarını yapılandırma | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- firewalls, configuring for test agents
- firewalls, configuring for test controllers
- test agents, firewalls
- test controllers, firewalls
- agents, firewalls
- controllers, firewalls
ms.assetid: 211edbd7-9fe4-4251-ba85-8bec4363261b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 079a4d588109dba4b95710ed816fba4177f41854
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="configure-ports-for-test-controllers-and-test-agents"></a>Test denetleyicileri ve Test aracıları için bağlantı noktalarını yapılandırma

Test denetleyicisi, test aracısı ve istemci tarafından kullanılan varsayılan gelen bağlantı noktalarını değiştirebilirsiniz. Test denetleyicisi, test aracısı veya başka bir yazılım ile birlikte istemci çakışan bağlantı noktası ayarlarıyla kullanmak çalışıyorsanız gerekli olabilir. Bağlantı noktalarını değiştirmek için başka bir test denetleyicisi ve istemci arasındaki güvenlik duvarı kısıtlama nedeniyle nedenidir. Bu durumda el ile test denetleyicisi sonuçları istemciye gönderebilmesi için bir güvenlik duvarını etkinleştirme uyum sağlamak için bağlantı noktası yapılandırmak isteyebilirsiniz.

 Aşağıdaki çizimde test denetleyicisi, test aracısı ile istemci arasındaki bağlantı noktalarını gösterir. Bu, bu bağlantı noktalarına kullanılan güvenlik kısıtlamaları yanı sıra gelen ve giden bağlantılar için hangi bağlantı noktalarının kullanılacağını açıklar.

 ![Contoller ve test aracısı bağlantı noktaları ve güvenlik](../test/media/test-controller-agent-firewall.png)

## <a name="incoming-connections"></a>Gelen bağlantıları

Test denetleyicisi tarafından kullanılan varsayılan bağlantı noktası 6901 ve test aracısının varsayılan bağlantı noktası 6910. İstemci, test denetleyicisinden test sonuçları almak için kullanılan varsayılan olarak bir rastgele bağlantı noktası kullanır. Tüm gelen bağlantıları için test denetleyicisi çağıran tarafın ve belirli güvenlik grubuna ait olduğunu doğrular.

- **Test denetleyicisi** gelen bağlantılar, TCP bağlantı noktası 6901 gerçekleştirilir. Gerekiyorsa, gelen bağlantı noktası yapılandırabilirsiniz. Daha fazla bilgi için bkz: [gelen bağlantı noktalarını yapılandırma](#ConfigurePorts).

    Test aracıları için giden bağlantı kurmak test denetleyicisi gerekir ve istemciye.

    > [!NOTE]
    > Test denetleyicisi gelen gereken **dosya ve Yazıcı Paylaşımı** bağlantı açık.

- **Test aracısı** gelen bağlantılar, TCP bağlantı noktası 6910 gerçekleştirilir. Gerekiyorsa, gelen bağlantı noktası yapılandırabilirsiniz. Daha fazla bilgi için bkz: [gelen bağlantı noktalarını yapılandırma](#ConfigurePorts).

   Test aracısı test denetleyicisine giden bağlantı olması gerekir.

- **İstemci** varsayılan olarak, gelen bağlantılar için rastgele bir TCP bağlantı noktası kullanılır. Gerekiyorsa, gelen bağlantı noktası yapılandırabilirsiniz. Daha fazla bilgi için bkz: [gelen bağlantı noktalarını yapılandırma](#ConfigurePorts).

   Test denetleyicisi istemci ilk kez bağlanmaya çalıştığında güvenlik duvarı bildirimleri alabilirsiniz.

   Windows Server 2008 üzerinde güvenlik duvarı bildirimleri varsayılan olarak devre dışıdır ve gelen bağlantıları kabul edebilmesi için istemci programları (devenv.exe, mstest.exe, mlm.exe) güvenlik duvarı özel durumlarını el ile eklemeniz gerekir.

## <a name="outgoing-connections"></a>Giden bağlantılar

Rastgele TCP bağlantı noktaları tüm giden bağlantılar için kullanılır.

- **Test denetleyicisi** giden aracıları ve istemci bağlantısı test denetleyicisi gerekir.

- **Test aracısı** denetleyicisine giden bağlantı kurmayı test aracısı gerekir.

- **İstemci** denetleyicisine giden bağlantı kurmayı istemci gerekir.

## <a name="configure-the-incoming-ports"></a>Gelen bağlantı noktalarını yapılandırma

Bir test denetleyicisi için bağlantı noktalarını yapılandırmak ve test aracıları için bu yönergeleri izleyin.

- **Denetleyici Hizmeti** % ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\QTCcontroller.exe.config dosyasını düzenleyerek bağlantı noktasının değerini değiştirin:

    ```xml
    <appSettings>
      <add key="ControllerServicePort" value="6901"/>
    </appSettings>
    ```

- **Aracı hizmeti** % ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\QTAgentService.exe.config dosyasını düzenleyerek bağlantı noktasını değiştirin:

    ```xml
    <appSettings>
      <add key="AgentServicePort" value="6910"/>
    </appSettings>
    ```

- **İstemci** aşağıdaki kayıt defteri (DWORD) değerlerini eklemek için Kayıt Defteri Düzenleyicisi'ni kullanın. Test denetleyicisinden veri almak için istemci belirtilen aralık bağlantı noktalarından birini kullanır:

     HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\VisualStudio\12.0\EnterpriseTools\QualityTools\ListenPortRange\PortRangeStart

     HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\VisualStudio\12.0\EnterpriseTools\QualityTools\ListenPortRange\PortRangeEnd

## <a name="see-also"></a>Ayrıca bkz.

- [Test aracılarını yükleme ve yapılandırma](../test/lab-management/install-configure-test-agents.md)