---
title: Menü öğesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, Menus
- Menus element (VSCT XML schema)
ms.assetid: ce0560f3-b4c9-4ab2-a99c-d4e10f37b9e0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5c44ca8a78a331d66d099b8d141c4b66c1144949
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="menu-element"></a>Menü öğesi
Bir menü öğesi tanımlar. Menüleri altı türleri şunlardır: bağlam menüsü, MenuController, MenuControllerLatched, araç ve ToolWindowToolbar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<Menu guid="guidMyCommandSet" id="MyCommand" priority="0x100" type="button">  
  <Parent>... </Parent>  
  <CommandFlag>... </CommandFlag>  
  <Strings>... </Strings>  
</Menu>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|GUID|Gerekli. GUID/kimliği komut tanımlayıcı GUID.|  
|kimlik|Gerekli. GUID/kimliği komut tanımlayıcısı kimliği.|  
|önceliği|İsteğe bağlı. Menüleri grubunda bir menü göreli konumunu belirtir sayısal bir değer.|  
|ToolbarPriorityInBand|İsteğe bağlı. Pencerenin yerleştirildiğinde bir araç çubuğu göreli konumunu içinde bir bant belirtiyor bir sayısal değer.|  
|türü|İsteğe bağlı. Öğenin türüne belirten bir Enum değeri.<br /><br /> Yoksa, varsayılan menü türüdür.<br /><br /> Bağlam<br /> Bir kullanıcı bir pencere tıklattığında görüntülenen bir kısayol menüsü. Bir kısayol menüsü aşağıdaki özelliklere sahiptir:<br /><br /> -Menüden kısayol menüsü olarak görüntülenecek olduğunda üst ve öncelik alanlarını kullanmayın.<br />-Alt menü ve ayrıca bir kısayol menüsü olarak kullanılabilir. Bu durumda, grup kimliği ve öncelik alanlarını dikkate alır.<br />-Olduğundan her zaman kullanılabilir değil.<br /><br /> Yalnızca aşağıdaki koşullar doğru olduğunda bir kısayol menüsü görüntülenir:<br /><br /> -Barındırdığı penceresi görüntülenir.<br />-VSPackage fare işleyici penceresinde sağ tıklatma algılar ve komut işleyen bir yöntem çağırır.<br />-Kısayol menüsünün çağrılarak görüntülenen <xref:Microsoft.VisualStudio.Shell.Interop.IOleComponentUIManager.ShowContextMenu%2A> yöntemi (önerilen yaklaşım) veya <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowContextMenu%2A> yöntemi.<br /><br /> Menü<br /> Aşağı açılır menüden sağlar. Aşağı açılır menüden aşağıdaki özelliklere sahiptir:<br /><br /> -Tanımına üst dikkate alır.<br />-Bir üst grubu veya bir gruba bir CommandPlacement sahip olmalıdır.<br />-Alt menü herhangi bir diğer tür menüde olabilir.<br />-Kendi üst menüsünde görüntülenen her otomatik olarak görüntülenen.<br />-Görüntülenen yapmak için herhangi bir VSPackage kod uyarlamasını gerektirmez.<br /><br /> MenuController<br /> Araç çubuklarında genelde kullanılan bir düğme açılır menü sağlar. MenuController menü aşağıdaki özelliklere sahiptir:<br /><br /> -Üst veya CommandPlacement aracılığıyla başka bir menüde yer gerekir.<br />-Tanımına üst dikkate alır.<br />-Menü herhangi bir tür, kendi üst öğesi olarak sahip olabilir.<br />-Kendi üst menüsünde görüntülenen her otomatik olarak kullanılabilir duruma getirilir.<br />-Görüntülenen menü yapmak için programlama desteği gerektirmez.<br /><br /> Bölünmüş düğme menüsünden komutunu menü düğmesi görüntülenir. Görüntülenen komutu aşağıdaki özelliklere sahiptir:<br /><br /> -Bu komutu hala görüntülenen etkin ve varsa, kullanılan son komutudur.<br />-Bu ilk görüntülenen komuttur.<br /><br /> MenuControllerLatched<br /> Kendisi için bir komut varsayılan seçim kilitli gibi komutu işaretleyerek belirtilebilir düğme açılır menü sağlar.<br /><br /> Mandallanmış komutu menüsünde seçilen, genellikle bir onay işareti görüntüleyerek işaretlenen bir komutudur. Bir komut OLECMDF_LATCHED varsa kilitli olarak işaretlenen bayrak uygulaması üzerindeki kümesinde `QueryStatus` yöntemi <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimi. MenuControllerLatched menü aşağıdaki özelliklere sahiptir:<br /><br /> -Bir üst grubun veya CommandPlacement üzerinden başka bir menüde yer gerekir.<br />-Tanımına üst dikkate alır.<br />-Menü herhangi bir tür, kendi üst öğesi olarak sahip olabilir.<br />-Kendi üst menüsünde görüntülenen her sunulacağını.<br />-Görüntülenen menü yapmak için programlama desteği gerektirmez.<br /><br /> Bölünmüş düğme menüsünden komutunu menü düğmesi görüntülenir. Görüntülenen komutu aşağıdaki özelliklere sahiptir:<br /><br /> -Bu kilitli ilk görüntülenen komutudur.<br />-Bu ilk görüntülenen komuttur.<br /><br /> Araç Çubuğu<br /> Bir araç sağlar. Araç çubuğu aşağıdaki özelliklere sahiptir:<br /><br /> -Tanımına üst yok sayar.<br />-Herhangi bir grubu alt bile CommandPlacement kullanılarak yapılan olamaz.<br />-Her zaman tıklayarak görüntülenebilir **araç çubukları** üzerinde **Görünüm** menüsü.<br />-Kullanarak görüntülenebilen bir [VisibilityItem](../extensibility/visibilityitem-element.md).<br />-Oluşturmak için herhangi bir kod gerektirmez. Araç çubuğu oluşturma konusunda bir örnek için bkz: [araç çubuğu ekleme](../extensibility/adding-a-toolbar.md).<br /><br /> ToolWindowToolbar<br /> Araç çubuğu geliştirme ortamına yalnızca bağlı olarak belirli araç penceresi için bağlı bir araç sağlar.<br /><br /> -Tanımına üst yok sayar.<br />-Herhangi bir grubu alt bile CommandPlacement kullanılarak yapılan olamaz.<br />-Yalnızca araç barındıran araç penceresi görüntülenir ve VSPackage araç çubuğu araç penceresi açıkça ekler. görüntülenir. Araç penceresi araç konak özelliğini elde ederek oluşturulduğunda, bu genellikle yapılır (tarafından temsil edilen <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolWindowToolbarHost> arabirimi) aracı pencere çerçevesi ve ardından arama <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolWindowToolbarHost.AddToolbar%2A> yöntemi.|  
|Koşul|İsteğe bağlı. Bkz: [koşullu öznitelikler](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|Üst|İsteğe bağlı. Menü öğesinin üst öğesi.|  
|CommandFlag|Gerekli. Bkz: [komut bayrağı öğesi](../extensibility/command-flag-element.md). Menü için geçerli CommandFlag değerler aşağıdaki gibidir:<br /><br /> -   **AlwaysCreate**<br />-   **DefaultDocked**<br />-   **DefaultInvisible** -Bu bayrak araç çubukları görüntüsünü etkilemez.<br />-   **DontCache**<br />-   **DynamicVisibility** -Bu bayrak araç çubukları görüntüsünü etkilemez.<br />-   **IconAndText**<br />-   **NoCustomize**<br />-   **NotInTBList**<br />-   **NoToolbarClose**<br />-   **TextChanges**<br />-   **TextIsAnchorCommand**|  
|Dizeler|Gerekli. Bkz: [dizeleri öğesi](../extensibility/strings-element.md). Alt `ButtonText` öğesi tanımlanmış olmalıdır.|  
|Ek Açıklama|İsteğe bağlı bir açıklama.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Menus Öğesi](../extensibility/menus-element.md)|Bir VSPackage uygulayan tüm menüleri tanımlar.|  
  
## <a name="example"></a>Örnek  
  
```  
<Menu guid="cmdGuidWidgetCommands" id="menuIDEditWidget"  
  priority="0x0002" type="Menu">  
  <Parent guid="cmdSetGuidWidgetCommands" id="groupIDFileEdit">  
    <CommandFlag>AlwaysCreate</CommandFlag>  
    <Strings>  
      <ButtonText>Edit Widget</ButtonText>  
    </Strings>  
    </Parent>  
</Menu>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)