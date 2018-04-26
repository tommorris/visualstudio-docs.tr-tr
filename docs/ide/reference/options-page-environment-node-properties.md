---
title: Seçenekler Sayfası, Ortam Düğümü Özellikleri
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- automation [Visual Studio], controlling Tools Options
- Tools Options settings, Environment node properties
ms.assetid: 26dca41f-91fc-4ca7-9103-3da402baa1d5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2ba201b4518b350a96c4c4057f6945d24ea603f0
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="options-page-environment-node-properties"></a>Seçenekler Sayfası, Ortam Düğümü Özellikleri
Bu belgede sayfaları (veya özellikleri koleksiyonları) açıklanır ile ilişkili **ortam** kategorisi, `DTE.Properties("Environment", <Property Page>)`, **seçenekleri** iletişim kutusu. Her alt bölüm başlığı özellikleri koleksiyonuna erişmek için kullanılan çağrıdır ve her alt tabloda bir koleksiyondaki özellikleri listeler.

## <a name="general"></a>Genel
 `DTE.Properties("Environment", "General")`

|Özellik Öğesi Adı|Değer|Açıklama|
|------------------------|-----------|-----------------|
|ShowStatusBar|Get/Set (Boole)|Durum çubuğu görünür olup olmadığını belirler.|
|WindowMenuContainsNItems|Get/Set (kısa)|Belge pencereleri Windows menüsünün alt kısmında bulunan nasıl belirler.|
|MRUListContainsNItems|Get/Set (kısa)|"En son kullanılan" alt kaç dosyaları görüntülemek belirler.|
|Animasyon|Get/Set (Boole)|Tümleşik geliştirme ortamı (IDE) durum çubuğunda animasyon kullanıp kullanmadığını belirler.|
|AnimationSpeed|Get/Set (kısa)||
|AutoAdjustExperience|Get/Set (Boole)|Görsel deneyimi istemci performansına bağlı olarak otomatik olarak ayarlar.|
|RichClientExperienceOptions|Get/Set (Enum)|Zengin istemci görsel deneyimi değerleriyle etkinleştirir <xref:EnvDTE100.vsRichClientExperienceOptions>.|
|CloseButtonActiveTabOnly|Get/Set (Boole)|Belirler olup olmadığını **Kapat** düğme, yalnızca active sekmesinde gösterilir.|
|AutohidePinActiveTabOnly|Get/Set (Boole)|Belirler olup olmadığını **AutoHide** düğmesi, yalnızca etkin sekme etkiler.|

## <a name="add-inmacros-security"></a>Ekleme/makro güvenlik
 `DTE.Properties("Environment", "AddinMacrosSecurity")`

|Özellik Öğesi Adı|Değer|Açıklama|
|------------------------|-----------|-----------------|
|MacrosEnabled|Get/Set (Boole)|Makroların çalıştırılmasına izin verir.|
|AddinsEnabled|Get/Set (Boole)|Yüklemek eklentiler sağlar.|
|LoadAddinsFromTheWeb|Get/Set (Boole)|Web üzerinde bir URL'den yüklemek eklentiler sağlar.|

## <a name="documents"></a>Belgeler
 `DTE.Properties("Environment", "Documents")`

