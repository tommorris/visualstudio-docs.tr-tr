---
title: 'Hata: Uzak makine uzak bağlantıları iletişim kutusunda görünmüyor | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
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
ms.openlocfilehash: c52a2ebd99b052171220fd8a06f1ae7ff5dc258e
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="error-remote-machine-does-not-appear-in-a-remote-connections-dialog"></a>Hata: Uzak makine uzak bağlantıları iletişim kutusunda görünmüyor
Uzak makine uzak bağlantıları iletişim kutusunda görünmüyorsa, aşağıdaki ortak nedenleri kontrol edin.  
  
 Yönetilen uyumluluk modu kullanıyorsanız, Lütfen Visual Studio 2010 belgelerine bakın: [sorun giderme uzaktan hata ayıklama - Visual Studio 2010](https://msdn.microsoft.com/en-us/library/2ys11ead\(v=vs.100\).aspx) .  
  
### <a name="common-causes-for-this-error"></a>Bu hatanın ortak nedenleri  
  
-   Uzak makinede farklı bir alt ağda bir makinede çalışıyor. Bu sorunu gidermek için el ile makine adı veya IP adresini niteleyicisi iletişim kutusunda yazın  
  
-   Uzaktan hata ayıklayıcı uzak makinede çalışmıyor. Bu sorunu gidermek için uzaktan hata ayıklayıcı başlatın.  
  
-   Güvenlik Duvarı, Visual Studio ile uzak makine arasındaki iletişimi engelliyor. Bu durumu düzeltmek için Visual Studio ve uzaktan hata ayıklayıcı (msvsmon) iletişim kurmasına izin vermek için güvenlik duvarınızı yapılandırma.  
  
-   Virüsten koruma yazılımı Visual Studio ile uzak makine arasındaki iletişimi engelliyor. Bu sorunu gidermek için virüsten koruma yazılımı Visual Studio ve uzaktan hata ayıklayıcı (msvsmon) iletişim kurmasına izin verecek şekilde yapılandırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)