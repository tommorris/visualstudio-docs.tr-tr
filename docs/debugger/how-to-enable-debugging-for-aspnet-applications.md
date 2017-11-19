---
title: "ASP.NET uygulamaları için hata ayıklamayı etkinleştirme | Microsoft Docs"
ms.custom: H1HackMay2017
ms.date: 09/21/17
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
helpviewer_keywords:
- debugging ASP.NET Web applications
- Web.config configuration file, debug mode
- debugging [Visual Studio], ASP.NET
ms.assetid: 3beed819-cece-4864-8184-bd410000973a
caps.latest.revision: "37"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9048f965ad2f04b4eed8fe3a753f6fddc280dbfa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="debug-aspnet-applications-in-visual-studio"></a>Visual Studio ASP.NET uygulamalarında hata ayıklama

Visual Studio'dan ASP.NET uygulamaları ayıklayabilirsiniz.

## <a name="requirements"></a>Gereksinimler

Bu konudaki yönergeleri izleyin, gerekir:

- IIS, Visual Studio 2012 ve sonraki sürümlerinde varsayılan olarak bulunan Express

    veya

- Yerel bir IIS web doğru bir şekilde yapılandırıldığından ve ASP.NET uygulaması hatasız çalıştırabilirsiniz sunucusu (sürüm 8.0 veya daha yüksek).

Uzak sunucu ise, uzak bilgisayarda uzaktan hata ayıklayıcı çalıştırması gerekir. Uzak IIS sunucu üzerinde hata ayıklamak için bkz: [bir IIS bilgisayarda uzaktan hata ayıklama ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md). 

## <a name="configure-debug-settings"></a>Hata ayıklama ayarlarını yapılandırma

### <a name="enable-aspnet-debugging-in-the-project-properties"></a>ASP.NET proje özellikleri'nde hata ayıklamayı etkinleştir

1. Projenizi ASP.NET Visual Studio'da açın.

2. ' Nde projeye sağ **Çözüm Gezgini**, seçin **özellikleri**ve ardından **Web** sekmesi.

    Bazı proje türleri için seçin **Özellikler > hata ayıklama** yerine. Bir Web Forms ASP.NET projesi için projesine sağ tıklatın ve **özellik sayfaları > başlangıç seçenekleri**.
  
3.  Altında **hata ayıklayıcıları**seçin **ASP.NET** onay kutusu.

    ![Hata ayıklayıcı ayarları](../debugger/media/dbg-aspnet-enable-debugging.png "hata ayıklayıcı ayarları")

> [!NOTE]
> Yeni ASP.NET projesi oluşturursanız (**Dosya > Yeni proje**), hata ayıklama ayarları zaten doğru yapılandırılmış.

### <a name="enable-debugging-in-the-webconfig-file"></a>Web.config dosyasında hata ayıklamayı etkinleştir  

Bir web uygulaması hata ayıklamak için uygulamanın web.config dosyasında doğru şekilde yapılandırılmalıdır. IIS veya IIS Express uygulama barındırıyorsanız bir web.config dosyası gereklidir.

(Bu zaten mevcut değilse) uygulamanın dağıtıldığı ASP.NET Core için web.config dosyasının otomatik olarak oluşturulur.

> [!TIP]
> Dağıtım işlemi web.config ayarları güncelleştirebilir. Bu nedenle hata ayıklamak denemeden önce sunucuda web.config ayarını doğrulayın.
  
1.  Visual Studio'da projenin web.config dosyasını açın.  
  
    > [!NOTE]  
    > Bir Web tarayıcısı kullanarak uzaktan web.config dosyasına erişemiyor. Güvenlik nedenleriyle, [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)], Microsoft IIS'i Web.config dosyalarına doğrudan tarayıcı erişimini engellemeye yardımcı olacak şekilde yapılandırır. Bir tarayıcı kullanarak bir yapılandırma dosyası erişmeye çalışırsa, bir HTTP erişim Hatası 403 (Yasak) alın.  
  
2.  Bulun `configuration/system.web/compilation` öğesi. Derleme ögesi yoksa, onu oluşturun.

    Web.config bir XML dosyasıdır ve bu yüzden etiketlerle işaretlenmiş iç içe yerleştirilmiş bölümler içerir.
  
