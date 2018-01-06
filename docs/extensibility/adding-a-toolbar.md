---
title: "Araç çubuğu ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Visual Studio], adding to IDE
- IDE, adding toolbars
ms.assetid: 17302c25-6f59-4e97-8c85-54f95336a07f
caps.latest.revision: "38"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f7b837a620a1e116b9bb8a11ff8a4edab7bfabfb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="adding-a-toolbar"></a>Araç çubuğu ekleme
Bu kılavuz Visual Studio IDE araç ekleme gösterilmektedir.  
  
 Bir araç çubuğu komutlarını bağlı düğmeleri içeren yatay veya dikey bir Şerit bulunur. Kendi uygulama bağlı olarak bir araç çubuğu IDE yeniden konumlandırılır, ana IDE penceresinin herhangi bir tarafında yerleştirilebilir ya da diğer windows önünde kalmak için yapılan.  
  
 Ayrıca, kullanıcıların komutları bir araç çubuğuna ekleyin veya onları ondan kullanarak kaldırın **Özelleştir** iletişim kutusu. Genellikle, VSPackages araç çubuklarında kullanıcı özelleştirilebilir. Tüm özelleştirme IDE işler ve VSPackage komutlarına yanıt verir. Bir komut fiziksel olarak bulunduğu bilmeniz VSPackage yok.  
  
 Menüleri hakkında daha fazla bilgi için bkz: [komutları, menüleri ve araç çubuklarını](../extensibility/internals/commands-menus-and-toolbars.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-an-extension-with-a-toolbar"></a>Bir uzantısı bir araç çubuğu oluşturma  
 Adlı VSIX proje oluşturma `IDEToolbar`. Adlı bir menü komutu öğesi şablonu Ekle **ToolbarTestCommand**. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz: [uzantı menü komutu ile oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
## <a name="creating-a-toolbar-for-the-ide"></a>IDE için bir araç çubuğu oluşturma  
  
1.  ToolbarTestCommandPackage.vsct içinde için simgeler bölümüne bakın. GuidToolbarTestCommandPackageCmdSet GuidSymbol öğesinde, bir araç ve bir araç grubu için bildirimler aşağıdaki şekilde ekleyin.  
  
    ```xml  
    <IDSymbol name="Toolbar" value="0x1000" />  
    <IDSymbol name="ToolbarGroup" value="0x1050" />  
  
    ```  
  
2.  Komutları bölümün başında menüleri bir bölüm oluşturun. Menü öğesi araç tanımlamak için menüleri bölümüne ekleyin.  
  
    ```xml  
    <Menus>  
        <Menu guid="guidToolbarTestCommandPackageCmdSet" id="Toolbar"  
            type="Toolbar" >  
            <CommandFlag>DefaultDocked</CommandFlag>  
            <Strings>  
                <ButtonText>Test Toolbar</ButtonText>  
                <CommandName>Test Toolbar</CommandName>  
            </Strings>  
          </Menu>  
    </Menus>  
    ```  
  
     Araç çubukları gibi alt menüler iç içe olamaz. Bu nedenle, bir üst gruba atamak gerekmez. Ayrıca, kullanıcı araç çubukları taşıyabilirsiniz çünkü bir öncelikler gerekmez. Genellikle, ilk bir araç çubuğu yerleşimini programlı olarak tanımlanır, ancak kullanıcı tarafından sonraki değişiklikler kalıcı.  
  
3.  İçinde [grupları](../extensibility/groups-element.md) bölümünde, var olan Grup girişten sonra tanımlayan bir [grup](../extensibility/group-element.md) araç komutları içerecek şekilde öğesi.  
  
    ```xml  
    <Group guid="guidToolbarTestCommandPackageCmdSet" id="ToolbarGroup"  
          priority="0x0000">  
      <Parent guid="guidToolbarTestCommandPackageCmdSet" id="Toolbar"/>  
    </Group>  
    ```  
  
4.  Araç çubuğunda görünen düğmesi olun. Düğmeleri bölümünde araç çubuğu düğme üst bloğunda değiştirin. Sonuçta elde edilen düğmesi blok aşağıdaki gibi görünmelidir:  
  
    ```xml  
    <Button guid="guidToolbarTestCommandPackageCmdSet" id="ToolbarTestCommandId" priority="0x0100" type="Button">  
        <Parent guid= "guidToolbarTestCommandPackageCmdSet" id="ToolbarGroup" />  
                <Icon guid="guidImages" id="bmpPic1" />  
        <Strings>  
            <ButtonText>Invoke ToolbarTestCommand</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
     Araç çubuğu hiçbir komut varsa, varsayılan olarak, bu görünmez.  
  
5.  Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görüntülenmesi gerekir.  
  
6.  Araç çubukları listesini almak için Visual Studio menü çubuğunu sağ tıklatın. Seçin **Test araç**.  
  
7.  Şimdi, simge dosyaları simgesi Bul sağındaki olarak araç görmeniz gerekir. Simgeyi tıklattığında bildiren bir ileti kutusu görmeniz gerekir **ToolbarTestCommandPackage. IDEToolbar.ToolbarTestCommand.MenuItemCallback() içinde**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komutlar, Menüler ve Araç Çubukları](../extensibility/internals/commands-menus-and-toolbars.md)