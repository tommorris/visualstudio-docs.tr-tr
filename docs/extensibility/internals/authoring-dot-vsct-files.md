---
title: Yazma. Vsct dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, manual authoring
ms.assetid: e9f715dc-12b7-439b-bdf3-f3dc75e62f1c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 65fc62d5685ca7c81b3ebb7f524db3cdbebe72c7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="authoring-vsct-files"></a>Yazma. Vsct dosyaları
Bu belge, menü öğeleri, araç çubukları ve diğer kullanıcı arabirimi (UI) öğeleri Visual Studio tümleşik geliştirme ortamı (IDE) eklemek için bir .vsct dosyasını yazar gösterilmektedir. Visual Studio .vsct dosya zaten sahip olmayan paket (VSPackage) kullanıcı Arabirimi öğeleri eklediğinizde, aşağıdaki adımları kullanın.  
  
 Yeni projeler için seçimlerinizi bağlı olarak gerekli öğeleri menü komutu, bir araç penceresi veya özel bir düzenleyici için zaten bir .vsct dosyası oluşturduğundan, Visual Studio Paketi şablonu kullanmanızı öneririz. VSPackage gereksinimlerini karşılamak için bu .vsct dosyasını değiştirebilirsiniz. Örneklerde .vsct dosya değiştirme hakkında daha fazla bilgi için bkz: [genişletme menüleri ve komutları](../../extensibility/extending-menus-and-commands.md).  
  
## <a name="authoring-the-file"></a>Dosya yazma  
 Bu aşamada .vsct dosya Yazar: dosyaları ve kaynakları için yapısı oluşturmak, kullanıcı Arabirimi öğeleri bildirme, kullanıcı Arabirimi öğeleri IDE'de put ve özelleştirilmiş davranışları ekleyin.  
  
### <a name="file-structure"></a>Dosya yapısı  
 .Vsct dosyasının temel yapısı bir [CommandTable](../../extensibility/commandtable-element.md) içeren kök öğe bir [komutları](../../extensibility/commands-element.md) öğesi ve bir [simgeleri](../../extensibility/symbols-element.md) öğesi.  
  
##### <a name="to-create-the-file-structure"></a>Dosya yapısı oluşturmak için  
  
1.  İçindeki adımları izleyerek bir .vsct dosyayı projenize eklemek [nasıl yapılır: oluşturmak bir. Vsct dosya](../../extensibility/internals/how-to-create-a-dot-vsct-file.md).  
  
2.  İçin gerekli ad alanları Ekle `CommandTable` aşağıdaki örnekte gösterildiği gibi öğesi.  
  
    ```xml  
    <CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable"   
        xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  
    ```  
  
3.  İçinde `CommandTable` öğesi ekleme bir `Commands` tüm özel menüler, araç çubukları, komut gruplar ve komutlar barındırmak için öğesi. Böylece, özel kullanıcı Arabirimi öğeleri yükleyebilir `Commands` öğesi olmalı, `Package` özniteliğini paketinin adını ayarlayın.  
  
     Sonra `Commands` öğesi ekleme bir `Symbols` paketi ve adlarını GUID'lerini tanımlamak ve komut kimlikleri için kullanıcı Arabirimi öğeleri için öğe.  
  
### <a name="including-visual-studio-resources"></a>Visual Studio kaynakları dahil etme  
 Kullanım [Extern](../../extensibility/extern-element.md) Visual Studio komutları ve IDE içinde kullanıcı Arabirimi öğeleri yerleştirmek için gereken menüleri tanımlayın dosyalara erişmek için öğesi. Paketin dışında tanımlanan komutları kullanacaksa, kullanın [UsedCommands](../../extensibility/usedcommands-element.md) Visual Studio hakkında bilgilendirmek için öğesi.  
  
##### <a name="to-include-visual-studio-resources"></a>Visual Studio kaynakları eklemek için  
  
1.  Üstündeki `CommandTable` öğesi, bir tane ekleyin `Extern` öğesi başvurulan ayarlamak ve dış her dosya için `href` özniteliği dosyasının adını. Visual Studio kaynaklara erişmek için aşağıdaki üstbilgi dosyaları başvurusu yapabilir:  
  
    -   Stdidcmd.h, Visual Studio tarafından kullanıma sunulan tüm komutlar için kimlikleri tanımlar.  
  
    -   Vsshlids.h, komut kimlikleri için Visual Studio menüleri içerir.  
  
