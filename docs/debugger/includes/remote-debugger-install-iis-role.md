---
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.openlocfilehash: 103cefa8573c8f44efff0b53b0c09a5ec26706e6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
Bu adımlar IIS, yalnızca temel yapılandırmasını gösterir. Daha ayrıntılı bilgi için veya bir Windows Masaüstü makineye yüklemek için bkz: [IIS yayımlama](https://docs.microsoft.com/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration) veya [IIS 8.0 kullanarak ASP.NET 3.5 ve ASP.NET 4.5](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45).

Windows Server işletim sistemleri için **rol ve Özellik Ekle** Sihirbazı aracılığıyla **Yönet** bağlantı veya **Pano** bağlamak **Sunucu Yöneticisi'ni**. Üzerinde **sunucu rolleri** adım, onay kutusunu için **Web sunucusu (IIS)**.

![Web sunucusu IIS rolünü sunucu rolleri adımda seçilir.](../media/remotedbg-server-roles-ws2012.png)

Üzerinde **rol hizmetlerini** adım, işlemleriniz veya sağlanan varsayılan rol hizmetlerini kabul IIS rol hizmetlerini seçin.

Web sunucusu rolü ve hizmetlerini yüklemek için onay adımlarla devam edin. Web sunucusu (IIS) rolü yüklendikten sonra özelliği sunucu/IIS yeniden başlatma gerekli değildir.