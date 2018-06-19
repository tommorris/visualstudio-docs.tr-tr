---
title: GUID ve Visual Studio menüleri kimliklerini | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- visual studio menus
- visual studio groups
- id
- existing menus
- guid
- menus
ms.assetid: 84639d86-dd21-4b35-9988-6bb654162488
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 163f7b81295468a69cfb28959f608a21f94a4a99
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134220"
---
# <a name="guids-and-ids-of-visual-studio-menus"></a>GUID ve Visual Studio menü kimlikleri
Bu konuda menüleri ve Visual Studio menü çubuğunda grupları GUID ve ID değerlerini numaralandırır. Bu değerler, Visual Studio SDK'sı bir parçası olarak yüklenen .vsct dosyalar içinde tanımlanır. Daha fazla bilgi için bkz: [IDE-Defined komutlar, menüler ve grupları](../../extensibility/internals/ide-defined-commands-menus-and-groups.md).  
  
 .Vsct dosyalarında tanımlanan tümleşik geliştirme ortamı (IDE) nesneleri ile çalışma hakkında daha fazla bilgi için bkz: [genişletme menüleri ve komutları](../../extensibility/extending-menus-and-commands.md).  
  
 Menüleri ve Visual Studio menü çubuğunda grupları GUID kullanın `guidSHLMainMenu`. Menü çubuğundaki Kimliğine sahip `IDM_VS_TOOL_MAINMENU`.  
  
## <a name="groups-on-the-visual-studio-menu-bar"></a>Visual Studio menü çubuğunda grupları  
 Menü çubuğunda bir menü eklemek için bu gruplardan birinin kendi üst öğesi olarak ayarlayın.  
  
|Grup|Kimlik|  
|-----------|--------|  
|Dosya/düzenleme/görünümü|IDG_VS_MM_FILEEDITVIEW|  
|Yeniden Düzenle|IDG_VS_MM_REFACTORING:|  
|Proje|IDG_VS_MM_PROJECT|  
|Derleme|IDG_VS_MM_BUILDDEBUGRUN|  
|Biçim/araçları|IDG_VS_MM_TOOLSADDINS|  
|Yardım/penceresi/topluluğu|IDG_VS_MM_WINDOWHELP|  
|Eklentileri|IDG_VS_MM_MACROS|  
|FullScreenBar|IDG_VS_MM_FULLSCREENBAR|  
  
## <a name="menus-on-the-visual-studio-menu-bar"></a>Visual Studio menü çubuğunda menüleri  
 Varolan bir Visual Studio menüsünde bir grup eklemek için aşağıdaki menülerden birine kendi üst öğesi olarak ayarlayın. Alt menüler bu listeye dahil edilmez.  
  
|Menü|Kimlik|  
|----------|--------|  
|Dosya|IDM_VS_MENU_FILE|  
|Düzenle|IDM_VS_MENU_EDIT|  
|Görüntüle|IDM_VS_MENU_VIEW|  
|Yeniden Düzenleme (Refactor)|IDM_VS_MENU_REFACTORING|  
|Proje|IDM_VS_MENU_PROJECT|  
|Derleme|IDM_VS_MENU_BUILD|  
|Biçimi|IDM_VS_MENU_FORMAT|  
|Araçlar|IDM_VS_MENU_TOOLS|  
|Pencere|IDM_VS_MENU_WINDOW|  
|Eklentileri|IDM_VS_MENU_ADDINS|  
|Topluluk|IDM_VS_MENU_COMMUNITY|  
|Yardım|IDM_VS_MENU_HELP|  
  
## <a name="groups-on-visual-studio-menus"></a>Visual Studio menü grupları  
 Aşağıdaki listeler Visual Studio menü çubuğunda doğrudan menülerden Düzen grupları göster. Visual Studio menüye komut eklemek için en hızlı yoludur, bu grupların bir üst öğe olarak ayarlamaktır. Alt menüler Düzen grupları bu bölümde görünmez.  
  
### <a name="file-menu-groups"></a>Dosya menü grupları  
  
|Grup|Kimlik|  
|-----------|--------|  
|Yeni/Aç|IDG_VS_FILE_FILE|  
|Ekle|IDG_VS_FILE_ADD|  
|Çözüm|IDG_VS_FILE_SOLUTION|  
|Çeşitli|IDG_VS_FILE_MISC|  
|Kaydet|IDG_VS_FILE_SAVE|  
|Rename|IDG_VS_FILE_RENAME|  
|Tarayıcı|IDG_VS_FILE_BROWSER|  
|Yazdırma|IDG_VS_FILE_PRINT|  
|Son Kullanılanlar|IDG_VS_FILE_MRU|  
|Taşıma|IDG_VS_FILE_MOVE|  
|Çık|IDG_VS_FILE_EXIT|  
  
