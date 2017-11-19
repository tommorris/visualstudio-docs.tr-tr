---
title: "Hatası: Hiçbir kimlik doğrulama güvenlik duvarı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.firewall.noauth
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: dda1acb8-bed7-4bc8-9991-9cdc49c2ac1e
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1750c0ab8bafe53136d01ba27ada9c242b318c3a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="error-firewall-no-authentication"></a>Hata: Güvenlik Duvarı Kimlik Doğrulaması Yok
Internet Bağlantısı Güvenlik Duvarı uzak makinesinde uzaktan hata ayıklama izin verecek şekilde ayarlanır değil. İle uzaktan hata ayıklama için `No Authentication`, msvsmon.exe özel durumlar listesine eklenmelidir. Bazı IPSec bağlantı noktaları açma de gerekebilir.  
  
> [!NOTE]
>  Uzaktan hata ayıklayıcı otomatik olarak Windows Güvenlik Duvarı'nı yapılandırmanız mümkün olur. Üçüncü taraf güvenlik duvarı yazılımı veya bir donanım güvenlik duvarı gibi Windows Güvenlik Duvarı dışında bir güvenlik duvarı kullanırken, uzaktan hata ayıklama izin vermek için Güvenlik Duvarı'nı el ile yapılandırılması gerekir. Bunu yapmak için bu msvsmon.exe TCP/IP bağlantı noktalarında trafiğe izin dinlemede. Varsayılan olarak, bu, bağlantı noktası 4018 ve burada 4018 tüm işletim sistemlerinde kullanılır ve 4019 yalnızca Windows x64 x86 hata ayıklama izin vermek için kullanılan 4019 işlemlerdir.  
  
 Daha fazla bilgi için bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md).