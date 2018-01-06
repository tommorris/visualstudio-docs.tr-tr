---
title: "Visual Studio menü çubuğunda bir menü ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- menus, creating top level
- top-level menus
ms.assetid: 58fc1a31-2aeb-441c-8e48-c7d5cbcfe501
caps.latest.revision: "51"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 7e334a148a205338a872e9581bce1c3c1a70b7df
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="adding-a-menu-to-the-visual-studio-menu-bar"></a>Visual Studio menü çubuğunda bir menü ekleme
Bu kılavuz, Visual Studio tümleşik geliştirme ortamı (IDE) menü çubuğunda bir menü eklemek gösterilmiştir. IDE menü çubuğu menü kategorileri gibi içeren **dosya**, **Düzenle**, **Görünüm**, **penceresi**, ve **yardımcı** .  
  
 Visual Studio menü çubuğunda yeni menü eklemeden önce komutlarınızı içinde varolan bir menü yerleştirilmiş olup olmadığını göz önünde bulundurun. Komut yerleşimi hakkında daha fazla bilgi için bkz: [menüleri ve Visual Studio için komutları](../extensibility/ux-guidelines/menus-and-commands-for-visual-studio.md).  
  
 Menüleri projenin .vsct dosyasında bildirilir. Menüler ve .vsct dosyaları hakkında daha fazla bilgi için bkz: [komutları, menüleri ve araç çubuklarını](../extensibility/internals/commands-menus-and-toolbars.md).  
  
 Bu kılavuzu izleyerek adlı bir menü oluşturabilirsiniz **TestMenu** bir komut içerir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-vsix-project-that-has-a-custom-command-item-template"></a>Bir özel komut öğesi şablonda VSIX proje oluşturma  
  
1.  Adlı VSIX proje oluşturma `TopLevelMenu`. VSIX proje şablonu bulabilirsiniz **yeni proje** altında iletişim **Visual C#** / **genişletilebilirlik**.  Daha fazla bilgi için bkz: [uzantı menü komutu ile oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2.  Proje açıldığında adlı bir özel komut öğesi şablonu Ekle **TestCommand**. İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **Ekle / yeni öğe**. İçinde **Yeni Öğe Ekle** iletişim kutusunda, Git **Visual C# / genişletilebilirlik** seçip **özel komut**. İçinde **adı** alan penceresinin alt kısmında, komut dosyası adı Değiştir **TestCommand.cs**.  
  
## <a name="creating-a-menu-on-the-ide-menu-bar"></a>IDE menü çubuğunda menü oluşturma  
  
#### <a name="to-create-a-menu"></a>Menü oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, TestCommandPackage.vsct açın.  
  
     Dosyanın sonunda, var olan bir \<simgeleri > birkaç içeren düğümü \<GuidSymbol > düğümleri. GuidTestCommandPackageCmdSet adlı düğümünde yeni bir sembol aşağıdaki şekilde ekleyin:  
  
    ```xml  
    <IDSymbol name="TopLevelMenu" value="0x1021"/>  
    ```  
  
2.  Boş bir oluşturma \<menüleri > düğümünde \<komutları > düğümü, hemen önce \<grupları >. İçinde \<menüleri > düğümü Ekle bir \<menü > şekilde düğümü:  
  
    ```xml  
    <Menus>  
          <Menu guid="guidTestCommandPackageCmdSet" id="TopLevelMenu" priority="0x700" type="Menu">  
            <Parent guid="guidSHLMainMenu"  
                    id="IDG_VS_MM_TOOLSADDINS" />  
            <Strings>  
              <ButtonText>TestMenu</ButtonText>  
              <CommandName>TestMenu</CommandName>  
            </Strings>  
        </Menu>  
    </Menus>  
    ```  
  
     `guid` Ve `id` değerleri menüsünün komut kümesini ve belirli menü komutu kümesinde belirtin.  
  
     `guid` Ve `id` üst değerleri, Araçlar ve eklentiler menüleri içeren Visual Studio menü çubuğu bölümünü menü konum.  
  
     Değeri `CommandName` dizesini belirtir menü öğesi metni görünmelidir.  
  
3.  İçinde \<grupları > bölümünde, Bul \<grup > değiştirip \<üst > yalnızca eklediğimiz menüsünde öğe:  
  
    ```csharp  
    <Groups>  
          <Group guid="guidTestCommandPackageCmdSet" id="MyMenuGroup" priority="0x0600">  
            <Parent guid="guidTestCommandPackageCmdSet" id="TopLevelMenu"/>  
          </Group>  
        </Groups>  
    ```  
  
     Bu yeni menü grubunun parçası yapar.  
  
4.  Bul `Buttons` bölümü. Dikkat [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] paketi şablonu oluşturursa bir `Button` üst kümesine sahip olan öğe `MyMenuGroup`. Sonuç olarak, bu komut, menüsünde görüntülenir.  
  
## <a name="building-and-testing-the-extension"></a>Derleme ve testi uzantısı  
  
1.  Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği örneği görüntülenmesi gerekir.  
  
2.  Deneysel örneği menü çubuğundaki içermesi gereken bir **TestMenu** menüsü.  
  
3.  Üzerinde **TestMenu** menüsünde tıklatın **çağırma Test komutu**.  
  
     Bir ileti kutusu görünür ve "TopLevelMenu.TestCommand.MenuItemCallback() içinde TestCommand paket" iletisini görüntüler. Bu, yeni bir komut çalıştığını gösterir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komutlar, Menüler ve Araç Çubukları](../extensibility/internals/commands-menus-and-toolbars.md)