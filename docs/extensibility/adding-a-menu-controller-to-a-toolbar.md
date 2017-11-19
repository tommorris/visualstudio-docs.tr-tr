---
title: "Bir araç çubuğuna menü denetleyicisi ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Visual Studio], adding menu controllers
- menus, adding menu controllers to toolbars
- menu controllers, adding to toolbars
ms.assetid: 6af9b0b4-037f-404c-bb40-aaa1970768ea
caps.latest.revision: "38"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 786d7c8841f680d5af5c539e30723289df4db0f5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="adding-a-menu-controller-to-a-toolbar"></a>Menü denetleyicisi araç çubuğuna ekleme
Bu kılavuzda derlemeler [araç çubuğu araç penceresi için ekleme](../extensibility/adding-a-toolbar-to-a-tool-window.md) gözden geçirme ve araç penceresi araç için bir menü denetleyicisi eklemeyi gösterir. Burada gösterilen adımları da oluşturulan araç uygulanabilir [araç çubuğu ekleme](../extensibility/adding-a-toolbar.md) gözden geçirme.  
  
 Bölme denetim menü denetleyicisidir. Son kullanılan komut menü denetleyicisi sol tarafında gösterir ve tıklayarak çalıştırılabilir. Menü denetleyicisi sağ tarafındaki bir ok olan, tıklatıldığında, ek komutların listesini açar. Ne zaman komutu çalıştırır listedeki bir komutuna tıklayın ve menü denetleyicisi sol tarafındaki komutu değiştirir. Bu şekilde, menü denetleyicisi her zaman listesinden son kullanılan komutunu gösteren komut düğmesi gibi çalışır.  
  
 Menü denetleyicileri menülerde görünebilir, ancak çoğunlukla çubuklarında kullanılan.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-menu-controller"></a>Menü denetleyicisi oluşturma  
  
#### <a name="to-create-a-menu-controller"></a>Menü denetleyicisi oluşturmak için  
  
1.  Açıklanan yordamları izleyin [araç çubuğu araç penceresi için ekleme](../extensibility/adding-a-toolbar-to-a-tool-window.md) bir araç olan bir araç penceresi oluşturulamadı.  
  
2.  TWTestCommandPackage.vsct içinde sembolleri bölümüne gidin. Adlı GuidSymbol öğesindeki **guidTWTestCommandPackageCmdSet**, menü denetleyicinizi, menü denetleyicisi grubunu ve üç menü öğeleri bildirin.  
  
    ```xml  
    <IDSymbol name="TestMenuController" value="0x1300" /><IDSymbol name="TestMenuControllerGroup" value="0x1060" /><IDSymbol name="cmdidMCItem1" value="0x0130" /><IDSymbol name="cmdidMCItem2" value="0x0131" /><IDSymbol name="cmdidMCItem3" value="0x0132" />  
    ```  
  
3.  Menüleri bölümünde son menü girişten sonra menü denetleyicisi menü olarak tanımlayın.  
  
    ```xml  
    <Menu guid="guidTWTestCommandPackageCmdSet" id="TestMenuController" priority="0x0100" type="MenuController">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TWToolbarGroup" />  
        <CommandFlag>IconAndText</CommandFlag>  
        <CommandFlag>TextChanges</CommandFlag>  
        <CommandFlag>TextIsAnchorCommand</CommandFlag>  
        <Strings>  
            <ButtonText>Test Menu Controller</ButtonText>  
            <CommandName>Test Menu Controller</CommandName>  
        </Strings>  
    </Menu>  
    ```  
  
     `TextChanges` Ve `TextIsAnchorCommand` bayrakları son seçilen komutu yansıtacak şekilde menü denetleyicisi etkinleştirmek için dahil olmalıdır.  
  
4.  Gruplara son grup girişten sonra bölümünde menü denetleyicisi grubunu ekleyin.  
  
    ```xml  
    <Group guid="guidTWTestCommandPackageCmdSet" id="TestMenuControllerGroup" priority="0x000">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TestMenuController" />  
    </Group>  
    ```  
  
     Menü denetleyicisi üst öğe olarak ayarlayarak, bu grupta herhangi bir komut menüsü denetleyicide görünür. `priority` Özniteliği belirtilmemişse, 0, varsayılan değerini ayarlar yalnızca grup menü denetleyicisinde olacağından.  
  
5.  Düğmeleri bölümünde son düğmesine girişten sonra bir düğme öğesi her menü öğeleri için ekleyin.  
  
    ```xml  
    <Button guid="guidTWTestCommandPackageCmdSet" id="cmdidMCItem1" priority="0x0000" type="Button">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TestMenuControllerGroup" />  
        <Icon guid="guidImages" id="bmpPic1" />  
        <CommandFlag>IconAndText</CommandFlag>  
        <Strings>  
            <ButtonText>MC Item 1</ButtonText>  
            <CommandName>MC Item 1</CommandName>  
        </Strings>  
    </Button>  
    <Button guid="guidTWTestCommandPackageCmdSet" id="cmdidMCItem2" priority="0x0100" type="Button">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TestMenuControllerGroup" />  
        <Icon guid="guidImages" id="bmpPic2" />  
        <CommandFlag>IconAndText</CommandFlag>  
        <Strings>  
            <ButtonText>MC Item 2</ButtonText>  
            <CommandName>MC Item 2</CommandName>  
        </Strings>  
    </Button>  
    <Button guid="guidTWTestCommandPackageCmdSet" id="cmdidMCItem3" priority="0x0200" type="Button">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TestMenuControllerGroup" />  
        <Icon guid="guidImages" id="bmpPicSearch" />  
        <CommandFlag>IconAndText</CommandFlag>  
        <Strings>  
            <ButtonText>MC Item 3</ButtonText>  
            <CommandName>MC Item 3</CommandName>  
        </Strings>  
    </Button>  
    ```  
  
