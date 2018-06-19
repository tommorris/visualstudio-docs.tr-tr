---
title: Çözüm Gezgini araç için bir komut ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- toolbars [Visual Studio], adding buttons
- buttons [Visual Studio], adding to Solution Explorer
- Solution Explorer, adding buttons
ms.assetid: f6411557-2f4b-4e9f-b02e-fce12a6ac7e9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f6f732900ff3e73decb1dc01d5c131e26ba50669
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31107393"
---
# <a name="adding-a-command-to-the-solution-explorer-toolbar"></a>Çözüm Gezgini araç için bir komut ekleme
Bu kılavuz bir düğmeye eklemeyi gösterir **Çözüm Gezgini** araç.  
  
 Herhangi bir araç veya menü komutu Visual Studio'da bir düğmeye denir. Düğme tıklatıldığında komut işleyici kodu yürütülür. Genellikle, ilgili komutları bir grup oluşturmak için birlikte gruplandırılır. Menüleri ve araç çubuklarını grupları için kapsayıcı görevi görür. Öncelik tek tek bir grup komutlarda menüsünden veya araç çubuğunda görünme sırasını belirler. Bir düğme araç veya menüsünde görünürlüğü denetleyerek görüntülenmesini engelleyebilirsiniz. Listede bir komut bir `<VisibilityConstraints>` .vsct dosyasının yalnızca ilişkili bağlamında görüntülenir. Gruplara görünürlük uygulanamaz.  
  
 .Vsct dosyaları menüleri ve araç komutları hakkında daha fazla bilgi için bkz: [komutları, menüleri ve araç çubuklarını](../extensibility/internals/commands-menus-and-toolbars.md).  
  
