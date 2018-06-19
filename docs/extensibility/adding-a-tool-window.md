---
title: Araç penceresi ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- tutorials
- tool windows
ms.assetid: 8e16c381-03c8-404e-92ef-3614cdf3150a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: db06bebd700fa229685d6b79ffcfb014ef301994
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31107887"
---
# <a name="adding-a-tool-window"></a>Araç penceresi ekleme
Bu kılavuzda bir araç penceresi oluşturun ve aşağıdaki yollarla Visual Studio'ya tümleştirme hakkında bilgi edinin:  
  
-   Bir denetim için araç penceresi ekleyin.  
  
-   Bir araç için bir araç penceresi ekleyin.  
  
-   Bir komut araç çubuğuna ekleyin.  
  
-   Komutları uygulayın.  
  
-   Araç penceresi için varsayılan konumu ayarlayın.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-tool-window"></a>Araç penceresi oluşturma  
  
1.  Adlı bir proje oluşturun **FirstToolWin** VSIX şablonu kullanarak ve adlandırılmış bir özel araç pencere öğesi şablonu Ekle **FirstToolWindow**.  
  
    > [!NOTE]
    >  Bir araç penceresi uzantı oluşturma hakkında daha fazla bilgi için bkz: [bir uzantısı bir araç penceresi oluşturma](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
## <a name="add-a-control-to-the-tool-window"></a>Araç penceresi denetim ekleme  
  
1.  Varsayılan Denetim kaldırın. FirstToolWindowControl.xaml açın ve silme **bana tıklayın!** düğme.  
  
2.  İçinde **araç**, genişletin **tüm WPF denetimleri** bölümünde ve sürükleyin **medya öğesi** denetimini **FirstToolWindowControl** formu. Denetimi seçin ve **özellikleri** penceresinde, bu öğe adı **mediaElement1**.  
  
## <a name="add-a-toolbar-to-the-tool-window"></a>Araç çubuğu araç penceresi ekleme  
 Aşağıdaki şekilde bir araç çubuğu ekleyerek, kendi gradyan ve renkleri IDE geri kalanı ile tutarlı olduğunu garanti.  
  
1.  İçinde **Çözüm Gezgini**, FirstToolWindowPackage.vsct açın. .Vsct dosya, XML kullanarak, aracı pencerenizde grafik kullanıcı arabirimi (GUI) öğelerini tanımlar.  
  
2.  İçinde `<Symbols>` bölümünde, Bul `<GuidSymbol>` düğümü, `name` özniteliği `guidFirstToolWindowPackageCmdSet`. Aşağıdaki iki eklemek `<IDSymbol>` listesi öğelerine `<IDSymbol>` bir araç ve araç grubu tanımlamak için bu düğümde öğeleri.  
  
    ```xml  
    <IDSymbol name="ToolbarID" value="0x1000" />  
    <IDSymbol name="ToolbarGroupID" value="0x1001" />  
    ```  
  
3.  Yukarıdaki `<Buttons>` bölümünde, oluşturmak bir `<Menus>` bu benzer bölümü:  
  
    ```xml  
    <Menus>  
        <Menu guid="guidFirstToolWindowPackageCmdSet" id="ToolbarID" priority="0x0000" type="ToolWindowToolbar">  
            <Parent guid="guidFirstToolWindowPackageCmdSet" id="ToolbarID" />  
            <Strings>  
                <ButtonText>Tool Window Toolbar</ButtonText>  
                <CommandName>Tool Window Toolbar</CommandName>  
            </Strings>  
        </Menu>  
    </Menus>  
    ```  
  
     Menü birkaç farklı türde vardır. Bu menü tarafından tanımlanan bir araç çubuğu araç penceresinde olan kendi `type` özniteliği. `guid` Ve `id` ayarları yapmak araç çubuğunun tam kimliği. Genellikle, `<Parent>` menüsüne içeren bir gruptur. Ancak, bir araç kendi üst öğe olarak tanımlanır. Bu nedenle, aynı tanımlayıcısı için kullanılan `<Menu>` ve `<Parent>` öğeleri. `priority` Özniteliktir yalnızca ' 0'.  
  
4.  Araç çubukları birçok yolla menüleri benzer. Örneğin, yalnızca bir menü komutları gruplarınız gibi araç çubukları de grupları olabilir. (Menülerde, komut grupları yatay çizgilerle ayrılır. Araç çubuklarında, grupları visual Bölücü tarafından ayrılmış olan değildir.)  
  
     Ekleme bir `<Groups>` içeren bölümü bir `<Group>` öğesi. Bu kimliği içinde bildirilen Grup tanımlar `<Symbols>` bölümü. Ekleme `<Groups>` hemen sonra bölümünde `<Menus>` bölümü.  
  
    ```xml  
    <Groups>  
       <Group guid="guidFirstToolWindowPackageCmdSet" id="ToolbarGroupID" priority="0x0000">  
           <Parent guid="guidFirstToolWindowPackageCmdSet" id="ToolbarID" />  
       </Group>  
    </Groups>  
    ```  
  
     Üst GUID ve ID GUID ve araç Kimliğini ayarlayarak, araç çubuğuna grubunu ekleyin.  
  
## <a name="add-a-command-to-the-toolbar"></a>Araç çubuğuna komut ekleme  
 Bir komut düğmesi olarak görüntülenen araç çubuğu'nu ekleyin.  
  
1.  İçinde `<Symbols>` bölümünde, aşağıdaki IDSymbol öğeleri yalnızca araç çubuğu ve araç sonra Grup bildirimleri bildirin.  
  
    ```xml  
    <IDSymbol name="cmdidWindowsMedia" value="0x0100" />  
    <IDSymbol name="cmdidWindowsMediaOpen" value="0x132" />  
    ```  
  
2.  İçinde bir düğme öğesi Ekle `<Buttons>` bölümü. Bu öğe, bir arama (Büyüteç) simgesiyle araç penceresi araç çubuğunda görünür.  
  
    ```xml  
    <Button guid="guidFirstToolWindowPackageCmdSet" id="cmdidWindowsMediaOpen" priority="0x0101" type="Button">  
        <Parent guid="guidFirstToolWindowPackageCmdSet" id="ToolbarGroupID"/>  
        <Icon guid="guidImages" id="bmpPicSearch" />  
        <Strings>  
            <CommandName>cmdidWindowsMediaOpen</CommandName>  
            <ButtonText>Load File</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
3.  FirstToolWindowCommand.cs açın ve sonra yalnızca var olan alanları sınıfında aşağıdaki satırları ekleyin.  
  
    ```csharp  
    public const string guidFirstToolWindowPackageCmdSet = "00000000-0000-0000-0000-0000";  // get the GUID from the .vsct file  
    public const uint cmdidWindowsMedia =        0x100;   
    public const int cmdidWindowsMediaOpen = 0x132;  
    public const int ToolbarID = 0x1000;  
    ```  
  
     Bunun yapılması, komutlarınızı kodda kullanılabilir hale getirir.  
  
## <a name="add-a-mediaplayer-property-to-firsttoolwindowcontrol"></a>İçin FirstToolWindowControl MediaPlayer özellik ekleme  
 Araç çubuğu denetimleri için olay işleyicileri kodunuzu FirstToolWindowControl sınıfı alt Media Player denetimi erişebilir olması gerekir.  
  
 İçinde **Çözüm Gezgini**, FirstToolWindowControl.xaml sağ tıklayın, **görünümü kodu**ve FirstToolWindowControl sınıfa aşağıdaki kodu ekleyin.  
  
```csharp  
public System.Windows.Controls.MediaElement MediaPlayer  
{  
    get { return mediaElement1; }  
}  
```  
  
## <a name="instantiate-the-tool-window-and-toolbar"></a>Araç çubuğu ve araç penceresi örneği  
 Araç çubuğu ekleyip çağıran menü komutu **Dosya Aç** iletişim ve seçilen ortam dosyasını yürütür.  
  
1.  FirstToolWindow.cs açın ve aşağıdakileri ekleyin `using` deyimleri.  
  
    ```csharp  
    using System.ComponentModel.Design;  
    using System.Windows.Forms;  
    using Microsoft.VisualStudio.Shell.Interop;   
    ```  
  
2.  FirstToolWindow sınıfı içinde FirstToolWindowControl denetlemek için ortak bir başvuru ekleyin.  
  
    ```csharp  
    public FirstToolWindowControl control;  
    ```  
  
3.  Oluşturucusu sonunda, bu denetim değişkeni yeni oluşturulan denetim olarak ayarlayın.  
  
    ```csharp  
    control = new FirstToolWindowControl();   
    base.Content = control;  
    ```  
  
4.  Araç çubuğu oluşturucusu içinde örneği oluşturur.  
  
    ```csharp  
    this.ToolBar = new CommandID(new Guid(FirstToolWindowCommand.guidFirstToolWindowPackageCmdSet),   
        FirstToolWindowCommand.ToolbarID);  
    this.ToolBarLocation = (int)VSTWT_LOCATION.VSTWT_TOP;  
    ```  
  
5.  Bu noktada FirstToolWindow oluşturucusu aşağıdaki gibi görünmelidir:  
  
    ```csharp  
    public FirstToolWindow() : base(null)  
    {  
        this.Caption = "FirstToolWindow";  
        this.BitmapResourceID = 301;  
        this.BitmapIndex = 1;  
        control = new FirstToolWindowControl();  
        base.Content = control;  
        this.ToolBar = new CommandID(new Guid(FirstToolWindowCommand.guidFirstToolWindowPackageCmdSet),   
            FirstToolWindowCommand.ToolbarID);  
            this.ToolBarLocation = (int)VSTWT_LOCATION.VSTWT_TOP;  
    }  
    ```  
  
6.  Menü komutunu araç çubuğuna ekleyin. FirstToolWindowCommand.cs sınıfında aşağıdaki ekleme deyimini kullanarak  
  
    ```csharp  
    using System.Windows.Forms;  
    ```  
  
7.  FirstToolWindowCommand sınıfında ShowToolWindow() yönteminin sonuna aşağıdaki kodu ekleyin. Sonraki bölümde ButtonHandler komutu uygulanacaktır.  
  
    ```csharp  
    // Create the handles for the toolbar command.   
    var mcs = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
    var toolbarbtnCmdID = new CommandID(new Guid(FirstToolWindowCommand.guidFirstToolWindowPackageCmdSet),  
        FirstToolWindowCommand.cmdidWindowsMediaOpen);  
    var menuItem = new MenuCommand(new EventHandler(  
        ButtonHandler), toolbarbtnCmdID);  
    mcs.AddCommand(menuItem);  
    ```  
  
#### <a name="to-implement-a-menu-command-in-the-tool-window"></a>Menü komutu araç penceresinde uygulamak için  
  
1.  Çağıran bir ButtonHandler yöntemi FirstToolWindowCommand sınıfında ekleme **Dosya Aç** iletişim. Bir dosya seçildiğinde ortam dosyasını yürütür.  
  
2.  FirstToolWindowCommand sınıfında FindToolWindow() yönteminde oluşturulduğunu FirstToolWindow penceresine özel bir başvuru ekleyin.  
  
    ```csharp  
    private FirstToolWindow window;  
    ```  
  
3.  (ButtonHandler komut işleyici pencere denetim erişebilmesi. yukarıda tanımlanan penceresini ayarlamak için ShowToolWindow() yöntemini değiştirme Tam ShowToolWindow() yöntemi aşağıda verilmiştir.  
  
    ```csharp  
    private void ShowToolWindow(object sender, EventArgs e)  
    {  
        window = (FirstToolWindow) this.package.FindToolWindow(typeof(FirstToolWindow), 0, true);  
        if ((null == window) || (null == window.Frame))  
        {  
                            throw new NotSupportedException("Cannot create tool window");  
        }  
  
        IVsWindowFrame windowFrame = (IVsWindowFrame)window.Frame;  
                Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(windowFrame.Show());  
  
         var mcs = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
        var toolbarbtnCmdID = new CommandID(new Guid(FirstToolWindowCommandguidFirstToolWindowPackageCmdSet),  
            FirstToolWindowCommand.cmdidWindowsMediaOpen);  
        var menuItem = new MenuCommand(new EventHandler(  
            ButtonHandler), toolbarbtnCmdID);  
        mcs.AddCommand(menuItem);  
    }  
    ```  
  
4.  ButtonHandler yöntemi ekleyin. Kullanıcının yürütmek için medya dosyası belirlemek bir OpenFileDialog oluşturur ve sonra seçilen dosya çalar.  
  
    ```csharp  
    private void ButtonHandler(object sender, EventArgs arguments)  
    {  
        OpenFileDialog openFileDialog = new OpenFileDialog();  
        DialogResult result = openFileDialog.ShowDialog();  
        if (result == DialogResult.OK)  
        {  
            window.control.MediaPlayer.Source = new System.Uri(openFileDialog.FileName);  
        }  
    }  
    ```  
  
## <a name="set-the-default-position-for-the-tool-window"></a>Araç penceresi için varsayılan konumu ayarlayın  
 Ardından, IDE araç penceresi için bir varsayılan konumu belirtin. Araç penceresi için yapılandırma bilgilerini FirstToolWindowPackage.cs dosyasıdır.  
  
1.  FirstToolWindowPackage.cs içinde bulma <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> özniteliği `FirstToolWindowPackage` FirstToolWindow oluşturucuya geçirir sınıfı. Varsayılan konumu belirtmek için aşağıdaki örneğine Oluşturucusu daha fazla parametre eklemeniz gerekir.  
  
    ```csharp  
    [ProvideToolWindow(typeof(FirstToolWindow),  
        Style = Microsoft.VisualStudio.Shell.VsDockStyle.Tabbed,  
        Window = "3ae79031-e1bc-11d0-8f78-00a0c9110057")]  
    ```  
  
     İlk adlandırılmış parametre `Style` ve değeri olduğu `Tabbed`, yani pencere varolan penceresinde sekme olacaktır. Yerleştirme konumunu tarafından belirtilen `Window` parametresi, bu durumda, n GUID'i **Çözüm Gezgini**.  
  
    > [!NOTE]
    >  IDE içinde windows türleri hakkında daha fazla bilgi için bkz: <xref:EnvDTE.vsWindowType>.  
  
## <a name="testing-the-tool-window"></a>Araç penceresi test etme  
  
1.  F5 tuşuna basarak Visual Studio Deneysel yeni bir örneğini açın oluşturun.  
  
2.  Üzerinde **Görünüm** menüsündeki **diğer pencereler** ve ardından **ilk araç penceresi**.  
  
     Media player araç penceresi aynı konumda yer alan açmalısınız **Çözüm Gezgini**. Hala aynı konumda yer önce görünürse, pencere düzenini sıfırlamak (**penceresi / pencere düzenini Sıfırla**).  
  
3.  Araç penceresinde (arama simgesine sahip) düğmesine tıklayın. Bir desteklenen ses veya video dosyası seçin, örneğin, C:\windows\media\chimes.wav tuşuna **açık**.  
  
     Çan ses.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komutlar, Menüler ve Araç Çubukları](../extensibility/internals/commands-menus-and-toolbars.md)