---
title: GUID ve Visual Studio araç çubukları kimliklerini | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- visual studio groups
- toolbars
- visual studio toolbar
- id
- toolgar group
- tool window toolbar
- guid
ms.assetid: c9cacd57-9225-450f-a9ac-cbf3168ea844
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 394e0991d734279879df89422ac23fdd26899eeb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31133998"
---
# <a name="guids-and-ids-of-visual-studio-toolbars"></a>GUID ve Visual Studio araç çubukları kimlikleri
Bu konu Visual Studio tümleşik geliştirme ortamı (IDE) dahil araç çubukları GUID ve ID değerlerini numaralandırır ve grupları içerir. Bu değerler, Visual Studio SDK'sı bir parçası olarak yüklenen .vsct dosyalar içinde tanımlanır. Daha fazla bilgi için bkz: [IDE-Defined komutlar, menüler ve grupları](../../extensibility/internals/ide-defined-commands-menus-and-groups.md).  
  
> [!NOTE]
>  Araç çubukları Visual Studio'ya kullanılabilir çoğunu Visual Studio ve bunların GUID tanımlanmaz ve kimliği değerleri ortak değildir. Bu konu, yalnızca Visual Studio SDK .vsct dosyalarında tanımlanan araç çubukları listeler.  
  
 .Vsct dosyalarında tanımlanan IDE nesneleri ile çalışma hakkında daha fazla bilgi için bkz: [genişletme menüleri ve komutları](../../extensibility/extending-menus-and-commands.md).  
  
 Visual Studio IDE tarafından sağlanan varsayılan araç çubukları GUID kullanmak `guidSHLMainMenu`, aksi takdirde GUID:ID sözdizimi kullanılarak belirtilen yerlerde dışındaki.  
  
## <a name="ide-toolbars"></a>IDE araç çubukları  
 Aşağıdaki araç çubukları, Visual Studio IDE tarafından sağlanır. Araç çubukları üzerinde seçerek görüntülenebilir **araç çubukları** alt **Araçları** menüsü. Araç çubukları aracı Windows bu bölümde dahil edilmez.  
  
 Yalnızca grupları doğrudan araç düzen. Bir grup eklemek için üst GUID ve araç Kimliğini ayarlayın. Bir araç için bir düğme eklemek için üst araç çubuğunda bir gruba ayarlayın.  
  
|Araç Çubuğu|Kimlik|  
|-------------|--------|  
|Standart|IDM_VS_TOOL_STANDARD|  
|Derleme|IDM_VS_TOOL_BUILD|  
|Metin Düzenleyici|IDM_VS_TOOL_TEXTEDITOR|  
|Hata ayıklama|guidVSDebugGroup:IDM_DEBUG_TOOLBAR|  
|Konum hata ayıklama|guidVSDebugGroup:IDM_DEBUG_CONTEXT_TOOLBAR|  
  
### <a name="special-toolbars"></a>Özel araç çubukları  
 Bu araç çubukları Visual Studio IDE tarafından tanımlanan, ancak özel işlevlerini hizmet ve komut ana bilgisayar gruplarıyla değil.  
  
|Araç Çubuğu|Kimlik|  
|-------------|--------|  
|Ekle Komutu|IDM_VS_TOOL_ADDCOMMAND|  
|Tanımlanmamış|IDM_VS_TOOL_UNDEFINED|  
|XML Şeması|IDM_VS_TOOL_SCHEMA|  
|XML verileri|IDM_VS_TOOL_DATA|  
  
## <a name="groups-on-the-ide-toolbars"></a>IDE çubuklarında grupları  
 Standart bir araç için bir düğme eklemek için aşağıdaki gruplardan birinin kendi üst öğesi olarak ayarlayın. Grupları, üst araç göre sıralanır.  
  
### <a name="standard-toolbar-groups"></a>Standart araç grupları  
  
|Ad|Kimlik|  
|----------|--------|  
|Kaydetme/açın|IDG_VS_TOOLSB_SAVEOPEN|  
|Kes/Kopyala|IDG_VS_TOOLSB_CUTCOPY|  
|Geri alma/yineleme|IDG_VS_TOOLSB_UNDOREDO|  
|Çalıştır/yapı|IDG_VS_TOOLSB_RUNBUILD|  
|Ara|IDG_VS_TOOLSB_SEARCH|  
|Windows|IDG_VS_TOOLSB_WINDOWS|  
|Yeni pencereler|IDG_VS_TOOLSB_NEWWINDOWS|  
|Yük/Kaydet|IDG_VS_WINDOWUI_LOADSAVE|  
|Ölçer|IDG_VS_TOOLSB_GAUGE|  
  