> [!NOTE]
>  XML komutu tablosu (.vsct) dosyaları yerine komutu tablo yapılandırma (.ctc) dosyaları, VSPackages menüleri ve komutları nasıl göründüğünü tanımlamak için kullanın. Daha fazla bilgi için bkz: [Visual Studio komut tablosu (. Vsct) dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-an-extension-with-a-menu-command"></a>Menü komutu ile bir uzantısı oluşturma  
 Adlı VSIX proje oluşturma `SolutionToolbar`. Adlı bir menü komutu öğesi şablonu Ekle **ToolbarButton**. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz: [uzantı menü komutu ile oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
## <a name="adding-a-button-to-the-solution-explorer-toolbar"></a>Çözüm Gezgini araç çubuğuna düğme ekleme  
 Kılavuzu'nun bu bölümünde bir düğmeye eklemeyi gösterir **Çözüm Gezgini** araç. Düğmesine tıklandığında, geri çağırma yöntemi kodda çalıştırılır.  
  
1.  ToolbarButtonPackage.vsct dosyasında Git `<Symbols>` bölümü. `<GuidSymbol>` Düğüm menü grubunu ve paketi şablonu tarafından oluşturulan komutu içerir. Ekleme bir `<IDSymbol>` komutunuzu tutacak Grup bildirmek için bu düğümü öğesi.  
  
    ```xml  
    <IDSymbol name="SolutionToolbarGroup" value="0x0190"/>  
    ```  
  
2.  İçinde `<Groups>` bölümüne, var olan Grup girişten sonra tanımlamak, bildirilen yeni Grup önceki adımda.  
  
    ```xml  
    <Group guid="guidToolbarButtonPackageCmdSet"  
           id="SolutionToolbarGroup" priority="0xF000">  
            <Parent guid="guidSHLMainMenu" id="IDM_VS_TOOL_PROJWIN"/>  
          </Group>  
    ```  
  
     Üst GUID:ID çifti ayarını `guidSHLMainMenu` ve `IDM_VS_TOOL_PROJWIN` bu grubun koyar **Çözüm Gezgini** araç ve yüksek öncelikli değerini ayarlar koyar, sonra diğer komut grupları.  
  
3.  İçinde `<Buttons>` bölümünde, oluşturulan üst Kimliğini değiştirmek `<Button>` önceki adımda tanımlanan grubunu yansıtacak şekilde girişi. Değiştirilen `<Button>` öğesi aşağıdaki gibi görünmelidir:  
  
    ```xml  
    <Button guid="guidToolbarButtonPackageCmdSet" id="ToolbarButtonId" priority="0x0100" type="Button">  
        <Parent guid="guidToolbarButtonPackageCmdSet" id="SolutionToolbarGroup" />  
        <Icon guid="guidImages" id="bmpPicStrikethrough" />  
        <Strings>  
            <ButtonText>Invoke ToolbarButton</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
4.  Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görüntülenir.  
  
     **Çözüm Gezgini** araç varolan düğmeleri sağındaki yeni bir komut düğmesi görüntülemelidir. Üstü çizili düğmesini simgedir.  
  
5.  Yeni düğmesini tıklatın.  
  
     İleti bir iletişim kutusu **ToolbarButtonPackage içinde SolutionToolbar.ToolbarButton.MenuItemCallback()** görüntülenmesi gerekir.  
  
## <a name="controlling-the-visibility-of-a-button"></a>Bir düğmesinin görünürlüğünü denetleme  
 Kılavuzu'nun bu bölümünde bir araç çubuğunda görünürlüğünü denetleme gösterir. Bir veya birden çok proje için bir bağlam ayarlayarak `<VisibilityConstraints>` bölüm SolutionToolbar.vsct dosyası, yalnızca bir proje veya projeleri açık olduğunda görünmesi bir düğme kısıtlayın.  
  
#### <a name="to-display-a-button-when-one-or-more-projects-are-open"></a>Bir veya daha fazla proje açık olduğunda bir düğme görüntülemek için  
  
1.  İçinde `<Buttons>` bölüm mevcut ToolbarButtonPackage.vsct iki komut bayrak eklemek `<Button>` öğesi, arasında `<Strings>` ve `<Icons>` etiketler.  
  
    ```xml  
    <CommandFlag>DefaultInvisible</CommandFlag>  
    <CommandFlag>DynamicVisibility</CommandFlag>  
    ```  
  
     `DefaultInvisible` Ve `DynamicVisibility` bayrakları bunu ayarlanmalıdır Bu girdiler `<VisibilityConstraints>` bölüm etkisi alabilir.  
  
2.  Oluşturma bir `<VisibilityConstraints>` iki sahip bölüm `<VisibilityItem>` girişleri. Yalnızca kapattıktan sonra yeni bir bölüm put `</Commands>` etiketi.  
  
    ```xml  
    <VisibilityConstraints>  
        <VisibilityItem guid="guidToolbarButtonPackageCmdSet"  
              id="ToolbarButtonId"  
              context="UICONTEXT_SolutionHasSingleProject" />  
        <VisibilityItem guid="guidToolbarButtonPackageCmdSet"  
              id="ToolbarButtonId"  
              context="UICONTEXT_SolutionHasMultipleProjects" />  
    </VisibilityConstraints>  
    ```  
  
     Her görünürlük öğeyi temsil eden bir koşul altında belirtilen düğmesi görüntülenir. Birden çok koşul uygulamak için aynı düğme için birden çok girdi oluşturmanız gerekir.  
  
3.  Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görüntülenir.  
  
     **Çözüm Gezgini** araç üstü çizili düğmesini içermiyor.  
  
4.  Bir proje içeren herhangi bir çözümü açın.  
  
     Üstü çizili düğmesi, varolan düğmeleri sağındaki araç çubuğunda görünür.  
  
5.  Üzerinde **dosya** menüsünde tıklatın **Kapat çözüm**. Araç çubuğundan düğme kaybolur.  
  
 Düğmesinin görünürlüğünü tarafından denetlenen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSPackage yüklenene kadar. VSPackage yüklendikten sonra düğmesinin görünürlüğünü VSPackage tarafından denetlenir.  Daha fazla bilgi için bkz: [MenuCommands Vs. OleMenuCommands](../extensibility/menucommands-vs-olemenucommands.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komutlar, Menüler ve Araç Çubukları](../extensibility/internals/commands-menus-and-toolbars.md)