---
redirect_url: shell/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file
title: "Yalıtılmış Kabuk kullanarak değiştirme. Pkgdef dosya | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio shell, isolated mode, .pkgdef file
ms.assetid: 69e8f78e-bcf1-46cb-8866-7de37d134997
caps.latest.revision: "27"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4716a2c69d64586131c913cde8e3e2d780f9aa69
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="modifying-the-isolated-shell-by-using-the-pkgdef-file"></a>Yalıtılmış Kabuk kullanarak değiştirme. Pkgdef dosyası
.Pkgdef dosya yalıtılmış Kabuk uygulama özelleştirmek için kullanabileceğiniz ayarlar destekler. Bir uygulamanın bir bilgisayarda yüklendiğinde ve uygulama başladığında, Visual Studio Kabuğu tarafından başvurulan oluşturulan değerleri belirtir. Ayarları, ilgili kayıt defteri anahtarlarının dayanarak dosyasında düzenlenir.  
  
> [!WARNING]
>  Visual Studio başladığında VSPackage .vsixmanifest dosyasında bildirilmemiş .pkgdef dosyaları taranır değil olduğunu unutmayın.  
  
 Her bir anahtar tarafından ya da tanımlanır bölümleri .pkgdef dosyayı içeren `[$RootKey$]` veya `[$RootKey$\` *alt*`]`, $RootKey$ uygulama için kök anahtarı olduğu.  
  
 Her bölüm aşağıdaki biçime sahip ad/değer çiftleri içerir: `"` *değer adı*`"=`*değeri*.  
  
 Tırnak içine alınmış bir dize veya dword olarak temsil edilen bir 32 bit tamsayı değerlerdir. Değerleri aşağıdaki sınırlamalar vardır:  
  
-   Tüm dword değerlerini onaltılık biçimde, örneğin: `dword:00000001`.  
  
     Boole değerleri için 1 true ve false 0 temsil eder.  
  
-   Kayıt defteri biçiminde tüm GUID dizeler şunlardır: Örneğin, `"{00000000-0000-0000-0000-000000000000}"`.  
  
-   Formun tüm yerelleştirilebilir kaynak tanımlayıcılar sahip "@*ResourceId*" veya "#*ResourceId*", burada *ResourceId* uygulama kullanıcı Arabirimi paketi kaynak tanımlayıcısı Örneğin, `"@102"`. Uygulama kullanıcı Arabirimi paketi AppLocalizationPackage ayarında başvurulan paketidir.  
  
 Örneğin,  
  
```  
"HideSolutionConcept"=dword:00000001  
"DefaultDebugEngine"="{00000000-0000-0000-0000-000000000000}"  
```  
  
 .Pkgdef dosya yorumlar ekleyebilirsiniz. Tek satırlı yorum iki eğik çizgi ilk iki karakterler içeriyor.  
  
 Değiştirme dizelerini listesi için bkz: [değiştirme dizeleri kullanılır. Pkgdef ve. Pkgundef dosyaları](../extensibility/substitution-strings-used-in-dot-pkgdef-and-dot-pkgundef-files.md).  
  
 Aşağıdaki bölümlerde, yalıtılmış modda Visual Studio Kabuğu davranışını etkileyen belirli kayıt defteri değerleri açıklanmaktadır. Ayrıca, bu dosyada uygulama için ek kayıt defteri değerleri tanımlayabilirsiniz.  
  
> [!NOTE]
>  Bir ayar .pkgdef dosyasında sağlanmazsa, karşılık gelen bir giriş kayıt defterinde yapılır.  
  
## <a name="settings"></a>Ayarlar  
 Aşağıdaki tabloda tanımlanan [altında $RootKey$] değerleri açıklanmaktadır.  
  
|Ad|Tür|Değer|  
|----------|----------|-----------|  
|AddinsAllowed|DWORD|Eklentiler yüklenebilir true; Aksi takdirde false.<br /><br /> Varsayılan değer true olur.|  
|AllowsDroppedFilesOnMainWindow|DWORD|Ana pencerede bırakılan dosyaları kabul edebiliyorsa true; Aksi takdirde false. Ana pencerede bırakılan dosyaları kullanarak açıldığından <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenDocumentViaProject%2A> yöntemi. Bu kullanarak bir belgeyi açmaya eşdeğerdir **açık** komutunu **dosya** uygulama menüsü.<br /><br /> Varsayılan değer true olur.|  
|AppIcon|dize|Program simgesi tam yolu. Bu simge, uygulama adı solundaki başlık çubuğunda görünür.<br /><br /> Varsayılan değer "$RootFolder$\\*solutionName*.ico", burada *solutionName* uygulama çözüm dosyasının adıdır.|  
|AppLocalizationPackage|dize|Uygulama için kullanıcı Arabirimi uydu derleme içeren VSPackage GUID. Bu VSPackage .vsct dosyasının derlenmiş bir sürümünü içerir ve diğer yerelleştirilmiş dizeleri içerebilir. Özellik kümeleri ve menü komut gruplarını etkin veya UI proje .vsct dosyasında ayarlarını değiştirerek devre dışı.<br /><br /> Varsayılan değer: "{*vsUiPackageGuid*}", burada *vsUiPackageGuid* uygulama kullanıcı Arabirimi paketi atanan GUID.|  
|AppName|dize|Uygulamanın adı. Ad uygulama penceresinin başlık çubuğunda görünür.<br /><br /> Varsayılan değer uygulama çözüm dosyasının adıdır.|  
|CommandLineLogo|dize|Konsol penceresinde uygulamayı çalıştırdığınızda başlık metni. Bu ayar yalnızca komut satırı derleme işlemlerini destekleyen uygulamaları etkiler.<br /><br /> Varsayılan değer "*ŞirketAdı**solutionName* sürüm 1.0.", burada *ŞirketAdı* Windows yüklendiğinde sağlanan şirket ve adı*solutionName* uygulama çözüm dosyasının adıdır.|  
|DefaultDebugEngine|dize|Varsayılan GUID hata ayıklama için uygulamayı kullanmak için altyapısı.<br /><br /> Not: Uygulamanın bir varsayılan hata ayıklama altyapısı belirtmiyor boş bir GUID (sıfır) gösterir. Bu hata ayıklama altyapısı kullanmak üzere seçmek hata ayıklayıcı sağlar.<br /><br /> "{00000000-0000-0000-0000-000000000000}" varsayılan değerdir.|  
|DefaultHomePage|dize|İç Web tarayıcısı penceresi için varsayılan giriş sayfası URL'si.<br /><br /> Varsa **giriş sayfası** seçenek, uygulama içinde kullanılabilir ve bu ayar seçeneği varsayılan durumunu da etkiler. Daha fazla bilgi için bkz: [Web tarayıcısı, ortam, Seçenekler iletişim kutusu](../ide/reference/web-browser-environment-options-dialog-box.md).<br /><br /> Varsayılan değer Windows yüklendiğinde sağlanan şirket URL'dir.|  
|DefaultProjectsLocation|dize|Varsayılan projeleri klasörün tam yolu. Örneğin,<br /><br /> `"DefaultProjectsLocation"="$MyDocuments$\MyVSShellStub\Projects"`<br /><br /> Varsa **Visual Studio projeleri konumu** seçenek, uygulama içinde kullanılabilir ve bu ayar seçeneği varsayılan durumunu da etkiler. Daha fazla bilgi için bkz: [NIB: Genel, projeler ve çözümler, Seçenekler iletişim kutusu](http://msdn.microsoft.com/en-us/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca).<br /><br /> Varsayılan değer "$MyDocuments$\\*solutionName*", burada *solutionName* uygulama çözüm dosyasının adıdır.|  
|DefaultSearchPage|dize|İç Web tarayıcı penceresini varsayılan arama sayfası URL'si.<br /><br /> Varsa **arama sayfası** seçenek, uygulama içinde kullanılabilir ve bu ayar seçeneği varsayılan durumunu da etkiler. Daha fazla bilgi için bkz: [Web tarayıcısı, ortam, Seçenekler iletişim kutusu](../ide/reference/web-browser-environment-options-dialog-box.md).<br /><br /> Varsayılan değer "http://search.live.com" dir.|  
|DefaultUserFilesFolderRoot|dize|Geçerli kullanıcının göre kullanıcı klasörün adını Belgelerim klasörünü kullanıcının.<br /><br /> Varsayılan değer uygulama çözüm dosyasının adıdır.|  
|DisableOutputWindow|DWORD|Yalıtılmış Kabuk çıktı penceresi devre dışı olarak düşünmelisiniz olup olmadığını gösterir.<br /><br /> Bu değer ayarlanırsa true, Visual Studio çözümü yapı yöneticisi çıktı görüntülemez **çıkış** penceresini açın ve gizler **yapı başladığında Göster çıktı penceresi** onay kutusuna  **Projeler ve çözümler** kategorisinde **seçenekleri** iletişim kutusu.<br /><br /> Varsayılan değer false'tur.|  
|HideMiscellaneousFilesByDefault|DWORD|Gizle true **çeşitli dosyalar** klasörü varsayılan olarak **Çözüm Gezgini**; Aksi takdirde false.<br /><br /> Varsa **Çözüm Gezgini'nde Göster çeşitli dosyalar** seçenek, uygulama içinde kullanılabilir ve bu ayar seçeneği varsayılan durumunu da etkiler. Daha fazla bilgi için bkz: [belgeler, ortam, Seçenekler iletişim kutusu](../ide/reference/documents-environment-options-dialog-box.md).<br /><br /> Varsayılan değer false'tur.|  
|HideSolutionConcept|DWORD|Tüm projeleri olarak tek başına projeleri oluşturmak ve varsayılan olarak çözüm ve çözüm ile ilgili komutları tek başına projeleri için gizlemek için true; Aksi takdirde false.<br /><br /> Varsa **çözüm her zaman göster** seçenek, uygulama içinde kullanılabilir ve bu ayar seçeneği varsayılan durumunu da etkiler. Daha fazla bilgi için bkz: [NIB: Genel, projeler ve çözümler, Seçenekler iletişim kutusu](http://msdn.microsoft.com/en-us/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca).<br /><br /> Varsayılan değer false'tur.|  
|NewProjDlgInstalledTemplatesHdr|dize|Visual Studio nstalled şablonları üstbilgisinde adını **şablonları** listesinde **yeni proje** iletişim kutusu. Bu, bir dize veya uygulama kullanıcı Arabirimi paketinden yüklenen yerelleştirilebilir kaynak tanımlayıcısı değil.<br /><br /> Varsayılan değer "*solutionName* yüklenmiş şablonlar", burada *solutionName* uygulama çözüm dosyasının adıdır.|  
|NewProjDlgSlnTreeNodeTitle|dize|İçin ad **Visual Studio çözümleri** düğümünde **proje türleri** içinde ağaç **yeni proje** iletişim kutusu. Bu, bir dize veya uygulama kullanıcı Arabirimi paketinden yüklenen yerelleştirilebilir kaynak tanımlayıcısı değil.<br /><br /> Varsayılan değer "*solutionName* yüklenmiş şablonlar", burada *solutionName* uygulama çözüm dosyasının adıdır.|  
|SolutionFileCreatorIdentifier|dize|Uygulama tanımlayıcısı uygulama tarafından üretilen çözüm dosyalarını ikinci satır olarak görünür. Bu satır dosyayı oluşturan uygulamayı gösterir. Kurala göre bu değer adı uygulama ve uygulamanın sürüm numarasını içerir. Örneğin,<br /><br /> `"SolutionFileCreatorIdentifier"="MyVSShellStub Solution File, Format Version 10.00"`<br /><br /> Visual Studio çözüm dosyasını açmak için varsayılan programı olan VSLauncher.exe program bu ikinci satır, çözüm dosyasını açmak Visual Studio sürümünü belirlemek için kullanır. Uygulamanın ilişkili çözüm dosyalarını işlemek için kendi Başlatıcısı gerektirir. Başlatıcı bu ikinci satır çözüm dosyasında çözümü açmak için uygulama hangi sürümünü belirlemek için de kullanabilirsiniz.<br /><br /> Not: Visual Studio VSLauncher.exe programın bir yalıtılmış Kabuk uygulama tarafından oluşturulan .sln dosyaları işlemez.<br /><br /> Varsayılan değer "*solutionName* çözüm dosya biçimi sürümü 10,00", burada *solutionName* uygulama çözüm dosyasının adıdır.|  
|SolutionFileExt|dize|Uygulama için çözüm dosya adı uzantısı. Benzersiz dosya adı uzantısı (not.sln) seçmenizi öneririz.<br /><br /> Varsayılan değer "*solutionName*_sln", burada *solutionName* uygulama çözüm dosyasının adıdır.|  
|SplashScreenBitmap|dize|Uygulama için giriş ekranı bit eşlem dosyasının tam yolu.<br /><br /> Varsayılan değer "$RootFolder$\Splash.bmp" dir.|  
|ThisVersionDTECLSID|dize|Uygulama için Otomasyon nesne sınıfı tanımlayıcısı (CLSID).<br /><br /> Uygulama Otomasyon nesnesi uygular ve Visual Studio Kabuğu otomasyon modeli uygulama en üst düzey nesnesidir <xref:EnvDTE._DTE?displayProperty=fullName> arabirimi.<br /><br /> Uygulama Otomasyon nesnesi altındaki HKEY_CLASSES_ROOT\CLSID kayıt defteri anahtarının doğru şekilde kaydedildiğini sonra kullanabileceğiniz [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance) işlevi doğrudan uygulama örneği oluşturun.<br /><br /> Visual Studio Kabuğu bu CLSID ACTIVEOBJECT_WEAK bayrağını kullanarak uygulama Otomasyon nesnesi çalışan nesne tablosunda'içinde (ROT) kaydetmek için kullanır. Bu kullanmanıza olanak sağlayan [GetActiveObject](http://msdn.microsoft.com/en-us/a276e30c-6a7f-4cde-9639-21a9f5170b62)uygulamanın çalışan bir örneği için bir işaretçi almaya işlevi. Uygulama Otomasyon nesnesinin bir ProgID tanımlarsanız, ayrıca, ardından Visual Studio Kabuğu'nu da her uygulama örneği ROT öğesi ad formun kullanarak kaydeder *ProgID*:*işlem kimliği* , burada *ProgID* ProgID: uygulama Otomasyon nesnesi ve *ProcessId* uygulama örneğini işlem tanımlayıcısıdır. Bir bilinen ad olarak oluşturursanız, örneğin, aşağıdaki gibidir:<br /><br /> `CreateItemMoniker(L"!",`  *instanceString*`, &instanceMoniker)`<br /><br /> Burada `instanceString` olan *ProgID*:*ProcessId* dize. sonra da kullanabileceğinizi `instanceMoniker` örneğini almak için ROT GetObject işlevi ile.<br /><br /> ThisVersionDTECLSID ayarı atlanırsa, uygulama Bileşen Nesne Modeli (COM) aracılığıyla gösterilmez. Bu durumda, uygulamanın bir örneği çağırarak oluşturulamıyor [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance) işlev ve ROT kaydedilemez.<br /><br /> Her bir VSPackage sürümü farklı bir CLSID olması gerekir.<br /><br /> Visual Studio uygulama Otomasyon nesnesi için üretilen GUID varsayılan değerdir.|  
|ThisVersionSolutionCLSID|dize|Uygulama için çözüm nesnesinin CLSID.<br /><br /> Çözüm Otomasyon nesnesi geçerli açık çözümü örneğindeki uygular ve uygulama hakkında bilgi içeren <xref:EnvDTE._Solution?displayProperty=fullName> arabirimi.<br /><br /> Çözüm Otomasyon nesnesi altındaki HKEY_CLASSES_ROOT\CLSID kayıt defteri anahtarının doğru şekilde kaydedildiğini sonra kullanabileceğiniz [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance) doğrudan uygulama için bir çözüm nesnesi oluşturmak için işlevi.<br /><br /> Visual Studio Kabuğu bu CLSID ACTIVEOBJECT_WEAK bayrağını kullanarak ROT çözüm Otomasyon nesnesi kaydetmek için kullanır.<br /><br /> Bu ayar atlanırsa, sonra çözüm sınıf Bileşen Nesne Modeli (COM) ile kayıtlı değil ve çağırarak bir çözüm nesnesi oluşturulamıyor [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance) işlev ve içinde kaydedilemez ROT.<br /><br /> Visual Studio uygulama çözüm nesne için oluşturulmuş bir GUID varsayılan değerdir.|  
|UserFilesSubFolderName|dize|Uygulama kullanıcı dosyaları ve alt klasörleri oluşturur kullanıcının Belgelerim klasörü altında alt adı.<br /><br /> Varsayılan değer uygulama çözüm dosyasının adıdır.|  
|UserOptsFileExt|dize|Uygulama için çözüm kullanıcı seçenekleri dosyaları uzantısı.<br /><br /> Varsayılan değer uygulama çözüm dosyasının adıdır.|  
  
## <a name="binding-path-settings"></a>Yol ayarlarını bağlama  
 [$RootKey$ \BindingPaths\\{00000000-0000-0000-0000-000000000000}] anahtarı için derlemeleri Kabuk denetler dizinleri listesini içerir. Bu dizinleri, uygulama için özel derlemeler için kabuk yoklamaları dizinleri listesine eklenir.  
  
 Varsayılan olarak, hiçbir bağlama yolu girişler .pkgdef dosyasına eklenir. Ancak, Visual Studio yükleme dizinini aşağıdaki alt dizinlerinin kayıt defterinde uygulama bağlama yolu listesine otomatik olarak eklenir.  
  
-   Common7\IDE\  
  
-   Common7\IDE\\\PrivateAssemblies  
  
-   Common7\IDE\\\PublicAssemblies  
  
 Bir dizin bağlama yolunu eklemek için bir giriş formunun Ekle "*directoryName*"="", burada *directoryName* mutlak bir yol. Örneğin,  
  
```  
[$RootKey$\BindingPaths\{00000000-0000-0000-0000-000000000000}]  
"$RootFolder$\directory1"=""  
"%CommonProgramFiles%\directory2"=""  
```  
  
## <a name="profile-settings"></a>Profil ayarları  
 Aşağıdaki tabloda [$RootKey$ \Profile] altında ilişkili her paket için tanımlanan değerleri açıklanmaktadır.  
  
|Ad|Tür|Değer|  
|----------|----------|-----------|  
|AutoSaveFile|dize|Dizin uygulama otomatik kayıt dosyalarını depolar.<br /><br /> Varsayılan değer "$RootFolder$\Profiles\CurrentSettings.vssettings" dir.|  
  
## <a name="package-satellite-dll-settings"></a>Paket uydu DLL ayarları  
 Altında tanımlanan değerleri aşağıdaki tabloda açıklanmaktadır [$RootKey$ \Packages\\{*vsPackageGuid*} \SatelliteDll] uydu DLL ilişkili her paket için burada *vsPackageGuid* ilişkili paket GUID'dir.  
  
|Ad|Tür|Değer|  
|----------|----------|-----------|  
|Dll|dize|DLL dosya adı.<br /><br /> Varsayılan değer "*solutionName*ui.dll", burada *solutionName* uygulama çözüm dosyasının adıdır.|  
|Yol|dize|DLL uydu içeren dizin.<br /><br /> Varsayılan değer "$PackageFolder$" dir.|  
  
## <a name="package-menu-item-settings"></a>Paket menü öğesi ayarları  
 [$RootKey$ \Menus] kayıt defteri anahtarı, uygulama için kullanıcı Arabirimi kaynak dosyaları tanımlar.  
  
 Menü öğesi değerlerine sahip form "{*vsUiPackageGuid*}"=" *ResourceId*, *versionNumber*", burada *vsUiPackageGuid* GUID'si değil uygulama kullanıcı Arabirimi paketi *ResourceId* kullanıcı Arabirimi öğeleri içeren CTMENU kaynağın kaynak tanımlayıcısıdır ve *versionNumber* CTMENU için sanal sürüm numarasıdır Kaynak. Daha fazla bilgi için bkz: [birlikte çalışabilirliği derleme komut işleyicileri kaydetme](../extensibility/internals/registering-interop-assembly-command-handlers.md).  
  
 Varsayılan olarak, uygulama kullanıcı Arabirimi paketi için .pkgdef dosyasında bir menü öğesi girişi oluşturulur.  
  
 Menü öğeleri sağlayan ve uygulamanın bir parçası olarak dağıtılan her paket için paket için bir menü öğe girişi ekleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yalıtılmış Kabuk özelleştirme](../extensibility/customizing-the-isolated-shell.md)   
 [. Pkgundef dosyaları](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgundef-file.md)