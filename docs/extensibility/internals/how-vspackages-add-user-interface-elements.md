---
title: Kullanıcı arabirimi öğeleri nasıl VSPackages eklemek | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- user interfaces, adding elements
- UI element design [Visual Studio SDK], VSPackages
- VSPackages, contributing UI elements
ms.assetid: abc5d9d9-b267-48a1-92ad-75fbf2f4c1b9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 930ab9e741b2fd5bbc0ca2954192fe5e2c4313d4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31136087"
---
# <a name="how-vspackages-add-user-interface-elements"></a>Kullanıcı arabirimi öğeleri VSPackages nasıl eklenir
Bir VSPackage kullanıcı arabirimi (UI) öğeleri, örneğin, menüler, araç çubukları, eklemek ve Visual Studio .vsct dosya yoluyla windows aracı.  
  
 UI öğeler için tasarım yönergeleri bulabilirsiniz [Visual Studio kullanıcı deneyimi yönergeleri](../../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md).  
  
## <a name="the-visual-studio-command-table-architecture"></a>Visual Studio komut tablo mimarisi  
 Belirtildiği gibi komut tabloda mimarisi yukarıda mimari ilkeleri destekler. Soyutlamalar, veri yapılarını ve Araçları komut tabloda mimarisinin arkasındaki tenets aşağıdaki gibidir:  
  
-   Üç temel tür öğe vardır: menüleri, komutları ve grupları. Menüleri kullanıcı Arabiriminde menüler, alt menüler, araç çubukları veya araç pencereleri gösterilebilir. IDE içinde kullanıcı yürütebilir ve menü öğeleri, düğmeleri, liste kutuları veya diğer denetimleri verilebilen yordamları komutlardır. Menüler ve komutlar için kapsayıcı gruplarıdır.  
  
-   Her öğe açıklayan öğesi, diğer öğeleri ve davranışını değiştirmek bayrakları göre önceliğini tanımı tarafından belirtilir.  
  
-   Her öğenin üst öğesinin açıklayan bir yerleştirme vardır. Böylece kullanıcı arabiriminde birden fazla konumda görünebilir bir öğe birden çok üst olabilir.  
  
     Bu gruptaki yalnızca alt olsa bile, her komutun kendi üst öğesi olarak bir grup olması gerekir. Her standart menü ayrıca bir üst grubu olmalıdır. Araç çubukları ve aracı windows kendi üst davranır. Bir grup ana Visual Studio menü çubuğunda, üst veya tüm menü, araç veya araç penceresi olabilir.  
  
### <a name="how-items-are-defined"></a>Öğeleri nasıl tanımlanır  
 . Vsct dosyaları XML biçimlendirilir. Bir .vsct dosyayı bir paket için kullanıcı Arabirimi öğeleri tanımlar ve bu öğeleri IDE içinde nerede görüneceğini belirler. Her menü, Grup veya paket komutta ilk bir GUID ve kimliği atanır `Symbols` bölümü. .vsct geri kalanı dosyası, her menü, komut ve grup, GUID ve ID bileşimiyle tanımlanır. Aşağıdaki örnek gösterilmektedir `Symbols` bölümünde Visual Studio Paketi şablonu tarafından oluşturulan olduğunda bir **menü komutu** şablonda seçilir.  
  
```xml  
<Symbols>  
  <!-- This is the package guid. -->  
  <GuidSymbol name="guidMenuTextPkg" value="{b1253bc6-d266-402b-89e7-5e3d3b22c746}" />  
  
  <!-- This is the guid used to group the menu commands together -->  
  <GuidSymbol name="guidMenuTextCmdSet" value="{a633d4e4-6c65-4436-a138-1abeba7c9a69}">  
  
    <IDSymbol name="MyMenuGroup" value="0x1020" />  
    <IDSymbol name="cmdidMyCommand" value="0x0100" />  
  </GuidSymbol>  
  
  <GuidSymbol name="guidImages" value="{53323d9a-972d-4671-bb5b-9e418480922f}" >  
    <IDSymbol name="bmpPic1" value="1" />  
    <IDSymbol name="bmpPic2" value="2" />  
    <IDSymbol name="bmpPicSearch" value="3" />  
    <IDSymbol name="bmpPicX" value="4" />  
    <IDSymbol name="bmpPicArrows" value="5" />  
  </GuidSymbol>  
</Symbols>  
```  
  
 Üst düzey öğenin `Symbols` bölüm [GuidSymbol öğesi](../../extensibility/guidsymbol-element.md). `GuidSymbol` öğe adları tarafından IDE paketleri ve bunların bileşen bölümleri tanımlamak için kullanılan GUID'ler eşleyin.  
  
