---
title: Proje türü kaydetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], new project registry entries
- registry, new project types
- registration, new project types
ms.assetid: dfc0e231-6b4e-447d-9d64-0e66dea3394a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8e6c91f2c92dd121cd135aef4291c7f7983206ff
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="registering-a-project-type"></a>Proje türü kaydetme
Yeni bir proje türü oluşturduğunuzda, etkinleştirme kayıt defteri girdileri oluşturmalısınız [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] algılar ve bu proje türü ile çalışmak için. Bu kayıt defteri girdileri genellikle bir kayıt defteri (.rgs) komut dosyası kullanarak oluşturun.  
  
 Aşağıdaki örnekte, kayıt defterinden deyimleri varsayılan yollar sağlamak ve veri geçerli olduğunda, her deyim için kayıt defteri komut dosyası girişlerinden içeren bir tablo arkasından. Tablolar komut dosyası girişleri ve deyimler hakkında ek bilgi sağlar.  
  
> [!NOTE]
>  Aşağıdaki kayıt defteri bilgilerini türünün bir örneği ve proje türü kaydetmek için yazma kayıt defteri komutlar girdileri amaçları olması amaçlanmıştır. Gerçek girişlerinizi ve kullanımları, proje türü belirli gereksinimlerine bağlı olarak değişebilir. Geliştirdiğiniz projenin türü çok benzeyen bir bulmak için kullanılabilecek örnekleri gözden geçirmeli ve bu örnek için kayıt defteri komut dosyasını gözden geçirin.  
  
 Aşağıdaki örnek HKEY_CLASSES_ROOT verilebilir.  
  
## <a name="example"></a>Örnek  
  
```  
\.figp  
   @="FigPrjFile"  
   "Content Type"="text/plain"  
\.figp\ShellNew  
   "NullFile"=""  
\FigPrjFile  
   @="Figure Project File"  
\DefaultIcon  
   @="<Visual Studio SDK installation path>\\9.0VSIntegration\\SomeFolder\\FigPkgs\\FigPrj\\Debug\\FigPrj.dll,-206"  
\shell\open  
   @="&Open in Visual Studio"  
\shell\open\command  
   @="devenv.exe \"%1\""  
```  
  
|Ad|Tür|Veri|Açıklama|  
|----------|----------|----------|-----------------|  
|`@`|REG_SZ|`FigPrjFile`|Ad ve açıklama projenin uzantısı .figp sahip dosyalar yazın.|  
|`Content Type`|REG_SZ|`Text/plain`|Proje dosyaları için içerik türü.|  
|`NullFile`|REG_SZ|`Null`||  
|`@`|REG_SZ|`%MODULE%,-206`|Bu tür bir proje için kullanılan varsayılan simge. Proje türü DLL varsayılan konumu için kayıt defterindeki % MODULE % deyimi tamamlandı.|  
|`@`|REG_SZ|`&Open in Visual Studio`|Varsayılan uygulama bu proje türü açılır.|  
|`@`|REG_SZ|`devenv.exe "%1"`|Bu tür bir proje açıldığında çalıştırılacak varsayılan komutu.|  
  
 Aşağıdaki örnek HKEY_LOCAL_MACHINE ' ve kayıt defteri anahtarı [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\99.0Exp\Packages] altında yer alır.  
  
## <a name="example"></a>Örnek  
  
```  
\{ACEF4EB2-57CF-11D2-96F4-000000000000} (The CLSID for the VSPackage)  
   @="FigPrj Project Package"  
   "InprocServer32"="9.0<Visual Studio SDK installation path>\\VSIntegration\\Archive\\FigPkgs\\FigPrj\\                      Debug\\FigPrj.dll"  
   "CompanyName"="Microsoft"  
   "ProductName"="Figure Project Sample"  
   "ProductVersion"="9.0"  
   "MinEdition"="professional"  
   "ID"=dword:00000001  
\{ACEF4EB2-57CF-11D2-96F4-000000000000}\SatelliteDLL  
   "DllName"="FigPrjUI.dll"  
   "Path"="9.0<Visual Studio SDK installation path>\\VSIntegration\\Archive\\FigPkgs\\FigPrj\\Debug\\"  
\{ACEF4EB2-57CF-11D2-96F4-000000000000}\Automation  
   "FigProjects"=""  
\{ACEF4EB2-57CF-11D2-96F4-000000000000}\AutomationEvents  
   "FigProjectsEvents"="Returns the FigProjectsEvents Object"  
   "FigProjectItemsEvents"="Returns the FigProjectItemsEvents Object"  
```  
  
