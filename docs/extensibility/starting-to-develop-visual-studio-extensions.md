---
title: Visual Studio uzantılar geliştirmek üzere başlangıç | Microsoft Docs
ms.custom: ''
ms.date: 09/18/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- getting started, Visual Studio integration
- Visual Studio, integration
ms.assetid: 8fe5e2ab-a424-4173-9d39-dd082c4d58d0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 44403b5d60fc13666ffc6ec00558b80ef3a50ea9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31144469"
---
# <a name="starting-to-develop-visual-studio-extensions"></a>Visual Studio uzantılar geliştirmek üzere başlatılıyor
Visual Studio uzantısı önce hiçbir zaman yazdıysanız bazı sorular'de vardır. Biz en yaygın olanları burada listelenen bazı. Aradığınız bilgileri görmüyorsanız, geri bildirim düğmelerini kullanın (**bu sayfayı yardımcı oldu?** ekranın altındaki), istediğiniz için isteyebilir.  
  
## <a name="what-software-do-i-need-to-develop-visual-studio-extensions"></a>Visual Studio uzantılar geliştirmek üzere hangi yazılım gerekiyor mu?  
 Visual Studio uzantılar geliştirmek için Visual Studio yanı sıra Visual Studio SDK yüklemeniz gerekir. Visual Studio SDK'sı normal kurulumunun bir parçası yükleyebilir veya daha sonra yükleyebilirsiniz. Visual Studio SDK'sını yükleme hakkında daha fazla bilgi için bkz: [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="what-kinds-of-things-can-i-do-with-visual-studio-extensions"></a>Visual Studio uzantıları ile ne tür şeyler yapabilirim?  
 Visual Studio uzantıları farklı imagining için geldiğinde sky sınırı kullanıcının. Elbette, çoğu uzantıları kod yazma ile yapmak için bir şey sahip ancak bu durumda olması gerekmez. Oluşturabileceğiniz uzantıları türlerini bazı örnekleri şunlardır:  
  
-   Visual Studio'da söz dizimi renklendirme, IntelliSense ve derleyici ve hata ayıklama desteği bulunmayan dil desteği  
  
-   Çekirdek genişletmek üretkenlik araçları IDE deneyimi ek şablonlar, kodu yeniden düzenleme, yeni iletişim kutuları veya araç pencereleri  
  
-   Etki alanına özgü tasarımcıları tasarım veya Bulut veri desteği gibi senaryolar için  
  
 Uzantıları örnekler için kullanıma [Visual Studio Market'te](https://marketplace.visualstudio.com/vs). Birçok Uzantılar açık kaynaklıdır ve Market kendi GitHub deposuna bağlantılarını içerir. 
  
## <a name="which-visual-studio-features-can-i-extend"></a>Visual Studio özellikleri ı genişletebilir miyim?  
 Teorik olarak, Visual Studio neredeyse herhangi bir kısmını genişletebilirsiniz: menüleri, araç çubukları, komutları, windows, çözümleri, projeler, düzenleyiciler ve benzeri.  
  
 Uygulamada, çoğu kişi genişletmek istediğiniz özellikleri komutları, menüleri ve araç çubukları, windows, IntelliSense ve projeleri olduğunu buldunuz. İlgili bölümlerin bağlantıları aşağıda verilmiştir:  
  
-   [Menüleri ve komutları genişletme](../extensibility/extending-menus-and-commands.md): Visual Studio menüleri ve araç çubuklarını kendi öğeleri ekleyin. Yeni Visual Studio işlev veya kendi dış yardımcı uygulamalar başlatmak için bunları kullanabilirsiniz. Özel kısayol menüsü öğelerinizi de sağlayabilirsiniz.  
  
-   [Genişletme ve Özelleştirme Aracı Windows](../extensibility/extending-and-customizing-tool-windows.md): mevcut aracı windows genişletmek veya kendi araç pencereleri oluşturun. Örneğin, yeni özellikleri ekleyebilirsiniz **özellikleri**, veya ek özellikler eklemek için yeni bir araç penceresi oluşturabilirsiniz.  
  
-   [Düzenleyici ve dil hizmeti uzantıları](../extensibility/editor-and-language-service-extensions.md): kendi özelleştirmeleri için Visual Studio dilleri sağlanan IntelliSense ekleyin veya yeni programlama dilleri için destek oluşturun. Yeni deyim tamamlamalar, öneriler ve yeni Quıckınfo araç ipuçları oluşturabilirsiniz. Ampullerle, yeniden düzenleme önerileri ekleyebilir ve yeni programlama dilleri desteklemek kod giderir.  
  
-   [Projeleri Genişletme](../extensibility/extending-projects.md)  
  
-   [Kullanıcı Ayarlarını ve Seçeneklerini Genişletme](../extensibility/extending-user-settings-and-options.md)  
  
-   [Özellikleri ve Özellik Penceresini Genişletme](../extensibility/extending-properties-and-the-property-window.md)  
  
-   [Visual Studio’nun Diğer Bölümlerini Genişletme](../extensibility/extending-other-parts-of-visual-studio.md)  
  
-   [Visual Studio Yalıtılmış Kabuğu](../extensibility/visual-studio-isolated-shell.md)  
  
##  <a name="BKMK_ProjectTemplate"></a> Hangi proje şablonları VSSDK tarafından sağlanan?  
 İki ana uzantıları VSPackages ve MEF uzantıları türleridir. Genel olarak, VSPackage uzantıları kullanan veya komutları, aracı windows ve projeleri genişletme uzantıları için kullanılır. MEF uzantıları genişletme veya Visual Studio düzenleyicisinde özelleştirmek için kullanılır.  
  
 Visual C# ve Visual Basic uzantıları için menü komutlarını, aracı windows ve düzenleyici uzantıları oluşturduğunuz yeni öğe şablonları ile birlikte kullanabileceğiniz bir boş VSIX proje şablonu VSSDK sağlar. Bu şablon paket proje şablonları, kod parçacıkları ve diğer yapıları, dağıtım diğer kullanıcılar için de kullanabilirsiniz.  
  
 C++ için VSPackage Sihirbazı'nı menü komutlarını, aracı windows ve özel düzenleyiciler eklemek için kod sağlar.  
  
 Yalıtılmış Kabuk şablon uzantı marka ve kendi olarak dağıtmak Visual Studio Kabuğu sürümünde paketlemek için kullanılır. Aşağıdaki konular her uzantı türü ile çalışmaya nasıl başlayacağınız gösterilmektedir:  
  
-   Menü komutları: [menü komutu ile bir uzantısı oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
-   Aracı windows: [bir uzantısı bir araç penceresi oluşturma](../extensibility/creating-an-extension-with-a-tool-window.md)  
  
-   Düzenleyici uzantıları: [bir düzenleyici öğesi şablonuyla bir uzantısı oluşturma](../extensibility/creating-an-extension-with-an-editor-item-template.md)  
  
-   Temel VSPackages: [VSPackage ile bir uzantısı oluşturma](../extensibility/creating-an-extension-with-a-vspackage.md)  
  
-   VSIX proje şablonu: [VSIX proje şablonu ile çalışmaya başlama](../extensibility/getting-started-with-the-vsix-project-template.md)  
  
-   Visual Studio shell yalıtılmış: [izlenecek yol: temel bir yalıtılmış Kabuk uygulama oluşturma](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)  
  
## <a name="how-do-i-get-my-extension-to-look-like-visual-studio"></a>Visual Studio gibi aramak için my uzantısı nasıl sağlarım?  
 Uzantı için kullanıcı Arabirimi tasarlamak için harika ipuçları alın [Visual Studio kullanıcı deneyimi yönergeleri](../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md).  
  
## <a name="where-can-i-find-examples-of-vssdk-code"></a>VSSDK kod örnekleri nereden bulabilirim?  
 Önceki bölümde listelenen bağlantıların her birini belirli özellikleri uygulamak nasıl gösteren adım adım izlenecek yollar vardır. Açık kaynak VSSDK örnekleri github'da bulabilirsiniz [Visual Studio örnekleri](https://github.com/Microsoft/VSSDK-Extensibility-Samples).  
  
## <a name="how-can-i-distribute-my-extension"></a>My uzantısını nasıl dağıtma?  
 Uzantınızı başka bir bilgisayara yüklemek ya da çift tıklatarak yükleyin .vsix dosyası olarak arkadaşlarınıza gönderebilir. VSIX paketler hakkında daha fazla bilgi bulabilirsiniz [sevkiyat Visual Studio uzantıları](../extensibility/shipping-visual-studio-extensions.md).  
  
 Uzantınızı Market'te Visual Studio, Visual Studio müşteriler çok sayıda görünür hale getirir, yayımlayabilirsiniz. Market uzantısı paketleme ilişkin bir örnek için bkz: [izlenecek yol: Visual Studio uzantısı yayımlama](../extensibility/walkthrough-publishing-a-visual-studio-extension.md). Market'te yayımlamak için yapmanız gerekenler hakkında daha fazla bilgi için bkz: [ürünleri ve Visual Studio uzantılarını](/vsts/integrate/ide/extensions/overview).
