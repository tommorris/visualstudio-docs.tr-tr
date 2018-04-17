---
title: 'Hatası: Hiçbir kimlik doğrulama güvenlik duvarı | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.firewall.noauth
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6a6a15196445555e883ebc76541f486d7de454b8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="error-firewall-no-authentication"></a>Hata: Güvenlik Duvarı Kimlik Doğrulaması Yok
Internet Bağlantısı Güvenlik Duvarı uzak makinesinde uzaktan hata ayıklama izin verecek şekilde ayarlanır değil. İle uzaktan hata ayıklama için `No Authentication`, msvsmon.exe özel durumlar listesine eklenmelidir. Bazı IPSec bağlantı noktaları açma de gerekebilir.  
  
> [!NOTE]
>  Uzaktan hata ayıklayıcı otomatik olarak Windows Güvenlik Duvarı'nı yapılandırmanız mümkün olur. Üçüncü taraf güvenlik duvarı yazılımı veya bir donanım güvenlik duvarı gibi Windows Güvenlik Duvarı dışında bir güvenlik duvarı kullanırken, uzaktan hata ayıklama izin vermek için Güvenlik Duvarı'nı el ile yapılandırılması gerekir. Bunu yapmak için bu msvsmon.exe TCP/IP bağlantı noktalarında trafiğe izin dinlemede. Varsayılan olarak, bu, bağlantı noktası 4018 ve burada 4018 tüm işletim sistemlerinde kullanılır ve 4019 yalnızca Windows x64 x86 hata ayıklama izin vermek için kullanılan 4019 işlemlerdir.  
  
 Daha fazla bilgi için bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md).