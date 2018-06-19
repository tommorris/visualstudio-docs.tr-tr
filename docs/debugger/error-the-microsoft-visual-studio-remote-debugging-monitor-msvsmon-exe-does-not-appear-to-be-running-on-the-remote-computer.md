---
title: 'Hata: Microsoft Visual Studio Uzaktan Hata Ayıklama İzleyicisi (MSVSMON.EXE) uzak bilgisayar üzerinde çalışıyor görünmüyor. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.server_machine_no_default
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
ms.openlocfilehash: 683af8cf0c75068a58b5e8cf4732cdf69c586d4f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31476071"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-msvsmonexe-does-not-appear-to-be-running-on-the-remote-computer"></a>Hata: Microsoft Visual Studio Uzaktan Hata Ayıklama İzleyicisi (MSVSMON.EXE) uzak bilgisayar üzerinde çalışıyor görünmüyor.
Bu hata iletisi, Visual Studio uzak bilgisayarda Visual Studio uzaktan hata ayıklama İzleyicisi doğru örneği bulunamadı anlamına gelir. Visual Studio uzaktan hata ayıklama İzleyicisi çalışmak için uzaktan hata ayıklama için yüklü olması gerekir. Karşıdan yükleme ve uzaktan hata ayıklayıcı ayarlama hakkında daha fazla bilgi için bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md).  
  
> [!IMPORTANT]
>  Bu ileti bir ürün hatası nedeniyle almış düşünüyorsanız, lütfen [Bu sorun Visual Studio rapor](../ide/how-to-report-a-problem-with-visual-studio-2017.md). Daha fazla yardıma gereksinim duyarsanız, bkz: [konuşun bize](../ide/talk-to-us.md) yollarını Microsoft ile iletişime geçin.  
  