2.  Paketinizi Visual Studio veya diğer paketleri tarafından tanımlanan herhangi bir komut çağırırsa eklemek bir `UsedCommands` öğeden sonra `Commands` öğesi. Bu öğeyle doldurmak bir [UsedCommand](../../extensibility/usedcommand-element.md) çağırmanız diğer bir deyişle, Paket parçası olmayan her komut öğesi. Ayarlama `guid` ve `id` özniteliklerini `UsedCommand` öğelerine GUID ve ID değerlerin çağrılacak komut. GUID ve Visual Studio kimlikleri komutları bulma hakkında daha fazla bilgi için bkz: [GUID ve Visual Studio komutları kimlikleri](../../extensibility/internals/guids-and-ids-of-visual-studio-commands.md). Diğer paketlerden komutlarını çağıran için GUID ve bu paketleri için .vsct dosyasında tanımlanan komut Kimliğini kullanın.  
  
### <a name="declaring-ui-elements"></a>Kullanıcı Arabirimi öğeleri bildirme  
 Tüm yeni kullanıcı Arabirimi öğeleri bildirme `Symbols` .vsct dosyasının bölümü.  
  
##### <a name="to-declare-ui-elements"></a>Kullanıcı Arabirimi öğeleri bildirmek için  
  
1.  İçinde `Symbols` öğesi, üç eklemek [GuidSymbol](../../extensibility/guidsymbol-element.md) öğeleri. Her `GuidSymbol` öğeye sahip bir `name` özniteliğini ve bir `value` özniteliği. Ayarlama `name` öğesi amacı yansıtması adına, öznitelik. `value` Özniteliği GUID alır. (Üzerinde bir GUID oluşturmak için **Araçları** menüsünde tıklatın **Create GUID**ve ardından **kayıt defteri biçimi**.)  
  
     İlk `GuidSymbol` öğesi paketinizi temsil eder ve genellikle alt öğesi yok. İkinci `GuidSymbol` öğesi temsil eder. komut ayarlamak ve menüleri, grupları ve komutları tanımlayan simgelerin tümünü içerir. Üçüncü `GuidSymbol` öğesi Image store temsil eder ve tüm komutlarınızı simgelerini simgelerini içerir. Simgeleri kullanın hiçbir komut varsa, üçüncü atlayabilirsiniz `GuidSymbol` öğesi.  
  
2.  İçinde `GuidSymbol` , komut kümesini temsil eden Öğe Ekle bir veya daha fazla [IDSymbol](../../extensibility/idsymbol-element.md) öğeleri. Bunların her biri temsil menüsü, araç, Grup veya kullanıcı Arabiriminde eklemekte olduğunuz komutu.  
  
     Her `IDSymbol` öğe, ayarladığınız `name` özniteliği karşılık gelen menü, Grup veya komut başvurmak için kullanın ve ardından adına `value` komut kimliğini temsil edecek bir onaltılık sayı öğesine. Hiçbir iki `IDSymbol` aynı üst öğeye sahip öğeleri aynı değere sahip olabilir.  
  
3.  Herhangi bir kullanıcı Arabirimi öğeleri simgeler gerekiyorsa eklemek bir `IDSymbol` öğesi her simge için `GuidSymbol` Image store temsil eden öğesi.  
  
### <a name="putting-ui-elements-in-the-ide"></a>IDE içinde kullanıcı Arabirimi öğeleri koyma  
 [Menüleri](../../extensibility/menus-element.md) öğesi, [grupları](../../extensibility/groups-element.md) öğesi ve [düğmeleri](../../extensibility/buttons-element.md) öğesi tüm menüleri, grupları ve paketinizdeki tanımlanan komutları için tanımları içerir. Bu menüler, gruplar ve komutlar ya da kullanarak IDE'de put bir [üst](../../extensibility/parent-element.md) kullanarak veya kullanıcı Arabirimi öğesi tanımının bir parçası olan öğenin bir [CommandPlacement](../../extensibility/commandplacement-element.md) olan öğeyi başka bir yerde tanımlanmış.  
  
 Her `Menu`, `Group`, ve `Button` öğeye sahip bir `guid` özniteliğini ve bir `id` özniteliği. Her zaman `guid` adı ile eşleşmesi için öznitelik `GuidSymbol` komutunuzu temsil eden öğesi ve ayarlayın `id` özniteliği adına `IDSymbol` menüsü, Grup veya komuttatemsiledenöğesi`Symbols`bölümü.  
  
##### <a name="to-define-ui-elements"></a>Kullanıcı Arabirimi öğeleri tanımlamak için  
  
