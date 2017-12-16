---
title: "Kaynak sunucu güvenlik uyarısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.sourceserver.enablewarning
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 8451c281-6914-469c-b80c-6271cc3f3d17
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cb65652840162be697abe535003de132c0ad55ea
ms.sourcegitcommit: 1e08318a8a684b21609af7a5e48b56abcc3239e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/13/2017
---
# <a name="source-server-security-alert"></a>Kaynak Sunucu Güvenlik Uyarısı
Kaynak sunucu kullanırken, yalnızca bilinen ve güvenli bir konumdan simge dosyaları kullanın.  
  
 Kaynak sunucu desteği etkinleştirdiğinizde, bu uyarı görüntülenir. Kaynak sunucu komutları hata ayıklama simge dosyaları ekli (***.pdb** dosyaları). PDB dosyaları alınacağı yeri bildiğinizden emin olun.  
  
> [!IMPORTANT]
>  Kaynak sunucu kullanırken dikkate aşağıdaki olası güvenlik tehditlerini izlenmelidir: rasgele komutları uygulamanın PDB dosyasında katıştırılmış, bu nedenle srcsrv.ini dosyasında yürütmek için yalnızca istediklerinizi yerleştirdiğiniz emin olun. srcsvr.ini dosyasında olmayan bir komutu yürütme girişimi, bir onay iletişim kutusunun görüntülenmesine neden olur. Daha fazla bilgi için bkz: [güvenlik uyarısı: hata ayıklayıcı gerekir yürütme güvenilmeyen komut](../debugger/security-warning-debugger-must-execute-untrusted-command.md). Komut parametrelerinde bir doğrulama yapılmadı, bu nedenle güvenilir komutlara dikkat edin. Örneğin, cmd.exe'ye güvendiyseniz, kötü niyetli bir kullanıcı, komutu tehlikeli duruma getirecek parametreler belirtebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Simge (.pdb) belirtin ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)   
 [Kaynak sunucusu](http://msdn.microsoft.com/library/windows/desktop/ms680641.aspx)
