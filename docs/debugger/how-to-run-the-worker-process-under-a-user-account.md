---
title: 'Nasıl yapılır: bir kullanıcı hesabı altında çalışan işlem çalıştırma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- user accounts, aspnet_wp.exe
- ASP.NET, debugging Web applications
- tools, aspnet_wp.exe
- ASP.NET, tools
- aspnet_wp.exe
ms.assetid: b58e97b1-e62a-4318-aea4-52276ea20735
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ad6407e4768acbeaf32cf4bebaf7064f04f21fba
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-run-the-worker-process-under-a-user-account"></a>Nasıl Yapılır: Çalışan İşlemi Kullanıcı Hesabı Altında Çalıştırma
Bilgisayarınızı çalıştırabilirsiniz şekilde ayarlamak için [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] bir kullanıcı hesabı altında çalışan işlemi (aspnet_wp.exe veya w3wp.exe) aşağıdaki adımları izleyin.  

 > [!IMPORTANT]
 > Windows Server 2008 R2 ile başlayarak, kullanılmasını öneririz [ApplicationPoolIdentity](/iis/manage/configuring-security/application-pool-identities) her bir uygulama havuzu kimliği olarak.
  
## <a name="procedure"></a>Yordam  
  
#### <a name="to-run-aspnetwpexe-under-a-user-account"></a>Bir kullanıcı hesabı altında Aspnet_wp.exe çalıştırmak için  
  
1.  Çalışma zamanı yüklendiği yapılandırma klasörü yolunda bilgisayarınızda bulunan machine.config dosyasını açın.  
  
2.  Bul &lt;processModel&gt; bölümünde ve kullanıcı ve parola öznitelikleri adına ve altında çalışacak şekilde aspnet_wp.exe istediğiniz kullanıcı hesabının parolasını değiştirin.  
  
3.  Machine.config dosyasının kaydedin.  
  
4.  Üzerinde [!INCLUDE[winxpsvr](../debugger/includes/winxpsvr_md.md)], IIS 6.0 varsayılan olarak yüklenir. İlgili çalışan işlemi w3wp.exe.To çalışan işlem olarak aspnet_wp.exe ile IIS 6.0 modunda çalıştırmak, şu adımları izlemelisiniz:  
  
    1.  Tıklatın **Başlat**, tıklatın **Yönetimsel Araçlar** ve ardından **Internet Information Services**.  
  
    2.  İçinde **Internet Information Services** iletişim kutusu, sağ **Web siteleri** klasörü ve seçin **özellikleri**.  
  
    3.  İçinde **Web siteleri özellikleri** iletişim kutusunda, seçin **hizmet**.  
  
    4.  Seçin **IIS6.0 yalıtım modunda çalıştır WWW hizmeti**.  
  
    5.  Kapat **özellikleri** iletişim kutusu ve **Internet Services Manager**.  
  
5.  Bir Windows komut istemi açın ve sunucu çalıştırarak sıfırlayın:  
  
    ```  
    iisreset  
    ```  
    — veya —  
  
    ```  
    net stop iisadmin /y  
    net start w3svc  
    ```  
  
6.  Geçici bulun [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] yapılandırma klasörü aynı yol bulunmalıdır dosyaları klasörü. Geçici sağ [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] seçin ve dosyaları klasörü **özellikleri** kısayol menüsünde.  
  
7.  İçinde **geçici ASP.NET dosyaları özellikleri** iletişim kutusu, tıklatın **güvenlik** sekmesi.  
  
8.  **Gelişmiş**'e tıklayın.  
  
9. İçinde **ASP.Net dosyaları için Gelişmiş güvenlik ayarları** iletişim kutusu, tıklatın **Ekle**.  
  
    **Kullanıcı seç, bilgisayar veya Grup iletişim kutusunda** görüntülenir.  
  
10. Kullanıcı adı yazın **Seçilecek nesne adını girin** kutusuna ve ardından **Tamam**. Kullanıcı adı şu biçimde olmalıdır: Etkialanıadı\kullanıcıadı.  
  
11. İçinde **ASP.NET dosyaları için izin girdisi** iletişim kutusunda, kullanıcıya vermek **tam denetim**ve ardından **Tamam** kapatmak için **geçici ASP için giriş .NET dosyaları** iletişim kutusu.  
  
12. A **güvenlik** iletişim kutusu görünür ve sizin gerçekten bir sistem klasörü izinleri değiştirmek isteyip istemediğinizi sorar. **Evet**'i tıklayın.  
  
13. Tıklatın **Tamam** kapatmak için **geçici ASP.NET dosyaları özellikleri** iletişim kutusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[ASP.NET uygulamalarında hata ayıklama](../debugger/how-to-enable-debugging-for-aspnet-applications.md)   
[ASP.NET hata ayıklama: Sistem gereksinimleri](../debugger/aspnet-debugging-system-requirements.md)  
  
