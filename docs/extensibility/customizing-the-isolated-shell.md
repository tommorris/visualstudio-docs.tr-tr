---
redirect_url: shell/customizing-the-isolated-shell
title: "Yalıtılmış Kabuk özelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio shell, isolated mode
ms.assetid: e0b7c3ae-210f-4f48-ac49-6a59e6034f5f
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e02d93e966f676e0933b866cc8e74bfdd011231f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="customizing-the-isolated-shell"></a>Yalıtılmış Kabuk özelleştirme
Visual Studio kullanıcı arabirimi farklı yönlerini değiştirme ve komutlar ve özelleştirilmiş uygulamanızda bulunan özellikler kısıtlayarak, Visual Studio yalıtılmış Kabuk uygulamanızı özelleştirebilirsiniz.  
  
## <a name="using-the-applicationpkgdef-file"></a>Application.pkgdef dosyasını kullanma  
 Yalıtılmış Kabuk şablonu çözümü içeren bir *SolutionName*. Aşağıdaki özellikleri değiştirmenize olanak tanır Application.pkgdef dosyası:  
  
##### <a name="the-application-title"></a>Uygulama Başlığı  
 "AppName" satırda değerini değiştirerek uygulama başlık çubuğunda görüntülenen addır uygulama başlığı özelleştirebilirsiniz *SolutionName*. Application.pkgdef dosyası. Daha fazla ayrıntı için bkz: [izlenecek yol: temel bir yalıtılmış Kabuk uygulama oluşturma](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md).  
  
 Şu anda yüklü proje görüntülenecek uygulama başlığı istemiyorsanız "ShowHierarchyRootInTitle" satırda değerini değiştirme *SolutionName*. DWORD: 00000001 Application.pkgdef dosyasından DWORD: 00000000 için.  
  
##### <a name="the-application-icon"></a>Uygulama simgesi  
 Uygulama adı uygulama başlık çubuğunda tarafından görüntülenen simgedir uygulama simgesi özelleştirebilirsiniz. Farklı bir simge simgesi dizinine kopyalayın. İçinde **Çözüm Gezgini**, kaynak dosyaları klasörüne simgesi ekleyin. Ardından VSShellStub.rc dosyasını açın ve yeni simgesine adıyla IDI_STUBPROGRAM değerini değiştirin. Daha fazla ayrıntı için bkz: [izlenecek yol: temel bir yalıtılmış Kabuk uygulama oluşturma](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md).  
  
##### <a name="the-command-line-logo"></a>Komut satırı logosu  
 Uygulama "CommandLineLogo" satırda değerini değiştirerek komut satırından başlatıldığında görüntülenen metin komut satırı logosunu özelleştirebilirsiniz *SolutionName*. Application.pkgdef dosyası. Daha fazla ayrıntı için bkz: [izlenecek yol: temel bir yalıtılmış Kabuk uygulama oluşturma](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)  
  
##### <a name="the-name-of-the-user-files-subfolder"></a>Kullanıcının adını alt dosyaları  
 Uygulamanız için kullanıcı dosyaları "UserFilesSubFolderName" satırda değerini değiştirerek tutar klasörün adını değiştirebilirsiniz *SolutionName*. Application.pkgdef dosyası.  
  
##### <a name="the-title-of-the-solution-tree-node-in-the-new-project-dialog"></a>Yeni Proje iletişim kutusunda çözüm Ağaç düğümünün başlığı  
 Yeni Proje iletişim çözüm düğümünde başlığı "NewProjDlgSlnTreeNodeTitle" satırda değerini değiştirerek özelleştirebileceğiniz *SolutionName*. Application.pkgdef dosyası.  
  
##### <a name="the-installed-templates-header-in-the-new-project-dialog"></a>Yeni Proje iletişim kutusunda yüklenmiş şablonlar üstbilgisi  
 Yeni Proje iletişim kutusu yüklenmiş şablonlar üstbilgisinde "NewProjDlgInstalledTemplatesHdr" satırın değerini değiştirerek değiştirebilirsiniz *SolutionName*. Application.pkgdef dosyası.  
  
##### <a name="whether-or-not-to-hide-miscellaneous-files-by-default"></a>Çeşitli dosyalar varsayılan olarak gizler gerekip gerekmediğini  
 Çeşitli dosyalar varsayılan olarak "HideMiscellaneousFilesByDefault" satırda değerini değiştirerek Gizle gerekip gerekmediğini belirtin *SolutionName*. Application.pkgdef dosyası. Çeşitli dosyalar gizlemek için değer ayarlayın `dword:00000001`ve dosyaları göstermek için değeri `dword:00000000`.  
  