> [!NOTE]
>  GUID, Visual Studio Paketi şablon tarafından otomatik olarak oluşturulur. Benzersiz bir GUID tıklatarak da oluşturabilirsiniz **Create GUID** üzerinde **Araçları** menüsü.  
  
 İlk `GuidSymbol` öğesi, "GUID [PackageName] Pkg", paket GUID'dir. Bu paketi yüklemek için Visual Studio tarafından kullanılan GUID değeridir. Genellikle, alt öğe yok.  
  
 Menüleri ve komutları bir saniyenin altında kurala göre gruplandırılır `GuidSymbol` öğesi, "GUID [PackageName] CmdSet", ve bit eşlemler altında üçüncü `GuidSymbol` öğesi, "guidImages". Bu kural izlemeniz gerekmez, ancak her menüsü, Grup, komut ve bit eşlem bir alt öğesi olması gerekir bir `GuidSymbol` öğesi.  
  
 İkinci `GuidSymbol` paket komut kümesini temsil eder, öğenin çeşitli `IDSymbol` öğeleri. Her [IDSymbol öğesi](../../extensibility/idsymbol-element.md) sayısal bir değer için bir ad eşler ve menü, Grup veya komut kümesinin parçası olan komutu gösterebilir. `IDSymbol` Üçüncü öğelerinde `GuidSymbol` simgelerle komutları için kullanılabilir öğe temsil bit eşlemler. GUID/kimliği çiftleri benzersiz bir uygulama, aynı iki alt öğesi olması gerektiğinden `GuidSymbol` öğesi aynı değere sahip olabilir.  
  
### <a name="menus-groups-and-commands"></a>Menüleri, gruplar ve komutlar  
 Menü, Grup veya komut bir GUID ve ID sahip olduğunda IDE eklenebilir. Her kullanıcı Arabirimi öğesi şunları içermelidir:  
  
-   A `guid` adıyla eşleşen öznitelik `GuidSymbol` UI öğesi altında tanımlanan öğesi.  
  
-   Bir `id` ilişkili adıyla eşleşen öznitelik `IDSymbol` öğesi.  
  
     Birlikte `guid` ve `id` öznitelikleri oluşturan *imza* kullanıcı Arabirimi öğesi.  
  
-   A `priority` UI öğesi kendi üst menü ya da Grup yerleşimini belirler özniteliği.  
  
-   A [üst öğesi](../../extensibility/parent-element.md) olan `guid` ve `id` imza üst menüsünün veya grup belirtin öznitelikleri.  
  
#### <a name="menus"></a>Menüler  
 Her menüye olarak tanımlanan bir [menü öğesi](../../extensibility/menu-element.md) içinde `Menus` bölümü. Menüleri olmalıdır `guid`, `id`, ve `priority` öznitelikleri ve `Parent` öğesini ve ayrıca aşağıdaki ek öznitelikler ve alt öğeleri:  
  
-   A `type` menü menü bir tür veya bir araç olarak IDE'de görünüp görünmeyeceğini belirten özniteliği.  
  
-   A [dizeleri öğesi](../../extensibility/strings-element.md) içeren bir [■ ButtonText öğesi](../../extensibility/buttontext-element.md), IDE içinde menü başlığı belirtir ve bir [CommandName öğesi](../../extensibility/commandname-element.md), adını belirtir kullanılan **komutu** menüsüne erişmek için penceresi.  
  
-   İsteğe bağlı bayraklar. A [komutu bayrağı öğesi](../../extensibility/command-flag-element.md) görünüşünü veya IDE'de davranışını değiştirmek için menü tanımında görünebilir.  
  
 Her `Menu` öğesi olmalı bir grup kendi üst öğesi olarak dockable öğe araç çubuğu gibi değilse. Dockable menü kendi üst öğedir. Menüleri ve değerlerini hakkında daha fazla bilgi için `type` özniteliği için bkz: [menü öğesi](../../extensibility/menu-element.md) belgeleri.  
  
 Aşağıdaki örnek, Visual Studio menü çubuğunda görünür bir menü gösterir **Araçları** menüsü.  
  