|Ad|Tür|Veri|Açıklama|  
|----------|----------|----------|-----------------|  
|`@` (Varsayılan)|REG_SZ|`FigPrj Project VSPackage`|Bu yerelleştirilebilir adı VSPackage (proje türü) kaydedilmiş.|  
|`InprocServer32`|REG_SZ|`%MODULE%`|Proje türü DLL yolu. IDE bu DLL'yi yükler ve VSPackage CLSID geçirir `DllGetClassObject` almak için <xref:Microsoft.VisualStudio.OLE.Interop.IClassFactory> oluşturmak için <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> nesnesi.|  
|`CompanyName`|REG_SZ|`Microsoft`|Proje türü geliştirilen şirketin adı.|  
|`ProductName`|REG_SZ|`Figure Project Sample`|Proje türü adı.|  
|`ProductVersion`|REG_SZ|`9.0`|Proje türü sürüm numarasını serbest bırakın.|  
|`MinEdition`|REG_SZ|`professional`|Kaydedilmekte VSPackage sürümü.|  
|`ID`|REG_DWORD|`%IDS_PACKAGE_LOAD_KEY%`|Paket VSPackage proje için anahtar yükleyin. Ortamını başlatıldıktan sonra bir projeye yüklendiğinde anahtar doğrulanır.|  
|`DllName`|REG_SZ|`%RESOURCE_DLL%`|Proje türü için yerelleştirilen kaynaklar içeren DLL uydu dosya adı.|  
|`Path`|REG_SZ|`%RESOURCE_PATH%`|Uydu DLL yolu.|  
|`FigProjectsEvents`|REG_SZ|Değer için bildirimine bakın.|Bu Otomasyon olay için döndürülen metin dizesini belirler.|  
|`FigProjectItemsEvents`|REG_SZ|Değer için bildirimine bakın.|Bu Otomasyon olay için döndürülen metin dizesini belirler.|  
  
 Aşağıdaki örneklerde, kayıt defterinde anahtar [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0Exp\Projects] altında yer alır.  
  
## <a name="example"></a>Örnek  
  
```  
\{C061DB26-5833-11D2-96F5-000000000000} (The CLSID for projects of this type)  
   @="FigPrj Project"  
   "DisplayName"="#2"  
   "Package"="{ACEF4EB2-57CF-11D2-96F4-000000000000}"  
   "ProjectTemplatesDir"="C:\\Program Files\\VSIP 9.0\\EnvSDK\\FigPkgs\\                           FigPrj\\FigPrjProjects"  
   "ItemTemplatesDir"="<Visual Studio SDK installation path>\\VSIntegration\\Archive9.0\\FigPkgs\\FigPrj\\                           FigPrjProjectItems"  
   "DisplayProjectFileExtensions"="#3"  
   "PossibleProjectExtensions"="figp"  
   "DefaultProjectExtension"=".figp"  
\{C061DB26-5833-11D2-96F5-000000000000}\Filters\1       (Folder 1 contains settings for Open Files filters.)  
   @="#4"  
   "CommonOpenFilesFilter"=dword:00000000  
   "CommonFindFilesFilter"=dword:00000000  
   "NotAddExistingItemFilter"=dword:00000000  
   "FindInFilesFilter"=dword:00000000  
   "NotOpenFileFilter"=dword:00000000  
   "SortPriority"=dword:000003e8  
\{C061DB26-5833-11D2-96F5-000000000000}\Filters\2  
      (Folder 2 contains settings for Find in Files filters.)  
   @="#5"  
   "CommonOpenFilesFilter"=dword:00000000  
   "CommonFindFilesFilter"=dword:00000000  
   "NotAddExistingItemFilter"=dword:00000001  
   "FindInFilesFilter"=dword:00000001  
   "NotOpenFileFilter"=dword:00000000  
   "SortPriority"=dword:000003e8  
\{C061DB26-5833-11D2-96F5-000000000000}\AddItemTemplates\TemplateDirs\ {ACEF4EB2-57CF-11D2-96F4-000000000000}\1 (Second GUID indicates the registered project type for the Add Items templates.)  
   @="#6"  
   "TemplatesDir"="<Visual Studio SDK installation path>\\VSIntegration\\Archive9.0\\FigPkgs\\FigPrj\\                    FigPrjProjectItems"  
   "SortPriority"=dword:00000064  
```  
  