6.  Bu noktada, menü denetleyicisinde bakabilirsiniz. Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görmeniz gerekir.  
  
    1.  Üzerinde **görünüm / diğer pencereler** menüsünde, açık **Test araç penceresi**.  
  
    2.  Araç penceresi araç çubuğunda menü denetleyicisi görüntülenir.  
  
    3.  Üç olası komutlarını görmek için menü denetçisinin sağ taraftaki oka tıklayın.  
  
     Bir komutu tıklattığınızda menü denetleyicisi başlığı komut görüntülenecek değiştiğine dikkat edin. Sonraki bölümde, bu komutları etkinleştirmek için kodu ekleyeceğiz.  
  
## <a name="implementing-the-menu-controller-commands"></a>Menü denetleyicisi komutları uygulama  
  
1.  TWTestCommandPackageGuids.cs içinde komut kimlikleri, üç menü öğeleri için var olan komut kimlikleri sonra ekleyin.  
  
    ```csharp  
    public const int cmdidMCItem1 = 0x130;  
    public const int cmdidMCItem2 = 0x131;  
    public const int cmdidMCItem3 = 0x132;  
    ```  
  
2.  TWTestCommand.cs içinde TWTestCommand sınıfı üstünde aşağıdaki kodu ekleyin.  
  
    ```csharp  
    private int currentMCCommand; // The currently selected menu controller command  
    ```  
  
3.  TWTestCommand oluşturucuda son çağrısından sonra `AddCommand` yöntemi, her komutu aracılığıyla aynı işleyicileri için olayları yönlendirmek için kodu ekleyin.  
  
    ```csharp  
    for (int i = TWTestCommandPackageGuids.cmdidMCItem1; i <=  
        TWTestCommandPackageGuids.cmdidMCItem3; i++)  
    {  
        CommandID cmdID = new  
        CommandID(new Guid(TWTestCommandPackageGuids.guidTWTestCommandPackageCmdSet), i);  
        OleMenuCommand mc = new OleMenuCommand(new  
          EventHandler(OnMCItemClicked), cmdID);  
        mc.BeforeQueryStatus += new EventHandler(OnMCItemQueryStatus);  
        commandService.AddCommand(mc);  
        // The first item is, by default, checked.   
        if (TWTestCommandPackageGuids.cmdidMCItem1 == i)  
        {  
            mc.Checked = true;  
            this.currentMCCommand = i;  
        }  
    }  
    ```  
  
4.  Olay işleyici seçili komut işaretli olarak işaretlemek için TWTestCommand sınıfına ekleyin.  
  
    ```csharp  
    private void OnMCItemQueryStatus(object sender, EventArgs e)  
    {  
        OleMenuCommand mc = sender as OleMenuCommand;  
        if (null != mc)  
        {  
            mc.Checked = (mc.CommandID.ID == this.currentMCCommand);  
        }  
    }  
    ```  
  
5.  Kullanıcı komut menü denetleyicisinde seçtiğinde MessageBox görüntüleyen bir olay işleyicisi ekleyin:  
  
    ```csharp  
    private void OnMCItemClicked(object sender, EventArgs e)  
    {  
        OleMenuCommand mc = sender as OleMenuCommand;  
        if (null != mc)  
        {  
            string selection;  
            switch (mc.CommandID.ID)  
            {  
                case c.cmdidMCItem1:  
                    selection = "Menu controller Item 1";  
                    break;  
  
                case TWTestCommandPackageGuids.cmdidMCItem2:  
                    selection = "Menu controller Item 2";  
                    break;  
  
                case TWTestCommandPackageGuids.cmdidMCItem3:  
                    selection = "Menu controller Item 3";  
                    break;  
  
                default:  
                    selection = "Unknown command";  
                    break;  
            }  
            this.currentMCCommand = mc.CommandID.ID;  
  
            IVsUIShell uiShell =  
              (IVsUIShell) ServiceProvider.GetService(typeof(SVsUIShell));  
            Guid clsid = Guid.Empty;  
            int result;  
            uiShell.ShowMessageBox(  
                       0,  
                       ref clsid,  
                       "Test Tool Window Toolbar Package",  
                       string.Format(CultureInfo.CurrentCulture,  
                                     "You selected {0}", selection),  
                       string.Empty,  
                       0,  
                       OLEMSGBUTTON.OLEMSGBUTTON_OK,  
                       OLEMSGDEFBUTTON.OLEMSGDEFBUTTON_FIRST,  
                       OLEMSGICON.OLEMSGICON_INFO,  
                       0,  
                       out result);  
        }  
    }  
    ```  
  
## <a name="testing-the-menu-controller"></a>Menü denetleyicisi test etme  
  
1.  Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görmeniz gerekir.  
  
2.  Açık **Test araç penceresi** üzerinde **görünüm / diğer pencereler** menüsü.  
  
     Menü denetleyicisi araç çubuğunda araç penceresi görünür ve görüntüler **MC madde 1**.  
  
3.  Sol Ok menüsü denetleyicisi düğmesini tıklatın.  
  
     İlki seçilir ve Vurgu Kutusu simgesini geçici üç öğe görmeniz gerekir. Tıklatın **MC öğesi 3**.  
  
     İletinin bir iletişim kutusu görünür **menü denetleyicisi öğesi 3 seçili**. İleti menü denetleyicisi düğmesinde metne karşılık gelen dikkat edin. Menü denetleyicisi düğmesini şimdi görüntüler **MC öğesi 3**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Araç çubuğu araç penceresine ekleme](../extensibility/adding-a-toolbar-to-a-tool-window.md)   
 [Araç çubuğu ekleme](../extensibility/adding-a-toolbar.md)