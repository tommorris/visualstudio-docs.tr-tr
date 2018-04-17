---
title: Uzantı menü komutu ile oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- write a vspackage
- vspackage
- tutorials
- visual studio package
ms.assetid: f97104c8-2bcb-45c7-a3c9-85abeda8df98
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 00c80692929ac19b55f68b8aa20306f39ddceae6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="creating-an-extension-with-a-menu-command"></a>Menü komutu ile bir uzantısı oluşturma
Bu kılavuz, Not Defteri başlatan menü komutu ile uzantı oluşturulacağını gösterir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-menu-command"></a>Menü komutu oluşturma  
  
1.  Adlı VSIX proje oluşturma **FirstMenuCommand**. VSIX proje şablonu bulabilirsiniz **yeni proje** altında iletişim **Visual C# / genişletilebilirlik**.  
  
2.  Proje açıldığında adlı bir özel komut öğesi şablonu Ekle **FirstCommand**. İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **Ekle / yeni öğe**. İçinde **Yeni Öğe Ekle** iletişim kutusunda, Git **Visual C# / genişletilebilirlik** seçip **özel komut**. İçinde **adı** alan penceresinin alt kısmında, komut dosyası adı Değiştir **FirstCommand.cs**.  
  
3.  Projeyi derleyin ve hata ayıklamayı Başlat.  
  
     Visual Studio'nun deneysel örneği görüntülenir. Deneysel örneği hakkında daha fazla bilgi için bkz: [deneysel örneği](../extensibility/the-experimental-instance.md).  
  
4.  Deneysel örneğinde açmak **Araçlar / Uzantılar ve güncelleştirmeler** penceresi. Görmeniz gerekir **FirstMenuCommand** burada uzantı. (Açarsanız **Uzantılar ve güncelleştirmeler** Visual Studio, çalışma örneğinde, görmezsiniz **FirstMenuCommand**).  
  
     Şimdi gidin **Araçları** deneysel örneği menüde. Görmeniz gerekir **çağırma FirstCommand** komutu. Bu noktada yalnızca "FirstCommandPackage içinde FirstMenuCommand.FirstCommand.MenuItemCallback()" bildiren bir ileti kutusunu getirir. Sonraki bölümde bu komut gerçekte not defteri başlangıç nasıl göreceğiz.  
  
## <a name="changing-the-menu-command-handler"></a>Menü komut işleyici değiştirme  
 Şimdi şimdi Notepad başlatmak için komut işleyici güncelleştirin.  
  
1.  Hata ayıklamayı durdurun ve çalışma Örneğiniz için Visual Studio geri dönün. FirstCommand.cs dosyasını açın ve aşağıdaki ekleme deyimini kullanarak:  
  
    ```csharp  
    using System.Diagnostics;  
    ```  
  
2.  Özel FirstCommand Oluşturucusu bulun. Burada komutu komut hizmeti sayfaya ve komut işleyici belirtilen budur. Komut işleyici adını StartNotepad için aşağıdaki gibi değiştirin:  
  
    ```csharp  
    private FirstCommand(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException(nameof(package));  
        }  
  
        this.package = package;  
  
         OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
        if (commandService != null)  
        {  
            CommandID menuCommandID = new CommandID(CommandSet, CommandId);  
            // Change to StartNotepad handler.  
            MenuCommand menuItem = new MenuCommand(this.StartNotepad, menuCommandID);  
            commandService.AddCommand(menuItem);  
        }  
    }  
    ```  
  
3.  MenuItemCallback yöntemi kaldırın ve Not Defteri yalnızca başlayacak bir StartNotepad yöntemi ekleyin:  
  
    ```csharp  
    private void StartNotepad(object sender, EventArgs e)  
    {  
        Process proc = new Process();  
        proc.StartInfo.FileName = "notepad.exe";  
        proc.Start();  
    }  
    ```  
  
4.  Şimdi deneyin. Ne zaman projenin hata ayıklamayı Başlat ve tıklatın **araçları / çağırma FirstCommand**, Not Defteri gündeme örneğini görmeniz gerekir.  
  
     Bir örneğini kullanabilir <xref:System.Diagnostics.Process> herhangi bir yürütülebilir dosya, yalnızca not defteri çalıştırmak için sınıf. Örneğin calc.exe ile deneyin.  
  
## <a name="cleaning-up-the-experimental-environment"></a>Deneysel ortamı temizleniyor  
 Birden çok uzantı geliştirme veya yalnızca sonuçlar uzantısı kodunuzu farklı sürümleri ile keşfetme, Deneysel ortamınızı gerektiği şekilde çalışmamaya başlayabilir. Bu durumda, sıfırlama komut dosyasını çalıştırmanız gerekir. Çağrılır **Visual Studio 2015 deneysel örneği sıfırlama**, ve Visual Studio SDK'sı bir parçası olarak gelir. Baştan başlamak için bu komut dosyası Deneysel ortamı uzantılarınızın tüm başvuruları kaldırır.  
  
 Bu komut dosyası iki yoldan biriyle alabilirsiniz:  
  
