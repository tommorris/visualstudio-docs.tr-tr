---
title: Visual Studio hata ayıklayıcısı ile çalıştırma işlemine iliştirme | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 05/18/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.processes.attach
- vs.debug.process
- vs.debug.programs
- vs.debug.detaching
- vs.debug.processes
- vs.debug.error.attach
- vs.debug.remotemachine
dev_langs:
- CSharp
- FSharp
- C++
- VB
helpviewer_keywords:
- remote debugging, attaching to programs
- processes, attaching to running processes
- Attach to Process dialog box
- debugging [Visual Studio], attaching to processes
- debugger, processes
ms.assetid: 27900e58-090c-4211-a309-b3e1496d5824
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 314a559e4370f254af9473ec38c77d11287c575a
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
---
# <a name="attach-to-running-processes-with-the-visual-studio-debugger"></a>Visual Studio Hata Ayıklayıcısı ile Çalıştırma İşlemleri İliştirme
Yerel veya uzak bilgisayarda çalışan bir işlemi için Visual Studio hata ayıklayıcısı ekleyebilirsiniz. İşlemin çalıştığı sonra tıklayın **hata ayıklama > ekleme işlemi için** (veya basın **CTRL + ALT + P**) açmak için **ekleme işlemi için** iletişim kutusu.

Bir yerel veya uzak bilgisayarda çalışan uygulamaları hata ayıklama, birden çok işlem aynı anda hatalarını ayıklama veya Visual Studio'da oluşturulmayan bir uygulamada hata ayıklamak için bu özelliği kullanın. Bir uygulama hata ayıklama istediğinizde sık yararlı olur ancak (herhangi bir nedenle), başlamadı uygulama Visual Studio hata ayıklayıcısı ekli. Örneğin, hata ayıklayıcı olmadan uygulamayı çalıştıran ve bir özel durum isabet, hata ayıklama başlamak için uygulama çalışan işlemi ardından ekleyin.

