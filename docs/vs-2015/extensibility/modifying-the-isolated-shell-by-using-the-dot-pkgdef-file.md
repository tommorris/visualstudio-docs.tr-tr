---
title: Kullanarak yalıtılmış Kabuğu değiştirme. Pkgdef dosya | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Visual Studio shell, isolated mode%2C .pkgdef file
ms.assetid: 69e8f78e-bcf1-46cb-8866-7de37d134997
caps.latest.revision: 28
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f70036f91eb52d85054465e6eea9f82672d851f6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684538"
---
# <a name="modifying-the-isolated-shell-by-using-the-pkgdef-file"></a>Kullanarak yalıtılmış Kabuğu değiştirme. Pkgdef dosyası
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [yalıtılmış Kabuğu kullanarak değiştirme. Pkgdef dosya](https://docs.microsoft.com/visualstudio/extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file).  
  
.Pkgdef dosyası, yalıtılmış Kabuk uygulaması özelleştirmek için kullanabileceğiniz ayarları destekler. Bu, uygulamanın bir bilgisayarda yüklendiğinde ve uygulama başladığında, Visual Studio shell tarafından başvurulan oluşturulan değerleri belirtir. Ayarlar dosyasındaki ilgili kayıt defteri anahtara göre düzenlenir.  
  
> [!WARNING]
>  Visual Studio başladığında VSPackage .vsixmanifest dosyasında bildirilmeyen .pkgdef dosyalar taranmaz olduğunu unutmayın.  
  
 Her bir anahtar tarafından ya da tanımlanmış bölümleri .pkgdef dosyası içeren `[$RootKey$]` veya `[$RootKey$\` *alt*`]`, uygulama için kök anahtarı $RootKey$ olduğu yer.  
  
 Her bölüm, aşağıdaki biçime sahip bir ad/değer çiftleri içerir: `"` *ValueName*`"=`*değer*.  
  
 Tırnak içine alınmış bir dize veya bir dword temsil edilen bir 32 bit tamsayı değerler. Değerleri aşağıdaki sınırlamalara sahiptir:  
  
-   Tüm dword değerlerini onaltılık biçiminde örnek olduğundan `dword:00000001`.  
  
     Boole değerleri 1 true ve false 0 gösterir.  
  
-   Tüm GUID biçimi kayıt defteri gibi dizelerdir `"{00000000-0000-0000-0000-000000000000}"`.  
  
-   Tüm yerelleştirilebilir kaynak tanımlayıcıları forma sahip "@*ResourceId*" veya "#*ResourceId*" burada *ResourceId* uygulama UI paketindeki kaynak tanımlayıcı Örneğin, `"@102"`. Uygulama kullanıcı Arabirimi paketi AppLocalizationPackage ayarında başvurulan paketidir.  
  
 Örneğin,  
  
```  
"HideSolutionConcept"=dword:00000001  
"DefaultDebugEngine"="{00000000-0000-0000-0000-000000000000}"  
```  
  
 .Pkgdef dosyasına yorum ekleyebilirsiniz. Tek satırlı açıklama ilk iki karakter olarak iki eğik çizgi vardır.  
  
 Değiştirme dizelerini listesi için bkz. [değiştirme dizeleri kullanılır. Pkgdef ve. Pkgundef dosyaları](../extensibility/substitution-strings-used-in-dot-pkgdef-and-dot-pkgundef-files.md).  
  
 Aşağıdaki bölümlerde, Visual Studio Kabuğu yalıtılmış modda davranışını etkileyen belirli kayıt defteri değerleri açıklanmaktadır. Ayrıca, bu dosyada uygulama için ek kayıt defteri değerlerini tanımlayabilirsiniz.  
  
> [!NOTE]
>  Ardından bir ayar .pkgdef dosyasında sağlanmazsa, karşılık gelen bir giriş kayıt defterinde yapılır.  
  
## <a name="settings"></a>Ayarlar  
 Aşağıdaki tabloda tanımlanan [altında $RootKey$] değerleri açıklanmaktadır.  
  
|Ad|Tür|Değer|  
|----------|----------|-----------|  
|AddinsAllowed|dword|Eklentilerin yüklü true; Aksi takdirde false.<br /><br /> Varsayılan değer true olur.|  
|AllowsDroppedFilesOnMainWindow|dword|Ana pencereyi bırakılan dosyaları kabul edebiliyorsa true; Aksi takdirde false. Ana pencerede bırakılan dosyaları kullanılarak açıldığından <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenDocumentViaProject%2A> yöntemi. Bu belge kullanarak açma eşdeğerdir **açık** komutunu **dosya** uygulamasında menüsü.<br /><br /> Varsayılan değer true olur.|  
|AppIcon|dize|Program simgesi tam yolu. Bu simge, uygulama adının sol tarafındaki için başlık çubuğunda görünür.<br /><br /> Varsayılan değer "$RootFolder$\\*solutionName*.ico" burada *solutionName* uygulama çözüm dosyasının adı.|  
|AppLocalizationPackage|dize|Uygulamanın UI uydu bütünleştirilmiş kodu içeren bir VSPackage GUİD'si. Bu VSPackage .vsct dosyası, derlenmiş bir sürümünü içerir ve diğer yerelleştirilmiş dizeleri içerebilir. Özellik kümeleri ve menü komut gruplarını etkinleştirilebilir veya devre dışı kullanıcı Arabirimi proje .vsct dosyası ayarlarını değiştirerek.<br /><br /> Varsayılan değer: "{*vsUiPackageGuid*}", burada *vsUiPackageGuid* uygulama UI paketi atanan GUID.|  
|AppName|dize|Uygulamanın adı. Ad, uygulama penceresinin başlık çubuğunda görünür.<br /><br /> Uygulama çözüm dosyasının adı varsayılan değerdir.|  
|CommandLineLogo|dize|Konsol penceresinde uygulamayı çalıştırdığınızda başlık metni. Bu ayar, yalnızca komut satırı derleme işlemleri destekleyen uygulamaları etkiler.<br /><br /> Varsayılan değer "*companyName ** solutionName* sürüm 1.0.", burada *companyName* Windows yüklendiğinde, sağlanan şirket adını ve *solutionName*uygulama çözüm dosyasının adı.|  
|DefaultDebugEngine|dize|GUID varsayılan hata ayıklama altyapısı uygulama için kullanılacak.<br /><br /> Not: Varsayılan hata ayıklama altyapısı uygulama belirtmiyor (sıfır) boş bir GUID belirtir. Bu, hata ayıklama altyapısının kullanılacağını seçmek hata ayıklayıcı sağlar.<br /><br /> Varsayılan değer " {00000000-0000-0000-0000-000000000000}".|  
|DefaultHomePage|dize|İç Web tarayıcısı penceresi varsayılan giriş sayfası URL'si.<br /><br /> Varsa **giriş sayfası** seçenek, uygulamada kullanılabilir ve bu ayar varsayılan durumu seçeneği de etkiler. Daha fazla bilgi için [Web tarayıcısı, ortam, Seçenekler iletişim kutusu](../ide/reference/web-browser-environment-options-dialog-box.md).<br /><br /> Varsayılan değer, Windows yüklendiğinde sağlanan şirketin URL'dir.|  
|DefaultProjectsLocation|dize|Varsayılan proje klasörün tam yolu. Örneğin,<br /><br /> `"DefaultProjectsLocation"="$MyDocuments$\MyVSShellStub\Projects"`<br /><br /> Varsa **Visual Studio projeleri konumu** seçenek, uygulamada kullanılabilir ve bu ayar varsayılan durumu seçeneği de etkiler. Daha fazla bilgi için [NIB: Genel, projeler ve çözümler, Seçenekler iletişim kutusu](http://msdn.microsoft.com/en-us/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca).<br /><br /> Varsayılan değer "$MyDocuments$\\*solutionName*" burada *solutionName* uygulama çözüm dosyasının adı.|  
|DefaultSearchPage|dize|İç Web tarayıcısı penceresi için varsayılan arama sayfasını URL'si.<br /><br /> Varsa **arama sayfası** seçenek, uygulamada kullanılabilir ve bu ayar varsayılan durumu seçeneği de etkiler. Daha fazla bilgi için [Web tarayıcısı, ortam, Seçenekler iletişim kutusu](../ide/reference/web-browser-environment-options-dialog-box.md).<br /><br /> Varsayılan değer " http://search.live.com".|  
|DefaultUserFilesFolderRoot|dize|Belgelerim klasörünü kullanıcı klasörle geçerli kullanıcı adını güçlendirin.<br /><br /> Uygulama çözüm dosyasının adı varsayılan değerdir.|  
|DisableOutputWindow|dword|Yalıtılmış Kabuğu çıkış penceresi devre dışı olarak düşünmelisiniz olup olmadığını gösterir.<br /><br /> Bu değer ayarlanırsa true, Visual Studio çözüm Yapılandırma Yöneticisi çıktısında görüntülemez **çıkış** penceresi ve gizler **derleme başladığında çıkış Göster penceresi** onay kutusuna  **Projeler ve çözümler** kategorisinde **seçenekleri** iletişim kutusu.<br /><br /> Varsayılan değer false'tur.|  
|HideMiscellaneousFilesByDefault|dword|Gizlemek için true **çeşitli dosyalar** klasörü varsayılan olarak **Çözüm Gezgini**; Aksi takdirde false.<br /><br /> Varsa **Çözüm Gezgini'nde Göster çeşitli dosyalar** seçenek, uygulamada kullanılabilir ve bu ayar varsayılan durumu seçeneği de etkiler. Daha fazla bilgi için [belgeler, ortam, Seçenekler iletişim kutusu](../ide/reference/documents-environment-options-dialog-box.md).<br /><br /> Varsayılan değer false'tur.|  
|HideSolutionConcept|dword|Tüm projeler bağımsız olarak projeleri oluşturmak ve çözüm ve çözümü ile ilgili komutları tek başına projeleri için varsayılan olarak gizlemek için true; Aksi takdirde false.<br /><br /> Varsa **çözümü her zaman göster** seçenek, uygulamada kullanılabilir ve bu ayar varsayılan durumu seçeneği de etkiler. Daha fazla bilgi için [NIB: Genel, projeler ve çözümler, Seçenekler iletişim kutusu](http://msdn.microsoft.com/en-us/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca).<br /><br /> Varsayılan değer false'tur.|  
|NewProjDlgInstalledTemplatesHdr|dize|Visual Studio nstalled şablonları üst bilgi adı **şablonları** listesinde **yeni proje** iletişim kutusu. Uygulama kullanıcı Arabirimi paketinden yüklenen bir yerelleştirilebilir kaynak tanımlayıcısı veya bir dize budur.<br /><br /> Varsayılan değer "*solutionName* yüklenmiş şablonlar" burada *solutionName* uygulama çözüm dosyasının adı.|  
|NewProjDlgSlnTreeNodeTitle|dize|Adı **Visual Studio çözümleri** düğümünde **proje türleri** içinde ağaç **yeni proje** iletişim kutusu. Uygulama kullanıcı Arabirimi paketinden yüklenen bir yerelleştirilebilir kaynak tanımlayıcısı veya bir dize budur.<br /><br /> Varsayılan değer "*solutionName* yüklenmiş şablonlar" burada *solutionName* uygulama çözüm dosyasının adı.|  
|SolutionFileCreatorIdentifier|dize|Uygulama tanımlayıcısı uygulama tarafından oluşturulan çözüm dosyalarını ikinci satırı olarak görünür. Bu satır, dosyanın oluşturduğunuz uygulamayı gösterir. Kural olarak, bu değer adı uygulama ve uygulama sürüm numarasını içerir. Örneğin,<br /><br /> `"SolutionFileCreatorIdentifier"="MyVSShellStub Solution File, Format Version 10.00"`<br /><br /> Visual Studio çözüm dosyasını açmak için varsayılan programı olan VSLauncher.exe programın bu ikinci satır, çözüm dosyasını açmak Visual Studio sürümünü belirlemek için kullanır. Uygulama kendi ilişkili çözüm dosyalarını işlemek için kendi Başlatıcısı gerektirir. Başlatıcı bu ikinci satırı çözüm dosyasına çözümü açmak için uygulama sürümünde belirlemek için de kullanabilirsiniz.<br /><br /> Not: Visual Studio VSLauncher.exe programın bir yalıtılmış Kabuk uygulaması tarafından oluşturulan .sln dosyaları işlemez.<br /><br /> Varsayılan değer "*solutionName* çözüm dosyası biçim sürümü boş, 10,00" burada *solutionName* uygulama çözüm dosyasının adı.|  
|SolutionFileExt|dize|Uygulama için çözüm dosya adı uzantısı. Benzersiz bir dosya adı uzantısı (not.sln) seçmenizi öneririz.<br /><br /> Varsayılan değer "*solutionName*_sln" burada *solutionName* uygulama çözüm dosyasının adı.|  
|SplashScreenBitmap|dize|Uygulamanın giriş ekranının bit eşlem dosyasının tam yolu.<br /><br /> "$RootFolder$\Splash.bmp" varsayılan değerdir.|  
|ThisVersionDTECLSID|dize|Uygulama için Otomasyon nesne sınıfı tanımlayıcısı (CLSID).<br /><br /> Uygulamayı Otomasyon nesnesi uygular ve Visual Studio shell otomasyon modeli uygulama en üst düzey nesnedir <xref:EnvDTE._DTE?displayProperty=fullName> arabirimi.<br /><br /> Uygulamayı Otomasyon nesnesi HKEY_CLASSES_ROOT\CLSID kayıt defteri anahtarında doğru şekilde kaydedildiğini sonra kullanabileceğiniz [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6) doğrudan uygulamanın bir örneğini oluşturmak için işlevi.<br /><br /> Visual Studio Kabuğu bu CLSID ACTIVEOBJECT_WEAK bayrağı kullanılarak uygulama Otomasyon nesnesi çalışan nesne tablo'nda (ROT) kaydetmek için kullanır. Bu kullanmanıza olanak tanır [GetActiveObject](http://msdn.microsoft.com/en-us/a276e30c-6a7f-4cde-9639-21a9f5170b62)çalışan bir uygulama örneği için bir işaretçi almak için işlevi. Uygulama Otomasyon nesnesi için bir ProgID tanımlarsanız, ayrıca, ardından Visual Studio Kabuğu ayrıca uygulamanın her örneği içinde ROT'ta bir öğe bilinen adı biçiminde kullanarak kaydeder *ProgID*:*ProcessId* burada *ProgID* ProgID: uygulama Otomasyon nesnesi ve *ProcessId* uygulamanın bu örneği için işlem tanımlayıcısı. Bilinen adı olarak oluşturursanız, örneğin, aşağıdaki gibidir:<br /><br /> `CreateItemMoniker(L"!",`  *instanceString* `, &instanceMoniker)`<br /><br /> Burada `instanceString` olduğu *ProgID*:*ProcessId* dize. sonra da kullanabileceğinizi `instanceMoniker` örneğini almak için ROT GetObject işlevi ile.<br /><br /> ThisVersionDTECLSID ayarı atlanırsa, uygulama Bileşen Nesne Modeli (COM) aracılığıyla gösterilmez. Bu durumda, uygulamanın bir örneğini çağırarak oluşturulamıyor [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6) işlev ve içinde ROT kaydedilemez.<br /><br /> VSPackage'nün her sürümü farklı bir CLSID olması gerekir.<br /><br /> Visual Studio uygulamayı Otomasyon nesnesi için oluşturulan GUID varsayılan değerdir.|  
|ThisVersionSolutionCLSID|dize|Uygulama için çözüm nesnesiyle CLSID değeri.<br /><br /> Çözüm Otomasyon nesnesi uygular ve uygulamanın bir örneğini Aç Geçerli çözümde hakkında bilgi içeren <xref:EnvDTE._Solution?displayProperty=fullName> arabirimi.<br /><br /> Çözüm Otomasyon nesnesi HKEY_CLASSES_ROOT\CLSID kayıt defteri anahtarında doğru şekilde kaydedildiğini sonra kullanabileceğiniz [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6) doğrudan uygulama için bir çözüm nesnesi oluşturmak için işlevi.<br /><br /> Visual Studio Kabuğu bu CLSID ACTIVEOBJECT_WEAK bayrağı kullanılarak çözüm Otomasyon nesnesi içinde ROT kaydetmek için kullanır.<br /><br /> Bu ayar atlanırsa, sonra çözüm sınıfı Bileşen Nesne Modeli (COM) kayıtlı değilse ve bir çözüm nesnesini çağırarak oluşturulamıyor, [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6) işlev ve olarak kaydedilemez ROT.<br /><br /> Visual Studio uygulamasının çözüm nesne için oluşturulan bir GUID varsayılan değerdir.|  
|UserFilesSubFolderName|dize|Uygulama kullanıcı dosyalarını ve alt klasörler oluşturur kullanıcının Belgelerim klasöründeki altındaki alt klasörün adı.<br /><br /> Uygulama çözüm dosyasının adı varsayılan değerdir.|  
|UserOptsFileExt|dize|Uygulama için çözüm kullanıcı seçenekleri dosya uzantısı.<br /><br /> Uygulama çözüm dosyasının adı varsayılan değerdir.|  
  
## <a name="binding-path-settings"></a>Bağlama yolu ayarları  
 [$RootKey$ \BindingPaths\\{00000000-0000-0000-0000-000000000000}] anahtarı derlemeler için kabuk denetleyen dizinler listesini içerir. Bu dizinler, kabuk uygulaması için özel derlemeler için araştırmaları dizinleri listesine eklenir.  
  
 Varsayılan olarak, .pkgdef dosyası için hiçbir bağlama yolu girişler eklenir. Ancak, Visual Studio yükleme dizininde aşağıdaki alt dizinlerinin kayıt defteri uygulama bağlama yolu listesine otomatik olarak eklenir.  
  
-   Common7\IDE\  
  
-   Common7\IDE\\\PrivateAssemblies  
  
-   Common7\IDE\\\PublicAssemblies  
  
 Bağlama yolu bir dizin eklemek için bir giriş formunun Ekle "*directoryName*"="", burada *directoryName* mutlak yoldur. Örneğin,  
  
```  
[$RootKey$\BindingPaths\{00000000-0000-0000-0000-000000000000}]  
"$RootFolder$\directory1"=""  
"%CommonProgramFiles%\directory2"=""  
```  
  
## <a name="profile-settings"></a>Profil ayarları  
 [$RootKey$ \Profile] altında ilişkili her paket için tanımlanan değerleri aşağıdaki tabloda açıklanmaktadır.  
  
|Ad|Tür|Değer|  
|----------|----------|-----------|  
|AutoSaveFile|dize|Uygulama dosyaları otomatik kaydetme depoladığı directory.<br /><br /> "$RootFolder$\Profiles\CurrentSettings.vssettings" varsayılan değerdir.|  
  
## <a name="package-satellite-dll-settings"></a>Paket uydu DLL ayarları  
 Altında tanımlanmış değerleri aşağıdaki tabloda açıklanmıştır [$RootKey$ \Packages\\{*vsPackageGuid*} \SatelliteDll] uydu DLL ilişkili her paket için burada *vsPackageGuid* ilişkili paket GUID'idir.  
  
|Ad|Tür|Değer|  
|----------|----------|-----------|  
|Dll adı|dize|DLL dosyasının adı.<br /><br /> Varsayılan değer "*solutionName*ui.dll" burada *solutionName* uygulama çözüm dosyasının adı.|  
|Yol|dize|Uydu DLL içeren dizin.<br /><br /> Varsayılan değer "$PackageFolder$" dir.|  
  
## <a name="package-menu-item-settings"></a>Paket menü öğesi ayarları  
 Uygulama için kullanıcı Arabirimi kaynak dosyaları [$RootKey$ \Menus] kayıt defteri anahtarı tanımlar.  
  
 Menü öğesi değerli form "{*vsUiPackageGuid*}"=" *ResourceId*, *versionNumber*" burada *vsUiPackageGuid* GUID'idir uygulama kullanıcı Arabirimi paketi *ResourceId* kullanıcı Arabirimi öğeleri içeren CTMENU kaynağın kaynak tanımlayıcısı ve *versionNumber* CTMENU için sanal sürüm numarasıdır Kaynak. Daha fazla bilgi için [birlikte çalışma bütünleştirilmiş kodu komut işleyicilerini kaydetme](../extensibility/internals/registering-interop-assembly-command-handlers.md).  
  
 Varsayılan olarak, bir menü öğesi girişi uygulama UI paketi için .pkgdef dosyası oluşturulur.  
  
 Menü öğelerini sağlayan ve uygulamanın bir parçası olarak dağıtılan her paket için paket için bir menü öğesi girişi ekleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yalıtılmış Kabuğu özelleştirme](../extensibility/customizing-the-isolated-shell.md)   
 [. Pkgundef dosyaları](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgundef-file.md)