```xml  
<Menu guid="guidTopLevelMenuCmdSet"  
id="TopLevelMenu" priority="0x700" type="Menu">  
  <Parent guid="guidSHLMainMenu"  
          id="IDG_VS_MM_TOOLSADDINS" />  
  <Strings>  
    <ButtonText>TestMenu</ButtonText>  
    <CommandName>TestMenu</CommandName>  
  </Strings>  
</Menu>  
```  
  
#### <a name="groups"></a>Gruplar  
 Bir grup içinde tanımlanan bir öğedir `Groups` .vsct dosyasının bölümü. Gruplar yalnızca kapsayıcılardır. IDE dışında bir menüsünde bir çizgi olarak görünmezler. Bu nedenle, bir [Grup öğesi](../../extensibility/group-element.md) yalnızca kendi imza, öncelik ve üst tarafından tanımlanır.  
  
 Bir grup menü, başka bir Grup ya da kendi üst olarak sahip olabilir. Ancak, üst genellikle bir menü veya araç olur. Önceki örneği menüde bir alt öğesi değil `IDG_VS_MM_TOOLSADDINS` grubu ve bu grubu olan Visual Studio menü çubuğu alt. Aşağıdaki örnekte önceki örnekte menüsünün alt grubudur.  
  
```  
 <Group guid="guidTopLevelMenuCmdSet" id="MyMenuGroup"  
priority="0x0600">  
   <Parent guid="guidTopLevelMenuCmdSet" id="TopLevelMenu"/>  
 </Group>  
```  
  
 Bir menüyü bir parçası olduğundan, bu grubun genellikle komutları içerir. Ancak, diğer menüleri de içerebilir. Alt menüler nasıl tanımlanan, aşağıdaki örnekte gösterildiği gibi budur.  
  
```xml  
<Menu guid="guidTopLevelMenuCmdSet" id="SubMenu"  
priority="0x0100" type="Menu">  
  <Parent guid="guidTopLevelMenuCmdSet" id="MyMenuGroup"/>  
  <Strings>  
    <ButtonText>Sub Menu</ButtonText>  
    <CommandName>Sub Menu</CommandName>  
  </Strings>  
</Menu>  
```  
  
#### <a name="commands"></a>Komutlar  
 IDE için sağlanan bir komut olarak tanımlanan bir [Button öğesi](../../extensibility/button-element.md) veya [açılan öğesi](../../extensibility/combo-element.md). Bir menüsü veya bir araç çubuğunda görünmesini için komutu, kendi üst öğesi olarak bir grup olması gerekir.  
  
##### <a name="buttons"></a>Düğmeleri  
 Düğmeleri tanımlanmış `Buttons` bölümü. Herhangi bir menü öğesini, düğme veya tek bir komut yürütmek için bir kullanıcı, başka bir öğenin bir düğme olarak kabul edilir. Bazı düğme türleri listesi işlevselliği de içerir. Düğmeleri sahip aynı gerekli ve menüleri olan isteğe bağlı öznitelikleri ve ayrıca olabilir bir [Icon öğesi](../../extensibility/icon-element.md) GUID ve IDE içinde düğmesi nesnesini temsil eden bit eşlem Kimliğini belirtir. Düğmeler ve onların öznitelikleri hakkında daha fazla bilgi için bkz: [düğmeleri öğesi](../../extensibility/buttons-element.md) belgeleri.  
  
 Aşağıdaki örnekte düğmesi önceki örnekte grubunun bir alt öğesi olan ve IDE içinde menü öğesi olarak o grubun üst menüsünde görüntülenir.  
  
```  
<Button guid="guidTopLevelMenuCmdSet" id="cmdidTestCommand" priority="0x0100" type="Button">  
  <Parent guid="guidTopLevelMenuCmdSet" id="MyMenuGroup" />  
  <Icon guid="guidImages" id="bmpPic1" />  
  <Strings>  
    <CommandName>cmdidTestCommand</CommandName>  
    <ButtonText>Test Command</ButtonText>  
  </Strings>  
</Button>  
```  
  
##### <a name="combos"></a>Birleşik  
 Birleşik tanımlanmış `Combos` bölümü. Her `Combo` öğesi IDE aşağı açılan liste kutusunda temsil eder. Liste kutusu olabilir veya değerine bağlı olarak kullanıcılar tarafından yazılabilir olmayabilir `type` açılan özniteliğidir. Birleşik aynı öğelere sahip ve düğmeleri davranış sahip ve aşağıdaki ek öznitelikler de sahip olabilir:  
  
-   A `defaultWidth` piksel genişliği belirten özniteliği.  
  
