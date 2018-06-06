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
ms.openlocfilehash: 103000c2ded944236762ffd55603877ece7b7968
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34768228"
---
Bu adımlar IIS, yalnızca temel yapılandırmasını gösterir. Daha ayrıntılı bilgi için veya bir Windows Masaüstü makineye yüklemek için bkz: [IIS yayımlama](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration) veya [IIS 8.0 kullanarak ASP.NET 3.5 ve ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45).

Windows Server işletim sistemleri için **rol ve Özellik Ekle** Sihirbazı aracılığıyla **Yönet** bağlantı veya **Pano** bağlamak **Sunucu Yöneticisi'ni**. Üzerinde **sunucu rolleri** adım, onay kutusunu için **Web sunucusu (IIS)**.

![Web sunucusu IIS rolünü sunucu rolleri adımda seçilir.](../media/remotedbg-server-roles-ws2012.png)

Üzerinde **rol hizmetlerini** adım, işlemleriniz veya sağlanan varsayılan rol hizmetlerini kabul IIS rol hizmetlerini seçin. Dağıtım kullanarak etkinleştirmek istiyorsanız, ayarları ve Web dağıtımı yayımlama, olduğundan emin olun **IIS Yönetim betikleri ve araçları** seçilir.

Web sunucusu rolü ve hizmetlerini yüklemek için onay adımlarla devam edin. Web sunucusu (IIS) rolü yüklendikten sonra özelliği sunucu/IIS yeniden başlatma gerekli değildir.