> [!TIP]
> Emin değil mi kullanmanızı gerektiren **ekleme işlemi için** hata ayıklama senaryonuz için? Bkz: [ortak senaryolar hata ayıklama](#BKMK_Scenarios). IIS'ye dağıtılan bkz ASP.NET uygulamalarının hatalarını istiyorsanız [Uzak IIS bilgisayarda uzaktan hata ayıklama ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md).

##  <a name="BKMK_Attach_to_a_running_process"></a> Yerel makine üzerinde çalışan bir işlemi ekleme  
 Bir işlemin iliştirmek için işlemin adını bilmeniz gerekir (bkz [ortak senaryolar hata ayıklama](#BKMK_Scenarios) birkaç ortak işlem adları için).
  
1.  Visual Studio'da seçin **hata ayıklama > ekleme işlemi için** (veya basın **CTRL + ALT + P**).

    Hızlı bir şekilde bir işlem için bunun yerine yeniden istiyorsanız, bkz: [işlem için yeniden bağlayın](#BKMK_reattach).
  
2.  İçinde **ekleme işlemi için** iletişim kutusunda, gelen eklemek istediğiniz program Bul **kullanılabilir işlemler** listesi.  

     Hızlı bir şekilde istediğiniz işlemi seçin için işlem adının ilk harfi yazın. İşlem adını bilmiyorsanız, bkz: [ortak senaryolar hata ayıklama](#BKMK_Scenarios).
     
     ![DBG_Basics_Attach_To_Process](../debugger/media/DBG_Basics_Attach_To_Process.png "DBG_Basics_Attach_To_Process") 
  
     İşlemi farklı bir kullanıcı hesabı altında çalışıyorsa, seçin **işlemleri tüm kullanıcıları göster** onay kutusu.
  
3.  İçinde **ekleme** kutusunda, hata ayıklama kod türünü listelendiğinden emin olun. Varsayılan **otomatik** ayarı çalıştığında, hata ayıklamak istediğiniz kod türünü belirlemek. Kod türünü el ile ayarlamak için aşağıdakileri yapın  
  
    1.  İçinde **ekleme** kutusunda, **seçin**.  
  
    2.  İçinde **kod türünü seç** iletişim kutusu, tıklatın **bu kodu türleri hata ayıklama** ve hata ayıklamak için türlerini seçin.  
  
    3.  **Tamam**'ı tıklatın.  
  
4.  Tıklatın **Attach**.

##  <a name="BKMK_Attach_to_a_process_on_a_remote_computer"></a> Uzak bir bilgisayarda bir işlem ekleme  
 Bir işlemin iliştirmek için işlemin adını bilmeniz gerekir (bkz [ortak senaryolar hata ayıklama](#BKMK_Scenarios) birkaç ortak işlem adları için). IIS'ye dağıtılan ASP.NET uygulamaları için daha ayrıntılı yönergeler için bkz [Uzak IIS bilgisayarda uzaktan hata ayıklama ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md). Diğer uygulamalar için Görev Yöneticisi'nde işlemin adını bulmak mümkün olabilir.
  
 Kullandığınızda **ekleme işlemi için** iletişim kutusunda, uzaktan hata ayıklama için ayarlanmış olan başka bir bilgisayar seçebilirsiniz. Daha fazla bilgi için bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md). Uzak bir bilgisayar seçildiğinde, bu bilgisayar üzerinde çalışan kullanılabilir işlemlerin listesini görüntülemek ve bir veya daha çok hata ayıklama işlemi ekleyin.
  
 **Uzak bir bilgisayar seçmek için:**  

1. Visual Studio'da seçin **hata ayıklama > ekleme işlemi için** (veya basın **CTRL + ALT + P**).

    Hızlı bir şekilde bir işlem için bunun yerine yeniden istiyorsanız, bkz: [işlem için yeniden bağlayın](#BKMK_reattach).

2.  İçinde **ekleme işlemi için** uygun bir bağlantı türü iletişim kutusunda **aktarım** listesi. **Varsayılan** çoğu zaman için doğru bir ayardır.

    **Aktarım** ayarı devam ederse hata ayıklama oturumları arasında. 
  
3.  Kullanım **niteleyicisi** liste kutusu uzak bilgisayar adı aşağıdaki yöntemlerden birini seçin:  
  
    1.  Adı yazın **niteleyicisi** liste kutusu.
    
        >**Not** daha sonraki adımlarda uzak bilgisayar adını kullanarak bağlanamazsa, IP adresini kullanın. (Bağlantı noktası numarasını otomatik olarak işlem seçtikten sonra görünebilir. Ayrıca, el ile girebilirsiniz. Aşağıdaki çizimde 4020 varsayılan bağlantı noktası uzaktan hata ayıklayıcı'tür.)  

        Kullanmak istiyorsanız, **Bul** düğmesini gerekebilir [açmak UDP bağlantı noktası 3702](../debugger/remote-debugger-port-assignments.md) sunucusunda.
  
    2.  Bağlı açılan oku tıklatın **niteleyicisi** liste kutusu ve aşağı açılan listeden bilgisayarın adını seçin.  
  
    3.  Tıklatın **bulmak** düğmesine**niteleyicisi** açmak için liste **seçin uzaktan hata ayıklayıcı bağlantı** iletişim kutusu. **Seçin uzaktan hata ayıklayıcı bağlantı** iletişim kutusu, yerel alt ağ üzerinde bulunan tüm cihazlar ve Ethernet kablosu üzerinden bilgisayarınıza doğrudan bağlı herhangi bir aygıttan listeler. Bilgisayar veya ve ardından aygıtın tıklatın **seçin**. 
  
     **Niteleyicisi** ayarı devam ederse yalnızca hata ayıklama başarılı bir bağlantı ile bu niteleyici oluşuyorsa oturumları hata ayıklama arasında.
     
4.  Tıklatın **yenileme**.

      **Kullanılabilir işlemler** listesi açtığınızda otomatik olarak görüntülenir **işlemleri** iletişim kutusu. İşlemleri başlatmak ve iletişim kutusu açıkken arka planda durdurun. Ancak, içeriği her zaman geçerli değildir. Tıklayarak işlemler geçerli listesini görmek için herhangi bir zamanda listesini yenileyebilirsiniz **yenileme**. 
     
4.  İçinde **ekleme işlemi için** iletişim kutusunda, gelen eklemek istediğiniz program Bul **kullanılabilir işlemler** listesi.

     Hızlı bir şekilde istediğiniz işlemi seçin için işlem adının ilk harfi yazın. İşlem adını bilmiyorsanız, bkz: [ortak senaryolar hata ayıklama](#BKMK_Scenarios).
  
     İşlemi farklı bir kullanıcı hesabı altında çalışıyorsa, seçin **işlemleri tüm kullanıcıları göster** onay kutusu.
     
5.  Tıklatın **Attach**.

## <a name="BKMK_reattach"></a> İşlem için yeniden bağlayın

Hızlı bir şekilde, daha önce seçerek eklendiği işlemlere iliştirebilirsiniz **hata ayıklama > işlem için yeniden bağlayın...** (**Shift + Alt + P**). Bu komutu seçtiğinizde, hata ayıklayıcı son bağlı kullanarak işlemleri eklemek hemen çalışacaktır **ekleme işlemi için** iletişim kutusu.

Hata ayıklayıcı ilk önceki işlem kimliği eşleşecek şekilde deneyerek yeniden ve ardından, bu, önceki işlemin adına eşleştirerek başarısız olursa. Herhangi bir eşleşme bulunamazsa veya aynı ada sahip bulunan birden çok işlemleri ise sonra **ekleme işlemi için** doğru işlem seçebilmeniz için iletişim kutusu görüntülenir.

> [!NOTE]
> **İşlem için yeniden bağlayın** komutu Visual Studio 2017 ' yenidir.

## <a name="additional-info"></a>Ek bilgi

Birden çok programlar ayıkladığınız ancak herhangi bir anda yalnızca bir program hata ayıklayıcısı'ndaki etkin olduğu durumlarda eklenebilir. Etkin program ayarlayabileceğiniz **hata ayıklama konumu** araç veya **işlemleri** penceresi.  
  
Güvenilmeyen kullanıcı hesabı tarafından sahip olunan bir işlem ekleme çalışırsanız, bir güvenlik uyarısı iletişim kutusu onay görünür. Daha fazla bilgi için bkz: [güvenlik uyarısı: güvenilmeyen bir kullanıcıya ait bir işlem ekleme tehlikeli olabilir. Aşağıdaki bilgiler şüpheli görünüyorsa veya emin değilseniz, bu işlem için eklemeyin](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user.md).  
  
Bazı durumlarda, bir Uzak Masaüstü'nü (Terminal Hizmetleri) oturumunda ayıklarken **kullanılabilir işlemler** listesi tüm kullanılabilir işlemleri görüntülemez. Visual Studio sınırlı kullanıcı hesabı olan bir kullanıcı olarak çalıştırıyorsanız, **kullanılabilir işlemler** listesi, hizmetleri ve w3wp.exe dahil olmak üzere diğer sunucu işlemleri için kullanılan 0, oturumda çalışan işlemleri gösterilmez. Çalıştırarak sorunu çözebilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yönetici hesabı altında ya da çalıştırarak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Terminal Hizmetleri oturumunda yerine sunucu konsolundan. Bu geçici çözümler hiçbiri olası üçüncü seçenek çalıştırarak işleme iliştirilemiyor ise, `vsjitdebugger.exe -p` *ProcessId* Windows komut satırından. Tlist.exe kullanarak işlem kimliği belirleyebilirsiniz. Tlist.exe elde etmek için karşıdan yükleyip Windows hata ayıklama araçları için kullanılabilir [WDK ve WinDbg yüklemeleri](http://go.microsoft.com/fwlink/?LinkId=168279).

## <a name="BKMK_Scenarios"></a> Hata ayıklama senaryoları

Kullanılacak gerekip gerekmediğini belirlemenize yardımcı olması için **ekleme işlemi için** ve eklemek, hangi işlemin birkaç genel hata ayıklama senaryoları burada gösterilir (Bu liste geniş kapsamlı değildir). Daha fazla yönerge kullanılabiliyorsa, bağlantılar sunuyoruz.

Bazı uygulama türleri (örneğin, UWP uygulamaları) için doğrudan bir işlem adı ekleme yoktur ancak kullanmak **yüklü uygulama paketi Debug** menü seçeneğinin yerine (tabloya bakın).

> [!NOTE]
> Temel Visual Studio'da hata ayıklama hakkında daha fazla bilgi için bkz: [hata ayıklayıcısını kullanmaya başlama](../debugger/getting-started-with-the-debugger.md).

|Senaryo|Yönteminde hata ayıklama|İşlem adı|Notlar ve bağlantıları|
|-|-|-|-|
|Yerel makine üzerinde yönetilen veya yerel bir uygulama hata ayıklama|Kullanım ekleme işlemi için veya [standart hata ayıklama](../debugger/getting-started-with-the-debugger.md)|*Appname*.exe|İletişim kutusu hızlı bir şekilde erişmek için **CTRL + ALT + P** ve işlem adının ilk harfi yazın.|
|Hata Ayıklayıcı olmadan uygulama başlattıktan sonra yerel makinedeki ASP.NET uygulamalarında hata ayıklama|Kullanım için işlem ekleme|iiexpress.exe|Bu yük uygulamanızı hale getirmek yararlı olabilir daha hızlı gibi (örneğin) profil olduğunda. |
|Uzaktan hata ayıklama ASP.NET 4 veya bir IIS sunucusundaki 4.5|Uzak araçları kullanmak ve işleme ekleme|W3wp.exe|Bkz: [Uzak IIS bilgisayarda uzaktan hata ayıklama ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)|
|Uzaktan hata ayıklamayı ASP.NET Core IIS sunucusu|Uzak araçları kullanmak ve işleme ekleme|DotNet.exe|Uygulama dağıtımı için bkz: [IIS Yayımla](https://docs.asp.net/en/latest/publishing/iis.html). Hata ayıklama için bkz: [Uzak IIS bilgisayarda uzaktan hata ayıklama ASP.NET Çekirdeği](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)|
|Başka bir sunucu işlemi desteklenen uygulama türlerinde hata ayıklama|Uzak Araçlar (sunucu uzak ise) kullanın ve işleme ekleme|iexplore.exe veya diğer işlemler|Gerekirse, işlem belirlemenize yardımcı olması için Görev Yöneticisi'ni kullanın. Bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md) ve bu konunun sonraki bölümlerinde|
|Uzaktan hata ayıklama Windows masaüstü uygulaması|Uzak Araçlar ve F5|Yok| Bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md)|
|Uzaktan hata ayıklama Evrensel (UWP), OneCore, HoloLens ve IOT uygulama|Hata ayıklama yüklü uygulama paketi|Yok|Bkz: [yüklü uygulama paketi Debug](debug-installed-app-package.md) kullanmak yerine **ekleme işlemi**|
|Visual Studio'dan başlatmadı bir evrensel Windows uygulaması (UWP), OneCore, HoloLens ve IOT uygulama hata ayıklama|Hata ayıklama yüklü uygulama paketi|Yok|Bkz: [yüklü uygulama paketi Debug](debug-installed-app-package.md) kullanmak yerine **ekleme işlemi**|  
  
> [!NOTE]
>  C++'da yazılmış kod eklemek hata ayıklayıcı için kod yayma gerekiyor `DebuggableAttribute`. Bu, kod için otomatik olarak ile bağlayarak ekleyebilirsiniz [/ASSEMBLYDEBUG](/cpp/build/reference/assemblydebug-add-debuggableattribute) bağlayıcı seçeneği.

## <a name="what-debugger-features-can-i-use"></a>Hata ayıklayıcı özellikleri kullanabilir miyim?

Visual Studio hata ayıklayıcısı (kesme noktaları basarsa gibi) tüm özelliklerini kullanmak için bir işlem eklerken yürütülebilir tam olarak yerel kaynağı ve simgeleri eşleşmelidir (diğer bir deyişle, hata ayıklayıcı doğru yük kurabilmesi gerekir [simge (.pbd) dosyaları ](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)). Varsayılan olarak, bu hata ayıklama derlemesi gerektirir.

Uzaktan hata ayıklama senaryoları için Visual Studio'da açık kaynak kodunu (veya kaynak kodu bir kopyasını) olması gerekir. Uzak makinedeki derlenmiş uygulama ikili dosyaları gibi yerel makinede aynı derlemeden gelmesi gerekir.

Doğru simge dosyaları uygulamayla varsa bazı yerel hata ayıklama senaryolarında Visual Studio'da kaynağına erişimi olmayan ayıklanabilmesi (varsayılan olarak, bu, bir hata ayıklama derlemesi'gerektirir). Daha fazla bilgi için bkz: [simgesi belirtin ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).
  
##  <a name="BKMK_Troubleshoot_attach_errors"></a> Sorun giderme hataları ekleme  
 Hata ayıklayıcı çalışan bir işlemi ekler, işlem kodu bir veya daha fazla türlerini içerebilir. Hata ayıklayıcı için iliştirebilirsiniz kod türleri görüntülenir ve seçili **kod türünü seç** iletişim kutusu.  
  
 Bazı durumlarda, hata ayıklayıcı başarılı bir şekilde bir kod türü, ancak başka bir kod türü ekleyebilirsiniz. Bir uzak bilgisayarda çalışan bir işlemin iliştirmek çalışıyorsanız, bu durum oluşabilir. Uzak bilgisayara uzaktan hata ayıklama bileşenleri bazı kod türleri için kullanılabilir ancak başkalarının yüklü olabilir. Doğrudan veritabanı hata ayıklama için iki veya daha fazla işlem eklemeye çalışırsanız da oluşabilir. SQL hata ayıklama için yalnızca tek bir işlem ekleme destekler.  
  
 Hata ayıklayıcı, ancak bazı değil tüm kod türleri eklemek mümkün ise, hangi tür eklenemedi tanımlayan bir ileti görürsünüz.  
  
 Hata ayıklayıcı başarıyla en az bir kod türü bağlanıyorsa, işlemde hata ayıklamak için devam edebilirsiniz. Yalnızca başarılı bir şekilde bağlı kod türleri hata ayıklama mümkün olacaktır. Yukarıdaki örnek ileti komut dosyası kodu türü eklemek başarısız olduğunu gösterir. Bu nedenle, kod işlemi içinde hata ayıklama mümkün olmayacaktır. Komut dosyası kodu işlem içinde hala çalışır, ancak kesme noktalarını ayarlayın, verileri görüntülemek ya da komut dosyasında hata ayıklama diğer işlemleri gerçekleştirmek mümkün olmayacaktır.  
  
 Hata ayıklayıcı neden kodu türüne kullanıma açılamadı hakkında daha fazla bilgi edinmek istiyorsanız, yalnızca bu kod türünü yeniden deneyebilirsiniz.  
  
 **Neden kodu türünde eklenemedi hakkında ayrıntılı bilgi edinmek için**  
  
1.  İşlemden kullanımdan çıkarın. Üzerinde **hata ayıklama** menüsünde tıklatın **Detach tüm**.  
  
2.  Yalnızca tek bir kod türü seçme işlemi için yeniden bağlayın.  
  
    1.  İçinde **ekleme işlemi için** iletişim kutusunda, işlemde seçin **kullanılabilir işlemler** listesi.  
  
    2.  Tıklatın **seçin**.  
  
    3.  İçinde **kod türünü seç** iletişim kutusunda **bu kodu türleri hata ayıklama** ve eklenemedi kod türü. Başka bir kod temizleyin.  
  
    4.  **Tamam**'ı tıklatın. **Kod türünü seç** iletişim kutusunu kapatır.  
  
    5.  İçinde **ekleme işlemi için** iletişim kutusu, tıklatın **Attach**.  
  
     Bu süre, attach tamamen başarısız olur ve belirli bir hata iletisi alırsınız.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birden çok işlem hata ayıklama](../debugger/debug-multiple-processes.md)   
 [Tam zamanında hata ayıklama](../debugger/just-in-time-debugging-in-visual-studio.md)   
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)