|Özellik Öğesi Adı|Değer|Açıklama|
|------------------------|-----------|-----------------|
|ReuseSavedActiveDocWindow|Get/Set (Boole)|Geçerli belge kaydedilirse, yeni bir dosyanın açılması geçerli pencereyi yeniden kullanır olup olmadığını belirler. `false` her zaman açık her belge için yeni bir belge penceresi açık anlamına gelir.|
|DetectFileChangesOutsideIDE|Get/Set (Boole)|Ortamında işletim sistemi dosyaları diskte değiştirilmiş IDE bildirdiğinde IDE içinde açılan dosyaları otomatik olarak yükler olup olmadığını belirler.|
|AutoloadExternalChanges|Get/Set (Boole)|Açık belgeyi değil değiştirilirse belgeleri otomatik olarak açmak için dış değişiklikler değiştirilmiş dosyayı yeniden algılanan olup olmadığını belirler. Açık belge değiştirilir ve bu özellik `true`, bu özellik değilmiş gibi IDE ister sonra `false`.|
|InitializeOpenFileFromCurrentDocument|Get/Set (Boole)|Belirler olup olmadığını <xref:EnvDTE.DTEClass.OpenFile%2A> komutu çekirdeğini oluşturur son etkin belgedeki dizin ve dosya adı veya bir dosya açıldığında son yerden.|
|MiscFilesProjectSavesLastNItems|Get/Set (kısa)|Çeşitli dosyalar proje kayıtları kaç dosyaları belirler. Sonuç olarak, ne en son açmış disk çeşitli dosya olarak IDE sonraki kullandığınızda görebilirsiniz.|
|ShowMiscFilesProject|Get/Set (Boole)|Çeşitli dosyalar proje gösterilip gösterilmeyeceğini belirler.|
|CheckForConsisentLineEndings|Get/Set (Boole)|Dosya yükleme tutarlı satır sonları denetler.|
|SaveDocsAsUnicodeWhenDataLoss|Get/Set (Boole)|Veri kod sayfasında kaydedildiğinde belgeleri Unicode olarak kaydeder.|
|DontShowGlobalUndoChangeLossDialog|Get/Set (Boole)|Genel Geri Al düzenlenen diğer dosyaları değiştirecek bir uyarı görüntüler.|
|AllowEditingReadOnlyFiles|Get/Set (Boole)|Salt okunur dosyalar, ancak bir uyarı verir bunları kaydetmek girişimi olduğunda düzenleme olanağı sağlar.|
|DocumentDockPreference|Get/Set (Enum)|<xref:EnvDTE100.vsDocumentDockPreferenceOptions>. Sekmesinde de açık belgeyi eklenecek konumu.|

## <a name="extension-manager"></a>Uzantı Yöneticisi
 `DTE.Properties("Environment", "ExtensionManager")`

|Özellik Öğesi Adı|Değer|Açıklama|
|------------------------|-----------|-----------------|
|EnableAdminExtensions|Get/Set (Boole)|Visual Studio yönetici kimlik bilgileriyle çalıştırdığınızda kullanıcı başına uzantıları yükler. Bu değer değiştikten sonra visual Studio'nun yeniden başlatılması gerekir.|
|EnableOnline|Get/Set (Boole)|Visual Studio Market'te uzantıları erişim sağlar.|
|AutomaticallyCheckForUpdates|Get/Set (Boole)|Otomatik olarak yüklenen uzantıları için güncelleştirmeleri denetler.|

## <a name="find-and-replace"></a>Bulma ve Değiştirme
 `DTE.Properties("Environment", "FindAndReplace")`

|Özellik Öğesi Adı|Değer|Açıklama|
|------------------------|-----------|-----------------|
|ShowWarningMessages|Get/Set (Boole)|Uyarı iletilerini görüntüler.|
|InitializeFromEditor|Get/Set (Boole)|Otomatik olarak doldurur **Aranan** düzenleyicisinden metin kutusu.|
|ShowMessageBoxes|Get/Set (Boole)|Bilgilendirici iletileri görüntüler.|
|HideWindowsAfterMatchFromQuickFindReplace|Get/Set (Boole)|Gizler **bulma ve değiştirme** kullanarak bir eşleşme bulunur sonra pencere **Hızlı Bul'u** veya **hızlı Değiştir**.|

## <a name="import-and-export-settings"></a>İçeri ve dışarı aktarma ayarları
 `DTE.Properties("Environment", "Import and Export Settings")`

