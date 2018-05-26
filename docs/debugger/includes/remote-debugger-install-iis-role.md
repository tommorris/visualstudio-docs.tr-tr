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
ms.openlocfilehash: 62bdcd8109263cc86e13484d146e46f8e95c7198
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/24/2018
---
Bu adımlar IIS, yalnızca temel yapılandırmasını gösterir. Daha ayrıntılı bilgi için veya bir Windows Masaüstü makineye yüklemek için bkz: [IIS yayımlama](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration) veya [IIS 8.0 kullanarak ASP.NET 3.5 ve ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45).

Windows Server işletim sistemleri için **rol ve Özellik Ekle** Sihirbazı aracılığıyla **Yönet** bağlantı veya **Pano** bağlamak **Sunucu Yöneticisi'ni**. Üzerinde **sunucu rolleri** adım, onay kutusunu için **Web sunucusu (IIS)**.

![Web sunucusu IIS rolünü sunucu rolleri adımda seçilir.](../media/remotedbg-server-roles-ws2012.png)

Üzerinde **rol hizmetlerini** adım, işlemleriniz veya sağlanan varsayılan rol hizmetlerini kabul IIS rol hizmetlerini seçin. Web dağıtımı kullanarak dağıtmayı planlıyorsanız, emin olun **IIS Yönetim betikleri ve araçları** seçilir.

Web sunucusu rolü ve hizmetlerini yüklemek için onay adımlarla devam edin. Web sunucusu (IIS) rolü yüklendikten sonra özelliği sunucu/IIS yeniden başlatma gerekli değildir.