-   Bir `idCommandList` liste kutusunda görüntülenen öğeleri içeren bir liste belirten özniteliği. Komut listesinden aynı bildirilmelidir `GuidSymbol` açılan içeren düğümü.  
  
 Aşağıdaki örnek, bir birleşik öğesi tanımlar.  
  
```xml  
<Combos>  
  <Combo guid="guidFirstToolWinCmdSet"  
         id="cmdidWindowsMediaFilename"  
         priority="0x0100" type="DynamicCombo"  
         idCommandList="cmdidWindowsMediaFilenameGetList"  
         defaultWidth="130">  
    <Parent guid="guidFirstToolWinCmdSet"  
            id="ToolbarGroupID" />  
    <CommandFlag>IconAndText</CommandFlag>  
    <CommandFlag>CommandWellOnly</CommandFlag>  
    <CommandFlag>StretchHorizontally</CommandFlag>  
    <Strings>  
      <CommandName>Filename</CommandName>  
      <ButtonText>Enter a Filename</ButtonText>  
    </Strings>  
  </Combo>  
</Combos>  
```  
  
##### <a name="bitmaps"></a>Bit eşlemler  
 İle birlikte bir simge görüntülenecek komutları içermelidir bir `Icon` GUID ve kimliğini kullanarak bir bit eşlem başvurur öğesi Her bit eşlem olarak tanımlanan bir [bit eşlem öğesi](../../extensibility/bitmap-element.md) içinde `Bitmaps` bölümü. Yalnızca gerekli öznitelikler için bir `Bitmap` definition `guid` ve `href`, kaynak dosyasına işaret eder. Kaynak dosya kaynak Şerit ise bir **usedList** özniteliği de, Şerit kullanılabilir görüntüleri listelemek için gereklidir. Daha fazla bilgi için bkz: [bit eşlem öğesi](../../extensibility/bitmap-element.md) belgeleri.  
  
### <a name="parenting"></a>Üst öğe ayarlama  
 Aşağıdaki kurallar, bir öğe başka bir öğe kendi üst nasıl çağırabilirsiniz kapsar.  
  
|Öğe|Bu komut tablo bölümünde tanımlanan|Yer alabilecek (üst öğe olarak ya da yerleşimini tarafından `CommandPlacements` bölüm veya her ikisi de)|İçerebilir (üst öğe olarak adlandırılır)|  
|-------------|--------------------------------------------------|---------------------------------------------------------------------------------------------------|---------------------------------------------|  
|Grup|[Gruplar öğesi](../../extensibility/groups-element.md), IDE, diğer VSPackages|Bir menüyü bir Grup öğesi|Menüleri, gruplar ve komutlar|  
|Menü|[Menü öğesi](../../extensibility/menus-element.md), IDE, diğer VSPackages|1 *n* grupları|0 olarak *n* grupları|  
|Araç Çubuğu|[Menü öğesi](../../extensibility/menus-element.md), IDE, diğer VSPackages|Öğenin kendisi|0 olarak *n* grupları|  
|Menü Öğesi|[Düğme öğesi](../../extensibility/buttons-element.md), IDE, diğer VSPackages|1 *n* gruplar, öğesi|-0 olarak *n* grupları|  
|Düğme|[Düğme öğesi](../../extensibility/buttons-element.md), IDE, diğer VSPackages|1 *n* gruplar, öğesi||  
|Birleşik giriş|[Birleşik öğesi](../../extensibility/combos-element.md), IDE, diğer VSPackages|1 *n* gruplar, öğesi||  
  
### <a name="menu-command-and-group-placement"></a>Menü, komut ve Grup yerleştirme  
 Menü, Grup veya komut IDE içinde birden fazla konumda yer alabilir. Bir öğenin birden fazla konumda görünmesini onu eklenmeli `CommandPlacements` olarak bölümünde bir [CommandPlacement öğesi](../../extensibility/commandplacement-element.md). Hiçbir menüsü, Grup veya komutu bir komut yerleşimi eklenebilir. Ancak, birden çok bağlama duyarlı konumda yer alamaz çünkü araç çubukları bu şekilde konumlandırılmış olamaz.  
  
 Komut yerleşimi sahip `guid`, `id`, ve `priority` öznitelikleri. GUID ve kimliği konumlandırılmış öğenin eşleşmelidir. `priority` Öznitelik öğe diğer öğeleri açısından yerleşimini yönetir. IDE aynı önceliğe sahip iki veya daha fazla öğe birleştirir, IDE paket yerleşik her zaman aynı sırada paket kaynaklarını okuma garanti etmez çünkü bunların yerleşimi tanımlanmaz.  
  
 Menü veya grup birden fazla konumda görünüyorsa, o menü veya grup tüm alt öğeleri her örnek görünür.  
  
