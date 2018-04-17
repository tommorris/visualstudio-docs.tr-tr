---
title: MenuCommands Vs. OleMenuCommands | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands, creating in VSPackages
- command buttons, creating and placing
- menus, creating commands
ms.assetid: 553d5e07-3e19-4aba-b490-6c7dd05fd82e
manager: douge
ms.openlocfilehash: 47ec8bd549f8f5093a7035f37ad728c1e245e3b9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="menucommands-vs-olemenucommands"></a>MenuCommands Vs. OleMenuCommands
Menü komutları herhangi birinden türetme oluşturabileceğiniz <xref:System.ComponentModel.Design.MenuCommand> veya <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> nesne ve impementling uygun olay işleyicileri. Çoğu durumda kullandığınız <xref:System.ComponentModel.Design.MenuCommand>VSPackage proje şablonu yapar ancak bazen kullanmanız gerekebilir gibi <xref:Microsoft.VisualStudio.Shell.OleMenuCommand>.  
  
 VSPackage hale getirir IDE kullanılabilir görünür ve kullanıcı önce etkin olması gerektiğini komutları bunları kullanabilirsiniz. Komutları Visual Studio Paketi proje şablonunu kullanarak bir .vsct dosyasında oluşturduğunuzda, görünür ve varsayılan olarak etkin. Bazı komut bayrakları gibi ayarı `DynamicItemStart`, varsayılan davranışı değiştirebilirsiniz. Görünürlük, etkin durumu ve diğer komutunun özelliklerini da kodda çalışma zamanında erişerek değiştirilebilir <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> komutu ile ilişkili nesne.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzda izlemek için Visual Studio SDK'yı yüklemeniz gerekir. Daha fazla bilgi için bkz: [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="template-locations-for-the-visual-studio-package-template"></a>Visual Studio Paketi şablonu için şablon konumları  
 Visual Studio Paketi şablonunda bulabilirsiniz **yeni proje** altında iletişim **Visual Basic / genişletilebilirlik**, **C# / genişletilebilirlik**, veya **diğer Proje türleri / genişletilebilirlik**.  
  
