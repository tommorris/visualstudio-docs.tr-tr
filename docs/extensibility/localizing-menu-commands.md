---
title: "Menü komutları yerelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- localize
- localization
- vsct
- menu commands
- localize visual studio
- localize vsct
ms.assetid: b04ee0f6-82ea-47e6-853a-72382267d6da
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 77bd698149ca4e73b462fc3ada9256ba5911177e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="localizing-menu-commands"></a>Yerelleştirme menü komutları
Yerelleştirilmiş metin menüsüne sağlayabilir ve araç yerelleştirilmiş .vsct dosyaları oluşturarak komutları ve .resx dosyaları, VSPackage ve ardından Proje dosyalarını güncelleştirmek için değişikliklerin uygulanması yerelleştirilmiş.  
  
 Yükleme deneyimi yerelleştirme hakkında daha fazla bilgi için bkz: [yerelleştirme VSIX paket](../extensibility/localizing-vsix-packages.md).  
  
## <a name="localizing-command-names"></a>Komut adlarının yerelleştirme  
 VSPackages içinde menü komutları ve araç çubuğu düğmeleri .vsct dosyasında tanımlanır.  
  
1.  İçinde **Çözüm Gezgini**, .vsct dosyanın adını değiştirmek *filename*için .vsct *filename*.en-US.vsct.  
  