3.  `compilation` öğesi bir `debug` özniteliği içermiyorsa, özniteliği öğeye ekleyin.  
  
4.  `debug` öznitelik değerinin `true`olarak ayarlandığından emin olun.  
  
Web.config dosyasında aşağıdaki gibi görünmelidir:

> [!NOTE]
> Bu örnek bir kısmi web.config dosyasıdır. Ek XML bölümler genellikle yapılandırma ve system.web öğeleri arasında yok. Derleme öğesi diğer öznitelikler ve öğeler içerebilir.
  
#### <a name="example"></a>Örnek  
  
```  
<configuration>  
    ...  
    <system.web>  
        <compilation  
            debug="true"  
            ...  
        >  
        ...  
        </compilation>  
    </system.web>  
</configuration>  
```

Varsayılan IIS Express sunucu yerine bir dış sunucu kullanıyorsanız, da emin olmanız gerekir `targetFramework` öznitelik değeri sunucusu üzerindeki yapılandırmayı eşleşir.

> [!IMPORTANT]
> En iyi performans için bir üretim uygulaması kümesine `debug=false` ve yayın derlemesi oluşturun ve uygulamayı yayımlama belirtin.

## <a name="configure-project-settings-for-the-server"></a>Sunucusu için proje ayarlarını yapılandırma

Bir yerel web sunucusunda hata ayıklama için proje özelliklerini ayarlayın. Uzak bir sunucu üzerinde hata ayıklama için açıklanan daha kapsamlı yönergeleri [IIS'de uzaktan hata ayıklama ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md) yerine.

1. İçinde **Web** Proje sekmesinde özelliklerini seçin ya da **IIS Express** veya **dış sunucu** altında **Server** ayarlar. (Bazı proje türleri için bu ayarlar altında görünür **hata ayıklama** yerine sekmesinde.)

    ![Sunucu ayarları](../debugger/media/dbg-aspnet-server-settings.png "sunucu ayarları")

    IIS Express ASP.NET için varsayılan sunucusudur ve genellikle özel bir yapılandırma gerektirmez. Bu, bir ASP.NET uygulaması hata ayıklamak için en kolay yoludur.

    Web Forms ASP.NET projesi için projeye sağ tıklayın, seçin **özellik sayfaları > başlangıç seçenekleri**seçin **kullanım varsayılan Web sunucusu** veya **özel sunucu kullan** () yerine **dış sunucu**).

    ![Web Forms uygulama için sunucu ayarlarını](../debugger/media/dbg-aspnet-server-settings-webforms.png "Web Forms uygulaması için sunucu ayarları")

2. Bir dış (özel) sunucusunu seçin, doğru URL'yi girin. **proje URL'sini** (veya **taban URL**) alan.

    Dış sunucunun yerel IIS ise, IIS yüklü ve doğru şekilde yapılandırılmış. Örneğin, ASP.NET doğru sürümü, IIS'de yapılandırılmalıdır. Daha fazla bilgi için bkz: [IIS 8.0 kullanarak ASP.NET 3.5 ve ASP.NET 4.5](https://docs.microsoft.com/en-us/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45). Dağıtım yanı sıra hata ayıklama test etmek isterseniz bkz [test etmek için dağıtma](https://docs.microsoft.com/en-us/aspnet/web-forms/overview/deployment/visual-studio-web-deployment/deploying-to-iis).

    Dış sunucunun ise [uzak](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)işleme yerine ekleyin ve bu proje ayarları hata ayıklama için kullanılmaz.

## <a name="local-iis-web-server-configure-iis"></a>(Yerel IIS web sunucusu) IIS yapılandırma

IIS Express için web sunucusu yapılandırmanız gerekmez (Bu bölüm atlayın). IIS Express ilk test etmek için önerilir.

Yerel IIS web sunucusu kullanıyorsanız, aşağıdaki adımları izleyin.