|Özellik Öğesi Adı|Değer|Açıklama|
|------------------------|-----------|-----------------|
|TrackTeamSettings|Get/Set (Boole)|TeamSettingsFile tarafından belirtilen dosyada ayarları kullanır.|
|TeamSettingsFile|Get/Set (dize)|Takım ayarları olan dosyanın adı.|
|AutoSaveFile|Get/Set (dize)|Kullanıcı ayarlarını otomatik olarak kaydedildiği dosyanın adı.|

## <a name="international-settings"></a>Uluslararası ayarlar
 `DTE.Properties("Environment", "International")`

|Özellik Öğesi Adı|Değer|Açıklama|
|------------------------|-----------|-----------------|
|Dil|Get/Set (dize)|Visual Studio için geçerli dilin LCID değeri.|

## <a name="keyboard"></a>Klavye
 `DTE.Properties("Environment", "Keyboard")`

|Özellik Öğesi Adı|Değer|Açıklama|
|------------------------|-----------|-----------------|
|Düzen|Get/Set (dize)|Yerleşik bir düzeni içeren bir dize, yüklenen .vsk dosyasının tam yolunu içeren bir dize veya "(hiçbir .vsk dosyası yüklü ise varsayılan)" döndürür.|

## <a name="projects-and-solution"></a>Proje ve çözüm
 `DTE.Properties("Environment", "ProjectsAndSolution")`

|Özellik Öğesi Adı|Değer|Açıklama|
|------------------------|-----------|-----------------|
|OnRunOrPreview|Get/Set (dize)|IDE herşeyi Önizleme veya yerleşik bir proje çalıştırmadan önce kaydeder olup olmadığını belirler.|
|ProjectsLocation|Get/Set (dize)|Varsayılan dizini belirler nerede **Proje Ekle** iletişim kutusunda yeni projeler kaydeder.|
|ShowOutputWindowBeforeBuild|Get/Set (Boole)|Bir yapı görüntüler başlangıç olup olmadığını belirleyen **çıkış** penceresi.|
|ShowTaskListAfterBuild|Get/Set (Boole)|Başarısız oluşturma işlemi görüntülenip görüntülenmeyeceğini belirler **görev listesi** yapı tamamlandığında.|
|TrackFileSelectionInExplorer|Get/Set (Boole)|Geçerli öğeye izleneceğini olup olmadığını belirler **Çözüm Gezgini**.|
|AlwaysShowSolutionNode|Get/Set (Boole)|Çözüm düğümüne görüntülenip görüntülenmeyeceğini belirler.|
|OnlySaveStartupProjectsAndDependencies|Get/Set (Boole)|Kaydetme işlemleri başlangıç projeleri ve bunların bağımlı dosyaları için sınırlı olup olmadığını belirler.|
|ShowAdvancedBuildConfigurations|Get/Set (Boole)|Gelişmiş derleme yapılandırmaları görüntülenip görüntülenmeyeceğini belirler.|
|ConcurrentBuilds|Get/Set (dize)|Oluşabilir paralel olarak proje derlemeleri maksimum sayısını belirler.|
|SaveNewProjects|Get/Set (Boole)|Yeni projeler otomatik olarak oluşturulan sonra kaydedilip kaydedilmeyeceğini belirler.|
|PromptForRenameSymbol|Get/Set (Boole)|Dosyaları yeniden adlandırıldığında simgesel yeniden adlandırmak için görüntülenip görüntülenmeyeceğini belirtir.|
|OnRunWhenErrors|Get/Set (Enum)|Hatalarla tamamlandı derleme zaman çalıştırmada davranışını belirtir.|
|OnRunWhenOutOfDate|Get/Set (Enum)|Bir proje güncel olduğunda çalıştırılmasında davranışını belirtir.|
|ProjectTemplatesLocation|Get/Set (dize)|Kullanıcı proje şablonları içeren dizini.|
|ProjectItemTemplatesLocation|Get/Set (dize)|Kullanıcı öğe şablonları içeren dizini.|
|DefaultBehaviorForStartupProjects|Get/Set (dize)||
|MSBuildOutputVerbosity|Get/Set (dize)|Derleme çıktı için ayrıntı düzeyini belirtir.|