### <a name="edit-menu-groups"></a>Menü grupları Düzenle  
  
|Grup|Kimlik|  
|-----------|--------|  
|Geri alma/yineleme|IDG_VS_EDIT_UNDOREDO|  
|Kes/kopyala/yapıştır|IDG_VS_EDIT_CUTCOPY|  
|Seçim|IDG_VS_EDIT_SELECT|  
|Git|IDG_VS_EDIT_GOTO|  
|Bul|IDG_VS_EDIT_FIND|  
|Nesneler|IDG_VS_EDIT_OBJECTS|  
|OLE fiiller|IDG_VS_EDIT_OLEVERBS|  
|İyi komutu|IDG_VS_EDIT_COMMANDWELL|  
  
### <a name="refactor-menu-groups"></a>Menü grupları yeniden Düzenle  
  
|Grup|Kimlik|  
|-----------|--------|  
|Ortak|IDG_REFACTORING_COMMON|  
|Gelişmiş|IDG_REFACTORING_ADVANCED|  
  
### <a name="view-menu-groups"></a>Görünüm menü grupları  
  
|Grup|Kimlik|  
|-----------|--------|  
|Form kodu|IDG_VS_VIEW_FORMCODE|  
|Tarayıcı|IDG_VS_VIEW_BROWSER|  
|Görünümler tanımlayın|IDG_VS_VIEW_DEFINEVIEWS|  
|Windows|IDG_VS_VIEW_WINDOWS|  
|Windows mimari|IDG_VS_VIEW_ARCH_WINDOWS|  
|Kuruluş Windows|IDG_VS_VIEW_ORG_WINDOWS|  
|Kod tarayıcı|IDG_VS_VIEW_CODEBROWSENAV_WINDOWS|  
|Geliştirme Windows|IDG_VS_VIEW_DEV_WINDOWS|  
|Araç Çubukları|IDG_VS_VIEW_TOOLBARS|  
|Simgeleri|IDG_VS_VIEW_SYMBOLNAVIGATE|  
|Gidin|IDG_VS_VIEW_NAVIGATE|  
|Küçük gidin|IDG_VS_VIEW_SMALLNAVIGATE|  
|Nesne Tarayıcısı|IDG_VS_VIEW_OBJBRWSR|  
|İyi komutu|IDG_VS_VIEW_COMMANDWELL|  
|Özellik Sayfaları|IDG_VS_VIEW_PROPPAGES|  
|Yenile|IDG_VS_VIEW_REFRESH|  
  
### <a name="project-menu-groups"></a>Proje menü grupları  
  
|Grup|Kimlik|  
|-----------|--------|  
|Çeşitli ekleme|IDG_VS_PROJ_MISCADD|  
|Ekle|IDG_VS_PROJ_ADD|  
|Klasör|IDG_VS_PROJ_FOLDER|  
|Kaldırma/yeniden yükleme|IDG_VS_PROJ_UNLOADRELOAD|  
|Başvuru|IDG_VS_PROJ_REFERENCE|  
|Seçenekler|IDG_VS_PROJ_OPTIONS|  
|Ayarlar|IDG_VS_PROJ_SETTINGS|  
  
### <a name="build-menu-groups"></a>Menü grupları oluşturma  
  
|Grup|Kimlik|  
|-----------|--------|  
|Çözüm|IDG_VS_BUILD_SOLUTION|  
|Seçim|IDG_VS_BUILD_SELECTION|  
|Profil Temelli İyileştirme|IDG_VS_PGO_SELECTION|  
|Çeşitli|IDG_VS_BUILD_MISC|  
|İptal|IDG_VS_BUILD_CANCEL|  
  
### <a name="tools-menu-groups"></a>Araçlar menü grupları  
  
|Grup|Kimlik|  
|-----------|--------|  
|Komut satırı|IDG_VS_TOOLS_CMDLINE|  
|Kod parçacıkları|IDG_VS_TOOLS_SNIPPETS|  
|Nesne alt|IDG_VS_TOOLS_OBJSUBSET|  
|Seçenekler|IDG_VS_TOOLS_OPTIONS|  
|Diğer 2|IDG_VS_TOOLS_OTHER2|  
|Dış Araçlar|IDG_VS_TOOLS_EXT_TOOLS|  
|Dış özelleştirmeleri|IDG_VS_TOOLS_EXT_CUST|  
  
### <a name="window-menu-groups"></a>Pencere menü grupları  
  
|Grup|Kimlik|  
|-----------|--------|  
|Yeni|IDG_VS_WINDOW_NEW|  
|Yerleştirme/Kapat|IDG_VS_DOCKCLOSE|  
|Yerleştirme/Gizle|IDG_VS_DOCKHIDE|  
|Düzenleme|IDG_VS_WINDOW_ARRANGE|  
|Gezinme|IDG_VS_WINDOW_NAVIGATION|  
|List|IDG_VS_WINDOW_LIST|  
  