2.  Bir kopyasını *filename*.en-US.vsct her yerelleştirilmiş dili.  
  
     Her kopya adı *filename*. *Yerel ayar*.vsct, burada *yerel* belirli kültür adı. Kültür adı değerlerinin listesi için bkz: [Microsoft tarafından atanan yerel kimlikler](https://msdn.microsoft.com/en-us/library/windows/apps/jj657969.aspx).  
  
     Bunlar *filename*. *Yerel ayar*.vsct dosyaları paketinize yerelleştirilmiş menü metni içerir.  
  
3.  Her açık *filename*. *Yerel ayar*.vsct metin yerelleştirme dosyaya.  
  
    1.  Değiştirme [■ ButtonText](../extensibility/buttontext-element.md) öğesi için belirli bir dili uygun şekilde değerleri.  
  
    2.  Yerelleştirilmiş simgeler sağlayacaksa değiştirme [bit eşlem](../extensibility/bitmap-element.md) hedef dosyaları işaret edecek şekilde değerleri.  
  
     Aşağıdaki örnek bir Aile ağacı Explorer araç penceresi açmak bir komut için İngilizce ve İspanyolca düğme metni gösterir.  
  
     [FamilyTree.en-US.vsct]  
  
    ```xml  
    <Button guid="guidLocalizedPackageCmdSet" id="cmdidFamilyTree" priority="0x0100" type="Button">  
      <Parent guid="guidSHLMainMenu" id="IDG_VS_WNDO_OTRWNDWS1"/>  
      <Icon guid="guidImages" id="bmpPic2" />  
      <Strings>  
        <CommandName>cmdidFamilyTree</CommandName>  
        <ButtonText>Family Tree Explorer</ButtonText>  
      </Strings>  
    </Button>  
    ```  
  
     [FamilyTree.es-ES.vsct]  
  
    ```xml  
    <Button guid="guidLocalizedPackageCmdSet" id="cmdidFamilyTree" priority="0x0100" type="Button">  
      <Parent guid="guidSHLMainMenu" id="IDG_VS_WNDO_OTRWNDWS1"/>  
      <Icon guid="guidImages" id="bmpPic2" />  
      <Strings>  
        <CommandName>cmdidFamilyTree</CommandName>  
        <ButtonText>Explorar el arbol genealogico</ButtonText>  
      </Strings>  
    </Button>  
  
    ```  
  
## <a name="localizing-other-text-resources"></a>Diğer metin kaynakları yerelleştirme  
 Metin kaynaklar komut adlarının dışında kaynak (.resx) dosyalarını tanımlanır.  
  
1.  VSPackage.resx VSPackage.en-US.resx yeniden adlandırın.  
  
2.  Yerelleştirilmiş her dille ilgili VSPackage.en US.resx dosyanın bir kopyasını oluşturun.  
  
     Her kopya VSPackage olarak adlandırın. *Yerel ayar*.resx, burada *yerel* belirli kültür adı.  
  
3.  Resources.resx Resources.en-US.resx yeniden adlandırın.  
  
4.  Yerelleştirilmiş her dille ilgili Resources.en US.resx dosyanın bir kopyasını oluşturun.  
  
     Her kopya kaynakları olarak adlandırın. *Yerel ayar*.resx, burada *yerel* belirli kültür adı.  
  
5.  Dize değerleri belirli dil ve kültür için uygun olarak değiştirmek için her .resx dosyasını açın. Aşağıdaki örnek, bir aracı penceresinin başlık çubuğunu yerelleştirilmiş kaynak tanımını gösterir.  
  
     [Resources.en-US.resx]  
  
    ```xml  
    <data name="ToolWindowTitle" xml:space="preserve">  
      <value>Family Tree Explorer</value>  
    </data>  
    ```  
  
     [Resources.es-ES.resx]  
  
    ```xml  
    <data name="ToolWindowTitle" xml:space="preserve">  
      <value>Explorador del arbol genealogico</value>  
    </data>  
  
    ```  
  
## <a name="incorporating-localized-resources-into-the-project"></a>Yerelleştirilmiş kaynaklar projeye ekleme  
 AssemblyInfo.cs dosyasını ve yerelleştirilmiş kaynaklar eklemenizi proje dosyasını değiştirmeniz gerekir.  
  
1.  Gelen **özellikleri** düğümünde **Çözüm Gezgini**, AssemblyInfo.cs veya AssemblyInfo.vb düzenleyicide açın.  
  
2.  Aşağıdaki girişi ekleyin.  
  
    ```csharp  
    [assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.Satellite)]  
    ```  
  
     Bu ABD İngilizcesi varsayılan dili ayarlar.  
  
3.  Proje kaldırın.  
  
4.  Proje dosyası düzenleyicisinde açın.  
  
5.  Bulun `ItemGroup` içeren öğe `EmbeddedResource` öğeleri.  
  
6.  İçinde `EmbeddedResource` VSPackage.en-US.resx, çağıran öğeyi değiştirin `ManifestResourceName` öğesi ile bir `LogicalName` kümesine öğesi `VSPackage.en-US.Resources`aşağıdaki gibi.  
  
    ```xml  
    <EmbeddedResource Include="VSPackage.en-US.resx">  
      <MergeWithCTO>true</MergeWithCTO>  
      <LogicalName>VSPackage.en-US.Resources</LogicalName>  
    </EmbeddedResource>  
    ```  
  
7.  Yerelleştirilmiş her dil için kopyalama `EmbeddedResource` öğesi VsPackage.en ABD ve kümesi için **INCLUDE** özniteliği ve **LogicalName** aşağıda gösterildiği gibi hedef yerel kopyasının öğesi örnek.  
  
8.  Her yerelleştirilmiş `VSCTCompile` öğesi ekleme bir `ResourceName` işaret öğesi `Menus.ctmenu`, aşağıdaki örnekte gösterildiği gibi.  
  
    ```xml  
    <ItemGroup>  
      <VSCTCompile Include="LocalizedPackage.es-ES.vsct">  
        <ResourceName>Menus.ctmenu</ResourceName>  
      </VSCTCompile>  
    </ItemGroup>  
    ```  
  
9. Proje dosyasını kaydedin ve projeyi yeniden yükleyin.  
  
10. Projeyi oluşturun.  
  
     Bu, ana derleme ve her dil için kaynak grupları oluşturur. Dağıtım işlemi yerelleştirme hakkında daha fazla bilgi için bkz: [VSIX paket yerelleştirme](../extensibility/localizing-vsix-packages.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletme menüleri ve komutları](../extensibility/extending-menus-and-commands.md)   
 [MenuCommands Vs. OleMenuCommands](../extensibility/menucommands-vs-olemenucommands.md)   
 [Uygulamaları Genelleştirme ve Yerelleştirme](../ide/globalizing-and-localizing-applications.md)