## <a name="startup"></a>Başlangıç
 `DTE.Properties("Environment", "Startup")`

|Özellik Öğesi Adı|Değer|Açıklama|
|------------------------|-----------|-----------------|
|OnStartUp|Get/Set (Enum)|Gelen başlangıçta yapılacak eylem <xref:EnvDTE.vsStartUp>, değerleri 0 ile 5 ile:<br /><br /> -0: giriş sayfasını açın<br />-1: yük en son yüklenen çözümü<br />-2: Göster **Proje Aç** iletişim kutusu<br />-3: Göster **yeni proje** iletişim kutusu<br />-4: Göster boş ortamı<br />-5: başlangıç sayfasını göster|
|StartPageRSSUrl|Get/Set (dize)|RSS, akışı URL'sini başlangıçta kullanılır.|
|StartPageRefreshDownloadedContent|Get/Set (Boole)|Başlangıç sayfası StartPageRefreshInterval içinde belirtilen aralık her geçişini sonra yeniler.|
|StartPageRefreshInterval|Get/Set (kısa)|Başlangıç sayfası yenilemek için dakika cinsinden aralığı.|

## <a name="tasklist"></a>TaskList
 `DTE.Properties("Environment", "TaskList")`

|Özellik Öğesi Adı|Değer|Açıklama|
|------------------------|-----------|-----------------|
|ConfirmTaskDeletion|Get/Set (Boole)|Bir onay kutusu görevlerden silerken görüntülenip görüntülenmeyeceğini belirtir **görev listesi**.|
|WarnOnAddingHiddenItem|Get/Set (Boole)|Bir kullanıcı eklerken uyarı olup olmadığını belirtir gösterilmez görev.|
|DontShowFilePaths|Get/Set (Boole)|Görev listesinde tam dosya yolları gösterilip gösterilmeyeceğini belirler.|
|CommentTokens|SafeArray|SafeArray açıklama belirteci değerleri döndürür. Her alanları sahip `Name` (dize) ve `Priority` (<xref:EnvDTE.vsTaskPriority>, yüksek, Orta veya düşük).|

## <a name="web-browser"></a>Web tarayıcısı
 `DTE.Properties("Environment", "WebBrowser")`

|Özellik Öğesi Adı|Değer|Açıklama|
|------------------------|-----------|-----------------|
|Giriş sayfası|Get/Set (dize)|Giriş sayfası URL'si temsil eder.|
|SearchPage|Get/Set (dize)|Arama sayfası URL'si temsil eder.|
|ViewSourceIn|Get/Set (Enum)|<xref:EnvDTE.vsBrowserViewSource> (Kaynak, tasarım, dış).|
|ViewSourceExternalProgram|Get/Set (dize)|Dış kaynak Görüntüleyicisi'ni yolu.|

## <a name="see-also"></a>Ayrıca Bkz.

- [Seçeneklerini denetleme](http://msdn.microsoft.com/Library/a09ed242-7494-4cde-bbd1-7a8ec617965d)
- [Seçenekler sayfalarında özellik öğelerinin adlarını belirleme](http://msdn.microsoft.com/Library/d450422d-47c7-4eeb-9f9f-3286264bc5aa)
- [Seçenekler Sayfası, Yazı Tipleri ve Renkler Düğümü Özellikleri](../../ide/reference/options-page-fonts-and-colors-node-properties.md)
- [Seçenekler Sayfası, Metin Düzenleyici Düğümü Özellikleri](../../ide/reference/options-page-text-editor-node-properties.md)
- [Ortam Seçenekleri İletişim Kutusu](../../ide/reference/environment-options-dialog-box.md)