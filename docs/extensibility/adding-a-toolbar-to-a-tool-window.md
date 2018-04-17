---
title: Araç çubuğu araç penceresi için ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- tool windows, adding toolbars
- toolbars [Visual Studio], adding to tool windows
ms.assetid: 172f64b3-87f8-4292-9c1c-65bffa2b0970
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 47ff5f69ff559ea1c08d0ae9bdd7192a257c844e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="adding-a-toolbar-to-a-tool-window"></a>Araç çubuğu araç penceresine ekleme
Bu kılavuz, bir araç için bir araç penceresi eklemek gösterilmiştir.  
  
 Bir araç çubuğu düğmeleri komutları bağlı içeren yatay veya dikey bir Şerit bulunur. Bir araç çubuğu araç penceresinde uzunluğu her zaman genişliği veya yüksekliği araç nereye yerleştirilir bağlı olarak araç penceresinin aynıdır.  
  
 IDE içinde araç çubukları, bir araç çubuğu araç penceresinde gerekir yerleşik ve taşınamaz veya özelleştirilmiş. VSPackage umanaged kodda yazılmışsa, araç çubuğunun herhangi bir kenarın sabit.  
  
 Araç çubuğu ekleme hakkında daha fazla bilgi için bkz: [araç çubuğu ekleme](../extensibility/adding-a-toolbar.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-toolbar-for-a-tool-window"></a>Araç çubuğu için araç penceresi oluşturma  
  
1.  Adlı VSIX proje oluşturma `TWToolbar` adlı iki menü komutu olan **TWTestCommand** ve adlı bir araç penceresi **TestToolWindow**. Daha fazla bilgi için bkz: [uzantı menü komutu ile oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md) ve [bir uzantısı bir araç penceresi oluşturma](../extensibility/creating-an-extension-with-a-tool-window.md). Araç penceresi şablonu eklemeden önce komut öğe şablonu eklemeniz gerekir.  
  
2.  TWTestCommandPackage.vsct içinde için simgeler bölümüne bakın. GuidTWTestCommandPackageCmdSet adlı GuidSymbol düğümünde gibi bir araç ve bir araç grubu bildirin.  
  
    ```xml  
    <IDSymbol name="TWToolbar" value="0x1000" />  
    <IDSymbol name="TWToolbarGroup" value="0x1050" />  
    ```  
  
3.  Üstündeki `Commands` bölümünde, oluşturmak bir `Menus` bölümü. Ekleme bir `Menu` araç tanımlamak için öğesi.  
  
    ```xml  
    <Menus>  
        <Menu guid="guidTWTestCommandPackageCmdSet" id="TWToolbar" type="ToolWindowToolbar">  
            <CommandFlag>DefaultDocked</CommandFlag>  
            <Strings>  
                <ButtonText>Test Toolbar</ButtonText>  
                <CommandName>Test Toolbar</CommandName>  
            </Strings>  
        </Menu>  
    </Menus>  
    ```  
  
     Araç çubukları gibi alt menüler iç içe olamaz. Bu nedenle, bir üst atamak gerekmez. Ayrıca, kullanıcı araç çubukları taşıyabilirsiniz çünkü bir öncelikler gerekmez. Genellikle, ilk bir araç çubuğu yerleşimini programlı olarak tanımlanır, ancak kullanıcı tarafından sonraki değişiklikler kalıcı.  
  
4.  Grupları bölümünde araç komutları içerecek şekilde grubu tanımlayın.  
  
    ```xml  
  
    <Group guid="guidTWTestCommandPackageCmdSet" id="TWToolbarGroup" priority="0x0000">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TWToolbar" />  
    </Group>  
    ```  
  
5.  Düğmeleri bölümünde, varolan Button öğesi üst araç grubuna değiştirin araç çubuğu görüntülenir.  
  
    ```xml  
    <Button guid="guidTWTestCommandPackageCmdSet" id="TWTestCommandId" priority="0x0100" type="Button">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TWToolbarGroup" />  
        <Icon guid="guidImages" id="bmpPic1" />  
        <Strings>  
            <ButtonText>Invoke TWTestCommand</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
     Araç çubuğu hiçbir komut varsa, varsayılan olarak, bu görünmez.  
  
     Yeni araç çubuğu araç penceresi otomatik olarak eklenmez çünkü araç açıkça eklenmesi gerekir. Bu konu, sonraki bölümde açıklanmaktadır.  
  
## <a name="adding-the-toolbar-to-the-tool-window"></a>Araç çubuğu araç penceresi ekleme  
  
1.  İçinde TWTestCommandPackageGuids.cs aşağıdaki satırları ekleyin.  
  
    ```csharp  
    public const string guidTWTestCommandPackageCmdSet = "00000000-0000-0000-0000-0000";  // get the GUID from the .vsct file  
    public const int TWToolbar = 0x1000;  
    ```  
  
2.  TestToolWindow.cs içinde aşağıdaki ekleme deyimini kullanarak.  
  
    ```csharp  
    using System.ComponentModel.Design;  
    ```  
  
3.  TestToolWindow oluşturucuda aşağıdaki satırı ekleyin.  
  
    ```csharp  
    this.ToolBar = new CommandID(new Guid(TWTestCommandPackageGuids.guidTWTestCommandPackageCmdSet), TWTestCommandPackageGuids.TWToolbar);  
    ```  
  
## <a name="testing-the-toolbar-in-the-tool-window"></a>Araç çubuğu araç penceresinde test etme  
  
1.  Projeyi derleyin ve hata ayıklamayı Başlat. Visual Studio deneysel örneği görüntülenmesi gerekir.  
  
2.  Üzerinde **görünüm / diğer pencereler** menüsünde tıklatın **Test araç penceresi** aracı penceresini görüntülemek için.  
  
     (Varsayılan simge gibi görünüyor) bir üst araç çubuğu araç penceresi başlığı altındaki sol görmeniz gerekir.  
  
3.  Araç çubuğunda iletiyi görüntülemek için bu simgeyi tıklatın **TWTestCommandPackage içinde TWToolbar.TWTestCommand.MenuItemCallback()**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Araç Çubuğu Ekleme](../extensibility/adding-a-toolbar.md)