---
title: "Dinamik menü öğeleri ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DYNAMICITEMSTART
- menu items, adding dynamically
- menus, adding dynamic items
ms.assetid: d281e9c9-b289-4d64-8d0a-094bac6c333c
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 8c7a803933b3b1e6d353b9899cb8997dbaa6897e
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="dynamically-adding-menu-items"></a>Dinamik menü öğeleri ekleme
Menü öğeleri çalışma zamanında belirterek ekleyebileceğiniz `DynamicItemStart` menü sayısı (kodda) tanımlama görüntüleme ve komutlar işleme öğelerini sonra Visual Studio komut-tablo (.vsct) dosyası bir yer tutucu düğmesi tanımında bayrağı komutu. VSPackage yüklendiğinde, yer tutucu Dinamik menü öğeleri ile değiştirilir.  
  
 Visual Studio kullanan dinamik listelerinde **en son kullanılan** son açtığınız belgeleri adlarını görüntüler, (MRU) listesi ve **Windows** windows adlarını görüntüler liste şu anda açık olan.   `DynamicItemStart` Bir komut tanımı bayrağı VSPackage açılıncaya kadar komutu bir yer tutucu olduğunu belirtir. VSPackage açıldığında, yer tutucu 0 veya çalışma zamanında oluşturulan ve dinamik listeye eklenen komut ile değiştirilir. Konumu VSPackage açılıncaya kadar dinamik listesi göründüğü menüsünde görmeye olmayabilir.  Dinamik listeyi doldurmak için Visual Studio ilk karakterine yer tutucu kimliği ile aynı olan bir Kimliğe sahip bir komutu aramak için VSPackage sorar. Visual Studio eşleşen bir komut bulduğunda, komutun adını dinamik listesine ekler. Ardından kimliği artırır ve daha fazla dinamik komutlar kadar dinamik listesine eklemek için başka bir eşleşen komutu için görünür.  
  
 Bu kılavuzda, bir Visual Studio çözümüne bir komutla başlangıç projesi ayarlamak gösterilmiştir **Çözüm Gezgini** araç. Etkin çözümde projeleri dinamik açılır listesini içeren bir menü denetleyicisi kullanır. Bu komut yok çözüm zaman görünmesini engellemek için açık olan veya yalnızca bir Proje Aç çözüm sahip olduğunda, yalnızca birden çok proje çözümü yoktur VSPackage yüklenir.  
  
 .Vsct dosyaları hakkında daha fazla bilgi için bkz: [Visual Studio komut tablosu (. Vsct) dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
## <a name="creating-an-extension-with-a-menu-command"></a>Menü komutu ile bir uzantısı oluşturma  
  
1.  Adlı VSIX proje oluşturma `DynamicMenuItems`.  
  
2.  Proje açıldığında bir özel komut öğesi şablon ekleyin ve adını **DynamicMenu**. Daha fazla bilgi için bkz: [uzantı menü komutu ile oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
## <a name="setting-up-the-elements-in-the-vsct-file"></a>.Vsct dosyasındaki öğeleri ayarlama  
 Araç çubuğundaki Dinamik menü öğeleriyle menü denetleyicisi oluşturmak için aşağıdaki öğeleri belirtin:  
  
-   İki grupları, menü denetleyicisi içeren bir ve açılır menü öğeleri içeren başka bir komutu  
  
-   Türünün bir menü öğesi `MenuController`  
  
-   İki düğmeleri, bir simge veya ipucu araç çubuğunda sağlayan için yer tutucu menü öğeleri ve başka gibi davranır.  
  
1.  Komut kimlikleri DynamicMenuPackage.vsct içinde tanımlayın. Simgeler bölümüne gidin ve IDSymbol öğeleri değiştirmek **guidDynamicMenuPackageCmdSet** GuidSymbol bloğu. İki grup, menü denetleyici, yer tutucu komut ve bağlantı komutu için IDSymbol öğeleri tanımlamanız gerekir.  
  
    ```csharp  
    <GuidSymbol name="guidDynamicMenuPackageCmdSet" value="{ your GUID here }">  
        <IDSymbol name="MyToolbarItemGroup" value="0x1020" />  
        <IDSymbol name="MyMenuControllerGroup" value="0x1025" />  
        <IDSymbol name="MyMenuController" value ="0x1030"/>  
        <IDSymbol name="cmdidMyAnchorCommand" value="0x0103" />  
        <!-- NOTE: The following command expands at run time to some number of ids.  
         Try not to place command ids after it (e.g. 0x0105, 0x0106).  
         If you must add a command id after it, make the gap very large (e.g. 0x200) -->  
        <IDSymbol name="cmdidMyDynamicStartCommand" value="0x0104" />  
    </GuidSymbol>    
    ```  
  
2.  Grupları bölümünde varolan gruplarını silin ve iki grupları yalnızca tanımlı ekleyin:  
  
    ```  
    <Groups>  
        <!-- The group that adds the MenuController on the Solution Explorer toolbar.   
             The 0x4000 priority adds this group after the group that contains the  
             Preview Selected Items button, which is normally at the far right of the toolbar. -->  
        <Group guid="guidDynamicMenuPackageCmdSet" id="MyToolbarItemGroup" priority="0x4000" >  
            <Parent guid="guidSHLMainMenu" id="IDM_VS_TOOL_PROJWIN" />  
        </Group>  
        <!-- The group for the items on the MenuController drop-down. It is added to the MenuController submenu. -->  
        <Group guid="guidDynamicMenuPackageCmdSet" id="MyMenuControllerGroup" priority="0x4000" >  
            <Parent guid="guidDynamicMenuPackageCmdSet" id="MyMenuController" />  
        </Group>  
    </Groups>  
    ```  
  
     MenuController ekleyin. Her zaman görünür olmadığından DynamicVisibility komutu bayrağını ayarlayın. ■ ButtonText görüntülenmez.  
  
    ```  
    <Menus>  
        <!-- The MenuController to display on the Solution Explorer toolbar.  
             Place it in the ToolbarItemGroup.-->  
        <Menu guid="guidDynamicMenuPackageCmdSet" id="MyMenuController" priority="0x1000" type="MenuController">  
            <Parent guid="guidDynamicMenuPackageCmdSet" id="MyToolbarItemGroup" />  
            <CommandFlag>DynamicVisibility</CommandFlag>  
            <Strings>  
               <ButtonText></ButtonText>  
           </Strings>  
        </Menu>  
    </Menus>  
    ```  
  
3.  Biri dinamik menü öğeleri için bir yer tutucu olarak diğeri bir bağlayıcı olarak iki düğmeleri için MenuController ekleyin.  
  
     Yer tutucu düğmesi üst **MyMenuControllerGroup**. DynamicItemStart, DynamicVisibility ve TextChanges komutu bayrakları yer tutucu düğme ekleyin. ■ ButtonText görüntülenmez.  
  
     Bağlantı düğmesi, simge ve araç ipucu metni tutar. Üst bağlantı düğmesinin da olan **MyMenuControllerGroup**. Düğmesi gerçekte menü denetleyicisi açılır listede görünmüyor emin olmak için NoShowOnMenuController komutu bayrağı ve kalıcı bağlantı yapmak için FixMenuController komutu bayrağını ekleyin.  
  
    ```  
    <!-- The placeholder for the dynamic items that expand to N items at runtime. -->  
    <Buttons>  
        <Button guid="guidDynamicMenuPackageCmdSet" id="cmdidMyDynamicStartCommand" priority="0x1000" >  
          <Parent guid="guidDynamicMenuPackageCmdSet" id="MyMenuControllerGroup" />  
          <CommandFlag>DynamicItemStart</CommandFlag>  
          <CommandFlag>DynamicVisibility</CommandFlag>  
          <CommandFlag>TextChanges</CommandFlag>  
          <!-- This text does not appear. -->  
          <Strings>  
            <ButtonText>Project</ButtonText>  
          </Strings>  
        </Button>  
  
        <!-- The anchor item to supply the icon/tooltip for the MenuController -->  
        <Button guid="guidDynamicMenuPackageCmdSet" id="cmdidMyAnchorCommand" priority="0x0000" >  
          <Parent guid="guidDynamicMenuPackageCmdSet" id="MyMenuControllerGroup" />  
          <!-- This is the icon that appears on the Solution Explorer toolbar. -->  
          <Icon guid="guidImages" id="bmpPicArrows"/>  
          <!-- Do not show on the menu controller's drop down list-->  
          <CommandFlag>NoShowOnMenuController</CommandFlag>  
          <!-- Become the permanent anchor item for the menu controller -->  
          <CommandFlag>FixMenuController</CommandFlag>  
          <!-- The text that appears in the tooltip.-->  
          <Strings>  
            <ButtonText>Set Startup Project</ButtonText>  
          </Strings>  
        </Button>  
    </Buttons>  
    ```  
  
4.  Bir simge (kaynakları klasöründe) proje ekleyin ve ardından referansı .vsct dosyasında ekleyin. Bu kılavuzda, proje şablona dahil ok simgesini kullanın.  
  
5.  Simgeler bölüm hemen önce komutları bölümüne dışında VisibilityConstraints bölümü ekleyin. (Sonra simgeleri eklerseniz, bir uyarı alabilirsiniz.) Bu bölümde menü denetleyicisi yalnızca birden çok proje çözümüyle ne zaman yüklendi göründüğünden emin hale getirir.  
  
    ```  
    <VisibilityConstraints>  
         <!--Make the MenuController show up only when there is a solution with more than one project loaded-->  
        <VisibilityItem guid="guidDynamicMenuPackageCmdSet" id="MyMenuController" context="UICONTEXT_SolutionHasMultipleProjects"/>  
    </VisibilityConstraints>  
    ```  
  
## <a name="implementing-the-dynamic-menu-command"></a>Dinamik menü komutunu uygulama  
 Öğesinden devralınan Dinamik menü komut sınıfı oluşturmak <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>. Bu uygulama, Oluşturucusu komutları eşleştirmek için kullanılacak bir koşulu belirtir. Geçersiz kılmanız gerekir <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.DynamicItemMatch%2A> ayarlamak üzere bu koşulu kullanmak için yöntemi <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.MatchedCommandId%2A> çağrılacak komut tanımlar özelliği.  
  
1.  DynamicItemMenuCommand.cs adlı yeni bir C# sınıfı dosya oluşturun ve adlı bir sınıf ekleyin **DynamicItemMenuCommand** devraldığı <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>:  
  
    ```csharp  
    class DynamicItemMenuCommand : OleMenuCommand  
    {  
  
    }  
  
    ```  
  
2.  Aşağıdaki using deyimlerini:  
  
    ```csharp  
    using Microsoft.VisualStudio.Shell;  
    using Microsoft.VisualStudio.Shell.Interop;  
    using System.ComponentModel.Design;  
    ```  
  
3.  Eşleşme koşulu depolamak için özel bir alan ekleyin:  
  
    ```csharp  
    private Predicate<int> matches;  
  
    ```  
  
4.  Öğesinden devralınan bir oluşturucu ekleyin <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> oluşturucusu ve bir komut işleyici belirtir ve bir <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> işleyicisi. Komut eşleme için bir koşul ekleyin:  
  
    ```csharp  
    public DynamicItemMenuCommand(CommandID rootId, Predicate<int> matches, EventHandler invokeHandler, EventHandler beforeQueryStatusHandler)  
        : base(invokeHandler, null /*changeHandler*/, beforeQueryStatusHandler, rootId)  
    {  
        if (matches == null)  
        {  
            throw new ArgumentNullException("matches");  
        }  
  
        this.matches = matches;  
    }  
    ```  
  
5.  Geçersiz kılma <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.DynamicItemMatch%2A> koşulu ve kümelerini eşleşmeleri olan çağırır yöntemi <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.MatchedCommandId%2A> özelliği:  
  
    ```csharp  
    public override bool DynamicItemMatch(int cmdId)  
    {  
        // Call the supplied predicate to test whether the given cmdId is a match.  
        // If it is, store the command id in MatchedCommandid   
        // for use by any BeforeQueryStatus handlers, and then return that it is a match.  
        // Otherwise clear any previously stored matched cmdId and return that it is not a match.  
        if (this.matches(cmdId))  
        {  
            this.MatchedCommandId = cmdId;  
            return true;  
        }  
  
        this.MatchedCommandId = 0;  
        return false;  
    }  
    ```  
  
## <a name="adding-the-command"></a>Komut ekleme  
 DynamicMenu Oluşturucusu dinamik menüler ve menü öğeleri dahil olmak üzere menü komutlarını ayarladığınız ' dir.  
  
1.  DynamicMenuPackage.cs içinde komut kümesini GUID ve komut Kimliğini ekleyin:  
  
    ```csharp  
    public const string guidDynamicMenuPackageCmdSet = "00000000-0000-0000-0000-00000000";  // get the GUID from the .vsct file  
    public const uint cmdidMyCommand = 0x104;  
    ```  
  
2.  Aşağıdaki DynamicMenu.cs dosyasına ekleyin using deyimleri:  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    using System.ComponentModel.Design;  
    ```  
  
3.  Özel alan DynamicMenu sınıfında ekleme **dte2**.  
  
    ```csharp  
    private DTE2 dte2;  
    ```  
  
4.  Bir özel rootItemId alanı ekleyin:  
  
    ```csharp  
    private int rootItemId = 0;  
    ```  
  
5.  DynamicMenu oluşturucuda menü komutunu ekleyin. Sonraki bölümde komut işleyici tanımlarız `BeforeQueryStatus` olay işleyicisi ve eşleşme koşulu.  
  
    ```csharp  
    private DynamicMenu(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException(nameof(package));  
        }  
  
        this.package = package;  
  
        OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
        if (commandService != null)  
        {  
            // Add the DynamicItemMenuCommand for the expansion of the root item into N items at run time.   
            CommandID dynamicItemRootId = new CommandID(new Guid(DynamicMenuPackageGuids.guidDynamicMenuPackageCmdSet), (int)DynamicMenuPackageGuids.cmdidMyCommand);  
            DynamicItemMenuCommand dynamicMenuCommand = new DynamicItemMenuCommand(dynamicItemRootId,  
                IsValidDynamicItem,  
                OnInvokedDynamicItem,  
                OnBeforeQueryStatusDynamicItem);  
                commandService.AddCommand(dynamicMenuCommand);  
                }  
  
        dte2 = (DTE2)this.ServiceProvider.GetService(typeof(DTE));  
    }  
    ```  
  
## <a name="implementing-the-handlers"></a>İşleyicileri uygulama  
 Dinamik menü öğeleri menü denetleyicisinde uygulamak için dinamik bir öğe tıklatıldığında komutu işlemesi gerekir. Menü öğesi durumunu ayarlar mantığı de uygulamanız gerekir. İşleyicileri DynamicMenu sınıfına ekleyin.  
  
1.  Uygulanacak **başlangıç projesi Ayarla** komutu, ekleme **OnInvokedDynamicItem** olay işleyicisi. Adı çağrılmış ve mutlak yolu ayarlayarak başlangıç projesi olarak ayarlayan komut metnini ile aynı olan proje arar <xref:EnvDTE.SolutionBuild.StartupProjects%2A> özelliği.  
  
    ```csharp  
    private void OnInvokedDynamicItem(object sender, EventArgs args)  
    {  
        DynamicItemMenuCommand invokedCommand = (DynamicItemMenuCommand)sender;  
        // If the command is already checked, we don't need to do anything  
        if (invokedCommand.Checked)  
            return;  
  
        // Find the project that corresponds to the command text and set it as the startup project  
        var projects = dte2.Solution.Projects;  
        foreach (Project proj in projects)  
        {  
            if (invokedCommand.Text.Equals(proj.Name))  
            {  
                dte2.Solution.SolutionBuild.StartupProjects = proj.FullName;  
                return;  
            }  
        }  
    }  
    ```  
  
2.  Ekleme `OnBeforeQueryStatusDynamicItem` olay işleyicisi. Bu önce adlı işleyicisidir bir `QueryStatus` olay. Menü öğesi bir "gerçek" öğesi, diğer bir deyişle, değil yer tutucu öğesi olup olmadığını belirler ve öğe zaten (proje başlangıç projesi olarak zaten ayarlanmış anlamına gelir) onay kutusunun işaretli olup.  
  
    ```csharp  
    private void OnBeforeQueryStatusDynamicItem(object sender, EventArgs args)  
    {  
        DynamicItemMenuCommand matchedCommand = (DynamicItemMenuCommand)sender;  
        matchedCommand.Enabled = true;  
        matchedCommand.Visible = true;  
  
        // Find out whether the command ID is 0, which is the ID of the root item.  
        // If it is the root item, it matches the constructed DynamicItemMenuCommand,  
         // and IsValidDynamicItem won't be called.  
        bool isRootItem = (matchedCommand.MatchedCommandId == 0);  
  
        // The index is set to 1 rather than 0 because the Solution.Projects collection is 1-based.  
        int indexForDisplay = (isRootItem ? 1 : (matchedCommand.MatchedCommandId - (int) DynamicMenuPackageGuids.cmdidMyCommand) + 1);  
  
        matchedCommand.Text = dte2.Solution.Projects.Item(indexForDisplay).Name;  
  
        Array startupProjects = (Array)dte2.Solution.SolutionBuild.StartupProjects;  
        string startupProject = System.IO.Path.GetFileNameWithoutExtension((string)startupProjects.GetValue(0));  
  
        // Check the command if it isn't checked already selected  
        matchedCommand.Checked = (matchedCommand.Text == startupProject);  
  
        // Clear the ID because we are done with this item.  
        matchedCommand.MatchedCommandId = 0;  
    }  
    ```  
  
## <a name="implementing-the-command-id-match-predicate"></a>Komut kimliği eşleşme koşulu uygulama  
  
1.  Şimdi eşleşme koşulu uygular. İki şey belirlemek ihtiyacımız: ilk olarak mı yoksa komut kimliği (olmasından sıfırdan büyük veya eşit bildirilen komut kimliği), geçerli ve ikinci, (olduğu Çözümdeki projeler sayısından daha az) olası bir proje olup olmadığını belirtir.  
  
    ```csharp  
    private bool IsValidDynamicItem(int commandId)  
    {  
        // The match is valid if the command ID is >= the id of our root dynamic start item   
        // and the command ID minus the ID of our root dynamic start item  
        // is less than or equal to the number of projects in the solution.  
        return (commandId >= (int)DynamicMenuPackageGuids.cmdidMyCommand) && ((commandId - (int)DynamicMenuPackageGuids.cmdidMyCommand) < dte2.Solution.Projects.Count);  
    }  
    ```  
  
## <a name="setting-the-vspackage-to-load-only-when-a-solution-has-multiple-projects"></a>Yalnızca bir çözüm birden çok proje olduğunda yüklemek için VSPackage ayarlama  
 Çünkü **başlangıç projesi Ayarla** komutu etkin çözüm birden çok proje olmadıkça algılama yapmak değil, otomatik yükle yalnızca bu durumda, VSPackage ayarlayabilirsiniz. Kullandığınız <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> UI bağlam birlikte <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids.SolutionHasMultipleProjects>. DynamicMenuPackage.cs dosyasında aşağıdaki öznitelikler DynamicMenuPackage sınıfına ekleyin:  
  
```csharp  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)]  
[ProvideMenuResource("Menus.ctmenu", 1)]  
[ProvideAutoLoad(UIContextGuids.SolutionHasMultipleProjects)]  
[Guid(DynamicMenuPackage.PackageGuidString)]  
public sealed class DynamicMenuItemsPackage : Package  
{}  
```  
  
## <a name="testing-the-set-startup-project-command"></a>Başlangıç projesi Ayarla komutu test etme  
 Artık kodunuzu test edebilirsiniz.  
  
1.  Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görüntülenmesi gerekir.  
  
2.  Deneysel örneğinde birden çok proje bulunduğu bir çözümü açın.  
  
     Ok simgesine görmeniz gerekir **Çözüm Gezgini** araç. Genişlettiğinizde, çözümdeki farklı projeler temsil menü öğeleri görüntülenmesi gerekir.  
  
3.  Projelerden biri işaretlediğinizde, başlangıç projesi haline gelir.  
  
4.  Çözümü kapatın veya yalnızca bir proje bulunduğu bir çözümü açın, araç çubuğu simgesi kaybolur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komutları, menüleri ve araç çubukları](../extensibility/internals/commands-menus-and-toolbars.md)   
 [VSPackage’ların Kullanıcı Arabirimi Öğeleri Eklemesi](../extensibility/internals/how-vspackages-add-user-interface-elements.md)