1.  Yeni menüler, alt menüler, kısayol menüleri veya araç çubukları tanımlıyorsanız, ekleme bir `Menus` öğesine `Commands` öğesi. Ardından, her menüye oluşturulacak ekleyin bir [menü](../../extensibility/menu-element.md) öğesine `Menus` öğesi.  
  
     Ayarlama `guid` ve `id` özniteliklerini `Menu` öğesi olarak ayarlayın ve ardından `type` özniteliği istediğiniz menü tür. Ayrıca ayarlayabilir `priority` menü göreli konumunu üst grubu oluşturmak için öznitelik.  
  
    > [!NOTE]
    >  `priority` Özniteliği araç çubukları ve bağlam menülerini için geçerli değildir.  
  
2.  Visual Studio IDE içinde tüm komutları menüleri ve araç çubuklarını doğrudan alt komutu grupları tarafından barındırılması gerekir. IDE yeni menüleri ve araç çubuklarını ekliyorsanız, bu yeni komutu Grup içermelidir. Böylece, komutlarınızı görsel olarak gruplandırabilirsiniz varolan menüleri ve araç çubuklarını ayrıca komut grupları ekleyebilirsiniz.  
  
     Yeni komut grupları eklediğinizde, önce oluşturmanız gerekir bir `Groups` öğesi ve ardından ekleyin bir [grup](../../extensibility/group-element.md) öğesi her komut grubu.  
  
     Ayarlama `guid` ve `id` her özniteliklerini `Group` öğesi olarak ayarlayın ve ardından `priority` grubun üst menüsünde göreli konumunu oluşturmak için öznitelik. Daha fazla bilgi için bkz: [, yeniden kullanılabilir grupları düğmeler oluşturma](../../extensibility/creating-reusable-groups-of-buttons.md).  
  
3.  Yeni komutlar IDE ekliyorsanız eklemek bir `Buttons` öğesine `Commands` öğesi. Ardından, her komut için ekleyin bir [düğmesini](../../extensibility/button-element.md) öğesine `Buttons` öğesi.  
  
    1.  Ayarlama `guid` ve `id` her özniteliklerini `Button` öğesi olarak ayarlayın ve ardından `type` özniteliği istediğiniz düğmesi tür. Ayrıca ayarlayabilir `priority` komutu göreli konumunu üst grubu oluşturmak için öznitelik.  
  
        > [!NOTE]
        >  Kullanım `type="button"` standart menü komutları ve araç çubuğu düğmeleri için.  
  
    2.  İçinde `Button` öğesi ekleme bir [dizeleri](../../extensibility/strings-element.md) içeren öğe bir [■ ButtonText](../../extensibility/buttontext-element.md) öğesi ve bir [CommandName](../../extensibility/commandname-element.md) öğesi. `ButtonText` Öğesi menü öğesi veya araç çubuğu düğmesi için araç ipucu için metin etiketi sağlar. `CommandName` Öğesi, komut içinde de kullanmak için komut adı sağlar.  
  
    3.  Komutunuzu bir simge olacaksa, oluşturma bir [simgesi](../../extensibility/icon-element.md) öğesinde `Button` öğesi ve kümesi kendi `guid` ve `id` özniteliklerini `Bitmap` simgesiyle öğesi.  
  
        > [!NOTE]
        >  Araç çubuğu düğmeleri simgeler olması gerekir.  
  
     Daha fazla bilgi için bkz: [MenuCommands Vs. OleMenuCommands](../../extensibility/menucommands-vs-olemenucommands.md).  
  
4.  Komutlardan herhangi birini simgeler gerekiyorsa eklemek bir [bit eşlemler](../../extensibility/bitmaps-element.md) öğesine `Commands` öğesi. Ardından, her bir simgenin ekleyin bir [bit eşlem](../../extensibility/bitmap-element.md) öğesine `Bitmaps` öğesi. Bit eşlem kaynağın konumu belirlediğiniz budur. Daha fazla bilgi için bkz: [menü komutlarını simgeleri ekleme](../../extensibility/adding-icons-to-menu-commands.md).  
  
 Çoğu menüleri, gruplar ve komutlar doğru yerleştirmek için ana öğe yapısı güvenebilirsiniz. Çok büyük komut kümeleri için veya menü, Grup veya komutu birden fazla yerde görünmelidir olduğunda, komut yerleşimi belirttiğiniz öneririz.  
  
##### <a name="to-rely-on-parenting-to-place-ui-elements-in-the-ide"></a>IDE içinde kullanıcı Arabirimi öğeleri yerleştirmek için ana öğe güvenemeyeceklerini  
  
