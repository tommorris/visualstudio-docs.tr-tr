---
title: 'Hata: Güvenlik duvarı kimlik doğrulaması yok | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.firewall.noauth
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: dda1acb8-bed7-4bc8-9991-9cdc49c2ac1e
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dca0d4421cb8b8b5e720ca079547f13ec75e3705
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693135"
---
# <a name="error-firewall-no-authentication"></a>Hata: Güvenlik Duvarı Kimlik Doğrulaması Yok
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata: güvenlik duvarı kimlik doğrulaması yok](https://docs.microsoft.com/visualstudio/debugger/error-firewall-no-authentication).  
  
Internet Bağlantısı Güvenlik Duvarı uzak makinede uzaktan hata ayıklamaya izin verecek şekilde ayarlanır değil. İle uzaktan hata ayıklama `No Authentication`, msvsmon.exe özel durumlar listesine eklenmesi gerekir. Bazı IPSec bağlantı noktaları açma de gerekebilir.  
  
> [!NOTE]
>  Uzaktan hata ayıklayıcıyı otomatik olarak Windows Güvenlik Duvarı'nı yapılandırabilirsiniz. Windows Güvenlik Duvarı gibi üçüncü taraf yazılım güvenlik duvarı veya donanım güvenlik duvarı dışında bir güvenlik duvarı kullanırken, uzaktan hata ayıklama izin vermek için güvenlik duvarını el ile yapılandırılması gerekir. Bunu yapmak için msvsmon.exe'nin TCP/IP bağlantı noktalarında trafiğe izin dinlediği. Varsayılan olarak, bu, bağlantı noktası 4018 ve burada 4018 tüm işletim sistemlerinde kullanılır ve 4019 yalnızca Windows üzerinde x64 x86 hata ayıklamaya izin verecek şekilde kullanılan 4019 işlemlerdir.  
  
 Daha fazla bilgi için [ayarlanmış yukarı uzak Araçlar cihazda](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c).



