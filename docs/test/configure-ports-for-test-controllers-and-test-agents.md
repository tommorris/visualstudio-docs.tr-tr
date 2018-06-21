---
title: Test denetleyicileri ve Test aracılarını Visual Studio için bağlantı noktalarını yapılandırma
ms.date: 10/19/2016
ms.topic: conceptual
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
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 9f41e372f6c75e10ebf4d66fcd68eb4652b02f0f
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36296297"
---
# <a name="configure-ports-for-test-controllers-and-test-agents"></a>Test denetleyicileri için bağlantı noktalarını yapılandırın ve test aracıları

Test denetleyicisi, test aracısı ve istemci tarafından kullanılan varsayılan gelen bağlantı noktalarını değiştirebilirsiniz. Test denetleyicisi, test aracısı veya başka bir yazılım ile birlikte istemci çakışan bağlantı noktası ayarlarıyla kullanmak çalışıyorsanız gerekli olabilir. Bağlantı noktalarını değiştirmek için başka bir test denetleyicisi ve istemci arasındaki güvenlik duvarı kısıtlama nedeniyle nedenidir. Bu durumda el ile test denetleyicisi sonuçları istemciye gönderebilmesi için bir güvenlik duvarını etkinleştirme uyum sağlamak için bağlantı noktası yapılandırmak isteyebilirsiniz.

 Aşağıdaki çizimde test denetleyicisi, test aracısı ile istemci arasındaki bağlantı noktalarını gösterir. Bu, bu bağlantı noktalarına kullanılan güvenlik kısıtlamaları yanı sıra gelen ve giden bağlantılar için hangi bağlantı noktalarının kullanılacağını açıklar.

 ![Contoller ve test aracısı bağlantı noktaları ve güvenlik](../test/media/test-controller-agent-firewall.png)

## <a name="incoming-connections"></a>Gelen bağlantıları

Test denetleyicisi tarafından kullanılan varsayılan bağlantı noktası 6901 ve test aracısının varsayılan bağlantı noktası 6910. İstemci, test denetleyicisinden test sonuçları almak için kullanılan varsayılan olarak bir rastgele bağlantı noktası kullanır. Tüm gelen bağlantıları için test denetleyicisi çağıran tarafın ve belirli güvenlik grubuna ait olduğunu doğrular.

- **Test denetleyicisi** gelen bağlantılar, TCP bağlantı noktası 6901 gerçekleştirilir. Gerekiyorsa, gelen bağlantı noktası yapılandırabilirsiniz. Daha fazla bilgi için bkz: [gelen bağlantı noktalarını yapılandırma](#configure-the-incoming-ports).

    Test aracıları için giden bağlantı kurmak test denetleyicisi gerekir ve istemciye.

    > [!NOTE]
    > Test denetleyicisi gelen gereken **dosya ve Yazıcı Paylaşımı** bağlantı açık.

- **Test aracısı** gelen bağlantılar, TCP bağlantı noktası 6910 gerçekleştirilir. Gerekiyorsa, gelen bağlantı noktası yapılandırabilirsiniz. Daha fazla bilgi için bkz: [gelen bağlantı noktalarını yapılandırma](#configure-the-incoming-ports).

   Test aracısı test denetleyicisine giden bağlantı olması gerekir.

- **İstemci** varsayılan olarak, gelen bağlantılar için rastgele bir TCP bağlantı noktası kullanılır. Gerekiyorsa, gelen bağlantı noktası yapılandırabilirsiniz. Daha fazla bilgi için bkz: [gelen bağlantı noktalarını yapılandırma](#configure-the-incoming-ports).

   Test denetleyicisi istemci ilk kez bağlanmaya çalıştığında güvenlik duvarı bildirimleri alabilirsiniz.

   Windows Server 2008'de güvenlik duvarı bildirimleri varsayılan olarak devre dışıdır ve istemci programları için güvenlik duvarı özel durumlarını el ile eklemeniz gerekir (*devenv.exe*, *mstest.exe*, *mlm.exe*) gelen bağlantıları kabul edebilmesi için.

## <a name="outgoing-connections"></a>Giden bağlantılar

Rastgele TCP bağlantı noktaları tüm giden bağlantılar için kullanılır.

- **Test denetleyicisi** giden aracıları ve istemci bağlantısı test denetleyicisi gerekir.

- **Test aracısı** denetleyicisine giden bağlantı kurmayı test aracısı gerekir.

- **İstemci** denetleyicisine giden bağlantı kurmayı istemci gerekir.

## <a name="configure-the-incoming-ports"></a>Gelen bağlantı noktalarını yapılandırın

Bir test denetleyicisi için bağlantı noktalarını yapılandırmak ve test aracıları için bu yönergeleri izleyin.

- **Denetleyici Hizmeti** düzenleyerek bağlantı noktasının değerini değiştirip *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\QTCcontroller.exe.config* dosyası:

    ```xml
    <appSettings>
      <add key="ControllerServicePort" value="6901"/>
    </appSettings>
    ```

- **Aracı hizmeti** düzenleyerek bağlantı noktasını Değiştir *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\QTAgentService.exe.config* dosyası:

    ```xml
    <appSettings>
      <add key="AgentServicePort" value="6910"/>
    </appSettings>
    ```

- **İstemci** aşağıdaki kayıt defteri eklemek için Kayıt Defteri Düzenleyicisi'ni kullanın (**DWORD**) değerleri. Test denetleyicisinden veri almak için istemci belirtilen aralık bağlantı noktalarından birini kullanır:

     **HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\VisualStudio\12.0\EnterpriseTools\QualityTools\ListenPortRange\PortRangeStart**

     **HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\VisualStudio\12.0\EnterpriseTools\QualityTools\ListenPortRange\PortRangeEnd**

## <a name="see-also"></a>Ayrıca bkz.

- [Test aracılarını yükleme ve yapılandırma](../test/lab-management/install-configure-test-agents.md)