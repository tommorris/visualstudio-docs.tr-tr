---
title: "Komutları kullanılabilir hale getirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- menus [Visual Studio SDK], commands
- best practices, menu and toolbar commands
- toolbars [Visual Studio], best practices
- menu commands, best practices
ms.assetid: 3ffc4312-c6db-4759-a946-a4bb85f4a17a
caps.latest.revision: "35"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0c3a9edc754070c7bb0aabdc76b2d52efd32a453
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="making-commands-available"></a>Komutları kullanılabilir hale getirme
Birden çok VSPackages Visual Studio'ya eklendiğinde, kullanıcı arabirimi (UI) komutları ile overcrowded haline gelir. Bu sorun aşağıdaki gibi azaltmaya yardımcı olmak için paket programlama yapabilirsiniz:  
  
-   Paketi programı yalnızca bir kullanıcı yüklenen böylece gerektiriyor.  
  
-   Tümleşik geliştirme ortamı (IDE) geçerli durumunu bağlamında bunlar yalnızca gerekebilir, kendi komutlar böylece paket program.  
  
## <a name="delayed-loading"></a>Gecikmeli yüklemesi  
 Etkinleştirmek için tipik Gecikmeli yüklemesi böylece kendi komutları kullanıcı Arabiriminde görüntülenir, ancak kullanıcı komutlarından birini tıklatır kadar paket yüklenmez VSPackage tasarlamak için bir yoludur. Bunu .vsct dosyasında gerçekleştirmek için hiçbir komut bayrakları sahip komutları oluşturun.  
  
 Aşağıdaki örnek bir .vsct dosyasından menü komutu tanımını gösterir. Bu, Visual Studio Paketi şablonunu tarafından oluşturulan komuttur zaman **menü komutu** şablondaki seçeneği işaretlidir.  
  
```xml  
<Button guid="guidTopLevelMenuCmdSet" id="cmdidTestCommand" priority="0x0100" type="Button">  
  <Parent guid="guidTopLevelMenuCmdSet" id="MyMenuGroup" />  
  <Icon guid="guidImages" id="bmpPic1" />  
  <Strings>  
    <CommandName>cmdidTestCommand</CommandName>  
    <ButtonText>Test Command</ButtonText>  
  </Strings>  
</Button>  
  
```  
  
 Örnekte, üst grup `MyMenuGroup`, olduğu gibi bir üst düzey menü alt **Araçları** menüsünde komutu bu menüsünde görünmez, ancak komut tıklanana kadar komutu yürütür paketi yüklü değil bir kullanıcı tarafından. Ancak, uygulama için komutu programlama tarafından <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimini, komut içeren menüyü ilk genişletildiğinde yüklenecek paket etkinleştirebilir.  
  
 Gecikmeli yükleme de başlangıç performansını artırabilir dikkat edin.  
  
## <a name="current-context-and-the-visibility-of-commands"></a>Geçerli içerik ve komutları görünürlüğü  
 Görünür mü yoksa gizli VSPackage veri veya şu anda ilgili eylemleri geçerli durumunu bağlı olarak olmasını VSPackage komutları programlama yapabilirsiniz. Uygulaması kullanarak kendi komutları durumunu genellikle ayarlamak VSPackage etkinleştirebilirsiniz <xref:EnvDTE.IDTCommandTarget.QueryStatus%2A> yönteminden <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimi, ancak bu kod yürütebilir önce yüklenecek VSPackage gerektirir. Bunun yerine, paketi yüklemeden komutları görünürlüğünü yönetmek için IDE'yi etkinleştirmenizi öneririz. Bunu .vsct dosyasında yapmak için bir veya daha fazla özel kullanıcı Arabirimi bağlamlarla komutları ilişkilendirin. Bu UI bağlamları olarak bilinen bir GUID tarafından tanımlanan bir *komutu bağlam GUID*.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]bir proje yüklenirken veya yapı için giderek düzenlemesini gibi kullanıcı eylemleri kaynaklanan yapılan değişiklikleri izler. Değişiklikler oldukça IDE görünümünü otomatik olarak değiştirilir. Aşağıdaki tabloda, dört ana bağlamları IDE değiştirmek gösterilmektedir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] izleyiciler.  
  
