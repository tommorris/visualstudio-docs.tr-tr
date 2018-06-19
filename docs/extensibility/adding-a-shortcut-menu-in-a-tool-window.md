---
title: Bir araç penceresinde bir kısayol menüsü ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- context menus, adding to tool windows
- menus, context menus
- shortcut menus, adding to tool windows
- tool windows, adding context menus
ms.assetid: 50234537-9e95-4b7e-9cb7-e5cf26d6e9d2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e4b36800ea291c6f1bc0948a46b67c4e3549f349
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31568675"
---
# <a name="adding-a-shortcut-menu-in-a-tool-window"></a>Bir araç penceresinde bir kısayol menüsü ekleme
Bu kılavuz bir kısayol menüsü araç penceresinde koyar. Bir kısayol menüsü kullanıcı düğme, metin kutusu veya pencere arka plan tıklattığında görünen menüsünde ' dir. Bir kısayol menü komutlarını diğer menüleri veya araç çubuklarını komutlarını olarak aynı şekilde davranır. Bir kısayol menüsü desteklemek için .vsct dosyasında belirtin ve yanıt fareyi sağ olarak görüntüleyin.  
  
 WPF kullanıcı denetimi devralan bir özel araç penceresi sınıfında araç penceresi oluşan <xref:Microsoft.VisualStudio.Shell.ToolWindowPane>.  
  
 Bu kılavuzda, menü öğeleri .vsct dosyasında bildirme ve ardından araç penceresi tanımlayan sınıfta uygulamak için paketi çerçevesi ile yönetilen kullanarak bir Visual Studio menü kısayol menü oluşturma gösterilmektedir. Bu yaklaşım, Visual Studio komutları, kullanıcı Arabirimi öğeleri ve Otomasyon nesne modeli erişimi kolaylaştırır.  
  
 Alternatif olarak, Visual Studio işlevselliği kısayol menüsünü erişemez, kullanabileceğiniz <xref:System.Windows.FrameworkElement.ContextMenu%2A> kullanıcı denetimindeki bir XAML öğesi özelliği. Daha fazla bilgi için bkz: [ContextMenu](/dotnet/framework/wpf/controls/contextmenu).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-the-tool-window-shortcut-menu-package"></a>Araç penceresi kısayol menüsü paketi oluşturma  
  
