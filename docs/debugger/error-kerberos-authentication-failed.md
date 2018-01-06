---
title: "Hata: Kerberos kimlik doğrulaması başarısız oldu. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.error.callback_kerberos_auth_failed
dev_langs:
- CSharp
- VB
- FSharp
- C++
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5c34b15d1611eaad106f3843070620af4470bc04
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="error-kerberos-authentication-failed"></a>Hata: Kerberos Kimlik Doğrulaması Başarısız
Uzaktan hata ayıklama yapın denediğinizde aşağıdaki hata iletisini alabilirsiniz:  
  
```  
Error: The Visual Studio Remote Debugger on the target computer cannot connect back to this computer. Kerberos authentication failed.  
```  
  
 Visual Studio uzaktan hata ayıklama İzleyicisi yerel sistem veya ağ hizmeti hesabı altında çalışıyorsa, bu hata oluşur. Bu hesaplardan birini altında uzaktan hata ayıklayıcı geri Visual Studio hata ayıklayıcısı ana bilgisayara iletişim kurmak için Kerberos kimlik doğrulaması bağlantı oluşturmanız gerekir.  
  
 Kerberos kimlik doğrulaması Bu koşullar altında kullanılabilir değil:  
  
-   Hedef bilgisayar ya da hata ayıklayıcı ana bilgisayar bir etki alanı yerine bir çalışma grubunda olan  
  
     \-veya -  
  
-   Kerberos etki alanı denetleyicisinde devre dışı bırakıldı.  
  
 Kerberos kimlik doğrulaması kullanılabilir durumda değilse, Visual Studio uzaktan hata ayıklama İzleyicisi çalıştırmak için kullanılan hesabı değiştirin. Yordamı için bkz: [hata: hedef bilgisayardaki Visual Studio uzaktan hata ayıklayıcı hizmeti geriye bu bilgisayara bağlanamıyor](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md).  
  
 Her iki bilgisayar aynı etki alanına bağlı ve bu iletiyi almaya devam, hedef bilgisayarda DNS hata ayıklayıcı ana bilgisayar adı doğru biçimde çözümleyemiyor doğrulayın. Aşağıdaki yordama bakın.  
  
### <a name="to-verify-that-dns-on-the-target-computer-is-correctly-resolving-the-debugger-host-computer-name"></a>Hedef bilgisayarda DNS hata ayıklayıcı ana bilgisayar adı doğru biçimde çözümleyemiyor doğrulamak için  
  
1.  Hedef bilgisayarda açın **Başlat** menüsündeki **Donatılar** ve ardından **komut istemi**.  
  
2.  İçinde **komut istemi** penceresinde, türü:  
  
    ```  
    ping <debugger_host_computer_name>  
    ```  
  
3.  İlk satırı `ping` tam bilgisayar adı ve IP adresi belirtilen bilgisayar için DNS tarafından döndürülen yanıt gösterir.  
  
4.  Hata ayıklayıcı ana bilgisayarda açık bir **komut istemi** penceresini açın ve Çalıştır `ipconfig`.  
  
5.  IP adresi değerlerini karşılaştırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)