## <a name="creating-a-command"></a>Bir komut oluşturma  
 Tüm komutlar, komut grupları, menüler, araç çubukları ve aracı windows .vsct dosyasında tanımlanır. Daha fazla bilgi için bkz: [Visual Studio komut tablosu (. Vsct) dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
 Paket şablonu kullanarak bir VSPackage oluşturuyorsanız seçin **menü komutu** .vsct dosyası oluşturabilir ve varsayılan menü komutu tanımlama. Daha fazla bilgi için bkz: [uzantı menü komutu ile oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
#### <a name="to-add-a-command-to-the-ide"></a>IDE komut eklemek için  
  
1.  .Vsct dosyasını açın.  
  
2.  İçinde `Symbols` bölümünde, Bul [GuidSymbol](../extensibility/guidsymbol-element.md) grupları ve komutları içeren öğe.  
  
3.  Oluşturma bir [IDSymbol](../extensibility/idsymbol-element.md) her menüsü, Grup veya komut eklemek için aşağıdaki örnekte gösterildiği gibi istediğiniz öğe.  
  
     <!--FIXME [!CODE [ButtonGroup#01](../CodeSnippet/VS_Snippets_VSSDK/buttongroup#01)]  -->
    ```xaml  
    <GuidSymbol name="guidButtonGroupCmdSet" value="{f69209e9-975a-4543-821d-1f4a2c52d737}">
      <IDSymbol name="MyMenuGroup" value="0x1020" />
      <IDSymbol name="cmdidMyCommand" value="0x0100" />
    </GuidSymbol>
    ```  
  
    `name` Özniteliklerini `GuidSymbol` ve `IDSymbol` öğeleri her yeni menü, Grup veya komut GUID:ID çifti belirtin. `guid` , VSPackage için tanımlanmış bir komut kümesini temsil eder. Birden çok komut kümelerini tanımlayabilirsiniz. Her GUID:ID çifti benzersiz olması gerekir.  
  
4.  İçinde [düğmeleri](../extensibility/buttons-element.md) bölümünde, oluşturmak bir [düğmesini](../extensibility/button-element.md) öğesi komutu aşağıdaki örnekte gösterildiği gibi tanımlayın.  
  
     <!--FIXME [!CODE [ButtonGroup#03](../CodeSnippet/VS_Snippets_VSSDK/buttongroup#03)]  -->
    ```xaml  
    <Button guid="guidButtonGroupCmdSet" id="cmdidMyCommand" priority="0x0100" type="Button">
      <Parent guid="guidButtonGroupCmdSet" id="MyMenuGroup" />
      <Icon guid="guidImages" id="bmpPic1" />
      <Strings>
        <CommandName>cmdidMyCommand</CommandName>
        <ButtonText>My Command name</ButtonText>
      </Strings>
    </Button>
    ```  
  
    1.  Ayarlama `guid` ve `id` yeni komutu GUID:ID eşleşecek alanları.  
  
    2.  Ayarlama `priority` özniteliği.  
  
         `priority` Özniteliği tarafından .vsct kendi üst grubundaki diğer nesneler arasında düğmesinin konumunu belirlemek için kullanılır.  
  
         Düşük öncelikli işler değerlere sahip komutları yukarıda veya solundaki daha yüksek öncelik değerine sahip komutları görüntülenir. Yinelenen öncelik değerlere izin verilir, ancak önceliği eşittir komutları göreli konumunu VSPackages çalışma zamanında işlenir sıraya göre belirlenir ve bu sırayla önceden belirlenmiş olamaz.  
  
         Atlama `priority` öznitelik değerini 0 olarak ayarlar.  
  
    3.  Ayarlama `type` özniteliği. Çoğu durumda, kendi değer olacaktır `"Button"`. Diğer geçerli düğme türleri açıklamaları için bkz: [Button öğesi](../extensibility/button-element.md).  
  
5.  Düğme tanımı'nda oluşturma bir [dizeleri](../extensibility/strings-element.md) içeren öğe bir [■ ButtonText](../extensibility/buttontext-element.md) öğesi IDE içinde göründüğü gibi menü adını içerir ve bir [CommandName](../extensibility/commandname-element.md) menüde erişmek için kullanılan komutun adını içerecek şekilde öğesi **komutu** penceresi.  
  
     '&' Karakteri düğmesi metin dizesini içeren, kullanıcıya menüsünün ALT tuşuna basarak açabilirsiniz artı karakteri bu hemen izleyen varsa '&'.  
  
     Ekleme bir `Tooltip` öğesi, bir kullanıcı işaretçiyi düğmenin üzerine geldiğinde görünmesi kapsanan metin neden olur.  
  
6.  Ekleme bir [simgesi](../extensibility/icon-element.md) varsa komutuyla gösterilecek simgeyi belirtmenizi öğesi. Simgeler araç çubuğu düğmeleri için menü öğeleri ancak gerekli değildir. `guid` Ve `id` , `Icon` öğe içeriğiyle eşleşmelidir bir [bit eşlem](../extensibility/bitmap-element.md) tanımlanan öğe `Bitmaps` bölümü.  
  
7.  Komut bayrakları, uygun şekilde, Görünüm ve düğme davranışını değiştirmek ekleyin. Bunu yapmak için ekleyin bir [CommandFlag](../extensibility/command-flag-element.md) menü tanımında öğesi.  
  
8.  Komut, üst grup olarak ayarlayın. Üst grubun oluşturduğunuz bir grup, bir gruptan başka bir paket veya bir gruptan IDE olabilir. Örneğin, komutunuzu Visual Studio düzenleme araç çubuğuna yanına eklemek için **açıklama** ve **kaldırmak açıklama** düğmeleri, üst guidStdEditor:IDG_VS_EDITTOOLBAR_COMMENT için ayarlayın. Üst kullanıcı tanımlı bir grup ise alt menü, araç ya da IDE içinde araç penceresi olması gerekir.  
  
     Tasarımınızın bağlı olarak bunu iki yoldan biriyle yapabilirsiniz:  
  
    -   İçinde `Button` öğesini oluşturmak bir [üst](../extensibility/parent-element.md) öğesi ve kümesi kendi `guid` ve `id` GUID ve komut olarak da bilinen barındıracak grubunun kimliği alanlarına *birincil üst grubu*.  
  
         Aşağıdaki örnekte görünecek komutu kullanıcı tanımlı bir menüsünde tanımlar.  
  
         <!--FIXME [!CODE [TopLevelMenu#03](../CodeSnippet/VS_Snippets_VSSDK/toplevelmenu#03)]  -->
        ```xaml  
        <Button guid="guidTopLevelMenuCmdSet" id="cmdidTestCommand" priority="0x0100" type="Button">
          <Parent guid="guidTopLevelMenuCmdSet" id="MyMenuGroup" />
          <Icon guid="guidImages" id="bmpPic1" />
          <Strings>
            <CommandName>cmdidTestCommand</CommandName>
            <ButtonText>Test Command</ButtonText>
          </Strings>
        </Button>
        ```  
  
    -   Atlayın `Parent` komutu komut yerleşimi kullanarak konumlandırılması gerekiyorsa öğesi. Oluşturma bir [CommandPlacements](../extensibility/commandplacements-element.md) öğesinden önce `Symbols` bölümünde ve ekleme bir [CommandPlacement](../extensibility/commandplacement-element.md) olan öğeyi `guid` ve `id` komutun, bir `priority`ve aşağıdaki örnekte gösterildiği gibi bir üst.  
  
         <!-- FIXME [!CODE [ButtonGroup#04](../CodeSnippet/VS_Snippets_VSSDK/buttongroup#04)] -->  
        ```xaml  
        <CommandPlacements>
          <CommandPlacement guid="guidButtonGroupCmdSet" id="cmdidMyCommand" priority="0x105">
            <Parent guid="guidButtonGroupCmdSet" id="MyMenuGroup" />
          </CommandPlacement>
        </CommandPlacements>
        ```  
  
         Aynı GUID:ID ve farklı üst sahip birden çok komut yerleşimi oluşturma birden fazla konumda görünmesi bir menü neden olur. Daha fazla bilgi için bkz: [CommandPlacements](../extensibility/commandplacements-element.md) öğesi.  
  
     Komut grupları ve ana öğe hakkında daha fazla bilgi için bkz: [, yeniden kullanılabilir grupları düğmeler oluşturma](../extensibility/creating-reusable-groups-of-buttons.md).  
  
 Bu noktada, komutu IDE içinde görünür, ancak hiçbir işlevselliğine sahip olacaktır. Varsayılan olarak komut paket şablon tarafından oluşturulmuşsa, bir ileti görüntüler click işleyicisi gerekir.  
  
## <a name="handling-the-new-command"></a>Yeni bir komut işleme  
 Yönetilen kod çoğu komutlarda komutu ile ilişkilendirerek yönetilen paket Framework (MPF tarafından) işlenebilir bir <xref:System.ComponentModel.Design.MenuCommand> nesne veya <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> nesne ve olay işleyicileri uygulama.  
  
 Kullanan kodu için <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimi doğrudan işleme komutu için uygulanmalı <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimi ve onun yöntemleri. İki en önemli yöntemler <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> ve <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A>.  
  
1.  Alma <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService> , aşağıdaki örnekte gösterildiği gibi örneği.  
  
     [!code-csharp[ButtonGroup#21](../extensibility/codesnippet/CSharp/menucommands-vs-olemenucommands_5.cs)]  
  
2.  Oluşturma bir <xref:System.ComponentModel.Design.CommandID> , aşağıdaki örnekte gösterildiği gibi parametre olarak GUID ve işlemek için komut kimliği sahip bir nesne.  
  
     [!code-csharp[ButtonGroup#22](../extensibility/codesnippet/CSharp/menucommands-vs-olemenucommands_6.cs)]  
  
     Visual Studio Paketi şablonu iki koleksiyonları sağlar `GuidList` ve `PkgCmdIDList`, GUID'ler ve komutları kimliklerini tutmak için. Bu şablon tarafından eklenen komutlar için otomatik olarak doldurulur, ancak el ile Ekle komutları kimliği girişine de eklemelisiniz `PkgCmdIdList` sınıfı.  
  
     Alternatif olarak, doldurmak <xref:System.ComponentModel.Design.CommandID> GUID'yi ham dize değerini ve kimliği tamsayı değerini kullanarak nesnesi  
  
3.  Ya da örneği bir <xref:System.ComponentModel.Design.MenuCommand> veya <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> komutu ile birlikte işleyen yöntem belirtir nesne <xref:System.ComponentModel.Design.CommandID>, aşağıdaki örnekte gösterildiği gibi.  
  
     [!code-csharp[ButtonGroup#23](../extensibility/codesnippet/CSharp/menucommands-vs-olemenucommands_7.cs)]  
  
     <xref:System.ComponentModel.Design.MenuCommand> Statik komutları için uygundur. Dinamik menü öğesi görüntüler QueryStatus olay işleyicileri gerektirir. <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> Ekler <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> ana menü komut açılmış ve bazı diğer özellikler gibi olduğunda oluşan olay <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.Text%2A>.  
  
     Paket şablon tarafından oluşturulan komutlar için varsayılan olarak geçirilir bir <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> nesnesinde `Initialize()` paketi sınıfının yöntemi.  
  
4.  <xref:System.ComponentModel.Design.MenuCommand> Statik komutları için uygundur. Dinamik menü öğesi görüntüler QueryStatus olay işleyicileri gerektirir. <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> Ekler <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> ana menü komut açılmış ve bazı diğer özellikler gibi olduğunda oluşan olay <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.Text%2A>.  
  
     Paket şablon tarafından oluşturulan komutlar için varsayılan olarak geçirilir bir <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> nesnesinde `Initialize()` paketi sınıfının yöntemi. Visual Studio Sihirbazı'nı uygulayan `Initialize` kullanarak yöntemi `MenuCommand`. Dinamik menü öğesi görüntüler için bu değiştirmelisiniz `OleMenuCommand`, sonraki adımda gösterildiği gibi. Ayrıca, menü öğesi metni değiştirmek için bir TextChanges komutu bayrak menü komut düğmesi .vsct dosyasında, aşağıdaki örnekte gösterildiği gibi eklemeniz gerekir  
  
     <!--FIXME [!CODE [MenuText#02](../CodeSnippet/VS_Snippets_VSSDK/menutext#02)]-->  
    ```xaml  
    <Button guid="guidMenuTextCmdSet" id="cmdidMyCommand" priority="0x0100" type="Button">
      <Parent guid="guidMenuTextCmdSet" id="MyMenuGroup" />
      <Icon guid="guidImages" id="bmpPic1" />
      <CommandFlag>TextChanges</CommandFlag>
      <Strings>
        <CommandName>cmdidMyCommand</CommandName>
        <ButtonText>My Command name</ButtonText>
      </Strings>
    </Button>
    ```
  
5.  Yeni menü komutu geçirmek <xref:System.ComponentModel.Design.IMenuCommandService.AddCommand%2A> yönteminde <xref:System.ComponentModel.Design.IMenuCommandService> arabirimi. Bu paket şablon tarafından oluşturulan komutlar için varsayılan olarak aşağıdaki örnekte gösterildiği gibi gerçekleştirilir  
  
     [!code-csharp[ButtonGroup#24](../extensibility/codesnippet/CSharp/menucommands-vs-olemenucommands_9.cs)]  
  
6.  Komut işleme yöntemi uygulayabilirsiniz.  
  
#### <a name="to-implement-querystatus"></a>QueryStatus uygulamak için  
  
1.  Bir komut görüntülenmeden önce QueryStatus olayı oluşur. Bu komut kullanıcı erişmeden olay işleyicisi için ayarlanacak özelliklerini sağlar. Olarak eklenen komutları <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> nesneler, bu yöntem erişebilir.  
  
     Ekleme bir `EventHandler` nesnesini <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> olayında <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> komutu işlemek için aşağıdaki örnekte gösterildiği gibi oluşturulan nesne (`menuItem` olan <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> örnek).  
  
     [!code-csharp[MenuText#14](../extensibility/codesnippet/CSharp/menucommands-vs-olemenucommands_10.cs)]
     [!code-vb[MenuText#14](../extensibility/codesnippet/VisualBasic/menucommands-vs-olemenucommands_10.vb)]  
  
     `EventHandler` Nesne menü komutu durumunu sorgulandığında çağrılan yöntemin adı verilir.  
  
2.  Komutu için sorgu durum işleyici yöntemi uygulayabilirsiniz. `object` `sender` Parametresi dönüştürülür için bir <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> menü komutu metni dahil olmak üzere, çeşitli özniteliklerini ayarlamak için kullanılan nesne. Aşağıdaki tabloda bulunan özellikleri gösterir <xref:System.ComponentModel.Design.MenuCommand> sınıfı (hangi MPF sınıfı <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> türetilen), karşılık <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF> bayrakları.  
  
    |MenuCommand özelliği|OLECMDF bayrağı|  
    |--------------------------|------------------|  
    |<xref:System.ComponentModel.Design.MenuCommand.Checked%2A> = `true`|OLECMDF_LATCHED|  
    |<xref:System.ComponentModel.Design.MenuCommand.Visible%2A> = `false`|OLECMDF_INVISIBLE|  
    |<xref:System.ComponentModel.Design.MenuCommand.Enabled%2A> = `true`|OLECMDF_ENABLED|  
  
     Menü komutu metni değiştirmek için kullanmak <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.Text%2A> özelliği <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> , aşağıdaki örnekte gösterildiği gibi nesne.  
  
     [!code-csharp[MenuText#11](../extensibility/codesnippet/CSharp/menucommands-vs-olemenucommands_11.cs)]
     [!code-vb[MenuText#11](../extensibility/codesnippet/VisualBasic/menucommands-vs-olemenucommands_11.vb)]  
  
 MPF desteklenmeyen veya bilinmeyen gruplarının durum otomatik olarak yönetir. Bir komut eklendi sürece <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService> kullanarak <xref:System.ComponentModel.Design.IMenuCommandService.AddCommand%2A> yöntemi, komutu desteklenmiyor.  
  
### <a name="handling-commands-by-using-the-iolecommandtarget-interface"></a>IOleCommandTarget arabirimi kullanarak komutları işleme  
 Kullanan kodu için <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> doğrudan arabirim, VSPackage her ikisi de uygulamalıdır <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> ve <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> yöntemlerinin <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimi. VSPackage bir proje hiyerarşisi uyguluyorsa <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A> yöntemlerinin <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> arabirimi uygulanan yerine.  
  
 Hem <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> ve <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> yöntemleri, tek bir komut kümesi almak için tasarlanmıştır `GUID` ve komut kimlikleri bir dizi girişi olarak. VSPackages tek çağrıda tam olarak bu kavramı, birden çok kimliği destekleyen öneririz. Bir VSPackage diğer VSPackages çağrılmaz sürece, Bununla birlikte, komut dizisi için tek bir komut kimliği içeren kabul edilebilir <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> ve <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> yöntemleri iyi tanımlanmış bir sırada çalıştırılır. Yönlendirme hakkında daha fazla bilgi için bkz: [komut yönlendirme VSPackages içinde](../extensibility/internals/command-routing-in-vspackages.md).  
  
 Kullanan kodu için <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimi doğrudan işleme komutu için uygulanmalı <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> gibi komutları işlemek için VSPackage yöntemi.  
  
##### <a name="to-implement-the-querystatus-method"></a>QueryStatus yöntemi uygulamak için  
  
1.  Dönüş <xref:Microsoft.VisualStudio.VSConstants.S_OK> geçerli komutlar için.  
  
2.  Ayarlama `cmdf` öğesinin `prgCmds` parametresi.  
  
     Değeri `cmdf` öğesidir değerlerinden mantıksal birleşimi <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF> mantıksal OR kullanarak birleştirilmiş numaralandırması (`|`) işleci.  
  
     Komut durumlarına dayalı uygun numaralandırma kullanın:  
  
    -   Komut destekleniyorsa:  
  
         `prgCmds[0].cmdf = OLECMDF_SUPPORTED;`  
  
    -   Komut şu anda görünmez gerekiyorsa:  
  
         `prgCmds[0].cmdf |= OLECMDF_INVISIBLE;`  
  
    -   Komut çubuğunda yükseğe ve tıklanan görünüyor ise:  
  
         `prgCmds[0].cmdf |= OLECMDF_LATCHED;`  
  
         Türü menüsünde barındırılan komutlarının işlenmesi durumunda `MenuControllerLatched`, tarafından işaretlenen ilk komut `OLECMDF_LATCHED` bayrağı olduğu başlangıç menüsünde tarafından görüntülenen varsayılan komutu. Hakkında daha fazla bilgi için `MenuController` menü türlerini görmek [menü öğesi](../extensibility/menu-element.md).  
  
    -   Komut şu anda etkin ise:  
  
         `prgCmds[0].cmdf |= OLECMDF_ENABLED;`  
  
    -   Komut bir kısayol menüsü parçası ise ve varsayılan olarak gizlidir:  
  
         `prgCmds[0] cmdf |= OLECMDF_DEFHIDEONCTXTMENU`  
  
    -   Komut kullanıyorsa, `TEXTCHANGES` bayrak, Ayarla `rgwz` öğesinin `pCmdText` yeni metin kümesi ve komut parametresi `cwActual` öğesinin `pCmdText` komutu dize boyutu parametresi.  
  
     Hata koşulları için <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> yöntemi, aşağıdaki hata durumları işlemek gerekir:  
  
    -   GUID bilinmeyen veya desteklenmeyen ise, döndürür `OLECMDERR_E_UNKNOWNGROUP`.  
  
    -   GUID bilinen ancak komut kimliği bilinmiyor veya desteklenmiyor, dönüş `OLECMDERR_E_NOTSUPPORTED`.  
  
 VSPackage uyarlamasını <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> yöntemi komutu desteklenip ve olup komutu başarılı bir şekilde yürütüldü bağlı olarak belirli hata kodları ayrıca döndürmesi gerekir.  
  
##### <a name="to-implement-the-exec-method"></a>Exec yöntemi uygulamak için  
  
-   Varsa komutu `GUID` bilinmiyor dönmek `OLECMDERR_E_UNKNOWNGROUP`.  
  
-   Varsa `GUID` bilinen ancak komut kimliği bilinmiyor, iade `OLECMDERR_E_NOTSUPPORTED`.  
  
-   Varsa `GUID` ve kimliği ile aynı .vsct dosyasında komutu tarafından kullanılan GUID:ID çifti komutu, komut ve return ilişkili kod yürütmek <xref:Microsoft.VisualStudio.VSConstants.S_OK>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSCT XML Şeması Başvurusu](../extensibility/vsct-xml-schema-reference.md)   
 [Menüleri ve Komutlari Genişletme](../extensibility/extending-menus-and-commands.md)