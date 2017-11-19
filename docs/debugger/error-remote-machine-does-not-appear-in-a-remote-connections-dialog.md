---
title: "Hata: Uzak makine uzak bağlantıları iletişim kutusunda görünmüyor | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 5fd98a5b-2cf3-4438-8b0f-6f1a742a62ce
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e0d8c28f2be735ebb1063715e19a6f2cae55753a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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