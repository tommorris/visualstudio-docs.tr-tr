---
title: 'Sık sorulan sorular: Eklentiler VSPackage Uzantıları dönüştürme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 3a01d333-6e31-423f-ae06-5091a4fcb7a9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: daec495ee71bf27bc40174b74cd95a6df47c247f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134051"
---
# <a name="faq-converting-add-ins-to-vspackage-extensions"></a>SSS: Eklentileri VSPackage Uzantılarına Dönüştürme
Eklentiler artık kullanım dışı bırakılmıştır. Yeni bir Visual Studio uzantısı yapmak için bir VSIX uzantısı oluşturmanız gerekir. Burada, VSIX uzantısı için bir Visual Studio eklentisi dönüştürmek hakkında sık sorulan bazı sorular için yanıtlar bulunmaktadır.  
  
> [!WARNING]
>  C# ve Visual Basic projeleri için Visual Studio 2015'te başlangıç VSIX proje kullanın ve öğe şablonları menü komutları, aracı windows ve VSPackages ekleyin. Daha fazla bilgi için bkz: [Visual Studio 2015 SDK yenilikler](../extensibility/what-s-new-in-the-visual-studio-2015-sdk.md).  
  
> [!IMPORTANT]
>  Çoğu durumda, eklenti kodunuzun VSPackage proje öğesi içeren bir VSIX proje yalnızca aktarabilir. Çağırarak DTE Otomasyon nesnesi alabilirsiniz <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> içinde <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> yöntemi.  
>   
>  `DTE2 dte = (DTE2)GetService(typeof(DTE));`  
>   
>  Daha fazla bilgi için bkz: [nasıl ı çalıştırabilirsiniz eklenti kodumu bir VSPackage?](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_RunAddin) aşağıda.  
  
## <a name="what-software-do-i-need-to-develop-vsix-extensions"></a>VSIX uzantılar geliştirmek üzere hangi yazılım gerekiyor mu?  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="wheres-the-extension-documentation"></a>Uzantı nerededir?  
 İle başlayan [Visual Studio uzantılar geliştirmek üzere başlangıç](../extensibility/starting-to-develop-visual-studio-extensions.md). MSDN'de VSSDK uzantısı geliştirme hakkında diğer makaleler bir ilgilidir.  
  
## <a name="can-i-convert-my-add-in-project-to-a-vsix-project"></a>Eklenti proje VSIX projeye dönüştürebilir miyim?  
 VSIX projelerinde kullanılan mekanizmaları eklenti projelerinde olanlarla aynı olmadığından bir eklenti projesi doğrudan bir VSIX proje dönüştürülemiyor. VSIX proje şablonu yanı sıra, doğru proje öğesi şablonları görece kolay hale getirmek ve bir VSIX uzantısı olarak çalışan kolaylaştırır kodu çok vardır.  
  
##  <a name="BKMK_StartDeveloping"></a> VSIX Uzantıları Geliştirme nasıl başlamanız gerekir?  
 Menü komutu sahip bir VSIX nasıl yaptığınız aşağıda verilmiştir:  
  
#### <a name="to-make-a-vsix-extension-that-has-a-menu-command"></a>Menü komutu sahip bir VSIX uzantısı yapma  
  
1.  VSIX projesi oluşturun. (**Dosya**, **yeni**, **proje**, veya türü **proje** içinde **hızlı başlatma** penceresi). Buna **yeni proje** iletişim kutusunda, genişletin **Visual C# / genişletilebilirlik** veya **Visual Basic / genişletilebilirlik** seçip **VSIX proje**.) Proje adı **TestExtension** ve bunun için bir konum belirtin.  
  
