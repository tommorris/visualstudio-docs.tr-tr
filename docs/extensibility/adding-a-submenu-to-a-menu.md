---
title: Bir alt menüye ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- context menus
- submenus, cascading
- cascading submenus
- menus, creating cascading submenus
ms.assetid: 692600cb-d052-40e2-bdae-4354ae7c6c84
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f6998c275aead7b12b107f700e699f5a82edd84e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="adding-a-submenu-to-a-menu"></a>Bir menüye alt menü ekleme
Bu kılavuzda tanıtım inşa edilmiştir [Visual Studio menü çubuğunda bir menü ekleme](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md) menüye ekleme göstererek **TestMenu** menüsü.  
  
 Alt menü başka bir menüsünde görünen ikincil menüsünde ' dir. Alt menü adını izleyen okla tanımlanabilir. Adını tıklatarak, alt ve görüntülenecek kendi komutları neden olur.  
  
 Bu kılavuz Visual Studio menü çubuğunda menüde bir alt oluşturur ve yeni bir komut menüdeki koyar. İzlenecek yol da yeni bir komut uygular.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="adding-a-submenu-to-a-menu"></a>Bir menüye alt menü ekleme  
  
1.  Adımları [Visual Studio menü çubuğunda bir menü ekleme](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md) proje ve menü öğesi oluşturmak için. Bu izlenecek adımları VSIX proje adı olduğunu varsayın `TopLevelMenu`.  
  
2.  Open TestCommandPackage.vsct. İçinde `<Symbols>` bölümünde bir `<IDSymbol>` öğesi alt, bir alt grup için diğeri için komut tümünde `<GuidSymbol>` "guidTopLevelMenuCmdSet." adlı düğüm Bu içeren, aynı düğümüdür `<IDSymbol>` en üst düzey menü öğesi.  
  
    ```xml  
    <IDSymbol name="SubMenu" value="0x1100"/>  
    <IDSymbol name="SubMenuGroup" value="0x1150"/>  
    <IDSymbol name="cmdidTestSubCommand" value="0x0105"/>  
    ```  
  
3.  Yeni oluşturulan menüye ekleme `<Menus>` bölümü.  
  
    ```xml  
    <Menu guid="guidTestCommandPackageCmdSet" id="SubMenu" priority="0x0100" type="Menu">  
        <Parent guid="guidTestCommandPackageCmdSet" id="MyMenuGroup"/>  
        <Strings>  
            <ButtonText>Sub Menu</ButtonText>  
            <CommandName>Sub Menu</CommandName>  
        </Strings>  
    </Menu>  
    ```  
  
     Üst GUID/kimliği çiftinin oluşturulduğu menü grubunu belirtir [Visual Studio menü çubuğunda bir menü ekleme](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md), ve bir alt düzey menü öğesi değil.  
  
4.  Adım 2'te tanımlanan menü grubunu eklemek `<Groups>` bölüm ve alt alt öğesi yapın.  
  
    ```xml  
    <Group guid="guidTestCommandPackageCmdSet" id="SubMenuGroup" priority="0x0000">  
        <Parent guid="guidTestCommandPackageCmdSet" id="SubMenu"/>  
    </Group>  
    ```  
  
5.  Yeni bir ekleme `<Button>` öğesine `<Buttons>` menüdeki bir öğe olarak 2. adımda oluşturduğunuz komutu tanımlamak için bölüm.  
  
    ```xml  
    <Button guid="guidTestCommandPackageCmdSet" id="cmdidTestSubCommand" priority="0x0000" type="Button">  
        <Parent guid="guidTestCommandPackageCmdSet" id="SubMenuGroup" />  
        <Icon guid="guidImages" id="bmpPic2" />  
        <Strings>  
           <CommandName>cmdidTestSubCommand</CommandName>  
           <ButtonText>Test Sub Command</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
6.  Çözümü derlemek ve hata ayıklamayı Başlat. Deneysel örneği görmeniz gerekir.  
  
7.  Tıklatın **TestMenu** adlı yeni bir alt görmek için **alt menü**. Tıklatın **alt menü** alt açmak ve yeni bir komut görmek için **Test alt komutu**. Bu tıklatarak fark **Test alt komutun** hiçbir şey yapmaz.  
  
## <a name="adding-a-command"></a>Bir komut ekleme  
  
1.  TestCommand.cs açın ve aşağıdaki komut kimliği sonra varolan komut kimliği ekleyin  
  
    ```csharp  
    public const int cmdidTestSubCmd = 0x105;  
    ```  
  
2.  Alt komutunu ekleyin. Komut Oluşturucu bulun. Çağırdıktan hemen sonra aşağıdaki satırları ekleyin `AddCommand` yöntemi.  
  
    ```csharp  
    CommandID subCommandID = new CommandID(CommandSet, cmdidTestSubCmd);  
    MenuCommand subItem = new MenuCommand(  
        new EventHandler(SubItemCallback), subCommandID);  
    commandService.AddCommand(subItem);  
  
    ```  
  
     `SubItemCallback` Komut işleyici tanımlanması daha sonra. Oluşturucusu gibi görünmelidir:  
  
    ```csharp  
    private TestCommand(Package package)  
            {  
                if (package == null)  
                {  
                    throw new ArgumentNullException("package");  
                }  
  
                this.package = package;  
  
                OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
                if (commandService != null)  
                {  
                    var menuCommandID = new CommandID(CommandSet, CommandId);  
                    var menuItem = new MenuCommand(this.MenuItemCallback, menuCommandID);  
                    commandService.AddCommand(menuItem);  
                    CommandID subCommandID = new CommandID(CommandSet, cmdidTestSubCmd);  
                    MenuCommand subItem = new MenuCommand(  
                        new EventHandler(SubItemCallback), subCommandID);  
                    commandService.AddCommand(subItem);  
                }  
    ```  
  
3.  SubItemCallback() ekleyin. Yeni alt komutta tıklatıldığında çağrılan yöntem budur.  
  
    ```csharp  
    private void SubItemCallback(object sender, EventArgs e)  
    {  
        IVsUIShell uiShell = (IVsUIShell)this.ServiceProvider.GetService(  
            typeof(SVsUIShell));  
        Guid clsid = Guid.Empty;  
        int result;  
        uiShell.ShowMessageBox(  
            0,  
            ref clsid,  
            "TestCommand",  
            string.Format(CultureInfo.CurrentCulture,  
            "Inside TestCommand.SubItemCallback()",  
            this.ToString()),  
            string.Empty,  
            0,  
            OLEMSGBUTTON.OLEMSGBUTTON_OK,  
            OLEMSGDEFBUTTON.OLEMSGDEFBUTTON_FIRST,  
            OLEMSGICON.OLEMSGICON_INFO,  
            0,  
            out result);  
    }  
    ```  
  
4.  Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görüntülenmesi gerekir.  
  
5.  Üzerinde **TestMenu** menüsünde tıklatın **alt menü** ve ardından **Test alt komutu**. Bir ileti kutusu görünür ve "TestCommand.SubItemCallback() içinde Test komut" metin görüntüleme.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio menü çubuğunda bir menü ekleme](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md)   
 [Komutlar, Menüler ve Araç Çubukları](../extensibility/internals/commands-menus-and-toolbars.md)