### <a name="help-menu-groups"></a>Yardım menü grupları  
  
|Grup|Kimlik|  
|-----------|--------|  
|Örnekler|IDG_VS_HELP_SAMPLES|  
|Destek|IDG_VS_HELP_SUPPORT|  
|Hakkında|IDG_VS_HELP_ABOUT|  
  
## <a name="submenus-of-visual-studio-menus"></a>Visual Studio menü alt menüler  
 Aşağıdaki hiyerarşi Visual Studio menü çubuğunda menülerle ilişkili alt menüler gösterir. Yalnızca bir grup kendi üst menü olabileceğinden, her alt bir gruptan bir menüsünde yerine doğrudan menüsünden Düzen gerekir. Menüleri, gruplar ve alt menüler arasındaki ilişki hakkında daha fazla bilgi için bkz: [bir alt menüye ekleme](../../extensibility/adding-a-submenu-to-a-menu.md).  
  
> [!NOTE]
>  Bunlar IDE grupları için adlandırma kuralı aşağıdaki gibi çıkarsanabileceği için Visual Studio menü çubuğunda menü adları bu hiyerarşide ayrı olarak gösterilmez: IDG_VS_*menüsü adı*_*Grupadı*.  
  
|Üst grubun|Alt menü|Alt gruplar|  
|------------------|-------------|------------------|  
|IDG_VS_FILE_FILE|IDM_VS_CSCD_NEW|IDG_VS_FILE_NEW_CASCADE|  
||IDM_VS_CSCD_OPEN|IDG_VS_FILE_OPENP_CASCADE|  
|||IDG_VS_FILE_OPENF_CASCADE|  
|IDG_VS_FILE_ADD|IDM_VS_CSCD_ADD|IDG_VS_FILE_ADD_PROJECT_NEW|  
|||IDG_VS_FILE_ADD_PROJECT_EXI|  
|IDG_VS_FILE_MRU|IDM_VS_CSCD_FILEMRU|IDG_VS_FILE_FMRU_CASCADE|  
||IDM_VS_CSCD_PROJMRU|IDG_VS_FILE_PMRU_CASCADE|  
|IDG_VS_FILE_MOVE|IDM_VS_CSCD_MOVETOPRJ|IDG_VS_FILE_MOVE_CASCADE|  
|||IDG_VS_FILE_MOVE_PICKER|  
|IDG_VS_VIEW_DEV_WINDOWS|IDM_VS_CSCD_FINDRESULTS|IDG_VS_WNDO_FINDRESULTS|  
||IDM_VS_CSCD_WINDOWS|IDG_VS_VIEW_CALLBROWSER|  
|||IDG_VS_WNDO_OTRWNDWS1... 6|  
|||IDG_VS_WNDO_WINDOWS2|  
|IDG_VS_VIEW_TOOLBARS|IDM_VS_CSCD_COMMANDBARS||  
|IDG_VS_EDIT_GOTO|IDM_VS_EDITOR_FIND_MENU||  
|IDG_VS_EDIT_OBJECTS|IDM_VS_CSCD_MNUDES|IDG_VS_MNUDES_INSERT|  
|||IDG_VS_MNUDES_EDITNAMES|  
||IDM_VS_CSCD_OLEVERBS|IDG_VS_EDIT_OLEVERBS|  
|IDG_VS_BUILD_SELECTION|IDM_VS_CSCD_BUILD|IDG_VS_BUILD_CASCADE|  
|||IDG_VS_BUILD_PROJPICKER|  
||IDM_VS_CSCD_REBUILD|IDG_VS_REBUILD_CASCADE|  
|||IDG_VS_REBUILD_PROJPICKER|  
||IDM_VS_CSCD_PROJONLY|IDG_VS_PROJONLY_CASCADE|  
||IDM_VS_CSCD_CLEAN|IDG_VS_CLEAN_CASCADE|  
|||IDG_VS_CLEAN_PROJPICKER|  
||IDM_VS_CSCD_DEPLOY|IDG_VS_DEPLOY_CASCADE|  
|||IDG_VS_DEPLOY_PROJPICKER|  
|IDG_VS_PGO_SELECTION|IDM_VS_CSCD_PGO_BUILD|IDG_VS_PGO_BUILD_CASCADE_BUILD|  
|||IDG_VS_PGO_BUILD_CASCADE_RUN|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [GUID ve Visual Studio araç çubukları kimlikleri](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)   
 [GUID ve Visual Studio komut kimlikleri](../../extensibility/internals/guids-and-ids-of-visual-studio-commands.md)   
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)