1.  Masaüstünden Bul **Visual Studio 2015 deneysel örneği sıfırlama**.  
  
2.  Komut satırından aşağıdakileri çalıştırın:  
  
    ```  
    <VSSDK installation>\VisualStudioIntegration\Tools\Bin\CreateExpInstance.exe /Reset /VSInstance=14.0 /RootSuffix=Exp && PAUSE  
  
    ```  
  
## <a name="deploying-your-extension"></a>Uzantınızı dağıtma  
 İstediğiniz şekilde çalışan aracı uzantınızı sahip olduğunuza göre arkadaşlarınıza ve iş arkadaşlarınızı ile paylaşma hakkında düşünmek için zaman yapılır. Visual Studio 2015 yüklü olduğu sürece bu kolay olmasıdır. Yapmanız gereken tek şey, yerleşik .vsix dosya göndermek. (Sürüm modu yapı emin olun.)  
  
 Bu uzantı için .vsix dosya FirstMenuCommand bin dizinindeki bulabilirsiniz. Özellikle, yayın yapılandırma yerleşik varsayıldığında, onu olacaktır:  
  
 **\<Kod dizini > \FirstMenuCommand\FirstMenuCommand\bin\Release\ FirstMenuCommand.vsix**  
  
 Uzantıyı yüklemek için Visual Studio tüm açık örnekleri kapatın, sonra da getirir .vsix dosyasını çift tıklatın arkadaşınız gereken **VSIX yükleyici**. Dosyalar kopyalanır **%LocalAppData%\Microsoft\VisualStudio\14.0\Extensions** dizini.  
  
 Visual Studio'yu yeniden arkadaşınız getirir, kendisinin FirstMenuCommand uzantısı'nda bulabilirsiniz **Araçlar / Uzantılar ve güncelleştirmeler**. Müşterinizle gidebilirsiniz **Uzantılar ve güncelleştirmeler** kaldırmak veya çok uzantıyı devre dışı bırakmak için.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bu kılavuz bir Visual Studio uzantısı ile ne yapabileceğinizi yalnızca küçük bir bölümün göstermiştir. Visual Studio uzantıları ile yapabileceğiniz diğer (makul kolay) şeyler kısa bir listesi aşağıda verilmiştir:  
  
1.  Daha fazla pek çok basit menü komutu ile yapabilirsiniz:  
  
    1.  Kendi simgesini ekleyin: [menü komutlarını simgeleri ekleme](../extensibility/adding-icons-to-menu-commands.md)  
  
    2.  Menü komut metnini değiştirme: [menü komutu metin değiştirme](../extensibility/changing-the-text-of-a-menu-command.md)  
  
    3.  Menü kısayolu komut ekleme: [klavye kısayolları menü öğelerine bağlama](../extensibility/binding-keyboard-shortcuts-to-menu-items.md)  
  
2.  Komutları, menüleri ve araç çubuklarını farklı türde ekleyin: [genişletme menüleri ve komutları](../extensibility/extending-menus-and-commands.md)  
  
3.  Araç pencereleri ekleyin ve yerleşik windows Visual Studio aracı genişletmek: [genişletme ve özelleştirme araç pencereleri](../extensibility/extending-and-customizing-tool-windows.md)  
  
4.  IntelliSense, kod önerileri eklemek ve varolan diğer özellikleri kod düzenleyicileri: [Düzenleyicisi ve dil Hizmetleri genişletme](../extensibility/extending-the-editor-and-language-services.md)  
  
5.  Dahili seçenekleri ve özellik sayfaları ve kullanıcı ayarlarını ekleyin: [genişletme özellikleri ve özellik penceresi](../extensibility/extending-properties-and-the-property-window.md) ve [genişletme kullanıcı ayarları ve seçenekleri](../extensibility/extending-user-settings-and-options.md)  
  
 Yeni bir proje türü oluşturma gibi biraz daha fazla iş, diğer tür uzantıların gerektirir ([projeleri genişletme](../extensibility/extending-projects.md)), düzenleyici yeni bir tür oluşturma ([özel düzenleyici oluşturma ve tasarımcıları](../extensibility/creating-custom-editors-and-designers.md)), veya yalıtılmış bir Kabuğu'nda dahili uygulama: [Visual Studio yalıtılmış Kabuk](../extensibility/visual-studio-isolated-shell.md)