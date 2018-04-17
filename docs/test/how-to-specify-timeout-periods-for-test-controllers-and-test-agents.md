---
title: Test denetleyicileri ve Visual Studio Test aracıları için zaman aşımı sürelerini | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- agents, configuring
- agetns, timeouts
- controllers, configuring
- controllers, timeouts
ms.assetid: 777d0db5-0073-458a-a2a3-58b1c1f24c60
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 067dee39ade864cd0e0211ed8fd27d8f8fd3d9c5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-specify-timeout-periods-for-test-controllers-and-test-agents"></a>Nasıl yapılır: Test denetleyicileri ve Test Aracıları için Zaman Aşımı Sürelerini Belirtme

Test denetleyicisi ve test aracısı ne kadar bunlar birbirinden ya da bir hata ile başarısız olmadan önce bir veri kaynağından yanıtlar için beklemesi gerektiğini belirten birkaç zaman aşımı ayarları vardır. Belirli koşullar altında topolojinizin ya da diğer ortam sorunlarını ihtiyaçlarını karşılamak için zaman aşımı değerlerini düzenlemek gerekli olabilir. Zaman aşımı değerlerini düzenlemek için aşağıdaki yordamlarda anlatıldığı gibi test denetleyicisi veya test aracısı ile ilişkili XML yapılandırma dosyasını düzenleyin.

 Bir test denetleyicisi veya test aracısının çeşitli zaman aşımı ayarlarını düzenlemek için anahtar adlarını ve değerlerini tablolarda kullanarak aşağıdaki yapılandırma dosyalarını değiştirin:

-   Test denetleyicisi: QTController.exe.config

    |Anahtar adı|Açıklama|Değer|
    |--------------|-----------------|-----------|
    |AgentConnectionTimeoutInSeconds|Aracının ping isteği için bağlantı olarak kabul edilmeden önce beklenecek saniye sayısını kesildi.|"n" saniye sayısı.|
    |AgentSyncTimeoutInSeconds|Ne zaman, eşitleme testi Çalıştır iptal etmeden önce eşitlemek tüm aracılar için beklenecek saniye sayısını başlatın.|"n" saniye sayısı.|
    |AgentInitializeTimeout|Test çalışmasını iptal etmeden önce bir test başında başlatmak için kendi veri toplayıcıları ve tüm aracılar için beklenecek saniye sayısı çalıştırın. Bu değer veri toplayıcıları kullanıyorsanız makul büyük olmalıdır.|"n" saniye sayısı. Varsayılan: "120" (iki dakika).|
    |AgentCleanupTimeout|Test tamamlanmadan önce temizlemek için kendi veri toplayıcıları ve tüm aracılar için beklenecek saniye sayısı çalıştırın. Bu değer veri toplayıcıları kullanıyorsanız makul büyük olmalıdır.|"n" saniye sayısı. Varsayılan: "120" (iki dakika).|

-   Test aracısı: QTAgentService.exe.config

    |Anahtar adı|Açıklama|Değer|
    |--------------|-----------------|-----------|
    |ControllerConnectionPeriodInSeconds|Denetleyicisine bağlanmak için girişimleri arasındaki saniye sayısı.|"n" saniye sayısı. Varsayılan: "30" (30 saniye).|
    |RemotingTimeoutSeconds|En uzun süreyi saniye cinsinden uzaktan iletişim çağrısı sürebilir.|"n" saniye sayısı. Varsayılan: "600" (on dakika).|
    |StopTestRunCallTimeoutInSeconds|Testi durdurma çağrısı için beklenecek saniye sayısını çalıştırın.|"n" saniye sayısı. Varsayılan: "120" (iki dakika).|
    |GetCollectorDataTimeout|Veri Toplayıcı için beklenecek saniye sayısı.|"n" saniye sayısı. Varsayılan: "300" (beş dakika).|

## <a name="to-specify-agent-timeout-options-for-a-test-controller"></a>Bir Test denetleyicisi Aracısı zaman aşımı seçeneklerini belirtmek için

1. % ProgramFiles(x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE bulunan QTCcontroller.exe.config XML yapılandırma dosyasını açın.

2. bulun `<appSettings>` etiketi.

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

3. Test denetleyicinin zaman aşımı anahtarlarından biri için var olan bir değeri düzenleyin. Örneğin, anahtar için varsayılan değeri değiştirebilirsiniz `AgentConnectionTimeoutInSeconds` üç dakika için iki dakika:

    ```xml
    <add key="AgentConnectionTimeoutInSeconds" value="180"/>
    ```

    -veya-

    İlave bir anahtar ekleyin ve bir zaman aşımı değeri belirtin. Örneğin, ekleyebileceğiniz `AgentInitializeTimeout` anahtarını `<appSettings>` bölümünde ve beş dakika değerini belirtin:

    ```xml
    <appSettings>
            <add key="AgentInitializeTimeout" value="300"/>
    </appSettings>
    ```

## <a name="to-specify-agent-timeout-options-for-a-test-agent"></a>Test aracısı Aracısı zaman aşımı seçeneklerini belirtmek için

1. % ProgramFiles(x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE bulunan QTAgentService.exe.config XML yapılandırma dosyasını açın.

2. bulun `<appSettings>` etiketi.

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

3. Test aracısının zaman aşımı anahtarlarından biri için var olan bir değeri düzenleyin. Örneğin, anahtar için varsayılan değeri değiştirebilirsiniz `ControllerConnectionPeriodInSeconds` bir dakika otuz dakikadan:

    ```xml
    <add key="ControllerConnectionPeriodInSeconds" value="60"/>
    ```

    -veya-

    İlave bir anahtar ekleyin ve bir zaman aşımı değeri belirtin. Örneğin, ekleyebileceğiniz `RemotingTimeoutSeconds` anahtarını `<appSettings>` bölümünde ve on beş dakikalık bir değer belirtin:

    ```xml
    <appSettings>
            <add key=" RemotingTimeoutSeconds " value="900"/>
    </appSettings>
    ```

## <a name="see-also"></a>Ayrıca bkz.

- [Test aracılarını yükleme ve yapılandırma](../test/lab-management/install-configure-test-agents.md)
- [Yük testi günlük oluşturma ayarlarını değiştirme](../test/modify-load-test-logging-settings.md)
- [Test denetleyicileri ve Test aracıları için bağlantı noktalarını yapılandırma](../test/configure-ports-for-test-controllers-and-test-agents.md)
- [Nasıl yapılır: günlük dosyası en büyük boyutu belirtin](../test/how-to-specify-the-maximum-size-for-the-log-file.md)
- [Nasıl yapılır: bir ağ bağdaştırıcısına bir Test denetleyicisi veya Test aracısı bağlama](../test/how-to-bind-a-test-controller-or-test-agent-to-a-network-adapter.md)