|Ad|Tür|Veri|Açıklama|  
|----------|----------|----------|-----------------|  
|`@`|REG_SZ|`FigPrj Project`|Bu tür projeleri varsayılan adı.|  
|`DisplayName`|REG_SZ|`#%IDS_PROJECT_TYPE%`|Uydu DLL kaynak Kimliğinin adının altındaki paketlerin kayıtlı.|  
|`Package`|REG_SZ|`%CLSID_Package%`|Sınıf kimliği VSPackage altındaki paketlerin kayıtlı.|  
|`ProjectTemplatesDir`|REG_SZ|`%TEMPLATE_PATH%\FigPrjProjects`|Proje şablonu dosyalarının varsayılan yolu. Bunlar yeni bir proje şablonu tarafından görüntülenen dosyalardır.|  
|`ItemTemplatesDir`|REG_SZ|`%TEMPLATE_PATH% \FigPrjProjectItems`|Proje öğesi şablonu dosyalarının varsayılan yolu. Bunlar Yeni Öğe Ekle şablon tarafından görüntülenen dosyalardır.|  
|`DisplayProjectFileExtensions`|REG_SZ|`#%IDS_DISPLAY_PROJ_FILE_EXT%`|Uygulanacak IDE sağlar **açık** iletişim kutusu.|  
|`PossibleProjectExtensions`|REG_SZ|`figp`|IDE tarafından açılmasını projesi bu proje türü (Proje fabrikada) işlenip işlenmediğini belirlemek için kullanılır. Birden fazla giriş biçimi noktalı virgülle ayrılmış listesidir. Örneğin "vdproj; vdp".|  
|`DefaultProjectExtension`|REG_SZ|`.figp`|IDE tarafından varsayılan dosya adı uzantısı olarak Kaydet işlemi için kullanılır.|  
|`Filter Settings`|REG_DWORD|Çeşitli, ifadeler ve açıklamaları aşağıdaki tablonun bakın.|Bu ayarlar, kullanıcı Arabirimi iletişim kutularında dosyalarını görüntülemek için çeşitli filtreler ayarlamak için kullanılır.|  
|`@`|REG_SZ|`#%IDS_ADDITEM_TEMPLATES_ENTRY%`|Öğe Ekle şablonları için kaynak kimliği.|  
|`TemplatesDir`|REG_SZ|`%TEMPLATE_PATH%\FigPrjProjectItems`|İletişim kutusunda görüntülenen proje öğeleri yolunu **Yeni Öğe Ekle** şablonu.|  
|`SortPriority`|REG_DWORD|`100 (vcprx64)`|Ağaç düğümünde görüntülenen dosyalar, sıralama düzeni belirler **Yeni Öğe Ekle** iletişim kutusu.|  
  
 Önceki kod kesimi filtreleri seçenekleri aşağıdaki tabloda gösterilmektedir.  
  
|Filtre seçeneği|Açıklama|  
|-------------------|-----------------|  
|`CommonFindFilesFilter`|Filtreyi genel filtre biri olduğunu gösterir **dosyalarda Bul** iletişim kutusu. Genel filtreler gibi ortak işaretlenmediği filtreleri önce Filtre listesinde listelenir.|  
|`CommonOpenFilesFilter`|Filtreyi genel filtre biri olduğunu gösterir **Dosya Aç** iletişim kutusu. Genel filtreler gibi ortak işaretlenmediği filtreleri önce Filtre listesinde listelenir.|  
|`FindInFilesFilter`|Filtre filtreleri birini olacağını gösterir **dosyalarda Bul** iletişim kutusuna ve sonra ortak filtreleri listelenir.|  
|`NotOpenFileFilter`|Filtre olarak kullanılmaz olduğunu gösteren **Dosya Aç** iletişim kutusu.|  
|`NotAddExistingItemFilter`|Filtre Ekle kullanılmayacak gösterir **varolan öğeyi** iletişim kutusu.|  
  
 Varsayılan olarak, bir filtre yok ya da birkaçı bayrakları kümesi, filtre kullanılan **varolan öğeyi Ekle** iletişim kutusu ve **açık dosya** ortak filtreleri listelenen sonra iletişim kutusu. Filtre kullanılmaz **dosyalarda Bul** iletişim kutusu.  
  
 Aşağıdaki örneklerde, kayıt defterinde anahtar [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0Exp\Projects] altında yer alır.  
  
