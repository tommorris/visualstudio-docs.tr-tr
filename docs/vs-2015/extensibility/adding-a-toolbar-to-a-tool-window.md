---
title: Araç penceresine araç çubuğu ekleme | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tool windows, adding toolbars
- toolbars [Visual Studio], adding to tool windows
ms.assetid: 172f64b3-87f8-4292-9c1c-65bffa2b0970
caps.latest.revision: 49
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2f35ed0f74f8d3fad711f7c1dd4158072b786eb7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688311"
---
# <a name="adding-a-toolbar-to-a-tool-window"></a>Araç Penceresine Araç Çubuğu Ekleme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [araç penceresine araç çubuğu ekleme](https://docs.microsoft.com/visualstudio/extensibility/adding-a-toolbar-to-a-tool-window).  
  
Bu izlenecek yol, araç penceresine araç ekleme işlemi gösterilmektedir.  
  
 Bir araç çubuğu düğmeleri bağlı komutları içeren bir yatay veya Dikey Şerit bulunur. Araç penceresi araç çubuğu uzunluğunu her zaman araç nereye yerleştirildiğini bağlı olarak araç penceresinin, yükseklik ve genişlik aynıdır.  
  
 IDE'de araç çubukları, bir araç penceresi araç çubuğu gerekir sabitlenebilir ve taşınamaz veya özelleştirilmiş. VSPackage'ı umanaged kodda yazıldığı, araç tüm edge üzerinde yerleştirilmiş olabilir.  
  
 Araç çubuğu ekleme hakkında daha fazla bilgi için bkz. [araç çubuğu ekleme](../extensibility/adding-a-toolbar.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, size Visual Studio SDK İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yi daha sonra yükleyebilirsiniz. Daha fazla bilgi için [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-toolbar-for-a-tool-window"></a>Araç çubuğu için araç penceresi oluşturma  
  
1.  Adlı bir VSIX projesi oluşturun `TWToolbar` adlı iki menü komutu olan **TWTestCommand** ve adlı bir araç penceresi **TestToolWindow**. Daha fazla bilgi için [bir menü komutuyla uzantı oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md) ve [araç penceresi içeren bir uzantı oluşturma](../extensibility/creating-an-extension-with-a-tool-window.md). Araç penceresi şablonu eklemeden önce komut öğe şablonu eklemek gerekir.  
  
2.  TWTestCommandPackage.vsct semboller bölümüne bakın. GuidSymbol düğümünde guidTWTestCommandPackageCmdSet adlı bir araç çubuğu ve araç çubuğu grubu, şu şekilde bildirin.  
  
    ```xml  
    <IDSymbol name="TWToolbar" value="0x1000" />  
    <IDSymbol name="TWToolbarGroup" value="0x1050" />  
    ```  
  
3.  Üst kısmındaki `Commands` bölümünde, oluşturun bir `Menus` bölümü. Ekleme bir `Menu` araç tanımlamak için.  
  
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
  
     Araç Çubukları alt menüler gibi iç içe olamaz. Bu nedenle, bir üst atama gerekmez. Ayrıca, kullanıcı araç çubukları taşıyabilirsiniz çünkü bir öncelikler gerekmez. Genellikle, ilk araç çubuğu yerleşimini programlı olarak tanımlanır, ancak kullanıcı tarafından sonraki değişiklikleri kalıcı.  
  
4.  Grupları bölümünde araç için komutları içeren bir grup tanımlayın.  
  
    ```xml  
  
    <Group guid="guidTWTestCommandPackageCmdSet" id="TWToolbarGroup" priority="0x0000">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TWToolbar" />  
    </Group>  
    ```  
  
5.  Düğmeler bölümünde, mevcut düğmesi öğenin üst araç gruba değiştirin araç çubuğu görüntülenir.  
  
    ```xml  
    <Button guid="guidTWTestCommandPackageCmdSet" id="TWTestCommandId" priority="0x0100" type="Button">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TWToolbarGroup" />  
        <Icon guid="guidImages" id="bmpPic1" />  
        <Strings>  
            <ButtonText>Invoke TWTestCommand</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
     Araç çubuğu hiçbir komut varsa, varsayılan olarak, bu görünmüyor.  
  
     Yeni araç çubuğu için araç penceresi otomatik olarak eklenmez çünkü araç açıkça eklenmelidir. Bu konu, sonraki bölümde açıklanmaktadır.  
  
## <a name="adding-the-toolbar-to-the-tool-window"></a>Araç penceresine araç çubuğu ekleme  
  
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
  
1.  Projeyi oluşturmak ve hata ayıklamaya başlayın. Visual Studio deneysel örneği görüntülenmesi gerekir.  
  
2.  Üzerinde **görünüm / diğer Windows** menüsünde tıklatın **Test ToolWindow** araç penceresini görüntülemek için.  
  
     Hemen altındaki başlığı araç penceresi araç çubuğu (varsayılan simgesi gibi görünür) üst sol görmeniz gerekir.  
  
3.  Araç çubuğunda iletiyi görüntülemek için simgeye tıklayın **TWTestCommandPackage içinde TWToolbar.TWTestCommand.MenuItemCallback()**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Araç Çubuğu Ekleme](../extensibility/adding-a-toolbar.md)