### <a name="build-toolbar-groups"></a>Araç çubuğu grupları oluşturma  
  
|Ad|Kimlik|  
|----------|--------|  
|Yapı çubuğu|IDG_VS_BUILDBAR|  
|İptal|IDG_VS_BUILD_CANCEL|  
  
### <a name="text-editor-toolbar-groups"></a>Metin Düzenleyici araç grupları  
  
|Ad|Kimlik|  
|----------|--------|  
|Tamamlama|IDM_VS_TOOL_TEXTEDITOR|  
|Girinti|IDG_VS_EDITTOOLBAR_INDENT|  
|Yorum|IDG_VS_EDITTOOLBAR_COMMENT|  
|Yer işaretleri|IDG_VS_EDITTOOLBAR_TEMPBOOKMARKS|  
  
### <a name="debug-toolbar-groups"></a>Araç çubuğu grupları hata ayıklama  
  
|Ad|Kimlik|  
|----------|--------|  
|Yürütme|IDM_DEBUG_TOOLBAR|  
|Atlama|IDG_DEBUG_TOOLBAR_STEPPING|  
|İzleme|IDG_DEBUG_TOOLBAR_WATCH|  
|Windows|IDG_DEBUG_TOOLBAR_WINDOWS|  
  
### <a name="debug-location-toolbar-groups"></a>Konum araç grupları hata ayıklama  
  
|Ad|Kimlik|  
|----------|--------|  
|Konum hata ayıklama|IDG_DEBUG_CONTEXT_TOOLBAR|  
  
## <a name="tool-window-toolbars"></a>Araç penceresi araç çubukları  
 Araç çubukları görünebilir doğrudan IDE veya araç pencereleri gibi **Çözüm Gezgini**. Araç pencereleri .vsct dosyalarında tanımlı değil çünkü araç penceresi araç çubukları tanımlanmış üst sahip değilsiniz. Bunun yerine, bunlar kodda yerleştirilir. Aşağıdaki tabloda, aracı windows IDE içinde görünür araç çubukları ve içerdikleri komut gruplarını gösterir.  
  
> [!NOTE]
>  Araç çubukları ve grupları kullanın GUID `guidSHLMainMenu`, aksi takdirde GUID:ID sözdizimi kullanılarak belirtilen yerlerde dışındaki. Bir araç için bir GUID belirtilmedikçe, bu araç çubuğundan Düzen grupları için de geçerlidir.  
  