## <a name="example"></a>Örnek  
  
```  
{FE3BBBB6-72D5-11d2-9ACE-00C04F79A2A4} (The CLSID for Enterprise Projects)  
\{FE3BBBB6-72D5-11d2-9ACE-00C04F79A2A4}\AddItemTemplates\TemplateDirs\ {ACEF4EB2-57CF-11D2-96F4-000000000000}\1 (CLSID for projects of this type)  
   @="#7"  
   "TemplatesDir"="<Visual Studio SDK installation path>\\VSIntegration\\Archive9.0\\FigPrj\\FigPrjProjects"  
   "SortPriority"=dword:00000029  
   "NewProjectDialogOnly"=dword:00000000  
```  
  
|Ad|Tür|Veri|Açıklama|  
|----------|----------|----------|-----------------|  
|`@`|REG_SZ|`#%IDS_NEWPROJ_ TEMPLATES_ENTRY%`|Yeni proje şablonları için kaynak kimliği.|  
|`TemplatesDir`|REG_SZ|`%TEMPLATE_PATH%\FigPrjProjects`|Varsayılan yolu kayıtlı proje türü projeleri için.|  
|`SortPriority`|REG_DWORD|`41 (x29)`|Sıralama düzeni yeni projeler Sihirbazı iletişim kutusunda görüntülenen projelerinin ayarlar.|  
|`NewProjectDialogOnly`|REG_DWORD|`0`|Bu tür projeleri yalnızca yeni proje iletişim kutusunda görüntülenen 0 gösterir.|  
  
 Aşağıdaki örneklerde, kayıt defterinde anahtar [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0Exp\Projects] altında yer alır.  
  
## <a name="example"></a>Örnek  
  
```  
\{A2FE74E1-B743-11d0-AE1A-00A0C90FFFC3} (CLSID for Miscellaneous Files projects)  
   @="Miscellaneous Files Project"  
\AddItemTemplates\TemplateDirs\{ACEF4EB2-57CF-11D2-96F4-000000000000}\1  
                                 (CLSID for Figures Project projects)  
   @="#6"  
   "TemplatesDir"="<Visual Studio SDK installation path>\\VSIntegration\\Archive9.0\\FigPkgs\\FigPrj\\                    FigPrjProjectItems"  
   "SortPriority"=dword:00000064  
```  
  
|Ad|Tür|Veri|Açıklama|  
|----------|----------|----------|-----------------|  
|`@`|REG_SZ|Yok.|Aşağıdaki girişleri için çeşitli dosyalar projeleri girişleri olup olmadığını belirten varsayılan değer.|  
|`@`|REG_SZ|`#%IDS_ADDITEM_TEMPLATES_ENTRY%`|Yeni öğe ekleme şablon dosyalarını kaynağı kimliği değeri.|  
|`TemplatesDir`|REG_SZ|`%TEMPLATE_PATH%\FigPrjProjectItems`|Varsayılan yolu görüntülenecek öğelerin **Yeni Öğe Ekle** iletişim kutusu.|  
|`SortPriority`|REG_DWORD|`100 (vcprx64)`|Ağaç düğümünde görüntülenmesi için sıralama düzeni oluşturur **Yeni Öğe Ekle** iletişim kutusu.|  
  
 Aşağıdaki örnek, kayıt defterinde anahtar [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0Exp\Menus] altında yer alır.  
  
## <a name="example"></a>Örnek  
  
```  
"{ACEF4EB2-57CF-11D2-96F4-000000000000}"=",1000,1"  
```  
  
 Menü girişi IDE menü bilgilerini almak için kullanılan kaynak işaret eder. Bu veriler menü veritabanına birleştirilmiş, aynı anahtarı kayıt defteri MenusMerged bölümünde eklenir. VSPackage MenusMerged bölümünde herhangi bir şey doğrudan değiştirmemelisiniz. Aşağıdaki tabloda veri alanında üç virgülle-ayrılmış-alanlar vardır. İlk alan bir menü kaynak dosyasının tam yolunu tanımlar:  
  
