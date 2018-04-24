---
title: 'Hata: Olmayan hata ayıklama&#39;t olası bir çekirdek hata ayıklayıcısı sistemde etkin olduğundan | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.kernel_dbg_enabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- kernel debugger
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ba943057da003a0fafee6d6fb8c6082d228779f9
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="error-debugging-isn39t-possible-because-a-kernel-debugger-is-enabled-on-the-system"></a>Hata: Olmayan hata ayıklama&#39;t olası bir çekirdek hata ayıklayıcısı sistemde etkin olduğundan
Yönetilen kodda hata ayıklarken, aşağıdaki hata iletisini alabilirsiniz:  
  
```  
Debugging isn't possible because a kernel debugger is enabled on the system  
```  
  
 Yönetilen kodda hata ayıklama çalıştığınızda bu ileti oluşur:  
  
-   üzerinde bir [!INCLUDE[win7](../debugger/includes/win7_md.md)] veya [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)]hata ayıklama modunda başlatılan sistem.  
  
-   Uygulama CLR sürüm 2.0, 3.0 veya 3.5 CLR kullanır.  
  
## <a name="solution"></a>Çözüm  
  
#### <a name="to-fix-this-problem"></a>Bu sorunu gidermek için  
  
-   CLR sürüm 4.0 veya 4.5 kullanmak için uygulamanızı yükseltin  
  
     —veya—  
  
-   Çekirdek hata ayıklamasını devre dışı bırakın ve içinde hata ayıklama [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
     —veya—  
  
-   Çekirdek hata ayıklayıcısı yerine kullanarak hata ayıklama [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
     —veya—  
  
-   Çekirdek Hata Ayıklayıcısı'ndaki kullanıcı modu özel durumlarını devre dışı bırakın.  
  
#### <a name="to-disable-kernel-debugging-in-the-current-session"></a>Geçerli oturumda çekirdek hata ayıklamasını devre dışı bırakmak için  
  
-   Komut isteminde, şunları yazın:  
  
    ```  
    Kdbgctrl.exe -d  
    ```  
  
#### <a name="to-disable-kernel-debugging-for-all-sessions-windows-vista-and-windows-7"></a>Tüm oturumları için (Windows Vista ve Windows 7) çekirdek hata ayıklamasını devre dışı bırakmak için  
  
1.  Komut isteminde, şunları yazın:  
  
    ```  
    bcdedit /debug off   
    ```  
  
2.  Bilgisayarı yeniden başlatın.  
  
#### <a name="to-disable-kernel-debugging-for-all-sessions-other-windows-operating-systems"></a>Tüm oturumları (diğer Windows işletim sistemleri) için çekirdek hata ayıklamasını devre dışı bırakmak için  
  
1.  Boot.ini sistem sürücünüzde bulun (genellikle C:\\). Boot.ini dosyası, gizli ve salt okunur olabilir. Bu nedenle, görmek için aşağıdaki komutu kullanmanız gerekir:  
  
    ```  
    dir /ASH  
    ```  
  
2.  Not Defteri'ni kullanarak boot.ini açın ve aşağıdaki seçenekleri kaldırın:  
  
    ```  
    /debug  
    /debugport  
    /baudrate  
    ```  
  
3.  Bilgisayarı yeniden başlatın.  
  
#### <a name="to-debug-with-the-kernel-debugger"></a>Çekirdek hata ayıklayıcısı ile hata ayıklamak için  
  
1.  Çekirdek hata ayıklayıcısı sayfaya hata ayıklama devam etmek isteyip istemediğinizi soran bir ileti görürsünüz. Devam etmek için düğmesini tıklatın.  
  
2.  Alma bir `User break exception(Int 3).` bu meydana gelirse, hata ayıklamak devam etmek için aşağıdaki çekirdek hata ayıklayıcısı komutu yazın:  
  
     `gn`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)   
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)