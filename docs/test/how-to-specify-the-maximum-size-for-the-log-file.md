---
title: Visual Studio Yük testleri için günlük dosyası boyutu
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, logging
ms.assetid: 417059bf-37ae-4e7a-b9b0-29bd71f1414f
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 7faf5402f495eefe64000c67048bcb85c9197388
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31965092"
---
# <a name="how-to-specify-the-maximum-size-for-the-log-file-for-load-tests"></a>Nasıl yapılır: yük testleri için günlük dosyası en büyük boyutu belirtin

Varsayılan olarak, yük testleri için kullanılan günlük dosyası en büyük boyutunu 20 megabayt ayarlanır. Denetleyici hizmetiyle ilişkilendirilmiş yapılandırma dosyasını düzenleyerek bu değeri değiştirebilirsiniz.

## <a name="specify-the-maximum-log-file-size-for-load-test"></a>Yük testi için maksimum günlük dosyası boyutu belirtin

1.  Açık *QTCcontroller.exe.config* % ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\QTCcontroller.exe.config bulunan XML yapılandırma dosyası.

2.  Bulun `<add key="LogSizeLimitInMegs" value="20"/>` altında girdisi `<appSettings>` etiketi.

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

3.  Değiştirme `value ="20"` günlük dosyası için belirtmek istediğiniz maksimum izin verilen boyutu.

    > [!NOTE]
    > "0" değerinin girilmesi boyutu kullanılabilir disk alanı tarafından günlük dosyası yalnızca sınırlı olduğunu belirtir.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi günlük oluşturma ayarlarını değiştirme](../test/modify-load-test-logging-settings.md)
- [Test denetleyicileri ve Test aracıları için bağlantı noktalarını yapılandırma](../test/configure-ports-for-test-controllers-and-test-agents.md)