## <a name="command-visibility-and-context"></a>Komut görünürlük ve bağlamı  
 Birden çok VSPackages yüklendiğinde, menüler, menü öğeleri ve araç çubuklarını bolluk IDE dağıtmayı. Bu sorunu önlemek için tek tek kullanıcı Arabirimi öğeleri görünürlüğünü kullanarak denetleyebilirsiniz *görünürlük kısıtlamaları* ve komut işaretler.  
  
##### <a name="visibility-constraints"></a>Görünürlüğü kısıtlama  
 Görünürlüğü kısıtlama olarak ayarlanmış olan bir [VisibilityItem öğesi](../../extensibility/visibilityitem-element.md) içinde `VisibilityConstraints` bölümü. Görünürlüğü kısıtlama hedef öğesi görülebilir belirli UI bağlamları tanımlar. Yalnızca biri tanımlanmış bağlamları etkin olduğunda bir menü veya bu bölümde komut görünür olur. Bu bölümde bir menü veya komut başvurulmuyorsa her zaman varsayılan olarak görülebilir. Bu bölümde gruplarına uygulanmaz.  
  
 `VisibilityItem` öğeleri özniteliklerine sahip olmalıdır üç, aşağıdaki gibi: `guid` ve `id` hedef UI öğesinin ve `context`. `context` Özniteliği, ne zaman hedef öğesi görünür ve değeri olarak geçerli bir kullanıcı Arabirimi bağlamı alan belirtir. Visual Studio için kullanıcı Arabirimi bağlam sabitleri üyesi <xref:Microsoft.VisualStudio.VSConstants> sınıfı. Her `VisibilityItem` öğesi yalnızca bir içerik değeri alabilir. İkinci bir bağlam uygulamak için ikinci bir oluşturma `VisibilityItem` aşağıdaki örnekte gösterildiği gibi aynı öğesine işaret öğesi.  
  
```xml  
<VisibilityConstraints>  
  <VisibilityItem guid="guidSolutionToolbarCmdSet"  
        id="cmdidTestCmd"  
        context="UICONTEXT_SolutionHasSingleProject" />  
  <VisibilityItem guid="guidSolutionToolbarCmdSet"  
        id="cmdidTestCmd"  
        context="UICONTEXT_SolutionHasMultipleProjects" />  
</VisibilityConstraints>  
```  
  
##### <a name="command-flags"></a>Komut bayrakları  
 Aşağıdaki komut bayrakları menüleri ve komutları uygulandıkları görünürlüğünü etkileyebilir.  
  
 AlwaysCreate  
 Menü grupları ya da düğmeleri sahip olsa bile oluşturulur.  
  
 Geçerlilik süresi: `Menu`  
  
 CommandWellOnly  
 Bu bayrak komutu en üst düzey menüsünde görünmez ve ek Kabuk özelleştirmesi için kullanılabilir hale getirmek istediğiniz örneğin, bir anahtara bağlama uygulayın. VSPackage yüklendikten sonra bir kullanıcı bu komutları açarak özelleştirebilir **seçenekleri** iletişim kutusunu ve ardından komut yerleşimi altında düzenleme **klavye ortamı** kategorisi. Kısayol menüleri, araç çubukları, menü denetleyicileri veya alt menüler yerleştirme etkilemez.  
  
 İçin geçerli: `Button`, `Combo`  
  
 DefaultDisabled  
 Varsayılan olarak, komut uygulayan VSPackage yüklenmedi veya QueryStatus yöntemi çağrılmazsa komutu devre dışıdır.  
  
 İçin geçerli: `Button`, `Combo`  
  
 DefaultInvisible  
 Varsayılan olarak, komut komutu uygulayan VSPackage yüklenmedi veya QueryStatus yöntemi çağrılmazsa görünmez olur.  
  
 İle birleştirilmelidir `DynamicVisibility` bayrağı.  
  
 İçin geçerli: `Button`, `Combo`, `Menu`  
  
 DynamicVisibility  
 Komut görünürlüğünü QueryStatus yöntemi veya bağlam dahil GUID kullanarak değiştirilebilir `VisibilityConstraints` bölümü.  
  
 Araç çubukları değil, menüler görünür komutları için geçerlidir. Üst düzey araç çubuğu öğeleri devre dışı ancak OLECMDF_INVISIBLE bayrağı QueryStatus yönteminden döndürüldüğünde, gizli değil.  
  
 Menüde, bu bayrak, üyelerine gizli olduğunda, otomatik olarak gizleneceğini de gösterir. En üst düzey menü Bu davranış zaten yüklü olduğu için alt menüler Bu bayrak genellikle atanır.  
  
 İle birleştirilmelidir `DefaultInvisible` bayrağı.  
  
 İçin geçerli: `Button`, `Combo`, `Menu`  
  
 NoShowOnMenuController  
 Bu bayrak sahip bir komut bir menü denetleyicisinde konumlandırılır, komut aşağı açılan listede görünmez.  
  
 Geçerlilik süresi: `Button`  
  
 Komut bayrakları hakkında daha fazla bilgi için bkz: [komutu bayrağı öğesi](../../extensibility/command-flag-element.md) belgeleri.  
  