1. IIS düzgün yüklendiğinden emin olun. Daha fazla bilgi için bkz: [IIS 8.0 kullanarak ASP.NET 3.5 ve ASP.NET 4.5](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45).

    * Sunucuda ASP.NET doğru sürümünü yüklediğinizden emin olun. ASP.NET 4.5 yüklemek için Web Platformu Yükleyicisi (Webpı) kullanın (Windows Server 2012 R2'de sunucu düğümünden diğerine seçin **yeni Web Platformu bileşenlerini Al** ve ASP.NET için arama yapın). ASP.NET Core yüklemek için bkz: [IIS yayımlama](https://docs.asp.net/en/latest/publishing/iis.html#iis-configuration).

    > [!NOTE]
    > Windows Server 2008 R2 kullanıyorsanız, bunun yerine bu komutu kullanarak ASP.NET 4'ü yükleyin:

     **C:\Windows\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe - ir**

2. Açık **Internet Information Services (IIS) Yöneticisi**. (Sunucu Yöneticisi'nin sol bölmesinde, seçin **IIS**. Sunucuya sağ tıklayın ve seçin **Internet Information Services (IIS) Yöneticisi'ni**.)

3. Altında **bağlantıları** sol bölmede, Git **siteleri**.

4. Sağ **varsayılan Web sitesi** düğümü ve select **uygulama Ekle**.

5. Ayarlama **diğer** alanı **MyASPApp**, uygulama havuzu Varsayılanları kabul (**DefaultAppPool**) ve ayarlayın **fiziksel yolu** için **C:\inetpub\myNewFolder** (uygulama için yeni bir klasör oluşturun).

6. Altında **bağlantıları**seçin **uygulama havuzları**. Açık **DefaultAppPool** ve uygulama havuzu alanı (ASP.NET 4.5 için ASP.NET 4 kullanın. uygulamanızın doğru değerine ayarlayın Kullanmak **yönetilen kod yok** ASP.NET çekirdek için).

## <a name="local-iis-web-server-deploy-the-app"></a>(Yerel IIS web sunucusu) Uygulamayı dağıtma

Hata ayıklama başlattığınızda IIS Express için web uygulaması otomatik olarak dağıtılır (Bu bölüm atlayın).

Yerel IIS web sunucusu kullanıyorsanız, aşağıdaki adımları izleyin. IIS için uygulamanızı yayımlamak için farklı yolu vardır. Bu adımlarda, nasıl oluşturulacağı ve bir yayımlama profili kullanabilir, böylece dosya sistemi kullanılarak dağıtabilirsiniz gösterir.

1. Visual Studio'yu yönetici olarak yeniden başlatın.

    Bu yöntemi kullanarak dağıtmak için yönetici ayrıcalıkları gerekir.

2. Visual Studio'da projeye sağ tıklayın ve seçin **Yayımla** (Web Forms için **Web uygulaması yayımlama**).

3. Seçin **IIS, FTP, vb.** tıklatıp **Yayımla**.

    ![IIS yayımlama](../debugger/media/dbg-aspnet-local-iis.png "IIS yayımlama")

    Web Forms uygulaması için seçin **özel** Yayımla iletişim kutusunda bir profil adı girin ve seçin **Tamam**.

4. İçinde **yayımlama yöntemi** alan, seçin **dosya sistemi**.

5. İçin **hedef konum**, tıklatın **Gözat** düğmesi.

6. (ASP.NET çekirdek) Seçin **dosya sistemi** ve daha önce oluşturduğunuz uygulama için klasörü seçin.

6. (ASP.NET) Seçin **yerel IIS**, daha önce oluşturduğunuz ve ardından web sitesini seçip **açık**.

    ![IIS yayımlama](../debugger/media/dbg-aspnet-local-iis-select-site.png "IIS yayımlama")

    > [!TIP]
    > Web sunucusu belirten bir ileti doğru yapılandırılmamış görürseniz, IIS için ASP.NET doğru sürümünün yüklü olduğundan emin olun.

7. Tıklatın **sonraki** ve bir **hata ayıklama** yapılandırma.

    > [!NOTE]
    > Bir yayın yapılandırmayla dağıtırsanız, bu ayarlar `debug=false` sunucunun web.config dosyasında.

8. Tıklatın **kaydetmek** yayımlama ayarları kaydedin ve ardından **Yayımla**.

    > [!CAUTION]
    >  Kod ya da yeniden değişiklikleri yapmanız gerekirse, yeniden yayımlamanız ve bu adımı yineleyin. Uzak makineye kopyaladığınız yürütülebilir yerel kaynağı ve simgeleri tam olarak eşleşmelidir.

## <a name="set-a-breakpoint-and-start-debugging"></a>Bir kesme noktası ayarlayın ve hata ayıklamayı Başlat

1. Visual Studio'da, projenizdeki kümesi bir kesme noktası bildiğiniz biraz kod üzerinde çalışır.

2. Hata ayıklama başlatmak için basın **F5** (**hata ayıklama > hata ayıklamayı Başlat**).

3. Kesme noktası içerdiğinden kodu çalıştırmak için eylemleri gerçekleştirin.

    Kesme noktası ayarladığınız hata ayıklayıcı duraklatır.

### <a name="local-iis-troubleshooting-cannot-hit-the-breakpoint"></a>(Yerel IIS) Sorun giderme: kesme noktası isabet olamaz

1. IIS web uygulaması başlatın ve düzgün çalıştığını doğrulayın. Çalışan web uygulaması bırakın.

2. Visual Studio'dan seçin **hata ayıklama > ekleme işlemi için** ve ASP.NET işleminin bağlayın (genellikle **w3wp.exe** veya **dotnet.exe**). Daha fazla bilgi için bkz: [ekleme işlemi için](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).

    Bağlanırken tamamlayabilirseniz **ekleme işlemi için** ve bir kesme noktası isabet, ancak kullanarak hata ayıklama başlatılamıyor **F5**, bir ayar Proje Özellikleri'nde hatalı olduğunu olasıdır sonra. HOSTS dosyasını kullanıyorsanız, doğru şekilde yapılandırıldığını doğrulayın.

  
## <a name="robust-programming"></a>Güçlü Programlama  
[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)], Web.config dosyalarına yapılan değişiklikleri otomatik olarak algılar ve yeni yapılandırma ayarlarını uygular. Bilgisayarı yeniden başlatın ya da değişikliklerin etkili olması IIS sunucuyu yeniden başlatmanız gerekmez.  
  