-   İlk alan atlanırsa, menü kaynak DLL VSPackage GUID ile tanımlanan uydu'ndan yüklenir.  
  
 İkinci alan türü CTMENU menüsü kaynak Kimliğini tanımlar:  
  
-   Kaynak Kimliği belirtilen ve dosya yolu ilk parametresi tarafından sağlanan, menü kaynağı tam dosya yolundan yüklenir.  
  
-   Kaynak kodu sağlanır, ancak dosya yolu değil, menü kaynağı uydu DLL yüklenir.  
  
-   Tam dosya yolunu sağlanır ve kaynak kimliği atlanırsa, yüklenecek dosyayı Teknolojiden dosyası olması beklenir.  
  
 Son alan CTMENU kaynak için sürüm numarasını belirtir. Sürüm numarasını değiştirerek menüsünün yeniden birleştirebilirsiniz.  
  
|Ad|Tür|Veri|Açıklama|  
|----------|----------|----------|-----------------|  
|% CLSID_Package %|REG_SZ|`,1000,1`|Menü bilgilerini almak için kaynak.|  
  
 Aşağıdaki örneklerde, kayıt defterinde anahtar [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0Exp\NewProjectTemplates] altında yer alır.  
  
```  
\TemplateDirs\{ACEF4EB2-57CF-11D2-96F4-000000000000}\1                (CLSID for Figures Project projects)  
   @="#7"  
   "TemplatesDir"="<Visual Studio SDK installation path>\\VSIntegration\\Archive9.0\\FigPkgs\\FigPrj\\FigPrjProjects"  
   "SortPriority"=dword:00000029  
   "NewProjectDialogOnly"=dword:00000000  
```  
  
|Ad|Tür|Veri|Açıklama|  
|----------|----------|----------|-----------------|  
|`@`|REG_SZ|`#%IDS_NEWPROJ_TEMPLATES_ENTRY%`|Kaynak Kimliği değeri rakamları proje yeni proje şablonları için.|  
|`TemplatesDir`|REG_SZ|`%TEMPLATE_PATH%\FigPrjProjects`|Yeni projeler dizinin varsayılan yolu. Bu dizinde öğeleri görüntülenir **Yeni Proje Sihirbazı** iletişim kutusu.|  
|`SortPriority`|REG_DWORD|`41 (x29)`|Hangi projeleri görüntülenir ağaç düğümü sipariş kurar **yeni proje** iletişim kutusu.|  
|`NewProjectDialogOnly`|REG_DWORD|`0`|0 gösterir projeleri bu tür yalnızca görüntülenir **yeni proje** iletişim kutusu.|  
  
 Aşağıdaki örnek, kayıt defterinde anahtar [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0Exp\InstalledProducts] altında yer alır.  
  
```  
\FiguresProductSample  
   "Package"="{ACEF4EB2-57CF-11D2-96F4-000000000000}"  
   "UseInterface"=dword:00000001  
```  
  
|Ad|Tür|Veri|Açıklama|  
|----------|----------|----------|-----------------|  
|`Package`|REG_SZ|`%CLSID_Package%`|Kayıtlı VSPackage sınıfı kimliği.|  
|`UseInterface`|REG_DWORD|`1`|1, kullanıcı arabirimini bu proje ile etkileşim kurmak için kullanılacağını gösterir. 0 UI arabirimini gösterir.|  
  
 Yeni proje türleri sık sık kontrol The.vsz dosyaları relatıve_path giriş içerir. Bu yol aşağıdaki Kurulum anahtarında proje türünde \ProductDir girdisini altında belirtilen yol görelidir:  
  
 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\7.0Exp\Setup  
  
 Örneğin, Kurumsal çerçeveleri proje şablonları aşağıdaki kayıt defteri girdilerini ekleyin:  
  
 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\7.0Exp\Setup\EF\ProductDir C:\Program Files\Microsoft Visual Studio\EnterpriseFrameworks\ =  
  
 Bir PROJECT_TYPE içerip içermediğini anlamına = EF girişi .vsz dosyasındaki, .vsz dosyaları daha önce belirtilen ProductDir dizinde ortamı bulur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetim listesi: Yeni proje türleri oluşturma](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [Proje modeli öğeleri](../../extensibility/internals/elements-of-a-project-model.md)   
 [Proje Üreteçlerini Kullanarak Proje Örnekleri Oluşturma](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)