##### <a name="general-requirements"></a>Genel gereksinimler  
 Bunu görüntülenir ve etkin kullanılmadan önce komut aşağıdaki dizi test geçmesi gerekir:  
  
-   Komut doğru konumlandırıldı.  
  
-   `DefaultInvisible` Bayrağı ayarlanmamış.  
  
-   Ana menü veya araç görünür olur.  
  
-   Komut bir bağlam giriş nedeniyle görünmez değil [VisibilityConstraints öğesi](../../extensibility/visibilityconstraints-element.md) bölümü.  
  
-   Uygulayan VSPackage kod <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimi görüntüler ve komutunuzu sağlar. Hiçbir arabirimi kodu, bunu engelledik ve üzerinde işlem.  
  
-   Bir kullanıcı komutunuzu tıkladığında kısmında özetlenen yordamı tabi olur [yönlendirme algoritması](../../extensibility/internals/command-routing-algorithm.md).  
  
## <a name="calling-pre-defined-commands"></a>Arama önceden tanımlanmış komutları  
 [UsedCommands öğesi](../../extensibility/usedcommands-element.md) diğer VSPackages veya IDE tarafından sağlanan komutlara erişmek için VSPackages sağlar. Bunu yapmak için Oluştur bir [UsedCommand öğesi](../../extensibility/usedcommand-element.md) GUID ve kullanmak için komut kimliği vardır. Geçerli Visual Studio yapılandırmasının bir parçası olmasa bile bu komutu Visual Studio tarafından yüklenecek sağlar. Daha fazla bilgi için bkz: [UsedCommand öğesi](../../extensibility/usedcommand-element.md).  
  
## <a name="interface-element-appearance"></a>Arabirim öğesi görünümü  
 Seçme ve komut öğeleri konumlandırma hakkında önemli noktalar aşağıdaki gibidir:  
  
-   [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] farklı yerleştirme bağlı olarak görünen birçok kullanıcı Arabirimi öğeleri sunar.  
  
-   Kullanılarak tanımlanmış bir kullanıcı Arabirimi öğesi `DefaultInvisible` bayrağı görüntülenmeyecek IDE içinde ya da kendi VSPackage uygulaması tarafından görüntülenen olmadıkça <xref:EnvDTE.IDTCommandTarget.QueryStatus%2A> yöntemini veya belirli bir kullanıcı Arabirimi bağlamında ilişkili `VisibilityConstraints` bölümü.  
  
-   Başarılı bir şekilde konumlandırılmış bir komutu görüntülenmeyebilir. IDE otomatik olarak gizler veya VSPackage (veya değil) arabirimleri bağlı olarak bazı komutlar görüntüler için uygulanır. Örneğin, bazı VSPackage'nın uygulama yapı arabirimleri nedenler yapı ilgili menü öğelerini otomatik olarak gösterilecek.  
  
-   Uygulama `CommandWellOnly` UI öğesi tanımı bayrağı anlamına gelir komutu yalnızca özelleştirme tarafından eklenebilir.  
  
-   IDE Tasarım görünümü içinde olduğunda yalnızca bir iletişim kutusu görüntülendiğinde komutları yalnızca belirli kullanıcı Arabirimi bağlamlarda, örneğin, kullanılabilir olabilir.  
  
-   IDE içinde görüntülenecek belirli kullanıcı Arabirimi öğeleri neden olmak için bir veya daha fazla arabirimlerini veya biraz kod yazalım.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Menüleri ve Komutlari Genişletme](../../extensibility/extending-menus-and-commands.md)