1.  Tipik ana öğe için oluşturma bir `Parent` her öğesinde `Menu`, `Group`, ve `Command` paketinize tanımlanan öğesi.  
  
     Hedefi `Parent` öğesidir menüsü veya menü içerecektir grup, Grup veya komutu.  
  
    1.  Ayarlama `guid` özniteliği adına `GuidSymbol` komut kümesini tanımlayan öğesi. Hedef öğe paketin bir parçası değilse, GUID karşılık gelen .vsct dosyasında tanımlanan bu komut kümesi için kullanın.  
  
    2.  Ayarlama `id` eşleşecek şekilde özniteliği `id` hedef menüsü veya grup özniteliği. Menüleri ve Visual Studio tarafından sunulan grupların listesi için bkz: [GUID ve Visual Studio menüleri kimlikleri](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md) veya [GUID ve kimlikleri, Visual Studio araç çubukları](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md).  
  
 Çok sayıda IDE içinde yerleştirmek için kullanıcı Arabirimi öğeleri varsa veya birden fazla yerde görünmesi gereken öğeler varsa, bunların yerleştirmeleri ile tanımlama [CommandPlacements](../../extensibility/commandplacements-element.md) aşağıdaki adımlarda gösterildiği gibi öğesi.  
  
##### <a name="to-use-command-placement-to-place-ui-elements-in-the-ide"></a>IDE içinde kullanıcı Arabirimi öğeleri yerleştirmek için komut yerleştirme kullanmak için  
  
1.  Sonra `Commands` öğesi ekleme bir `CommandPlacements` öğesi.  
  
2.  İçinde `CommandPlacements` öğesi ekleme bir `CommandPlacement` öğesi her menüsü, Grup veya yerleştirmek için komutu.  
  
     Her `CommandPlacement` öğesi veya `Parent` öğesi, bir IDE konumda bir menü, Grup veya komut yerleştirir. Bir kullanıcı Arabirimi öğesi yalnızca bir üst olabilir ancak birden çok komut yerleşimi sahip olabilir. Bir kullanıcı Arabirimi öğesi birden fazla konumda yerleştirmek için ekleme bir `CommandPlacement` her konum için öğesi.  
  
3.  Ayarlama `guid` ve `id` her özniteliklerini `CommandPlacement` barındırma menüsü veya olduğu gibi grubuna öğe olduğu için bir `Parent` öğesi. Ayrıca ayarlayabilirsiniz `priority` UI öğenin göreli konumunu oluşturmak için öznitelik.  
  
 Ana öğe tarafından yerleştirme ve komut yerleşimi karıştırabilirsiniz. Ancak, çok büyük komut kümeleri için yalnızca komut yerleşimi kullanmanızı öneririz.  
  
### <a name="adding-specialized-behaviors"></a>Özelleştirilmiş davranışları ekleme  
 Kullanabileceğiniz [CommandFlag](../../extensibility/command-flag-element.md) öğeler Örneğin menüleri ve komutları davranışını değiştirmek için kendi Görünüm ve görünürlüğünü değiştirmek için. Bir komut kullanarak görünür olduğunda, aynı zamanda etkileyebilir [VisibilityConstraints](../../extensibility/visibilityconstraints-element.md), veya klavye kısayollarını kullanarak [taşıyan](../../extensibility/keybindings-element.md). Menüler ve komutlar zaten belirli türdeki yerleşik davranışları özelleştirilmiş.  
  
##### <a name="to-add-specialized-behaviors"></a>Özelleştirilmiş davranışları eklemek için  
  
1.  Bir çözümü yüklendiğinde bir kullanıcı Arabirimi öğesi yalnızca bağlamlarda belirli kullanıcı Arabirimi, örneğin, görünür yapmak için görünürlük kısıtlamaları kullanın.  
  
    1.  Sonra `Commands` öğesi ekleme bir `VisibilityConstraints` öğesi.  
  
    2.  Her kullanıcı Arabirimi öğesi sınırlamak ekleme bir [VisibilityItem](../../extensibility/visibilityitem-element.md) öğesi.  
  
    3.  Her `VisibilityItem` öğe, ayarladığınız `guid` ve `id` menü, grubu veya komutu ve ardından öznitelikleri `context` tanımlandığı gibi istediğiniz UI bağlamı için öznitelik <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80> sınıfı. Daha fazla bilgi için bkz: [VisibilityItem öğesi](../../extensibility/visibilityitem-element.md).  
  
