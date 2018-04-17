---
title: Menü komutu metin değiştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- menus, changing text
- text, menus
- commands, changing text
ms.assetid: 5cb676a0-c6e2-47e5-bd2b-133dc8842e46
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 717e360e08cbdfee23221b9384a5574530f92e23
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="changing-the-text-of-a-menu-command"></a>Menü komutu metin değiştirme
Aşağıdaki adımları kullanarak menü komutu metin etiketini değiştirmek nasıl Göster <xref:System.ComponentModel.Design.IMenuCommandService> hizmet.  
  
## <a name="changing-a-menu-command-label-with-the-imenucommandservice"></a>Menü komutu etiketinin IMenuCommandService ile değiştirme  
  
1.  Adlı VSIX proje oluşturma `MenuText` menü komutu ile adlı **ChangeMenuText**. Daha fazla bilgi için bkz: [uzantı menü komutu ile oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2.  .Vstc dosyasına ekleyin `TextChanges` aşağıdaki örnekte gösterildiği gibi menü komutu için bayrak.  
  
    ```xml  
    <Button guid="guidChangeMenuTextPackageCmdSet" id="ChangeMenuTextId" priority="0x0100" type="Button">  
        <Parent guid="guidChangeMenuTextPackageCmdSet" id="MyMenuGroup" />  
        <Icon guid="guidImages" id="bmpPic1" />  
        <CommandFlag>TextChanges</CommandFlag>  
        <Strings>  
            <ButtonText>Invoke ChangeMenuText</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
3.  ChangeMenuText.cs dosyasında menü komutu görüntülenmeden önce çağrılacak bir olay işleyicisi oluşturun.  
  
    ```csharp  
    private void OnBeforeQueryStatus(object sender, EventArgs e)  
    {  
        var myCommand = sender as OleMenuCommand;  
        if (null != myCommand)  
        {  
            myCommand.Text = "New Text";  
        }  
    }  
    ```  
  
     Değiştirerek bu yöntemde menü komutu durumunu güncelleştirebilir <xref:System.ComponentModel.Design.MenuCommand.Visible%2A>, <xref:System.ComponentModel.Design.MenuCommand.Checked%2A>, ve <xref:System.ComponentModel.Design.MenuCommand.Enabled%2A> özellikleri <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> nesnesi.  
  
4.  ChangeMenuText oluşturucuda özgün komut başlatma ve yerleştirme kodu oluşturan kod ile değiştirin. bir <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> (yerine bir `MenuCommand`) menü komutu temsil eder, ekler <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> olay işleyicisi ve menüsü sağlar Menü komut hizmeti komutu.  
  
     İşte ne gibi görünmelidir:  
  
    ```csharp  
    private ChangeMenuText(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException(nameof(package));  
        }  
  
        this.package = package;  
  
        OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
        if (commandService != null)  
        {  
            CommandID menuCommandID = new CommandID(MenuGroup, CommandId);  
            EventHandler eventHandler = this.ShowMessageBox;  
            OleMenuCommand menuItem = new OleMenuCommand(ShowMessageBox, menuCommandID);  
            menuItem.BeforeQueryStatus +=  
                new EventHandler(OnBeforeQueryStatus);  
            commandService.AddCommand(menuItem);  
        }  
    }  
    ```  
  
5.  Projeyi derleyin ve hata ayıklamayı Başlat. Visual Studio'nun deneysel örneği görüntülenir.  
  
6.  Üzerinde **Araçları** menü adlı bir komut görmelisiniz **çağırma ChangeMenuText**.  
  
7.  Komutuna tıklayın. İleti kutusu Duyurusu MenuItemCallback çağrıldı görmeniz gerekir. İleti kutusu yok sayın, Araçlar menüsünden komutun adını artık olduğunu görmeniz gerekir **yeni metin**.
