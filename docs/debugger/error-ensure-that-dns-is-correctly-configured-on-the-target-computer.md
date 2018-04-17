---
title: 'Hata: DNS hedef bilgisayarda doğru yapılandırılmış olduğundan emin olun | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.callback_dns_failed
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
ms.openlocfilehash: 2b2238cd606f748d53c48722d9719bd936550ae1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="error-ensure-that-dns-is-correctly-configured-on-the-target-computer"></a>Hata: DNS'nin Hedef Bilgisayarda Doğru Yapılandırıldığından Emin Olma
Uzaktan hata ayıklama yapmaya çalışırken, aşağıdaki hata iletisini alabilirsiniz:  
  
```  
Error: The Visual Studio Remote Debugger on the target computer cannot connect back to this computer. Ensure that DNS is correctly configured on the target computer.  
```  
  
 Bu ileti, hedef bilgisayar, Visual Studio hata ayıklayıcısı ana bilgisayar adını çözümleyemediğinde oluşur. Hedef bilgisayarda DNS ayarlarını denetleyin.  
  
-   Windows 8.1, Vista, Windows 7, Windows Server 2012, Windows Server 2008 veya Windows Server 2008 R2, DNS ayarınız görüntüleme hakkında bilgi için bunu: üzerinde **Başlat** menüsünde seçin **Yardım ve Destek** , arayın ve sonra **değişiklik TCP/IP ayarları**.  
  
-   Daha fazla bilgi için Git [Microsoft Windows web sitesi](http://go.microsoft.com/fwlink/?LinkId=252720) arayın ve **değişiklik TCP/IP ayarları**.  
  
 DNS sorununu gideremezseniz, farklı bir hesap altında Uzaktan Hata Ayıklayıcı'yı çalıştırmayı deneyebilirsiniz. Bu hata yalnızca Yerel Sistem veya Ağ Hizmeti hesabı altında Uzaktan Hata Ayıklayıcı'yı çalıştırırken oluşur. Uzaktan Haya Ayıklayıcı'yı başka bir hesap altında çalıştırırsanız, DNS gerektirmeyen NTLM kimlik doğrulaması kullanabilir. biçimindeki telefon numarasıdır. Yordamı için bkz: [hata: hedef bilgisayardaki Visual Studio uzaktan hata ayıklayıcı hizmeti geriye bu bilgisayara bağlanamıyor](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md).