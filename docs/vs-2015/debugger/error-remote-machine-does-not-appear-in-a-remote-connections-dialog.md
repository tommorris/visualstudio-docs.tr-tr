---
title: 'Hata: Uzak makine, Uzaktan bağlantılar iletişim kutusunda görünmüyor | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 5fd98a5b-2cf3-4438-8b0f-6f1a742a62ce
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 552be1e38cdb7401af36b287b23091d754c35980
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695325"
---
# <a name="error-remote-machine-does-not-appear-in-a-remote-connections-dialog"></a>Hata: Uzak makine, Uzaktan bağlantılar iletişim kutusunda görünmüyor
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata: uzak makine, Uzaktan bağlantılar iletişim kutusunda görünmez](https://docs.microsoft.com/visualstudio/debugger/error-remote-machine-does-not-appear-in-a-remote-connections-dialog).  
  
Uzak makinede uzaktan bağlantılar iletişim kutusunda görüntülenmezse, aşağıdaki yaygın nedenleri kontrol edin.  
  
 Yönetilen Uyumluluk modunu kullanıyorsanız, Lütfen Visual Studio 2010 belgeleri denetleyin: [sorun giderme uzaktan hata ayıklama - Visual Studio 2010](https://msdn.microsoft.com/library/2ys11ead\(v=vs.100\).aspx) .  
  
### <a name="common-causes-for-this-error"></a>Bu hata için olası nedenler  
  
-   Uzak makine, farklı bir alt ağda bir makinede çalışıyor. Bu sorunu gidermek için el ile makine adı veya IP adresini niteleyicisi iletişim kutusunda yazın  
  
-   Uzaktan hata ayıklayıcı uzak makinede çalışmıyor. Bu sorunu gidermek için uzaktan hata ayıklayıcıyı başlatın.  
  
-   Güvenlik Duvarı, Visual Studio uzak makineye arasındaki iletişimi engelliyor. Bu sorunu gidermek için Visual Studio ve uzaktan hata ayıklayıcı (msvsmon) iletişim kurmasına izin vermek için güvenlik duvarını yapılandırın.  
  
-   Virüsten koruma yazılımı Visual Studio uzak makineye arasındaki iletişimi engelliyor. Bu sorunu gidermek için virüsten koruma yazılımı Visual Studio ve uzaktan hata ayıklayıcı (msvsmon) iletişim kurmasına izin verecek şekilde yapılandırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cihazda uzak araçları ayarlama](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)