##### <a name="whether-or-not-to-disable-the-output-window"></a>Çıktı penceresi devre dışı gerekip gerekmediğini  
 Uygulamanızı çıkış penceresinde "DisableOutputWindow" satırda değerini değiştirerek devre dışı bırakmak isteyip istemediğinizi belirtebilirsiniz *SolutionName*. Application.pkgdef dosyası. Çıktı penceresi devre dışı bırakmak için değer ayarlayın `dword:00000001`ve Çıktı Penceresi'ne göstermeyi değeri `dword:00000000`.  
  
##### <a name="whether-or-not-to-allow-dropped-files-on-the-main-window"></a>Ana pencerede bırakılan dosyalara izin verilip verilmeyeceğini  
 Ana pencerede, uygulamanızda bırakılan dosyaları "AllowsDroppedFilesOnMainWindow" satırda değerini değiştirerek izin verilip verilmeyeceğini belirtin *SolutionName*. Application.pkgdef dosyası. Bırakılan dosyalara izin vermek için değeri ayarlayın `dword:00000001`ve bırakılan dosyalara izin vermeyecek şekilde değeri `dword:00000000`.  
  
##### <a name="the-default-search-page"></a>Varsayılan arama sayfası  
 Web tarayıcısı penceresi açıldığında "DefaultSearchPage" satırda değerini değiştirerek görüntülenen sayfadır web tarayıcısı sayfasını özelleştirebilirsiniz *SolutionName*. Application.pkgdef dosyası.  
  
##### <a name="the-default-home-page"></a>Varsayılan giriş sayfası  
 Giriş sayfası "DefaultHomePage" satırda değerini değiştirerek özelleştirebileceğiniz *SolutionName*. Application.pkgdef dosyası. Daha fazla ayrıntı için bkz: [izlenecek yol: temel bir yalıtılmış Kabuk uygulama oluşturma](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)  
  
##### <a name="whether-or-not-to-hide-the-solution-concept"></a>Çözüm kavramı Gizle gerekip gerekmediğini  
 "HideSolutionConcept" satırda değerini değiştirerek, uygulamanızın çözümde Gizle gerekip gerekmediğini belirtin *SolutionName*. Application.pkgdef dosyası. Çözüm gizlemek için değer ayarlayın `dword:00000001`ve çözüm göstermek için değeri `dword:00000000`.  
  
##### <a name="the-default-debug-engine"></a>Varsayılan hata ayıklama altyapısı  
 Uygulamanızın kullandığı "DefaultDebugEngine" satırda değerini değiştirerek hata ayıklama altyapısı değiştirebileceğiniz *SolutionName*. Hata ayıklama altyapınız GUID Application.pkgdef dosyası.  
  
##### <a name="the-file-extension-of-the-user-options-file"></a>Kullanıcı seçenekleri dosyanın dosya uzantısını  
 Uygulamanız için kullanıcı dosyaları "UserOptsFileExt" satırda değerini değiştirerek tutar klasörün adını değiştirebilirsiniz *SolutionName*. Application.pkgdef dosyası.  
  
##### <a name="the-solution-file-extension"></a>Çözüm dosya uzantısı  
 "SolutionFileExt" satırda değerini değiştirerek çözüm dosyalarınız için kullanılan uzantısı değiştirebileceğiniz *SolutionName*. Application.pkgdef dosyası.  
  
##### <a name="the-default-user-files-folder-root"></a>Varsayılan kullanıcı dosyaları klasörü kök  
 "UserFilesSubFolderName" satırın değerini değiştirerek, uygulamanız için kullanıcı dosyalarının kök klasörün adını değiştirebilirsiniz *SolutionName*. Application.pkgdef dosyası.  
  
##### <a name="the-solution-file-creator-identifier"></a>Çözüm dosyası creator tanımlayıcısı  
 "SolutionFileCreatorIdentifier" satırda değerini değiştirerek, çözüm dosyaları için kullanılan tanımlayıcı değiştirebileceğiniz *SolutionName*. Application.pkgdef dosyası.  
  
##### <a name="the-default-projects-location"></a>Varsayılan projeleri konumu  
 "DefaultProjectsLocation" satırın değerini değiştirerek varsayılan projeleri konumun adını değiştirebilirsiniz *SolutionName*. Application.pkgdef dosyası.  
  
##### <a name="the-application-localization-package"></a>Uygulama yerelleştirme paketi  
 "AppLocalizationPackage" satırda değerini değiştirerek, uygulamanız için kullanılan yerelleştirme paketini değiştirebilirsiniz *SolutionName*. Application.pkgdef dosyası.  
  
##### <a name="whether-or-not-to-show-the-hierarchy-root-in-the-title"></a>Hiyerarşi kök başlığında gösterilip gösterilmeyeceğini  
 "ShowHierarchyRootInTitle" satırda değerini değiştirerek, uygulamanızda başlık çubuğunda hiyerarşi kök gösterilip gösterilmeyeceğini belirtebilirsiniz *SolutionName*. Application.pkgdef dosyası. Hiyerarşi kök göstermek için değer ayarlayın `dword:00000001`, hiyerarşi kök gizlemek için değer ayarlayın `dword:00000000`.  
  