1.  Adlı VSIX proje oluşturma `TWShortcutMenu` ve adlı bir araç penceresi şablonu Ekle **kısayol menüsü** ona. Araç penceresi oluşturma hakkında daha fazla bilgi için bkz: [bir uzantısı bir araç penceresi oluşturma](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
## <a name="specifying-the-shortcut-menu"></a>Kısayol menüsünün belirtme  
 Bu kılavuzda gösterilen bir kullanıcı gibi sağlar bir kısayol menüsünden araç penceresi arka doldurmak için kullanılan renk listesinden seçin.  
  
1.  ShortcutMenuPackage.vsct, guidShortcutMenuPackageCmdSet adlı GuidSymbol öğesinde bulun ve kısayol menüsünde, kısayol menüsünde grubunu ve menü seçeneklerini bildirin. GuidSymbol öğesi gibi görünmelidir:  
  
    ```xml  
    <GuidSymbol name="guidShortcutMenuPackageCmdSet" value="{00000000-0000-0000-0000-0000}"> // your GUID here  
        <IDSymbol name="ShortcutMenuCommandId" value="0x0100" />  
        <IDSymbol name="ColorMenu" value="0x1000"/>  
        <IDSymbol name="ColorGroup" value="0x1100"/>  
        <IDSymbol name="cmdidRed" value="0x102"/>  
        <IDSymbol name="cmdidYellow" value="0x103"/>  
        <IDSymbol name="cmdidBlue" value="0x104"/>  
    </GuidSymbol>  
    ```  
  
2.  Düğmeleri öğesi hemen önce bir menü öğesi oluşturun ve ardından kısayol menüsünün içinde tanımlayın.  
  
    ```vb  
    <Menus>  
      <Menu guid="guidShortcutMenuPackageCmdSet" id="ColorMenu" type="Context">  
        <Strings>  
          <ButtonText>Color change</ButtonText>  
          <CommandName>ColorChange</CommandName>  
        </Strings>  
      </Menu>  
    </Menus>  
    ```  
  
     Menü veya araç parçası olmadığından bir kısayol menüsü bir üst öğesi yok.  
  
3.  Kısayol menüsü öğelerini içeren bir Grup öğesi ile öğe grupları oluşturun ve Grup kısayol menüsünün ile ilişkilendirin.  
  
    ```xml  
    <Groups>  
        <Group guid="guidShortcutMenuPackageCmdSet" id="ColorGroup">  
            <Parent guid="guidShortcutMenuPackageCmdSet" id="ColorMenu"/>  
        </Group>  
    </Groups>  
    ```  
  
4.  Düğmeleri öğesinde görünür tekil komutlar kısayol menüsünde tanımlayın. Düğmeleri öğesi aşağıdaki gibi görünmelidir:  
  
    ```xml  
    <Buttons>  
        <Button guid="guidShortcutMenuPackageCmdSet" id="ShortcutMenuCommandId" priority="0x0100" type="Button">  
            <Parent guid="guidSHLMainMenu" id="IDG_VS_WNDO_OTRWNDWS1"/>  
            <Icon guid="guidImages" id="bmpPic1" />  
            <Strings>  
                <ButtonText>ShortcutMenu</ButtonText>  
            </Strings>  
        </Button>  
  
        <Button guid="guidShortcutMenuPackageCmdSet" id="cmdidRed" priority="1" type="Button">  
            <Parent guid="guidShortcutMenuPackageCmdSet" id="ColorGroup" />  
            <Strings>  
                <ButtonText>Red</ButtonText>  
            </Strings>  
        </Button>  
  
        <Button guid="guidShortcutMenuPackageCmdSet" id="cmdidYellow" priority="3" type="Button">  
            <Parent guid="guidShortcutMenuPackageCmdSet" id="ColorGroup" />  
            <Strings>  
                <ButtonText>Yellow</ButtonText>  
            </Strings>  
        </Button>  
  
        <Button guid="guidShortcutMenuPackageCmdSet" id="cmdidBlue" priority="5" type="Button">  
            <Parent guid="guidShortcutMenuPackageCmdSet" id="ColorGroup" />  
            <Strings>  
                <ButtonText>Blue</ButtonText>  
            </Strings>  
        </Button>  
    </Buttons>  
    ```  
  
5.  ShortcutMenuCommand.cs içinde komutu tanımlarında GUID, kısayol menüsünde ve menü öğeleri kümesine ekleyin.  
  
    ```csharp  
    public const string guidShortcutMenuPackageCmdSet = "00000000-0000-0000-0000-00000000"; // your GUID will differ  
    public const int ColorMenu = 0x1000;  
    public const int cmdidRed = 0x102;  
    public const int cmdidYellow = 0x103;  
    public const int cmdidBlue = 0x104;  
    ```  
  
     ShortcutMenuPackage.vsct dosyasının simgeler bölümünde tanımlanan aynı komut kimlikleri bunlar. Bağlam grubu yalnızca .vsct dosyasında gerektirdiğinden buraya dahil edilmez.  
  
## <a name="implementing-the-shortcut-menu"></a>Kısayol menüsünün uygulama  
 Bu bölümde, kısayol menüsünde ve kendi komutları uygular.  
  
1.  ShortcutMenu.cs, araç penceresi menü komut hizmeti alabilir, ancak içerdiği denetleyemezsiniz. Aşağıdaki adımlar menü komut hizmeti kullanıcı denetimi kullanılabilir hale getirmek nasıl gösterir.  
  
2.  ShortcutMenu.cs içinde aşağıdaki ekleme deyimlerini kullanarak:  
  
    ```csharp  
    using Microsoft.VisualStudio.Shell;  
    using System.ComponentModel.Design;  
    ```  
  
3.  Menü komut hizmeti almak ve menü komut hizmeti contructor geçirme denetim eklemek için aracı pencerenin önce Initialize() yöntemini geçersiz kılın:  
  
    ```csharp  
    protected override void Initialize()  
    {  
        var commandService = (OleMenuCommandService)GetService(typeof(IMenuCommandService));  
        Content = new ShortcutMenuControl(commandService);  
    }  
    ```  
  
4.  Kısayol menüsü araç penceresi oluşturucuda denetimi ekler satırını kaldırın. Oluşturucusu gibi görünmelidir:  
  
    ```csharp  
    public ShortcutMenu() : base(null)  
    {  
        this.Caption = "ShortcutMenu";  
        this.BitmapResourceID = 301;  
        this.BitmapIndex = 1;  
    }  
    ```  
  
5.  ShortcutMenuControl.xaml.cs, menü komut hizmeti için özel bir alan ekleyin ve menü komut hizmeti yapılacak denetim Oluşturucusu değiştirin. Ardından bağlam menüsü komutlarını eklemek için menü komut hizmeti kullanın. ShortcutMenuControl oluşturucusu, aşağıdaki kod gibi görünmelidir. Komut işleyici daha sonra tanımlanır.  
  
    ```csharp  
    public ShortcutMenuControl(OleMenuCommandService service)  
    {  
        this.InitializeComponent();  
        commandService = service;  
  
        if (null !=commandService)  
        {  
            // Create an alias for the command set guid.  
            Guid guid = new Guid(ShortcutMenuCommand.guidShortcutMenuPackageCmdSet);  
  
            // Create the command IDs.   
            var red = new CommandID(guid, ShortcutMenuCommand.cmdidRed);  
            var yellow = new CommandID(guid, ShortcutMenuCommand.cmdidYellow);  
            var blue = new CommandID(guid, ShortcutMenuCommand.cmdidBlue);  
  
            // Add a command for each command ID.  
            commandService.AddCommand(new MenuCommand(ChangeColor, red));  
            commandService.AddCommand(new MenuCommand(ChangeColor, yellow));  
            commandService.AddCommand(new MenuCommand(ChangeColor, blue));  
        }  
    }  
    ```  
  
6.  ShortcutMenuControl.xaml içinde eklemek bir <xref:System.Windows.UIElement.MouseRightButtonDown> en üst düzey olay <xref:System.Windows.Controls.UserControl> öğesi. XAML dosyası gibi görünmelidir:  
  
    ```vb  
    <UserControl x:Class="TWShortcutMenu.ShortcutMenuControl"  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
            Background="{DynamicResource VsBrush.Window}"  
            Foreground="{DynamicResource VsBrush.WindowText}"  
            mc:Ignorable="d"  
            d:DesignHeight="300" d:DesignWidth="300"  
            Name="MyToolWindow"  
            MouseRightButtonDown="MyToolWindow_MouseRightButtonDown">  
        <Grid>  
            <StackPanel Orientation="Vertical">  
                <TextBlock Margin="10" HorizontalAlignment="Center">ShortcutMenu</TextBlock>  
            </StackPanel>  
        </Grid>  
    </UserControl>  
    ```  
  
7.  ShortcutMenuControl.xaml.cs olay işleyicisi için bir saplama ekleyin.  
  
    ```csharp  
    private void MyToolWindow_MouseRightButtonDown(object sender, MouseButtonEventArgs e)  
    {  
    . . .  
    }  
    ```  
  
8.  Aşağıdaki using deyimlerini aynı dosyaya:  
  
    ```csharp  
    using Microsoft.VisualStudio.Shell;  
    using System.ComponentModel.Design;  
    using System;  
    using System.Windows.Input;  
    using System.Windows.Media;  
    ```  
  
9. Uygulama `MyToolWindowMouseRightButtonDown` şekilde olay.  
  
    ```csharp  
    private void MyToolWindow_MouseRightButtonDown(object sender, MouseButtonEventArgs e)  
    {  
        if (null != commandService)  
        {  
            CommandID menuID = new CommandID(  
                new Guid(ShortcutMenuCommand.guidShortcutMenuPackageCmdSet),  
                ShortcutMenuCommand.ColorMenu);  
            Point p = this.PointToScreen(e.GetPosition(this));  
            commandService.ShowContextMenu(menuID, (int)p.X, (int)p.Y);  
        }  
    }  
    ```  
  
     Bu oluşturur bir <xref:System.ComponentModel.Design.CommandID> kısayol menüsü nesne fare tıklatma konumunu tanımlar ve kısayol menüsünü kullanarak söz konusu konumda açar <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService.ShowContextMenu%2A> yöntemi.  
  
10. Komut işleyici uygulayın.  
  
    ```csharp  
    private void ChangeColor(object sender, EventArgs e)  
    {  
        var mc = sender as MenuCommand;  
  
        switch (mc.CommandID.ID)  
        {  
            case ShortcutMenuCommand.cmdidRed:  
                MyToolWindow.Background = Brushes.Red;  
                break;  
            case ShortcutMenuCommand.cmdidYellow:  
                MyToolWindow.Background = Brushes.Yellow;  
                break;  
            case ShortcutMenuCommand.cmdidBlue:  
                MyToolWindow.Background = Brushes.Blue;  
                break;  
        }  
    }  
    ```  
  
     Bu durumda, tek yöntemi belirleyerek tüm menü öğelerini olaylarını işleme <xref:System.ComponentModel.Design.CommandID> ve buna uygun olarak arka plan rengini ayarlama. Menü öğeleri ilgisiz komutları içeriyorsa, her komut için ayrı olay işleyicisi oluşturacak.  
  
## <a name="testing-the-tool-window-features"></a>Araç penceresi özelliklerini test etme  
  
1.  Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görüntülenir.  
  
2.  Deneysel örneğinde tıklatın **görünüm / diğer pencereler**ve ardından **kısayol menüsü**. Bunun yapılması, araç penceresi görüntülemelidir.  
  
3.  Araç penceresi gövdesinde sağ tıklayın. Renkleri listesini içeren bir kısayol menüsü görüntülenmesi gerekir.  
  
4.  Bir renk kısayol menüsünde tıklatın. Seçili renk araç penceresi arka plan rengini değiştirilmelidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komutları, menüleri ve araç çubukları](../extensibility/internals/commands-menus-and-toolbars.md)   
 [Hizmetleri Kullanma ve Sağlama](../extensibility/using-and-providing-services.md)