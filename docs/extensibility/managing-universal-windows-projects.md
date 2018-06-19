---
title: Evrensel Windows projeleri yönetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 47926aa1-3b41-410d-bca8-f77fc950cbe7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d251818d9fba0c025b94fa17611a725daad3cec8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31147600"
---
# <a name="managing-universal-windows-projects"></a>Evrensel Windows projeleri yönetme
Evrensel Windows uygulamaları, Windows 8.1 ve Windows Phone 8.1, kod ve diğer varlıkları hem platformlarda geliştiriciler izin vererek hedef uygulamalardır. Ayrı projeler, bir Windows ve Windows Phone için diğer kaynaklar ve platforma özgü kodu tutulan sırada kaynakların ve paylaşılan kodu paylaşılan bir proje tutulur. Evrensel Windows uygulamaları hakkında daha fazla bilgi için bkz: [Evrensel Windows uygulamaları](http://msdn.microsoft.com/library/windows/apps/dn609832.aspx). Projeleri Yönetme visual Studio uzantıları Evrensel Windows uygulaması projeleri tek platform uygulamalardan farklı bir yapıya sahip bilmeniz gerekir. Bu kılavuzda paylaşılan bir proje gidin ve paylaşılan öğelerini yönetmek nasıl gösterir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
### <a name="navigate-the-shared-project"></a>Paylaşılan bir proje gidin  
  
1.  Adlı bir C# VSIX proje oluşturma **TestUniversalProject**. (**Dosya, yeni, proje** ve ardından **C#, genişletilebilirlik, Visual Studio Paketi**). Ekle bir **özel komut** proje öğesi şablonu (Çözüm Gezgini proje düğümüne sağ tıklayın ve seçin **Ekle / yeni öğe**, ardından **genişletilebilirlik**). Dosya adı **TestUniversalProject**.  
  
2.  Microsoft.VisualStudio.Shell.Interop.12.1.DesignTime.dll ve Microsoft.VisualStudio.Shell.Interop.14.0.DesignTime.dll bir başvuru ekleyin (içinde **uzantıları** bölümü).  
  
3.  TestUniversalProject.cs açın ve aşağıdakileri ekleyin `using` deyimleri:  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.PlatformUI;  
    using Microsoft.Internal.VisualStudio.PlatformUI;   
    using System.Collections.Generic;   
    using System.IO;  
    using System.Windows.Forms;  
    ```  
  
4.  TestUniversalProject sınıfında işaret eden bir özel alan eklemek **çıkış** penceresi.  
  
    ```csharp  
    public sealed class TestUniversalProject   
    {  
        IVsOutputWindowPane output;  
    . . .  
    }  
    ```  
  
5.  Çıkış Bölmesi'TestUniversalProject oluşturucusu içinde referansı ayarlayın:  
  
    ```csharp  
    private TestUniversalProject(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException("package");  
        }  
  
        this.package = package;  
  
        OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
        if (commandService != null)  
        {  
            CommandID menuCommandID = new CommandID(MenuGroup, CommandId);  
            EventHandler eventHandler = this.ShowMessageBox;  
            MenuCommand menuItem = new MenuCommand(eventHandler, menuCommandID);  
            commandService.AddCommand(menuItem);  
        }  
        // get a reference to the Output window  
                    output = (IVsOutputWindowPane)ServiceProvider.GetService(typeof(SVsGeneralOutputWindowPane));  
    }  
    ```  
  
6.  Var olan koddan kaldırmak `ShowMessageBox` yöntemi:  
  
    ```csharp  
    private void ShowMessageBox(object sender, EventArgs e)   
    {  
    }  
    ```  
  
7.  Bu kılavuzda birkaç farklı amaçlarla kullanırız DTE nesnesini alın. Ayrıca, bir çözüm menü düğmesine tıklandığında yüklü olduğundan emin olun.  
  
    ```csharp  
    private void ShowMessageBox(object sender, EventArgs e)  
    {   
        var dte = (EnvDTE.DTE)this.ServiceProvider.GetService(typeof(EnvDTE.DTE));  
        if (dte.Solution != null)   
        {  
            . . .  
        }  
        else   
        {  
            MessageBox.Show("No solution is open");  
            return;   
        }  
    }  
    ```  
  
8.  Paylaşılan bir proje bulun. Saf bir kapsayıcı paylaşılan projedir; derleme bulunamıyor veya çıkışları üretir. Aşağıdaki yöntem ilk paylaşılan proje bakarak çözümde bulur <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> paylaşılan projesi özelliğine sahip bir nesne.  
  
    ```csharp  
    private IVsHierarchy FindSharedProject()  
    {  
        var sln = (IVsSolution)this.ServiceProvider.GetService(typeof(SVsSolution));  
        Guid empty = Guid.Empty;  
        IEnumHierarchies enumHiers;  
  
        //get all the projects in the solution  
        ErrorHandler.ThrowOnFailure(sln.GetProjectEnum((uint)__VSENUMPROJFLAGS.EPF_LOADEDINSOLUTION, ref empty, out enumHiers));  
        foreach (IVsHierarchy hier in ComUtilities.EnumerableFrom(enumHiers))  
        {  
            if (PackageUtilities.IsCapabilityMatch(hier, "SharedAssetsProject"))  
            {  
                return hier;  
            }  
        }  
        return null;  
    }  
    ```  
  
9. İçinde `ShowMessageBox` yöntemi, resim yazısını çıkış (görünür proje adı **Çözüm Gezgini**) paylaşılan projesinin.  
  
    ```csharp  
    private void ShowMessageBox(object sender, EventArgs e)  
    {  
        var dte = (DTE)this.ServiceProvider.GetService(typeof(DTE));  
  
        if (dte.Solution != null)  
        {  
            var sharedHier = this.FindSharedProject();  
            if (sharedHier != null)  
            {  
                string sharedCaption = HierarchyUtilities.GetHierarchyProperty<string>(sharedHier, (uint)VSConstants.VSITEMID.Root,  
                     (int)__VSHPROPID.VSHPROPID_Caption);  
                output.OutputStringThreadSafe(string.Format("Found shared project: {0}\n", sharedCaption));  
            }  
            else  
            {  
                MessageBox.Show("Solution has no shared project");  
                return;  
            }  
                }  
        else  
        {  
            MessageBox.Show("No solution is open");  
            return;  
        }  
    }  
    ```  
  
10. Etkin platform projesinde alın. Platform projeleri platforma özgü kodu hem de kaynaklar içeren projeler ' dir. Aşağıdaki yöntem yeni alanını kullanır <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID7> etkin platform projesinde alınamıyor.  
  
    ```csharp  
    private IVsHierarchy GetActiveProjectContext(IVsHierarchy hierarchy)  
    {  
        IVsHierarchy activeProjectContext;  
        if (HierarchyUtilities.TryGetHierarchyProperty(hierarchy, (uint)VSConstants.VSITEMID.Root,  
             (int)__VSHPROPID7.VSHPROPID_SharedItemContextHierarchy, out activeProjectContext))  
        {  
            return activeProjectContext;  
        }  
        else  
        {  
            return null;  
        }  
    }  
    ```  
  
11. İçinde `ShowMessageBox` yöntemi, active platform projesinde resim yazısını çıktı.  
  
    ```csharp  
    private void ShowMessageBox(object sender, EventArgs e)  
    {  
        var dte = (DTE)this.ServiceProvider.GetService(typeof(DTE));  
  
        if (dte.Solution != null)  
        {  
            var sharedHier = this.FindSharedProject();  
            if (sharedHier != null)  
            {  
                string sharedCaption = HierarchyUtilities.GetHierarchyProperty<string>(sharedHier, (uint)VSConstants.VSITEMID.Root,  
                     (int)__VSHPROPID.VSHPROPID_Caption);  
                output.OutputStringThreadSafe(string.Format("Shared project: {0}\n", sharedCaption));  
  
                var activePlatformHier = this.GetActiveProjectContext(sharedHier);  
                if (activePlatformHier != null)  
                {  
                    string activeCaption = HierarchyUtilities.GetHierarchyProperty<string>(activePlatformHier,  
                         (uint)VSConstants.VSITEMID.Root, (int)__VSHPROPID.VSHPROPID_Caption);  
                    output.OutputStringThreadSafe(string.Format("Active platform project: {0}\n", activeCaption));  
                }  
                else  
                {  
                MessageBox.Show("Shared project has no active platform project");  
                }  
            }  
            else  
            {  
                MessageBox.Show("Solution has no shared project");  
                return;  
            }  
        }  
        else  
            {  
                MessageBox.Show("No solution is open");  
                return;  
            }  
        }  
  
    ```  
  
12. Platform projeleri yineleme. Aşağıdaki yöntem tüm alma (platform) projeleri paylaşılan projeden alır.  
  
    ```csharp  
    private IEnumerable<IVsHierarchy> EnumImportingProjects(IVsHierarchy hierarchy)  
    {  
        IVsSharedAssetsProject sharedAssetsProject;  
        if (HierarchyUtilities.TryGetHierarchyProperty(hierarchy, (uint)VSConstants.VSITEMID.Root,  
            (int)__VSHPROPID7.VSHPROPID_SharedAssetsProject, out sharedAssetsProject)  
            && sharedAssetsProject != null)  
        {  
            foreach (IVsHierarchy importingProject in sharedAssetsProject.EnumImportingProjects())  
            {  
                yield return importingProject;  
            }  
        }  
    }  
    ```  
  
    > [!IMPORTANT]
    >  Kullanıcı deneysel örneğinde C++ Evrensel Windows uygulaması projesi açmışsa, yukarıdaki kod bir özel durum oluşturur. Bu bilinen bir sorundur. Özel durum önlemek için yerini `foreach` şununla engelleme yukarıda:  
  
    ```csharp  
    var importingProjects = sharedAssetsProject.EnumImportingProjects();  
    for (int i = 0; i < importingProjects.Count; ++i)  
    {  
        yield return importingProjects[i];  
    }   
    ```  
  
13. İçinde `ShowMessageBox` yöntemi, her platform projesinde resim yazısını çıktı. Etkin platform projesinde resim yazısını çıkarır satırından sonra aşağıdaki kodu ekleyin. Yüklenen platform projeleri bu listede görüntülenir.  
  
    ```csharp  
    output.OutputStringThreadSafe("Platform projects:\n");  
  
    IEnumerable<IVsHierarchy> projects = this.EnumImportingProjects(sharedHier);  
  
    bool isActiveProjectSet = false;  
    foreach (IVsHierarchy platformHier in projects)  
    {  
        string platformCaption = HierarchyUtilities.GetHierarchyProperty<string>(platformHier, (uint)VSConstants.VSITEMID.Root,  
            (int)__VSHPROPID.VSHPROPID_Caption);  
        output.OutputStringThreadSafe(string.Format(" * {0}\n", platformCaption));  
    }  
    ```  
  
14. Etkin platform projesinde değiştirin. Aşağıdaki yöntemi kullanarak etkin proje ayarlar <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.SetProperty%2A>.  
  
    ```csharp  
    private int SetActiveProjectContext(IVsHierarchy hierarchy, IVsHierarchy activeProjectContext)  
    {  
        return hierarchy.SetProperty((uint)VSConstants.VSITEMID.Root, (int)__VSHPROPID7.VSHPROPID_SharedItemContextHierarchy, activeProjectContext);  
    }  
    ```  
  
15. İçinde `ShowMessageBox` yöntemi, active platform projesini değiştirebilir. Bu kod içinde ekleme `foreach` bloğu.  
  
    ```csharp  
    bool isActiveProjectSet = false;  
    string platformCaption = null;  
    foreach (IVsHierarchy platformHier in projects)  
    {  
        platformCaption = HierarchyUtilities.GetHierarchyProperty<string>(platformHier, (uint)VSConstants.VSITEMID.Root,  
             (int)__VSHPROPID.VSHPROPID_Caption);  
        output.OutputStringThreadSafe(string.Format(" * {0}\n", platformCaption));  
  
        // if this project is neither the shared project nor the current active platform project,   
        // set it to be the active project  
        if (!isActiveProjectSet && platformHier != activePlatformHier)  
        {  
            this.SetActiveProjectContext(sharedHier, platformHier);  
            activePlatformHier = platformHier;  
            isActiveProjectSet = true;  
        }  
    }  
    output.OutputStringThreadSafe("set active project: " + platformCaption +'\n');  
    ```  
  
16. Şimdi deneyin. Deneysel örneği başlatmak için F5 tuşuna basın. Deneysel örneğinde bir C# hub'ı Evrensel uygulama projesi oluşturun (içinde **yeni proje** iletişim kutusu, **Visual C# / Windows / Windows 8 / Evrensel / Hub uygulama**). Çözüm yüklendikten sonra Git **Araçları** menüsüne ve ardından **çağırma TestUniversalProject**ve ardından metin iade **çıkış** bölmesi. Aşağıdakine benzer bir şey görmeniz gerekir:  
  
    ```  
    Found shared project: HubApp.Shared  
    The active platform project: HubApp.Windows  
    Platform projects:  
     * HubApp.Windows  
     * HubApp.WindowsPhone  
    set active project: HubApp.WindowsPhone  
    ```  
  
### <a name="manage-the-shared-items-in-the-platform-project"></a>Platform projesinde paylaşılan öğelerini yönetme  
  
1.  Paylaşılan öğeleri platform projesinde bulun. Paylaşılan bir proje öğelerinde platform projesinde paylaşılan öğeleri olarak görünür. Bunları göremiyorum **Çözüm Gezgini**, ancak bunları bulmak için proje hiyerarşisi yol. Aşağıdaki yöntem hiyerarşi anlatılmaktadır ve paylaşılan tüm öğeleri toplar. Bu isteğe bağlı olarak her öğenin başlığını çıkarır. Paylaşılan öğeler yeni özelliği tarafından tanımlanan <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID7>.  
  
    ```csharp  
    private void InspectHierarchyItems(IVsHierarchy hier, uint itemid, int level, List<uint> itemIds, bool getSharedItems, bool printItems)  
    {  
        string caption = HierarchyUtilities.GetHierarchyProperty<string>(hier, itemid, (int)__VSHPROPID.VSHPROPID_Caption);  
        if (printItems)  
            output.OutputStringThreadSafe(string.Format("{0}{1}\n", new string('\t', level), caption));  
  
        // if getSharedItems is true, inspect only shared items; if it's false, inspect only unshared items  
        bool isSharedItem;  
        if (HierarchyUtilities.TryGetHierarchyProperty(hier, itemid, (int)__VSHPROPID7.VSHPROPID_IsSharedItem, out isSharedItem)  
            && (isSharedItem == getSharedItems))  
        {  
            itemIds.Add(itemid);  
        }  
  
        uint child;  
        if (HierarchyUtilities.TryGetHierarchyProperty(hier, itemid, (int)__VSHPROPID.VSHPROPID_FirstChild, Unbox.AsUInt32, out child)  
            && child != (uint)VSConstants.VSITEMID.Nil)  
        {  
            this.InspectHierarchyItems(hier, child, level + 1, itemIds, isSharedItem, printItems);  
  
            while (HierarchyUtilities.TryGetHierarchyProperty(hier, child, (int)__VSHPROPID.VSHPROPID_NextSibling, Unbox.AsUInt32, out child)  
                && child != (uint)VSConstants.VSITEMID.Nil)  
            {  
                this.InspectHierarchyItems(hier, child, level + 1, itemIds, isSharedItem, printItems);  
            }  
                    }  
    }  
    ```  
  
2.  İçinde `ShowMessageBox` yöntemi, platform proje hiyerarşisi öğeleri yürütmek için aşağıdaki kodu ekleyin. İçine eklemek `foreach` bloğu.  
  
    ```csharp  
    output.OutputStringThreadSafe("Walk the active platform project:\n");  
    var sharedItemIds = new List<uint>();  
    this.InspectHierarchyItems(activePlatformHier, (uint)VSConstants.VSITEMID.Root, 1, sharedItemIds, true, true);  
    ```  
  
3.  Paylaşılan öğeler okuyun. Paylaşılan öğeler platform projesinde gizli bağlantılı dosyaları olarak görüntülenir ve sıradan bağlı dosyalar olarak tüm özelliklerini okuyabilirler. Aşağıdaki kod ilk paylaşılan öğesinin tam yol okur.  
  
    ```csharp  
    var sharedItemId = sharedItemIds[0];  
    string fullPath;  
    ErrorHandler.ThrowOnFailure(((IVsProject)activePlatformHier).GetMkDocument(sharedItemId, out fullPath));  
    output.OutputStringThreadSafe(string.Format("Shared item full path: {0}\n", fullPath));  
    ```  
  
4.  Şimdi deneyin. Deneysel örneği başlatmak için F5 tuşuna basın. Deneysel örneğinde bir C# hub'ı Evrensel uygulama projesi oluşturun (içinde **yeni proje** iletişim kutusu, **Visual C# / Windows / Windows 8 / Evrensel / Hub uygulama**) gidin **Araçları** menüsüne ve ardından **çağırma TestUniversalProject**ve ardından metin iade **çıkış** bölmesi. Aşağıdakine benzer bir şey görmeniz gerekir:  
  
    ```  
    Found shared project: HubApp.Shared  
    The active platform project: HubApp.Windows  
    Platform projects:  
     * HubApp.Windows  
     * HubApp.WindowsPhone  
    set active project: HubApp.WindowsPhone  
    Walk the active platform project:  
        HubApp.WindowsPhone  
            <HubApp.Shared>  
                App.xaml  
                    App.xaml.cs  
                Assets  
                    DarkGray.png  
                    LightGray.png  
                    MediumGray.png  
                Common  
                    NavigationHelper.cs  
                    ObservableDictionary.cs  
                    RelayCommand.cs  
                    SuspensionManager.cs  
                DataModel  
                    SampleData.json  
                    SampleDataSource.cs  
                HubApp.Shared.projitems  
                Strings  
                    en-US  
                        Resources.resw  
            Assets  
                HubBackground.theme-dark.png  
                HubBackground.theme-light.png  
                Logo.scale-240.png  
                SmallLogo.scale-240.png  
                SplashScreen.scale-240.png  
                Square71x71Logo.scale-240.png  
                StoreLogo.scale-240.png  
                WideLogo.scale-240.png  
            HubPage.xaml  
                HubPage.xaml.cs  
            ItemPage.xaml  
                ItemPage.xaml.cs  
            Package.appxmanifest  
            Properties  
                AssemblyInfo.cs  
            References  
                .NET for Windows Store apps  
                HubApp.Shared  
                Windows Phone 8.1  
            SectionPage.xaml  
                SectionPage.xaml.cs  
    ```  
  
### <a name="detecting-changes-in-platform-projects-and-shared-projects"></a>Platform projeleri ve paylaşılan projeleri değişiklikleri algılama  
  
1.  Platform projelerde gibi paylaşılan projelerinde değişikliklerini algılamak için hiyerarşi ve proje olayları kullanabilirsiniz. Bununla birlikte, paylaşılan bir proje proje öğelerinde paylaşılan proje öğeleri değiştiğinde belirli olaylar başlatılmaz anlamına gelir, görünmez.  
  
     Proje dosyasında yeniden adlandırıldığında olayların sırası göz önünde bulundurun:  
  
    1.  Dosya adı diskte değiştirilir.  
  
    2.  Proje dosyası, dosyanın yeni adını içerecek şekilde güncelleştirilmiştir.  
  
     Hiyerarşi olaylar (örneğin, <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents>) genellikle kullanıcı Arabiriminde olarak görüntülenen değişiklikleri izleyen **Çözüm Gezgini**. Hiyerarşi olayları bir dosya yeniden adlandırma işlemi dosya silme ve ardından dosya toplama oluşan göz önünde bulundurun. Ancak, hiyerarşi olay sistem görünmeyen öğeleri değiştirildiğinde ateşlenir bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemDeleted%2A> olay ama bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemAdded%2A> olay. Platform projesinde dosyasını yeniden adlandırırsanız, bu nedenle, her ikisi de elde <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemDeleted%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemAdded%2A>, ancak paylaşılan bir proje dosyasında yeniden adlandırırsanız, yalnızca get <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemDeleted%2A>.  
  
     Proje öğeleri değişiklikleri izlemek için DTE proje öğesi olayları işleyebilirsiniz (olanları bulunan <xref:EnvDTE.ProjectItemsEventsClass>). Ancak, çok sayıda olayları işleme, olayları işleme daha iyi performans elde edebilirsiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>. Bu kılavuzda yalnızca Hiyerarşi olayları ve DTE olayları gösterir. Bu yordamda bir olay dinleyicisi, paylaşılan bir proje ve platform proje ekleyin. Ardından, bir paylaşılan bir proje dosyasında ve platform projedeki başka bir dosyayı yeniden adlandırdığınızda, her yeniden adlandırma işlemi için tetiklenen olayları görebilirsiniz.  
  
     Bu yordamda bir olay dinleyicisi, paylaşılan bir proje ve platform proje ekleyin. Ardından, bir paylaşılan bir proje dosyasında ve platform projedeki başka bir dosyayı yeniden adlandırdığınızda, her yeniden adlandırma işlemi için tetiklenen olayları görebilirsiniz.  
  
2.  Olay dinleyicisi ekleyin. Yeni bir sınıf dosyası projeye ekleyin ve HierarchyEventListener.cs çağırın.  
  
3.  HierarchyEventListener.cs dosyasını açın ve aşağıdaki using deyimlerini:  
  
    ```csharp  
    using Microsoft.VisualStudio.Shell.Interop;  
    using Microsoft.VisualStudio;  
    using System.IO;  
  
    ```  
  
4.  Sahip `HierarchyEventListener` sınıfı uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents>:  
  
    ```csharp  
    class HierarchyEventListener : IVsHierarchyEvents  
    { }  
  
    ```  
  
5.  Üyelerini uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents>, aşağıdaki kod gibi.  
  
    ```csharp  
    class HierarchyEventListener : IVsHierarchyEvents  
    {  
        private IVsHierarchy hierarchy;  
        IVsOutputWindowPane output;   
  
        internal HierarchyEventListener(IVsHierarchy hierarchy, IVsOutputWindowPane outputWindow) {  
             this.hierarchy = hierarchy;  
             this.output = outputWindow;  
        }  
  
        int IVsHierarchyEvents.OnInvalidateIcon(IntPtr hIcon) {  
            return VSConstants.S_OK;  
        }  
  
        int IVsHierarchyEvents.OnInvalidateItems(uint itemIDParent) {  
            return VSConstants.S_OK;  
        }  
  
        int IVsHierarchyEvents.OnItemAdded(uint itemIDParent, uint itemIDSiblingPrev, uint itemIDAdded) {  
            output.OutputStringThreadSafe("IVsHierarchyEvents.OnItemAdded: " + itemIDAdded + "\n");  
            return VSConstants.S_OK;  
        }  
  
        int IVsHierarchyEvents.OnItemDeleted(uint itemID) {  
            output.OutputStringThreadSafe("IVsHierarchyEvents.OnItemDeleted: " + itemID + "\n");  
            return VSConstants.S_OK;  
        }  
  
        int IVsHierarchyEvents.OnItemsAppended(uint itemIDParent) {  
            output.OutputStringThreadSafe("IVsHierarchyEvents.OnItemsAppended\n");  
            return VSConstants.S_OK;  
        }  
  
        int IVsHierarchyEvents.OnPropertyChanged(uint itemID, int propID, uint flags) {  
            output.OutputStringThreadSafe("IVsHierarchyEvents.OnPropertyChanged: item ID " + itemID + "\n");  
            return VSConstants.S_OK;  
        }  
    }  
  
    ```  
  
6.  Aynı sınıfta DTE olayı için başka bir olay işleyicisi ekleme <xref:EnvDTE.ProjectItemsEventsClass.ItemRenamed>, bir proje öğesi yeniden adlandırılmış olduğunda oluşur.  
  
    ```csharp  
    public void OnItemRenamed(EnvDTE.ProjectItem projItem, string oldName)  
    {  
        output.OutputStringThreadSafe(string.Format("[Event] Renamed {0} to {1} in project {2}\n",  
             oldName, Path.GetFileName(projItem.get_FileNames(1)), projItem.ContainingProject.Name));  
    }  
    ```  
  
7.  Hiyerarşi olaylar için kaydolun. Ayrı ayrı izlemekte olduğunuz her proje için kaydolmanız gerekir. Aşağıdaki kodu ekleyin `ShowMessageBox`, paylaşılan bir proje ve platform projelerden biri diğer için bir tane.  
  
    ```csharp  
    // hook up the event listener for hierarchy events on the shared project  
    HierarchyEventListener listener1 = new HierarchyEventListener(sharedHier, output);  
    uint cookie1;  
    sharedHier.AdviseHierarchyEvents(listener1, out cookie1);  
  
    // hook up the event listener for hierarchy events on the   
    active project  
    HierarchyEventListener listener2 = new HierarchyEventListener(activePlatformHier, output);  
    uint cookie2;  
    activePlatformHier.AdviseHierarchyEvents(listener2, out cookie2);  
    ```  
  
8.  DTE proje öğesi olayı için kaydolun <xref:EnvDTE.ProjectItemsEventsClass.ItemRenamed>. İkinci dinleyiciyi kanca sonra aşağıdaki kodu ekleyin.  
  
    ```csharp  
    // hook up DTE events for project items  
    Events2 dteEvents = (Events2)dte.Events;  
    dteEvents.ProjectItemsEvents.ItemRenamed += listener1.OnItemRenamed;  
  
    ```  
  
9. Paylaşılan öğesini değiştirin. Bir platform projesinde paylaşılan öğeleri değiştirilemiyor; Bunun yerine, bunları bu öğeler gerçek sahibi paylaşılan projede değiştirmelisiniz. Karşılık gelen öğe kimliği ile paylaşılan projesinde alabileceğiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject.IsDocumentInProject%2A>, paylaşılan öğesinin tam yol vermiş. Daha sonra paylaşılan öğesi değiştirebilirsiniz. Değişiklik platform projelerine yayılır.  
  
    > [!IMPORTANT]
    >  Olsun veya olmasın bir proje öğesi paylaşılan öğe değiştirmeden önce olduğunu düşünür.  
  
     Aşağıdaki yöntem, bir proje öğesi dosyasının adını değiştirir.  
  
    ```csharp  
    private void ModifyFileNameInProject(IVsHierarchy project, string path)  
    {    
        int found;  
        uint projectItemID;  
        VSDOCUMENTPRIORITY[] priority = new VSDOCUMENTPRIORITY[1];  
        if (ErrorHandler.Succeeded(((IVsProject)project).IsDocumentInProject(path, out found, priority, out projectItemID))  
            && found != 0)  
        {  
            var name = DateTime.Now.Ticks.ToString() + Path.GetExtension(path);  
            project.SetProperty(projectItemID, (int)__VSHPROPID.VSHPROPID_EditLabel, name);  
            output.OutputStringThreadSafe(string.Format("Renamed {0} to {1}\n", path,name));  
        }  
    }  
    ```  
  
10. Bu yöntem tüm diğer kodda çağrı `ShowMessageBox` dosyayı değiştirmek için paylaşılan bir proje öğesi adı. Bu, paylaşılan bir proje öğesi tam yolunu alır koddan sonra ekleyin.  
  
    ```csharp  
    // change the file name of an item in a shared project  
    this.InspectHierarchyItems(activePlatformHier, (uint)VSConstants.VSITEMID.Root, 1, sharedItemIds, true, true);  
    ErrorHandler.ThrowOnFailure(((IVsProject)activePlatformHier).GetMkDocument(sharedItemId, out fullPath));   
    output.OutputStringThreadSafe(string.Format("Shared project item ID = {0}, full path = {1}\n", sharedItemId, fullPath));  
    this.ModifyFileNameInProject(sharedHier, fullPath);  
    ```  
  
11. Oluşturun ve projeyi çalıştırın. Deneysel örneğinde bir C# Evrensel hub uygulaması oluşturma, Git **Araçları** menüsüne ve ardından **çağırma TestUniversalProject**ve genel çıkış bölmesinde metni kontrol edin. Paylaşılan ilk öğesinin adı (bekliyoruz App.xaml dosyası olmasını) proje değiştirilmesi ve, görmelisiniz <xref:EnvDTE.ProjectItemsEventsClass.ItemRenamed> olay tetiklenir. Bu durumda, App.XAML yeniden adlandırma de yeniden adlandırılacak App.xaml.cs neden olduğundan, dört olayları (her platform proje için iki) görmeniz gerekir. (DTE olayları paylaşılan bir proje öğelerinde izlemez.) İki görmelisiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemDeleted%2A> olayları (platformu projelerin her biri için bir tane) ancak hiçbir <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemAdded%2A> olaylar.  
  
12. Şimdi bir platform projesinde bir dosya yeniden adlandırmayı deneyin ve puanlı olayları farkı görebilirsiniz. Aşağıdaki kodu ekleyin `ShowMessageBox` çağrısından sonra `ModifyFileName`.  
  
    ```csharp  
    // change the file name of an item in a platform project  
    var unsharedItemIds = new List<uint>();  
    this.InspectHierarchyItems(activePlatformHier, (uint)VSConstants.VSITEMID.Root, 1, unsharedItemIds, false, false);  
  
    var unsharedItemId = unsharedItemIds[0];  
    string unsharedPath;  
    ErrorHandler.ThrowOnFailure(((IVsProject)activePlatformHier).GetMkDocument(unsharedItemId, out unsharedPath));  
    output.OutputStringThreadSafe(string.Format("Platform project item ID = {0}, full path = {1}\n", unsharedItemId, unsharedPath));  
  
    this.ModifyFileNameInProject(activePlatformHier, unsharedPath);  
    ```  
  
13. Oluşturun ve projeyi çalıştırın. Deneysel örneğinde bir C# Evrensel projesi oluşturun, Git **Araçları** menüsüne ve ardından **çağırma TestUniversalProject**ve genel çıkış bölmesinde metni kontrol edin. Platform proje dosyasında yeniden adlandırıldıktan sonra her ikisi de görmelisiniz bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemAdded%2A> olay ve bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyEvents.OnItemDeleted%2A> olay. Dosya değiştirilecek diğer dosyaları neden değiştirilmesi ve öğelerde platform projesinde yapılan değişikliklerin herhangi bir yere yayılan yok, yoktur yalnızca her aşağıdaki olaylardan biri.