##### <a name="specifying-a-start-page"></a>Başlangıç sayfası belirtme  
 Özel uygulamanız için bir başlangıç sayfası belirtmek üzere *SolutionName*. Application.pkgdef dosya kümesine "DisableStartPage" değeri `dword:00000000`ve altında `[$RootKey$\StartPage\Default]` URI .xaml dosyasında konumuna ayarlayın:  
  
```  
DisableStartPage=dword:00000000  
[$RootKey$\StartPage\Default]  
"Uri"="$RootFolder$\<name of XAML file>"  
```  
  
 Applicationcommands.vsct dosyasında *SolutionName*UI proje, yorum "No_ShellPkg_startPageCommand" giriş çıkışı:  
  
```  
<!--<Define name="No_ShellPkg_StartPageCommand"/>-->  
```  
  
 .Xaml dosyasında ve ihtiyacınız kadar herhangi grafik dosyalarını eklemelisiniz *SolutionName* projesi. Bu dosyalar için gerçekten kopyalanmalıdır *SolutionName* proje dizinine, bazı diğer dizinden eklenmedi.  
  
 Tüm dosyalar üzerinde ayarlayın **öğesi türü** özelliğine **yalıtılmış Kabuk Dosya** dosyaların kopyalanması sırayla *$RootFolder$* dizin. (Ayarlamak için **öğesi türü** özelliği, dosyaya sağ tıklayın ve seçin **özellikleri**. Bu özellik altında bulunan **yapılandırma özellikleri**, **genel**.)  
  
 Başlangıç sayfalarını özelleştirme hakkında daha fazla bilgi için bkz: [başlangıç sayfasını özelleştirme](../ide/customizing-the-start-page-for-visual-studio.md).  
  
## <a name="using-other-elements-of-the-isolated-shell"></a>Yalıtılmış Kabuk diğer öğeleri kullanma  
 Diğer dosya ve uygulamanızı daha fazla özelleştirmek için yalıtılmış Kabuk çözüm şablona dahil projeleri kullanabilirsiniz.  
  
##### <a name="enabledisable-visual-studio-packages"></a>Visual Studio paketleri etkinleştir/devre dışı bırak  
 *SolutionName*.pkgundef dosya belirli paketleri hariç tutarak, belirli türde bir Visual Studio işlevselliği devre dışı bırakmanıza olanak sağlar. Örneğin, aşağıdaki satırı:  
  
```  
[$RootKey$\Projects\{A2FE74E1-B743-11d0-AE1A-00A0C90FFFC3}\AddItemTemplates\TemplateDirs\{39c9c826-8ef8-4079-8c95-428f5b1c323f}]  
```  
  
 Çeşitli dosyalar proje görüntülenen proje şablonları kümesini kaldırır **yeni proje** iletişim. Daha fazla ayrıntı için bkz: [izlenecek yol: temel bir yalıtılmış Kabuk uygulama oluşturma](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md).  
  
##### <a name="enabledisable-menu-commands"></a>Menü komutlarını etkinleştir/devre dışı bırak  
 *SolutionName*UI.vsct dosyası kılınan listesini yalıtılmış Kabuk kullanılabilir tüm menü komutlarını içerir. Verilen komut devre dışı bırakmak için karşılık gelen satırda açıklamadan çıkarın. Örneğin, pencere/bölünmüş yorum devre dışı bırakmak için açıklamadan çıkarın `<Define name="No_SplitCommand"/>` satır. Daha fazla ayrıntı için bkz: [izlenecek yol: temel bir yalıtılmış Kabuk uygulama oluşturma](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md).  
  
##### <a name="the-bitmap-used-on-the-splash-screen"></a>Karşılama ekranında kullanılan bit eşlem  
 Uygulama başlatıldığında "SplashScreenBitmap" satırda değerini değiştirerek görüntülenen penceresi Karşılama ekranında kullanılan bit eşlem özelleştirebilirsiniz *SolutionName*. Application.pkgdef dosyası. Daha fazla ayrıntı için bkz: [izlenecek yol: temel bir yalıtılmış Kabuk uygulama oluşturma](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md).  
  
##### <a name="the-helpabout-window"></a>Yardım/penceresi hakkında  
 Yalıtılmış Kabuk şablonunda Yardım özelleştirmek için kullanabileceğiniz ayrı bir proje yok/uygulamanız için kutusu hakkında. Daha fazla ayrıntı için bkz: [izlenecek yol: temel bir yalıtılmış Kabuk uygulama oluşturma](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md).