2.  Ekleme bir **özel komut** proje öğesi şablonu. (Proje düğümüne sağ tıklayın **Çözüm Gezgini** seçip **Ekle / yeni öğe**. Buna **yeni proje** Visual C# veya Visual Basic, Seç iletişim kutusunda **genişletilebilirlik** düğümü ve select **özel komut**.)  
  
3.  Derleme ve projeyi hata ayıklama modunda çalıştırmak için F5 tuşuna basın.  
  
     Visual Studio ikinci bir örneğini görüntülenir. Bu ikinci örneği Deneysel örneği adı verilir ve kod yazmak için kullanmakta olduğunuz Visual Studio örneğini aynı ayarlara sahip olmayabilir. İlk kez deneysel örneği çalıştırdığınızda VS Online'a oturum açın ve tema ve profil belirtin istenir.  
  
     Üzerinde **Araçları** menüde (deneysel örneği) adlı bir düğme görmeniz gerekir **My komut adı**. Bu düğme seçtiğinizde, bir ileti görüntülenmelidir: **içinde TestVSPackagePackage.MenuItemCallback()**.  
  
##  <a name="BKMK_RunAddin"></a> Bir VSPackage eklenti kodumu nasıl çalıştırabilirim?  
 Eklenti kodu genellikle iki yoldan biriyle çalıştırır:  
  
-   Menü komutu tarafından tetiklenen (kod `IDTCommandTarget.Exec` yöntemi)  
  
-   Otomatik olarak girişte (kod `OnConnection` olay işleyicisi.)  
  
 Bir VSPackage aynı şeyler yapabilirsiniz. Geri arama yönteminde bazı eklenti kodu ekleme şöyledir:  
  
#### <a name="to-implement-a-menu-command-in-a-vspackage"></a>Menü komutu bir VSPackage uygulamak için  
  
1.  Menü komutu sahip bir VSPackage oluşturun. (Daha fazla bilgi için bkz: [uzantı menü komutu ile oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md).)  
  
2.  VSPackage tanımını içeren dosyayı açın. (C# projesinde, bunun  *\<projenizin adına >* Package.cs.)  
  
3.  Aşağıdakileri ekleyin `using` deyimlerini dosyaya:  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
4.  Bul `MenuItemCallback` yöntemi. Bir çağrı ekleyin <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> almak için <xref:EnvDTE80.DTE2> nesnesi:  
  
    ```csharp  
    DTE2 dte = (DTE2)GetService(typeof(DTE));  
    ```  
  
5.  Eklentiniz olan kodu ekleyin, `IDTCommandTarget.Exec` yöntemi. Örneğin, yeni bir bölmesine ekler biraz kod işte **çıkış** penceresini açın ve yeni bölmesinde "Bazı metin" yazdırır.  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        DTE2 dte = (DTE2) GetService(typeof(DTE));  
        OutputWindow outputWindow = dte.ToolWindows.OutputWindow;  
  
        OutputWindowPane outputWindowPane = outputWindow.OutputWindowPanes.Add("A New Pane");  
        outputWindowPane.OutputString("Some Text");  
    }  
  
    ```  
  
6.  Oluşturun ve bu projeyi çalıştırın. F5 tuşuna basın veya seçin **Başlat** üzerinde **hata ayıklama** araç. Visual Studio deneysel örneğinde **Araçları** menü adlı bir düğmeye sahip olmalıdır **My komut adı**. Bu düğme, sözcükler seçtiğinizde **bazı metin** görüntülenmelidir bir **çıkış** bölme. (Açmak zorunda kalabilirsiniz **çıkış** penceresi.)  
  
 Başlangıçta çalıştırmak kodunuzu da sahip olabilirsiniz. Ancak, bu yaklaşım VSPackage uzantıları için genellikle önerilmez. Çok fazla uzantıları Visual Studio başladığında yüklemeye çalışırsanız, başlangıç zamanı önemli ölçüde uzun olabilir. Yalnızca bazı koşul (açılmakta olan bir çözümü gibi) karşılandığında VSPackage otomatik olarak yüklenmesini daha iyi bir uygulamadır.  
  
 Bu yordamda, bir çözüm açıldığında otomatik olarak yükleyen bir VSPackage eklenti kodu çalıştırmak gösterilmiştir:  
  
#### <a name="to-autoload-a-vspackage"></a>AutoLoad bir VSPackage  
  
1.  VSIX proje ile Visual Studio Paketi proje öğesi oluşturun. (Bunu yapma adımları için bkz: [nasıl geliştirme VSIX uzantıları başlamalıyım?](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_StartDeveloping). Yalnızca Ekle **Visual Studio Paketi** öğesi yerine proje.) VSIX proje adı **TestAutoload**.  
  
2.  TestAutoloadPackage.cs açın. Paket sınıfı burada bildirilmiş satırı bulun:  
  
    ```csharp  
    public sealed class <name of your package>Package : Package  
    ```  
  
3.  Bu satırın üzerine öznitelikleri kümesidir. Bu öznitelik ekleyin:  
  
    ```csharp  
    [ProvideAutoLoad(UIContextGuids80.SolutionExists)]  
    ```  
  
4.  Bir kesme noktası kümesinde `Initialize()` yöntemi ve (F5) hata ayıklamayı Başlat.  
  
5.  Deneysel örneğinde bir projeyi açın. VSPackage yükleyeceğini ve, kesme noktası isabet.  
  
 Alanlarını kullanarak, VSPackage yükleneceği diğer bağlamlarda belirtebilirsiniz <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80>. Daha fazla bilgi için bkz: [yüklenirken VSPackages](../extensibility/loading-vspackages.md).  
  
## <a name="how-can-i-get-the-dte-object"></a>DTE nesnesine nasıl alabilirim?  
 Eklentiniz UI görüntülemiyorsa — menü komutları, araç çubuğu düğmeleri veya araç pencereleri — kodunuzu olarak kullanmak mümkün olabilir-VSPackage DTE Otomasyon nesne get kadar uzun. İşte nasıl:  
  
#### <a name="to-get-the-dte-object-from-a-vspackage"></a>Bir VSPackage DTE nesnesini almak için  
  
1.  Visual Studio Paketi öğesi şablona sahip bir VSIX proje ile Ara  *\<proje adı >* Package.cs dosya. Bu türeyen sınıftır <xref:Microsoft.VisualStudio.Shell.Package>; Visual Studio ile etkileşim yardımcı olabilir. Bu durumda, kullandığınız kendi <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> almak için <xref:EnvDTE80.DTE2> nesnesi.  
  
2.  Bunlar eklemek `using` deyimleri:  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
3.  Bul `Initialize` yöntemi. Bu yöntem paket Sihirbazı'nda belirtilen komut işler. Bir çağrı ekleyin <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> DTE nesnesini almak için:  
  
    ```csharp  
    DTE dte = (DTE)GetService(typeof(DTE));  
    ```  
  
 Sonra <xref:EnvDTE.DTE> Otomasyon nesnesi, eklenti kodunuzun geri kalanı projeye ekleyebilirsiniz. Gerekirse <xref:EnvDTE80.DTE2> nesne aynısını yapabilir.  
  
## <a name="how-do-i-change-menu-commands-and-toolbar-buttons-in-my-add-in-to-the-vspackage-style"></a>Nasıl menü komutları ve araç çubuğu düğmeleri my eklenti VSPackage stiline değiştirebilirim?  
 VSPackage uzantıları .vsct dosya menü komutları, araç çubukları, araç çubuğu düğmeleri ve diğer UI çoğunu oluşturmak için kullanın. **Özel komut** proje öğesi şablonu, bir komut oluşturmak için seçeneği verir **Araçları** menüsü. Daha fazla bilgi için bkz: [uzantı menü komutu ile oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
 .Vsct dosyaları hakkında daha fazla bilgi için bkz: [nasıl VSPackages ekleme kullanıcı arabirimi öğeleri](../extensibility/internals/how-vspackages-add-user-interface-elements.md). .vsct dosyasının menü öğeleri, araç çubukları ve araç çubuğu düğmeleri eklemek için nasıl kullanılacağını gösteren izlenecek yollar için bkz: [genişletme menüleri ve komutları](../extensibility/extending-menus-and-commands.md).  
  
## <a name="how-do-i-add-custom-tool-windows-in-the-vspackage-way"></a>VSPackage şekilde nasıl özel araç pencereleri eklensin mi?  
 Özel araç penceresi proje öğesi şablonu bir araç penceresi oluşturma seçeneği sunar. Bu proje öğesi şablonu hakkında daha fazla bilgi için bkz: [bir uzantısı bir araç penceresi oluşturma](../extensibility/creating-an-extension-with-a-tool-window.md). Araç pencereleri hakkında daha fazla bilgi için bkz: [genişletme ve Özelleştirme Aracı Windows](../extensibility/extending-and-customizing-tool-windows.md) ve makalelerin altında özellikle [araç penceresi ekleme](../extensibility/adding-a-tool-window.md).  
  
## <a name="how-do-i-manage-visual-studio-windows-in-the-vspackage-way"></a>Visual Studio windows VSPackage şekilde nasıl yönetebilirim?  
 Eklentinizi Visual Studio windows yönetiliyorsa, eklenti kodu bir VSPackage çalışması gerekir. Örneğin, bu yordamı nasıl yönetir kodu ekleneceğini gösterir **görev listesi** için `MenuItemCallback` VSPackage yöntemi.  
  
#### <a name="to-insert-window-management-code-from-an-add-in-into-a-vspackage"></a>Pencere Yönetimi kod bir eklentiyi VSPackage ekleme  
  
1.  Menü komutu, olarak sahip bir VSPackage oluşturma [nasıl geliştirme VSIX uzantıları başlamalıyım?](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_StartDeveloping) bölümü.  
  
2.  VSPackage tanımını içeren dosyayı açın. (C# projesinde, bunun  *\<projenizin adına >* Package.cs.)  
  
3.  Bunlar eklemek `using` deyimleri:  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
4.  Bul `MenuItemCallback` yöntemi. Bir çağrı ekleyin <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> almak için <xref:EnvDTE80.DTE2> nesnesi:  
  
    ```csharp  
    DTE2 dte = (DTE2)GetService(typeof(DTE));  
    ```  
  
5.  Eklentiden kodu ekleyin. Örneğin, yeni görevler ekler biraz kod işte **görev listesi**görevleri sayısını listeler ve bir görevi siler.  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)   
    {  
        DTE2 dte = (DTE2) GetService(typeof(DTE));   
  
        TaskList tl = (TaskList)dte.ToolWindows.TaskList;   
        askItem tlItem;   
  
        // Add a couple of tasks to the Task List.   
        tlItem = tl.TaskItems.Add(" ", " ", "Test task 1.",    
            vsTaskPriority.vsTaskPriorityHigh, vsTaskIcon.vsTaskIconUser,   
            true, "", 10, true, true);  
        tlItem = tl.TaskItems.Add(" ", " ", "Test task 2.",   
            vsTaskPriority.vsTaskPriorityLow, vsTaskIcon.vsTaskIconComment, true, "", 20, true,true);  
  
        // List the total number of task list items after adding the new task items.  
        System.Windows.Forms.MessageBox.Show("Task Item 1 description: "+tl.TaskItems.Item(2).Description);  
        System.Windows.Forms.MessageBox.Show("Total number of task items: "+tl.TaskItems.Count);   
  
        // Remove the second task item. The items list in reverse numeric order.   
        System.Windows.Forms.MessageBox.Show("Deleting the second task item");  
        tl.TaskItems.Item(2).Delete();  
        System.Windows.Forms.MessageBox.Show("Total number of task items: "+tl.TaskItems.Count);   
    }  
    ```  
  
## <a name="how-do-i-manage-projects-and-solutions-in-a-vspackage"></a>Projeler ve çözümler bir VSPackage içinde nasıl yönetebilirim?  
 Eklentinizi projeler ve çözümler yönetiliyorsa, eklenti kodu bir VSPackage çalışması gerekir. Örneğin, bu yordam nasıl başlangıç projesi alır kodu ekleneceğini gösterir.  
  
1.  Menü komutu, olarak sahip bir VSPackage oluşturma [nasıl geliştirme VSIX uzantıları başlamalıyım?](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_StartDeveloping) bölümü.  
  
2.  VSPackage tanımını içeren dosyayı açın. (C# projesinde, bunun  *\<projenizin adına >* Package.cs.)  
  
3.  Bunlar eklemek `using` deyimleri:  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
4.  Bul `MenuItemCallback` yöntemi. Bir çağrı ekleyin <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> almak için <xref:EnvDTE80.DTE2> nesnesi:  
  
    ```csharp  
    DTE2 dte = (DTE2)GetService(typeof(DTE));  
    ```  
  
5.  Eklentiden kodu ekleyin. Örneğin, aşağıdaki kod bir çözümde başlangıç projesi adını alır. (Bu paketi çalıştığında birden çok proje çözümü açık olması gerekir.)  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        DTE2 dte = (DTE2) GetService(typeof(DTE));   
  
        SolutionBuild2 sb = (SolutionBuild2)dte.Solution.SolutionBuild;   
        Project startupProj;   
        string msg = "";  
  
        foreach (String item in (Array)sb.StartupProjects)   
        {  
            msg += item;   
        }  
        System.Windows.Forms.MessageBox.Show("Solution startup Project: "+msg);   
        startupProj = dte.Solution.Item(msg);   
        System.Windows.Forms.MessageBox.Show("Full name of solution's startup project: "+"/n"+startupProj.FullName);   
    }  
    ```  
  
## <a name="how-do-i-set-keyboard-shortcuts-in-a-vspackage"></a>Klavye kısayolları bir VSPackage nasıl ayarlarım?  
 Kullandığınız `<KeyBindings>` .vsct dosyasının öğesi. Aşağıdaki örnekte, komutu için klavye kısayolu `idCommand1` Alt + A ve komutu için klavye kısayolu `idCommand2` Alt + Ctrl + a. Anahtar adları sözdizimi dikkat edin.  
  
```xml  
<KeyBindings>  
    <KeyBinding guid="MyProjectCmdSet" id="idCommand1" editor="guidVSStd97" key1="A" mod1="ALT" />  
    <KeyBinding guid="MyProjectCmdSet" id="idCommand2" editor="guidVSStd97" key1="A" mod1="CONTROL" mod2="ALT" />  
</KeyBindings>  
```  
  
## <a name="how-do-i-handle-automation-events-in-a-vspackage"></a>Bir VSPackage Otomasyon olayları nasıl işler?  
 Eklentiniz olduğu gibi aynı şekilde bir VSPackage Otomasyon olayları işler. Aşağıdaki kodu nasıl işleneceğini gösterir `OnItemRenamed` olay. (Bu örnekte, DTE nesne zaten kabulünüzü varsayılır.)  
  
```csharp  
Events2 dteEvents = (Events2)dte.Events;  
dteEvents.ProjectItemsEvents.ItemRenamed += listener1.OnItemRenamed;   
. . .  
public void OnItemRenamed(EnvDTE.ProjectItem projItem, string oldName)   
{  
    string s = "[Event] Renamed " + oldName + " to " + Path.GetFileName(projItem.get_FileNames(1) + " in project " + projItem.ContainingProject.Name;   
}  
```