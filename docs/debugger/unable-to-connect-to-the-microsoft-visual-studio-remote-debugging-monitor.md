---
title: "Microsoft Visual Studio uzaktan hata ayıklama İzleyicisi bağlanılamıyor | Microsoft Docs"
ms.custom: 
ms.date: 08/24/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.error.remote_debug
- vs.debug.error.firewall.remotemachine
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: a1d959fc-3817-491c-831b-e6b768a3877a
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 345dbfd982c2e80fadc0f4c3d9484c662b6090ac
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="unable-to-connect-to-the-microsoft-visual-studio-remote-debugging-monitor"></a>Microsoft Visual Studio Uzaktan Hata Ayıklama İzleyicisi'ne Bağlanılamıyor.
Bu ileti, uzaktan hata ayıklama İzleyicisi düzgün uzak makinede kurulu değil veya uzak makineye ağ sorunları veya bir güvenlik duvarı varlığını nedeniyle erişilemez durumda nedeniyle oluşabilir.
  
> [!IMPORTANT]
>  Bu ileti bir ürün hatası nedeniyle almış düşünüyorsanız, lütfen [bu sorunu bildiren](../ide/how-to-report-a-problem-with-visual-studio-2017.md) Visual Studio. Daha fazla yardıma gereksinim duyarsanız, bkz: [konuşun bize](../ide/talk-to-us.md) yollarını Microsoft ile iletişime geçin.

## <a name="specificerrors"></a>Ayrıntılı hata iletisi nedir?

`Unable to Connect to the Microsoft Visual Studio Remote Debugging Monitor` İleti geneldir. Genellikle, daha belirli bir ileti hata dizesi içinde bulunur ve sorunu ya da daha kesin bir düzeltme için arama nedenini belirlemenize yardımcı olabilir. Birkaç ana hata iletisi eklenir daha sık karşılaşılan hata iletileri şunlardır:

- [Hata ayıklayıcıyı uzak bilgisayara bağlanamıyor. Hata ayıklayıcı belirtilen bilgisayar adı çözemedi](#cannot_connect)
- [Bağlantı isteği uzaktan hata ayıklayıcı tarafından reddedildi](#rejected)
- [Bellek konumuna geçersiz erişim](#invalid_access)
- [Uzak bilgisayarda çalışan belirtilen ada göre sunucusu yok](#no_server)
- [İstenen ad geçerli, ancak istenen türde hiçbir veri bulunamadı](#valid_name)
- [Visual Studio uzaktan hata ayıklayıcı hedef bilgisayarda bu bilgisayara bağlanamıyor](#cant_connect_back)
- [Erişim reddedildi](#access_denied)
- [Güvenlik paketi özgü bir hata oluştu](#security_package)

## <a name="cannot_connect"></a>Hata ayıklayıcıyı uzak bilgisayara bağlanamıyor. Hata ayıklayıcı belirtilen bilgisayar adı çözemedi

Aşağıdaki adımları deneyin:

1. Geçerli bir bilgisayar adı girin ve bağlantı noktası numarasını emin olun **ekleme işlemi için** iletişim kutusu veya Proje Özellikleri'nde (özelliklerini ayarlamak için bkz: [adımları](#server_incorrect)). Bilgisayar adı şu biçimde olmalıdır:

    `computername:port`

    > [!NOTE]
    > Bağlantı noktası numarasını eşleşmelidir [bağlantı noktası numarasını uzaktan hata ayıklayıcı](../debugger/remote-debugger-port-assignments.md), hangi *çalıştırmalıdır* hedef makinede.

2. Bilgisayar adı çalışmazsa, IP adresini deneyin ve bunun yerine bağlantı noktası numarası.

3. Hedef makine üzerinde çalışan uzaktan hata ayıklayıcı sürümünü Visual Studio sürümünüzle eşleştiğinden emin olun. Uzaktan hata ayıklayıcı doğru sürümünü almak için bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md).

    > [!TIP]
    > İşlemine iliştirme başarıyla bağlanıp ancak istediğiniz işlem görmüyorsanız, seçin ve **Göster tüm kullanıcıların bu onay kutusunu işlemlerini**. Bu, işlemleri farklı bir kullanıcı hesabı altında bağlı olmadığını gösterir.

4. Bu adımları bu hatayı gidermezse bkz [uzak makineye ulaşılabilir değil](#dns).

## <a name="rejected"></a>Bağlantı isteği uzaktan hata ayıklayıcı tarafından reddedildi

İçinde **ekleme işlemi için** iletişim kutusu veya Proje Özellikleri'nde uzak bilgisayar adı ve bağlantı noktası numarası uzaktan hata ayıklayıcı penceresinde gösterilen adı ve bağlantı noktası numarası eşleştiğinden emin olun. Yanlış olmadığını düzeltin ve yeniden deneyin.

Bu değerler doğru olduğundan ve ileti değinmektedir **Windows kimlik doğrulaması** modu, uzaktan hata ayıklayıcı doğru kimlik doğrulama modudur onay (**Araçlar > Seçenekler**).

## <a name="invalid_access"></a>Bellek konumuna geçersiz erişim

Bir iç hata oluştu. Visual Studio'yu yeniden başlatın ve yeniden deneyin.

## <a name="no_server"></a>Uzak bilgisayarda çalışan belirtilen ada göre sunucusu yok

Visual Studio uzaktan hata ayıklayıcıya bağlanamadı. Bu ileti, çeşitli nedenlerle ortaya çıkabilir:

- Uzaktan hata ayıklayıcı farklı bir kullanıcı hesabı altında çalışıyor olabilir. Bkz: [adımları](#user_accounts)

- Bağlantı noktasının Güvenlik Duvarı'nı engellendi. Güvenlik Duvarı olduğundan emin olun [isteğiniz engellemediğini](#firewall), özellikle bir üçüncü taraf güvenlik duvarı kullanıyorsanız.

- Visual Studio uzaktan hata ayıklayıcı sürümü eşleşmiyor. Uzaktan hata ayıklayıcı doğru sürümünü almak için bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md)


## <a name="#valid_name"></a>İstenen ad geçerli, ancak istenen türde hiçbir veri bulunamadı

Uzak bilgisayar var, ancak Visual Studio uzaktan hata ayıklayıcıya bağlanamadı. Bu ileti, çeşitli nedenlerle ortaya çıkabilir:

- Bir DNS sorununun bağlantıyı engelliyor. Bkz: [adımları](#dns).

- Uzaktan hata ayıklayıcı farklı bir kullanıcı hesabı altında çalışıyor olabilir. İzleyin [adımları](#user_accounts).

- Bağlantı noktasının Güvenlik Duvarı'nı engellendi. Güvenlik Duvarı olduğundan emin olun [isteğiniz engellemediğini](#firewall), özellikle bir üçüncü taraf güvenlik duvarı kullanıyorsanız.

- Visual Studio uzaktan hata ayıklayıcı sürümü eşleşmiyor. Uzaktan hata ayıklayıcı doğru sürümünü almak için bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md).

## <a name="cant_connect_back"></a>Visual Studio uzaktan hata ayıklayıcı hedef bilgisayarda bu bilgisayara bağlanamıyor

Uzaktan hata ayıklayıcı farklı bir kullanıcı hesabı altında çalışıyor olabilir. Uzaktan hata ayıklayıcı açmak **Araçlar > izinleri** uzaktan hata ayıklayıcı'nın izni kullanıcı eklemek için. Daha fazla bilgi için bkz: [uzaktan hata ayıklayıcı farklı bir kullanıcı hesabı altında çalışıyor](#user_accounts).

Hata iletisi de ilgili bir güvenlik duvarı varsa, Güvenlik Duvarı'nı yerel makinede Visual Studio'ya geri dönün uzak bilgisayardan iletişimi engelliyor olabilir. Bkz: [adımları](#firewall).

## <a name="access_denied"></a>Erişim reddedildi

Uzak bir bilgisayarda 64-bit (desteklenmiyor) bir 32 bit bilgisayardan hata ayıklamak çalışırsanız, bu hatayı görebilirsiniz.

## <a name="security_package"></a>Güvenlik paketi özgü bir hata oluştu

Bu, Windows XP ve Windows 7 için belirli bir eski sorunu olabilir. Bu bkz [bilgi](https://stackoverflow.com/questions/4786016/unable-to-connect-to-the-microsoft-remote-debugging-monitor-a-security-package). 

## <a name="causes-and-recommendations"></a>Neden olur ve öneriler

### <a name="dns"></a>Uzak makinede erişilebilir değil 

Uzak bilgisayar adını kullanarak bağlanamazsa, IP adresi kullanmayı deneyin. Kullanabileceğiniz `ipconfig` IPv4 adresini almak için uzak bilgisayarda bir komut satırında. HOSTS dosyasını kullanıyorsanız, doğru şekilde yapılandırıldığını doğrulayın.

Başarısız olursa, uzak bilgisayarın ağda erişilebilir olduğunu doğrulayın ([ping](https://technet.microsoft.com/en-us/library/cc732509(v=ws.10).aspx) uzak makine). Internet üzerinden uzaktan hata ayıklama desteklenmiyor, dışındaki bazı Microsoft Azure senaryolarda.
  
### <a name="server_incorrect"></a>Sunucu adı yanlış veya üçüncü taraf yazılım ile uzaktan hata ayıklayıcı engelliyor

Visual Studio Proje özelliklerine bakmak ve sunucu adının doğru olduğundan emin olun. Konular için bkz: [C# ve Visual Basic](../debugger/remote-debugging-csharp.md#remote_csharp) ve [C++](../debugger/remote-debugging-cpp.md#remote_cplusplus). ASP.NET için açık **özellikleri / Web / sunucuları** veya **özellikleri / Debug** proje türüne bağlı olarak.

> [!NOTE]
> İşleme bağlıyorsanız proje özelliklerinde uzak ayarları kullanılmaz.

Sunucu adı doğruysa, virüsten koruma yazılımınızı veya bir üçüncü taraf güvenlik duvarı uzaktan hata ayıklayıcı engelliyor olabilir. Visual Studio uzaktan hata ayıklayıcı 64-bit sürümü 64-bit uygulamalar hata ayıklamak için kullanan 32 bit bir uygulama olduğundan, yerel olarak hata ayıklama sırasında bu durum oluşabilir. 32 bit ve 64 bit işlemleri, yerel bilgisayarda yerel ağ kullanarak iletişim kurar. Bilgisayar ağ trafiği bırakır, ancak üçüncü taraf güvenlik yazılımı iletişimi engelleyebilir mümkündür.

### <a name="user_accounts"></a>Uzaktan hata ayıklayıcı farklı bir kullanıcı hesabı altında çalışıyor 

Uzaktan hata ayıklayıcı varsayılan olarak, yalnızca uzaktan hata ayıklayıcı ve Yöneticiler grubu üyelerinin başlatanın bağlantılarını kabul edecekse. Ek kullanıcılar açıkça izinleri verilmelidir. 
 
Bu aşağıdaki yollardan biriyle çözebilir:  

-   Visual Studio kullanıcı uzaktan hata ayıklayıcı'nın izinleri ekleyin (uzaktan hata ayıklayıcı penceresinde seçin **Araçlar > izinleri**).

-   Uzak bilgisayarda uzaktan hata ayıklayıcı altında aynı kullanıcı hesabı ve Visual Studio bilgisayarda kullandığınız parolayı yeniden başlatın.

    > [!NOTE]
    > Uzaktan hata ayıklayıcı uzak bir sunucuda çalışıyorsa, uzaktan hata ayıklayıcı uygulama sağ tıklatın ve seçin **yönetici olarak çalıştır** (veya, bir hizmet olarak uzaktan hata ayıklayıcı çalıştırılabilir). Uzak bir sunucuda bu çalıştırmıyorsanız yalnızca başlatın normalde.
  
-   Uzaktan hata ayıklayıcı komut satırından başlatabilirsiniz **/ izin \<kullanıcı adı >** parametresi: `msvsmon /allow <username@computer>`. 
  
-   Alternatif olarak, uzaktan hata ayıklama yapmak herhangi bir kullanıcı izin verebilirsiniz. Uzaktan hata ayıklayıcı penceresine gidin **Araçlar > Seçenekler** iletişim. Seçtiğinizde, **doğrulaması yok**, ardından denetleyebilirsiniz **hata ayıklamak herhangi bir kullanıcının**. Ancak, bu seçenek yalnızca diğer seçenekleri başarısız olursa veya özel bir ağda ise denemelisiniz.

### <a name="firewall"></a>Güvenlik Duvarı'nı uzak makinesinde uzaktan hata ayıklayıcı gelen bağlantılara izin vermez  
 Visual Studio makinede güvenlik duvarı ve Güvenlik Duvarı'nı uzak makinede Visual Studio uzaktan hata ayıklayıcı arasındaki iletişime izin verecek şekilde yapılandırılması gerekir. Uzaktan hata ayıklayıcı kullanarak bağlantı noktaları hakkında daha fazla bilgi için bkz: [uzaktan hata ayıklayıcı bağlantı noktası atamaları](../debugger/remote-debugger-port-assignments.md). Windows Güvenlik Duvarı'nı yapılandırma hakkında daha fazla bilgi için bkz: [uzaktan hata ayıklama için Windows Güvenlik Duvarı Yapılandırma](../debugger/configure-the-windows-firewall-for-remote-debugging.md).
  
### <a name="the-version-of-the-remote-debugger-doesnt-match-the-version-of-visual-studio"></a>Uzaktan hata ayıklayıcı sürümünü Visual Studio sürümü eşleşmiyor  
 Yerel olarak çalıştırılan Visual Studio sürümünü uzak makine üzerinde çalışan uzaktan hata ayıklama İzleyicisi sürümü ile eşleşmesi gerekir. Bu sorunu gidermek için karşıdan yükleme ve uzaktan hata ayıklama İzleyicisi eşleşen sürümü yükleyin. Uzaktan hata ayıklayıcı doğru sürümünü almak için bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md).
  
### <a name="the-local-and-remote-machines-have-different-authentication-modes"></a>Yerel ve uzak makineye farklı kimlik doğrulama modları sahip  
 Yerel ve uzak makineler aynı kimlik doğrulama modunu kullanmanız gerekir. Bu sorunu gidermek için her iki makine aynı kimlik doğrulama modu kullandığınızdan emin olun. Kimlik doğrulama modu değiştirebilirsiniz. Uzaktan hata ayıklayıcı penceresine gidin **Araçlar > Seçenekler** iletişim kutusu.
  
 Kimlik doğrulama modları hakkında daha fazla bilgi için bkz: [Windows kimlik doğrulamasına genel bakış](https://technet.microsoft.com/en-us/library/hh831472.aspx).   
  
### <a name="anti-virus-software-is-blocking-the-connections"></a>Virüsten koruma yazılımı bağlantıları engelliyor  
 Windows virüsten koruma yazılımı uzaktan hata ayıklayıcı bağlantılara izin verir, ancak bazı üçüncü taraf virüsten koruma yazılımı engelliyor olabilir. Bu bağlantılarına izin verecek şekilde nasıl öğrenmek virüsten koruma yazılımınızın belgelerine bakın.  
  
### <a name="network-security-policy-is-blocking-communication-between-the-remote-machine-and-visual-studio"></a>Ağ güvenlik ilkesi Visual Studio ve uzak makine arasındaki iletişimi engelliyor  
 Ağınızda güvenlik iletişim engellemediğinden emin olmak için gözden geçirin. Windows ağ güvenlik ilkesi hakkında daha fazla bilgi için bkz: [güvenlik ilkesi ayarları](/windows/device-security/security-policy-settings/security-policy-settings).  
  
### <a name="the-network-is-too-busy-to-support-remote-debugging"></a>Ağ uzaktan hata ayıklama desteği çok meşgul  
 Farklı bir zamanda uzaktan hata ayıklama yapın veya farklı bir saat için ağ üzerinde çalışmayı yeniden gerekebilir.  
  
## <a name="more-help"></a>Daha fazla yardım  
 Daha fazla uzaktan hata ayıklayıcı Yardım almak için uzaktan hata ayıklayıcı'nın Yardım sayfasını açın (**Yardım > kullanım** uzaktan hata ayıklayıcı).
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)