## <a name="i-got-this-message-while-i-was-debugging-in-visual-studio-2010-or-earlier"></a>Hata ayıklama Visual Studio 2010 veya önceki sürümlerde sırada bu iletisi aldım  
 Kullandığınız Visual Studio sürümünü Visual Studio 2010 veya önceki bir sürümü ise, dosya ve yazıcı paylaşımı etkinleştirilmemişse, bu hatayı alabilirsiniz. Bu sorun hakkında daha fazla bilgi için lütfen bu belgeleri Visual Studio 2010 sürümüne bakın: [hata: Microsoft Visual Studio uzaktan hata ayıklama İzleyicisi (MSVSMON. EXE) uzak bilgisayar üzerinde çalışıyor görünmüyor. -Visual Studio 2010](https://msdn.microsoft.com/en-us/library/ms164726\(v=vs.100\).aspx)  
  
## <a name="i-got-this-message-while-i-was-debugging-locally"></a>Yerel olarak debugging sırada bu iletisi aldım  
 Yerel olarak hata ayıklarken bu iletiyi alıyorsanız, virüsten koruma yazılımınızı veya bir üçüncü taraf güvenlik duvarı için blame olabilir. Visual Studio 32 bit bir uygulama kitabıdır uzaktan hata ayıklayıcı 64-bit sürümü 64-bit uygulamalarda hata ayıklama için kullanır. İki işlem, yerel bilgisayarda yerel ağ kullanarak iletişim kurar. Bilgisayar hiçbir trafik bırakır, ancak üçüncü taraf güvenlik yazılımı iletişimi engelleyebilir mümkündür.  
  
 Aşağıdaki bölümlerde başka bir nedenle neden, bu iletiyi getirildiğini ve sorunu düzeltmek için yapabileceklerinizi listelenmektedir.  
  
## <a name="the-remote-machine-is-not-reachable"></a>Uzak makinede erişilebilir değil  
 Deneyin [ping](https://technet.microsoft.com/en-us/library/ee624059\(v=ws.10\).aspx) uzak makine. Ping işlemine yanıt değil, uzak Araçlar ya da bağlanabiliyor olmayacaktır. Uzak makine yeniden başlatılıyor ve aksi takdirde ağ üzerinde doğru şekilde yapılandırıldığından emin yapmayı deneyin.  
  
## <a name="the-version-of-the-remote-debugger-doesnt-match-the-version-of-visual-studio"></a>Uzaktan hata ayıklayıcı sürümünü Visual Studio sürümü eşleşmiyor  
 Yerel olarak çalıştırılan Visual Studio sürümünü uzak makine üzerinde çalışan uzaktan hata ayıklama İzleyicisi sürümü ile eşleşmesi gerekir. Bu sorunu gidermek için karşıdan yükleme ve uzaktan hata ayıklama İzleyicisi eşleşen sürümü yükleyin. Git [Yükleme Merkezi'nden](http://www.microsoft.com/en-us/download) uzaktan hata ayıklayıcı doğru sürümü bulunamıyor.  
  
## <a name="the-local-and-remote-machines-have-different-authentication-modes"></a>Yerel ve uzak makineye farklı kimlik doğrulama modları sahip  
 Yerel ve uzak makineler aynı kimlik doğrulama modunu kullanmanız gerekir. Bu sorunu gidermek için her iki makine aynı kimlik doğrulama modu kullandığınızdan emin olun. Kimlik doğrulama modları hakkında daha fazla bilgi için bkz: [Windows kimlik doğrulamasına genel bakış](https://technet.microsoft.com/en-us/library/hh831472.aspx).  
  
## <a name="the-remote-debugger-is-running-under-a-different-user-account"></a>Uzaktan hata ayıklayıcı farklı bir kullanıcı hesabı altında çalışıyor  
 Bu aşağıdaki yollardan biriyle çözebilir:  
  
-   Uzaktan hata ayıklayıcı durdurun ve yerel bilgisayarda kullandığınız hesapla başlatın.  
  
-   Uzaktan hata ayıklayıcı komut satırından başlatabilirsiniz **/ izin \<kullanıcı adı >** parametre: `msvsmon /allow <username@computer>`  
  
-   Uzaktan Hata Ayıklayıcı'nın izni kullanıcı ekleyebilirsiniz (uzaktan hata ayıklayıcı penceresinde **Araçlar > izinleri**).  
  
-   Önceki adımlarda yöntemlerini kullanamıyorsanız, uzaktan hata ayıklama yapmak herhangi bir kullanıcı izin verebilirsiniz. Uzaktan hata ayıklayıcı penceresine gidin **Araçlar > Seçenekler** iletişim. Seçtiğinizde, **doğrulaması yok**, ardından denetleyebilirsiniz **hata ayıklamak herhangi bir kullanıcının**. Ancak, bu seçenek yalnızca hiç seçimi varsa veya özel bir ağda olduğunda kullanmanız gerekir.  
  
## <a name="the-firewall-on-the-remote-machine-doesnt-allow-incoming-connections-to-the-remote-debugger"></a>Güvenlik Duvarı'nı uzak makinesinde uzaktan hata ayıklayıcı gelen bağlantılara izin vermez  
 Visual Studio makinede güvenlik duvarı ve Güvenlik Duvarı'nı uzak makinede Visual Studio uzaktan hata ayıklayıcı arasındaki iletişime izin verecek şekilde yapılandırılması gerekir. Uzaktan hata ayıklayıcı kullanarak bağlantı noktaları hakkında daha fazla bilgi için bkz: [uzaktan hata ayıklayıcı bağlantı noktası atamaları](../debugger/remote-debugger-port-assignments.md). Windows Güvenlik Duvarı'nı yapılandırma hakkında daha fazla bilgi için bkz: [uzaktan hata ayıklama için Windows Güvenlik Duvarı Yapılandırma](../debugger/configure-the-windows-firewall-for-remote-debugging.md).  
  
## <a name="anti-virus-software-is-blocking-the-connections"></a>Virüsten koruma yazılımı bağlantıları engelliyor  
 Windows virüsten koruma yazılımı uzaktan hata ayıklayıcı bağlantılara izin verir, ancak bazı üçüncü taraf virüsten koruma yazılımı engelliyor olabilir. Bu bağlantılarına izin verecek şekilde nasıl öğrenmek virüsten koruma yazılımınızın belgelerine bakın.  
  
## <a name="network-security-policy-is-blocking-communication-between-the-remote-machine-and-visual-studio"></a>Ağ güvenlik ilkesi Visual Studio ve uzak makine arasındaki iletişimi engelliyor  
 Ağınızda güvenlik iletişim engellemediğinden emin olmak için gözden geçirin. Windows ağ güvenlik ilkesi hakkında daha fazla bilgi için bkz: [güvenlik ilkesi ayarları](/windows/device-security/security-policy-settings/security-policy-settings).  
  
## <a name="the-network-is-too-busy-to-support-remote-debugging"></a>Ağ uzaktan hata ayıklama desteği çok meşgul  
 Farklı bir zamanda uzaktan hata ayıklama yapın veya farklı bir saat için ağ üzerinde çalışmayı yeniden gerekebilir.  
  
## <a name="more-help"></a>Daha fazla yardım  
 Komut satırı anahtarları dahil olmak üzere daha uzaktan hata ayıklayıcı Yardım almak için tıklatın **Yardım > kullanım** uzaktan hata ayıklayıcı penceresinde. Açık yoksa, aşağıdaki satırı kopyalayarak web sayfasını görebilirsiniz bir **dosya Gezgini** penceresi. (Değiştirmeniz gerekiyor \<Visual Studio yükleme dizini > Visual Studio yüklemenizin konumla.)  
  
 res: / /*\<Visual Studio yükleme dizini >* \Common7\IDE\Remote%20Debugger\x64\msvsmon.exe/help.htm  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)