---
title: Uzaktan hata ayıklama bir C# veya Visual Studio'da VB projesi | Microsoft Docs
ms.custom: remotedebugging
ms.date: 08/14/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords:
- remote debugging, setup
ms.assetid: a9753fbb-e7f4-47f0-9dbe-9de90c6c8457
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: a7c6892eb43191c69608e66b05f8177777e3e006
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="remote-debugging-a-c-or-visual-basic-project-in-visual-studio"></a>Uzaktan Visual Studio C# veya Visual Basic projesinde hata ayıklama
Başka bir bilgisayara dağıtılan bir Visual Studio uygulama hatalarını ayıklamak için yüklemek ve uygulamanızı dağıtıldığı bilgisayarda Uzak araçları çalıştırmak, projeniz Visual Studio'dan uzak bilgisayara bağlanmak için yapılandırın ve uygulamanızı çalıştırın.

![Uzaktan hata ayıklayıcı bileşenleri](../debugger/media/remote-debugger-client-apps.png "Remote_debugger_components")
  
Uzaktan hata ayıklama Evrensel Windows uygulamaları (UWP) hakkında daha fazla bilgi için bkz: [yüklü uygulama paketi Debug](debug-installed-app-package.md).

## <a name="requirements"></a>Gereksinimler

Windows 7 ve daha yeni uzaktan hata ayıklayıcı desteklenir (telefon değil) ve Windows Server 2008 Service Pack 2 ile başlayarak Windows Server sürümleri. Gereksinimlerinin tam listesi için bkz: [gereksinimleri](../debugger/remote-debugging.md#requirements_msvsmon).

> [!NOTE]
> Bir proxy üzerinden bağlı iki bilgisayar arasında hata ayıklama desteklenmiyor. Bir yüksek gecikme veya çevirmeli Internet gibi düşük bant genişliği bağlantısı veya Internet üzerinden ülkelerde arasında hata ayıklama önerilmez ve başarısız olabilir veya edilemeyecek yavaş.
  
## <a name="download-and-install-the-remote-tools"></a>Uzak araçları yükleyip

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

> [!TIP]
> Bazı senaryolarda, bir dosya paylaşımından uzaktan hata ayıklayıcı çalıştırmak için etkili olabilir. Daha fazla bilgi için bkz: [dosya paylaşımından uzaktan hata ayıklayıcı çalıştırmak](../debugger/remote-debugging.md#fileshare_msvsmon).
  
## <a name="BKMK_setup"></a> Uzaktan hata ayıklayıcı ayarlayın

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> Gerektiğinde ek kullanıcılar için izinler eklemek için kimlik doğrulaması modunu değiştirme veya bağlantı noktası numarası uzaktan hata ayıklayıcı için bkz: [uzaktan hata ayıklayıcı yapılandırma](../debugger/remote-debugging.md#configure_msvsmon).
  
## <a name="remote_csharp"></a> Uzaktan hata ayıklama proje
Hata ayıklayıcıyı uzak makineye Visual C# veya Visual Basic Masaüstü uygulamaları dağıtamazsınız, ancak hala bunları aşağıdaki gibi uzaktan hata ayıklama. Aşağıdaki yordam adlı bir bilgisayarda hata ayıklama istediğinizi varsayar **MJO DL**, aşağıdaki çizimde gösterildiği gibi.
  
1.  Adlı bir WPF projesi oluşturma **MyWpf**.  
  
2.  Bir kesme noktası yere kolayca ulaşıldığında kodda ayarlayın.  
  
     Örneğin, bir düğme işleyicisi bir kesme noktası ayarlayabilirsiniz. Bunu yapmak için MainWindow.xaml, açın ve Araç Kutusu'ndan düğme denetimi ekleyin, sonra onun işleyici açmak için düğmesini çift tıklayın.
  
3.  Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **özellikleri**.  
  
4.  Üzerinde **özellikleri** sayfasında, **hata ayıklama** sekmesi.  
  
     ![RemoteDebuggerCSharp](../debugger/media/remotedebuggercsharp.png "RemoteDebuggerCSharp")  
  
5.  Emin olun **çalışma dizini** metin kutusu boştur.  
  
6.  Seçin **kullanım uzak makine**ve türü **MJO-DL:4022** metin kutusuna. (4022 uzaktan hata ayıklayıcı penceresinde gösterilen bağlantı noktası numarasıdır. Bağlantı noktası numarasını 2'de Visual Studio her sürümü artırır).
  
7.  Olduğundan emin olun **yerel kod hata ayıklamayı etkinleştir** seçilmemiş.  
  
8.  Projeyi oluşturun.  
  
9. Aynı yol olan uzak bilgisayarda bir klasör oluşturun **hata ayıklama** Visual Studio bilgisayarınızda klasörü:  **\<kaynak yolu > \MyWPF\MyWPF\bin\Debug**.  
  
10. Yalnızca Visual Studio bilgisayarınızdan yeni oluşturulan klasöre uzak bilgisayarda oluşturulan yürütülebilir kopyalayın.
  
    > [!CAUTION]
    >  Değişiklikler kod veya yeniden yapmayın (veya bu adımı tekrarlamalısınız). Uzak makineye kopyaladığınız yürütülebilir yerel kaynağı ve simgeleri tam olarak eşleşmelidir.

    Proje el ile kopyalamanız, Xcopy, Robocopy, Powershell veya diğer seçenekleri kullanın.
  
11. Uzaktan hata ayıklayıcı hedef makinede çalıştığından emin olun (değilse, arama **uzaktan hata ayıklayıcı** içinde **Başlat** menüsü). Uzaktan hata ayıklayıcı penceresini şöyle görünür.  
  
     ![RemoteDebuggerWindow](../debugger/media/remotedebuggerwindow.png "RemoteDebuggerWindow")  
  
12. Visual Studio'da hata ayıklamayı başlatma (**hata ayıklama > hata ayıklamayı Başlat**, veya **F5**).  
  
13. İstenirse, uzak makineye bağlanmak için ağ kimlik bilgilerini girin.  
  
     Gerekli kimlik bilgilerini, ağınızın güvenlik yapılandırmasına bağlı olarak değişir. Örneğin, bir etki alanı bilgisayarında etki alanı adınızı ve parolanızı girebilirsiniz. Bir etki alanı dışı makinede, makine adı ve geçerli kullanıcı hesabı adı gibi girebilir **MJO-DL\name@something.com**, doğru parolayı yanı sıra.

     WPF uygulamanın ana penceresinde uzak bilgisayarda açık olduğunu görmeniz gerekir.
  
14. Gerekirse, kesme noktası isabet eylemi uygulayın. Kesme noktası etkin olduğunu görmeniz gerekir. Aksi takdirde uygulama simgelerini yüklenen henüz. Yeniden deneyin ve bu işe yaramazsa, simgeler yükleme hakkında bilgi almak ve onları nasıl sorun giderme [anlama simge dosyaları ve Visual Studio'nun simge ayarları](http://blogs.msdn.com/b/visualstudioalm/archive/2015/01/05/understanding-symbol-files-and-visual-studio-s-symbol-settings.aspx).
  
15. Visual Studio makinede yürütme kesme noktasında durdurdu görmeniz gerekir.
  
 Uygulama tarafından kullanılması gereken kod olmayan dosyalar varsa, Visual Studio projesinde eklemeniz gerekir. Ek dosyalar için bir proje klasör oluşturun (içinde **Çözüm Gezgini**, tıklatın **Ekle > Yeni bir klasör**). Klasöre dosya ekleme (içinde **Çözüm Gezgini**, tıklatın **Ekle > varolan öğeyi**, dosyaları seçin). Üzerinde **özellikleri** sayfasında her dosya için **çıktı dizinine Kopyala** için **her zaman Kopyala**.

## <a name="set-up-debugging-with-remote-symbols"></a>Uzak simgeleri ile hata ayıklama Kurulumu 

[!INCLUDE [remote-debugger-symbols](../debugger/includes/remote-debugger-symbols.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio’da hata ayıklama](../debugger/index.md)  
 [Hata ayıklayıcı özelliği turu](../debugger/debugger-feature-tour.md)   
 [Uzaktan hata ayıklama için Windows Güvenlik duvarını yapılandırma](../debugger/configure-the-windows-firewall-for-remote-debugging.md)   
 [Uzaktan hata ayıklayıcı bağlantı noktası atamaları](../debugger/remote-debugger-port-assignments.md)   
 [Uzaktan bir uzak IIS bilgisayarda ASP.NET hata ayıklama](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)