|İçerik türü|Açıklama|  
|---------------------|-----------------|  
|Etkin proje türü|Çoğu proje türleri için bu `GUID` değerdir proje uygulayan VSPackage GUID ile aynı. Ancak, [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] projeleri kullanmak proje türü `GUID` değeri olarak.|  
|Etkin pencereyi|Genellikle, bu anahtar bağlama geçerli UI bağlamının kuran son etkin belgeyi penceredir. Ancak, iç Web tarayıcısı benzer bir anahtar bağlama tablo içeren bir araç penceresi de olabilir. HTML düzenleyicisi gibi çoklu sekmeli belge pencereleri için her sekme farklı komut bağlam sahip `GUID`.|  
|Etkin dil hizmeti|Bir metin düzenleyicisinde görüntülenmekte dosyayla ilişkili dil hizmeti.|  
|Etkin araç penceresi|Açık ve odaklanmış bir araç penceresi.|  
  
 Beşinci ana içerik alanı IDE UI durumda. UI bağlamları etkin komut içeriğini tarafından tanımlanan `GUID`şekilde s:  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionBuilding>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_Debugging>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_Dragging>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_FullScreenMode>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_DesignMode>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_NoSolution>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionExists>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_EmptySolution>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionHasSingleProject>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionHasMultipleProjects>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_CodeWindow>  
  
 Bu GUID, etkin veya devre dışı, IDE geçerli durumuna bağlı olarak işaretlenir. Aynı anda birden çok UI bağlamları etkin olabilir.  
  
### <a name="hiding-and-displaying-commands-based-on-context"></a>Bağlama göre komutları görüntüleme ve gizleme  
 Görüntüleme ya da paketi yüklemeden IDE paket komutta gizleme. Bunu yapmak için paket .vsct dosyasında kullanarak tanımla komutu `DefaultDisabled`, `DefaultInvisible`, ve `DynamicVisibility` bayrakları ve ekleyerek bir veya daha fazla komut [VisibilityItem](../../extensibility/visibilityitem-element.md) öğelerine [ VisibilityConstraints](../../extensibility/visibilityconstraints-element.md) bölümü. Belirtilen komut bağlam zaman `GUID` hale etkin komut paket yüklemeden görüntülenir.  
  
### <a name="custom-context-guids"></a>Özel bağlam GUID'leri  
 GUID zaten tanımlanmamış bir uygun komutu bağlamı, etkin veya devre dışı olarak komutlarınızı görünürlüğünü denetlemek için gerekli olması için program ve, VSPackage birinde tanımlayın. Kullanım <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> hizmet için:  
  
-   Bağlam GUID'ler kaydetmek (çağırarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.GetCmdUIContextCookie%2A> yöntemi).  
  
-   Bir içerik durumunu alma `GUID` (çağırarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A> yöntemi).  
  
-   Bağlam kapatma `GUID`s açma ve kapatma (çağırarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.SetCmdUIContext%2A> yöntemi).  
  
    > [!CAUTION]
    >  Diğer VSPackages bunlara bağımlı çünkü, VSPackage her mevcut bağlam GUID durumunu etkilemez emin olun.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek VSPackage komut VSPackage yüklemeden komutu bağlamları tarafından yönetilen bir komut dinamik görünürlüğünü gösterir.  
  
 Komutu etkin ve çözüm bulunduğunda gösterilen şekilde ayarlayın; diğer bir deyişle, her, aşağıdaki komut bağlam GUID'ler biri etkin:  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_EmptySolution>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionHasMultipleProjects>  
  
-   <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionHasSingleProject>  
  
 Örnekte, her komut bayrağı ayrı bir fark [komutu bayrağı](../../extensibility/command-flag-element.md) öğesi.  
  
```  
<Button guid="guidDynamicVisibilityCmdSet" id="cmdidMyCommand"   
        priority="0x0100" type="Button">  
  <Parent guid="guidDynamicVisibilityCmdSet" id="MyMenuGroup" />  
  <Icon guid="guidImages" id="bmpPic1" />  
  <CommandFlag>DefaultDisabled</CommandFlag>  
  <CommandFlag>DefaultInvisible</CommandFlag>  
  <CommandFlag>DynamicVisibility</CommandFlag>  
  <Strings>  
    <CommandName>cmdidMyCommand</CommandName>  
    <ButtonText>My Command name</ButtonText>  
  </Strings>  
</Button>  
  
```  
  
 Ayrıca her UI bağlam ayrı bir verilmelidir bildirimi `VisibilityItem` şekilde öğesi.  
  
```xml  
<VisibilityConstraints>  
  <VisibilityItem guid="guidDynamicVisibilityCmdSet"  
                  id="cmdidMyCommand" context="UICONTEXT_EmptySolution" />  
  <VisibilityItem guid="guidDynamicVisibilityCmdSet"  
                      id="cmdidMyCommand" context="UICONTEXT_SolutionHasSingleProject" />  
  <VisibilityItem guid="guidDynamicVisibilityCmdSet"  
                  id="cmdidMyCommand" context="UICONTEXT_SolutionHasMultipleProjects" />  
</VisibilityConstraints>  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MenuCommands Vs. OleMenuCommands](../../extensibility/menucommands-vs-olemenucommands.md)   
 [Kullanıcı arabirimi öğeleri VSPackages nasıl eklenir](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Komut içinde VSPackages yönlendirme](../../extensibility/internals/command-routing-in-vspackages.md)   
 [Dinamik Olarak Menü Öğeleri Ekleme](../../extensibility/dynamically-adding-menu-items.md)