2.  Bir kullanıcı Arabirimi öğesi kullanılabilirliğini ve görünürlük kodda ayarlamak için bir veya daha fazla aşağıdaki komut bayrakları kullanın:  
  
    -   DefaultDisabled  
  
    -   DefaultInvisible  
  
    -   DynamicItemStart  
  
    -   DynamicVisibility  
  
    -   NoShowOnMenuController  
  
    -   NotInTBList  
  
     Daha fazla bilgi için bkz: [komutu bayrağı öğesi](../../extensibility/command-flag-element.md).  
  
3.  Nasıl bir öğe görünür veya görünümünü dinamik olarak değiştirmek değiştirmek için bir veya daha fazla aşağıdaki komut bayrakları kullanın:  
  
    -   AlwaysCreate  
  
    -   CommandWellOnly  
  
    -   DefaultDocked  
  
    -   DontCache  
  
    -   DynamicItemStart  
  
    -   FixMenuController  
  
    -   IconAndText  
  
    -   PICT  
  
    -   StretchHorizontally  
  
    -   TextMenuUseButton  
  
    -   TextChanges  
  
    -   TextOnly  
  
     Daha fazla bilgi için bkz: [komutu bayrağı öğesi](../../extensibility/command-flag-element.md).  
  
4.  Komutları aldığında, bir öğenin nasıl tepki verdiğini değiştirmek için bir veya daha fazla aşağıdaki komut bayrakları kullanın:  
  
    -   AllowParams  
  
    -   CaseSensitive  
  
    -   CommandWellOnly  
  
    -   Süzme  
  
    -   NoAutoComplete  
  
    -   NoButtonCustomize  
  
    -   NoKeyCustomize  
  
    -   NoToolbarClose  
  
    -   PostExec  
  
    -   RouteToDocs  
  
    -   TextIsAnchorCommand  
  
     Daha fazla bilgi için bkz: [komutu bayrağı öğesi](../../extensibility/command-flag-element.md).  
  
5.  Menü bağımlı klavye kısayol menü veya menü bir öğe eklemek için bir karakterini ekleyin ('& ') içinde `ButtonText` menüsü veya menü öğesi için öğe. Ana menü açık olduğunda ve işareti izleyen karakterin etkin klavye kısayolu'dir.  
  
6.  Bir komutu menü bağımsız klavye kısayolu eklemek için kullanın [taşıyan](../../extensibility/keybindings-element.md). Daha fazla bilgi için bkz: [KeyBinding öğesi](../../extensibility/keybinding-element.md).  
  
7.  Menü metni yerelleştirme için kullanmak `LocCanonicalName` öğesi. Daha fazla bilgi için bkz: [dizeleri öğesi](../../extensibility/strings-element.md).  
  
 Bazı menü ve düğme türleri özel davranışları içerir. Aşağıdaki tabloda bazı özel menü ve düğme türleri açıklanmaktadır. Diğer türleri için bkz: `types` özniteliği açıklamasında [menü öğesi](../../extensibility/menu-element.md), [Button öğesi](../../extensibility/button-element.md), ve [açılan öğesi](../../extensibility/combo-element.md).  
  
 Birleşik giriş kutusu  
 Birleşik giriş kutusu araç çubuğunda kullanılabilecek açılan listesidir. Birleşik giriş kutuları için kullanıcı Arabirimi eklemek için oluşturma bir [birleşik](../../extensibility/combos-element.md) öğesinde `Commands` öğesi. Daha sonra ekleyin `Combos` öğesi bir `Combo` eklemek her birleşik giriş kutusu öğesi. `Combo` aynı öznitelikleri ve alt öğeleri olarak öğelere sahip `Button` öğeleri ve ayrıca `DefaultWidth` ve `idCommandList` öznitelikleri. `DefaultWidth` Öznitelik piksel cinsinden genişliği ayarlar ve `idCommandList` özniteliği noktaları birleşik giriş kutusunu doldurmak için kullanılan bir komut kimliği. Daha fazla bilgi için bkz: `Combo` öğesi belgeleri.  
  
 MenuController  
 Menü denetleyicisi yanında bir ok olan bir düğme vardır. Okunu listesini açar. UI menü denetleyicisi eklemek için Oluştur bir `Menu` öğesi ve kümesi kendi `type` özniteliğini **MenuController** veya **MenuControllerLatched**istediğiniz davranış bağlı olarak. Menü denetleyicisi doldurmak için üst öğesi olarak ayarlanmış bir `Group` öğesi. Menü denetleyicisi o grubun tüm alt öğeleri, aşağı açılan listede görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletme menüleri ve komutları](../../extensibility/extending-menus-and-commands.md)   
 [Visual Studio komut tablosu (. Vsct) dosyaları](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [VSCT XML Şeması Başvurusu](../../extensibility/vsct-xml-schema-reference.md)