|Araç penceresi|Araç Çubuğu|Gruplar|  
|-----------------|-------------|------------|  
|Çözüm Gezgini|IDM_VS_TOOL_PROJWIN|IDG_VS_PROJ_TOOLBAR1... 5|  
|Server Explorer|guid_SE_MenuGroup:IDM_SE_TOOLBAR_SERVEREXPLORER|IDG_SE_TOOLBAR_REFRESH|  
|Özellikler|IDM_VS_TOOL_PROPERTIES|IDG_VS_PROPERTIES_SORT<br /><br /> IDG_VS_PROPERTIES_PAGES|  
|Sınıf Görünümü|IDM_VS_TOOL_CLASSVIEW|IDG_VS_CLASSVIEW_FOLDERS<br /><br /> IDG_VS_CLASSVIEW_SEARCH<br /><br /> IDG_VS_CLASSVIEW_SETTINGS|  
|Sınıf Görünümü|IDM_VS_TOOL_CLASSVIEW_GO|IDG_VS_CLASSVIEW_SEARCH2|  
|Nesne Tarayıcısı|IDM_VS_TOOL_OBJBROWSER|IDG_VS_OBJBROWSER_SUBSETS<br /><br /> IDG_VS_OBJBROWSER_SEARCH<br /><br /> IDG_VS_OBJBROWSER_ADDREFERENCE<br /><br /> IDG_VS_OBJBROWSER_BROWSERSETTINGS|  
|Nesne Tarayıcısı|IDM_VS_TOOL_OBJECT_BROWSER_GO|IDG_VS_OBJBROWSER_SEARCH2|  
|Çıkış|IDM_VS_TOOL_OUTPUTWINDOW|IDG_VS_OUTPUTWINDOW_SELECT<br /><br /> IDG_VS_OUTPUTWINDOW_GOTO<br /><br /> IDG_VS_OUTPUTWINDOW_NEXTPREV<br /><br /> IDG_VS_OUTPUTWINDOW_CLEAR<br /><br /> IDG_VS_OUTPUTWINDOW_WORDWRAP|  
|Bulma ve Değiştirme|IDM_VS_TOOL_UNIFIEDFIND|IDG_VS_FINDTAB<br /><br /> IDG_VS_REPLACETAB|  
|Sonuçları 1 Bul|IDM_VS_TOOL_FINDRESULTS1|IDG_VS_FINDRESULTS1_GOTO<br /><br /> IDG_VS_FINDRESULTS1_NEXTPREV<br /><br /> IDG_VS_FINDRESULTS1_CLEAR<br /><br /> IDG_VS_FINDRESULTS1_STOPFIND|  
|Sonuçları 2 Bul|IDM_VS_TOOL_FINDRESULTS2|IDG_VS_FINDRESULTS2_GOTO<br /><br /> IDG_VS_FINDRESULTS2_NEXTPREV<br /><br /> IDG_VS_FINDRESULTS2_CLEAR<br /><br /> IDG_VS_FINDRESULTS2_STOPFIND|  
|kod parçacığında|IDM_VS_TOOL_SNIPPETMENUS|IDG_VS_SNIPPET_REPL<br /><br /> IDG_VS_SNIPPET_REF<br /><br /> IDG_VS_SNIPPET_PROP|  
|Yer işaretleri|IDM_VS_TOOL_BOOKMARKWIND|IDG_VS_BWNEWFOLDER<br /><br /> IDG_VS_BWNEXTBM<br /><br /> IDG_VS_BWNEXTBMF<br /><br /> IDG_VS_BWENABLE<br /><br /> IDG_VS_BWDELETE|  
|Görev Listesi|IDM_VS_TOOL_TASKLIST|IDG_VS_TASKLIST_PROVIDERLIST|  
|Kullanıcı görevleri|IDM_VS_TOOL_USERTASKS|IDG_VS_TASKLIST_PROVIDERLIST<br /><br /> IDG_VS_USERTASKS_EDIT|  
|Hata Listesi|IDM_VS_TOOL_ERRORLIST|IDG_VS_ERRORLIST_ERRORGROUP<br /><br /> IDG_VS_ERRORLIST_WARNINGGROUP<br /><br /> IDG_VS_ERRORLIST_MESSAGEGROUP|  
|Tarayıcı çağırın|IDM_VS_TOOL_CALLBROWSER1... 16|IDG_VS_TOOLBAR_CALLBROWSER1_ACTIONS<br /><br /> IDG_VS_TOOLBAR_CALLBROWSER1_TYPE<br /><br /> IDG_VS_TOOLBAR_CALLBROWSER1_CBSETTINGS|  
|Kesme noktaları|guidVSDebugGroup:IDM_BREAKPOINTS_WINDOW_TOOLBAR|IDG_BREAKPOINTS_WINDOW_NEW<br /><br /> IDG_BREAKPOINTS_WINDOW_DELETE<br /><br /> IDG_BREAKPOINTS_WINDOW_ALL<br /><br /> IDG_BREAKPOINTS_WINDOW_VIEW<br /><br /> IDG_BREAKPOINTS_WINDOW_EDIT<br /><br /> IDG_BREAKPOINTS_WINDOW_COLUMNS|  
|Ayrıştırılmış kodu|guidVSDebugGroup:IDM_DISASM_WINDOW_TOOLBAR|IDG_DISASM_WINDOW_TOOLBAR|  
|Bellek 1-4|guidVSDebugGroup:IDM_MEMORY_WINDOW_TOOLBAR1... 4|IDG_MEMORY_EXPRESSION1... 4<br /><br /> IDG_MEMORY_COLUMNS1... 4|  
|İşlemler|guidVSDebugGroup:IDM_ATTACHED_PROCS_TOOLBAR|IDG_ATTACHED_PROCS_EXECCNTRL IDG_ATTACHED_PROCS_STEPPING<br /><br /> IDG_ATTACHED_PROCS_EXECCNTRL2<br /><br /> IDG_ATTACHED_PROCS_ATTACH<br /><br /> IDG_ATTACHED_PROCS_COLUMNS|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Menü denetleyicisi araç çubuğuna ekleme](../../extensibility/adding-a-menu-controller-to-a-toolbar.md)   
 [Araç çubuğu araç penceresine ekleme](../../extensibility/adding-a-toolbar-to-a-tool-window.md)   
 [Visual Studio Menülerinin GUID’leri ve Kimlikleri](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md)