Bir Web sitesi birden çok sanal dizin ve alt dizinler içerebilir ve her birinde Web.config dosyaları bulunabilir. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] uygulamaları, URL yolunda daha yüksek düzeylerde Web.config dosyalarından ayarları miras alabilir. Hiyerarşik yapılandırma dosyaları, aynı anda çeşitli [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] uygulamalarının ayarlarını değiştirmenize olanak tanır, örneğin hiyerarşide onun altındaki tüm uygulamalar için. Ancak, varsa `debug` ayarlanmış hiyerarşisinde daha düşük bir dosya, daha yüksek değerini geçersiz kılar.  
  
Örneğin, belirtebilirsiniz `debug="true"` www.microsoft.com/aaa/Web.config ve herhangi bir uygulama aaa klasöründe veya buna ayrıca herhangi bir alt bu ayarı devralır. Dolayısıyla, [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] uygulama www.microsoft.com/aaa/bbb, herhangi bir olarak bu ayarı devralan [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] www.microsoft.com/aaa/ccc, www.microsoft.com/aaa/ddd ve benzeri uygulamaları. Tek istisna durum, bu uygulamalardan biri kendi alt Web.config dosyasını kullanarak ayarı geçersiz kılarsa söz konusudur.  
  
> [!IMPORTANT]
> Hata ayıklama modu büyük ölçüde etkinleştirilmesi, performansını etkiler, [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] uygulama. Bir yayınlama uygulaması dağıtmadan veya performans ölçümleri gerçekleştirmeden önce, hata ayıklama modunu devre dışı bırakmayı unutmayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[ASP.NET hata ayıklama: sistem gereksinimleri](aspnet-debugging-system-requirements.md)   
[Nasıl yapılır: bir kullanıcı hesabı altında çalışan işlem çalıştırma](how-to-run-the-worker-process-under-a-user-account.md)   
[Nasıl yapılır: ASP.NET işleminin adını bulma](how-to-find-the-name-of-the-aspnet-process.md)   
[Dağıtılmış Web uygulamalarında hata ayıklama](debugging-deployed-web-applications.md)   
[İzlenecek yol: Web formunda hata ayıklama](walkthrough-debugging-a-web-form.md)   
[Nasıl yapılır: ASP.NET özel durumlarında hata ayıklama](how-to-debug-aspnet-exceptions.md)   
[Web uygulamalarında hata ayıklama: hatalar ve sorun giderme](debugging-web-applications-errors-and-troubleshooting.md)
  