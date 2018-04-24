---
title: Yaygın MSBuild proje özellikleri | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2018
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- msbuild, common properties
- msbuild, project file properties
- ExcludeDeploymentUrl property
- project file properties (MSBuild)
ms.assetid: 9857505d-ae15-42f1-936d-6cd7fb9dd276
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bd3483a47946d51890708186a38fc05ae2576ed1
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="common-msbuild-project-properties"></a>Yaygın MSBuild Proje Özellikleri
Aşağıdaki tabloda sık Visual Studio Proje dosyasında tanımlanan özellikler kullanılan veya sağlayan MSBuild .targets dosyasında bulunur.  
  
 Proje dosyaları (.csproj, .vbproj, vcxproj ve diğerleri) Visual Studio IDE kullanarak bir projeyi derlerken çalıştırılan MSBuild XML kodunu içerir. Projeleri genellikle kendi derleme işlemi tanımlamak için bir veya daha fazla .targets dosyaları içeri aktarın. Daha fazla bilgi için bkz: [. Hedefler dosyaları](../msbuild/msbuild-dot-targets-files.md).  
  
## <a name="list-of-common-properties-and-parameters"></a>Ortak Özellikler ve Parametreler listesi  
  
|Özellik veya parametre adı|Açıklama|  
|--------------------------------|-----------------|  
|AdditionalLibPaths|Ek klasörler derleyicileri için başvuru bütünleştirilmiş görünmelidir belirtir.|  
|AddModules|Tüm türü hale getirmesine neden olan belirtilen bilgilerinden dosyaları derlediğiniz projesi için kullanılabilir. Bu özellik eşdeğerdir `/addModules` derleyici anahtar.|  
|ALToolPath|AL.exe bulunduğu yolu. Bu özellik için farklı bir sürüm kullanımını etkinleştirmek için AL.exe geçerli sürümü geçersiz kılar.|  
|ApplicationIcon|Win32 simgesi olarak katıştırma derleyiciye geçmesine .ico simge dosyası. Özellik eşdeğerdir `/win32icon` derleyici anahtar.|  
|ApplicationManifest|Dış kullanıcı hesabı denetimi (UAC) bildirim bilgileri oluşturmak için kullanılan dosya yolunu belirtir. Yalnızca hedefleyen Visual Studio projelerine yöneliktir [!INCLUDE[windowsver](../deployment/includes/windowsver_md.md)].<br /><br /> Çoğu durumda, bildirim katıştırılır. Ancak, kayıt ücretsiz COM kullanırsanız veya [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım sonra bildirim, uygulama derlemeler ile birlikte yüklenen dış dosyası olabilir. Daha fazla bilgi için bu konudaki NoWin32Manifest özelliğine bakın.|  
|AssemblyOriginatorKeyFile|İçin geçirilen ve (.snk veya .pfx) derlemeyi imzalamak için kullanılan dosyayı belirtir [ResolveKeySource görevi](../msbuild/resolvekeysource-task.md) derlemeyi imzalamak için kullanılan gerçek anahtarı oluşturmak için.|  
|AssemblySearchPaths|Derleme zamanı referans derleme çözümlemesi sırasında aranacak konumların listesi. Yukarıda listelenen yollar aldığından öncelik sonraki girişleri yollarının bu listede görünme sırasını anlamlıdır.|  
|AssemblyName|Proje oluşturulduktan sonra son çıktı derleme adı.|  
|BaseAddress|Ana çıkış derlemesi temel adresini belirtir. Bu özellik eşdeğerdir `/baseaddress` derleyici anahtar.|  
|BaseOutputPath|Çıktı dosyası için temel yolunu belirtir. Bu ayarlanırsa [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] kullanacağı `OutputPath = $(BaseOutputPath)\$(Configuration)\`. Örnek sözdizimi: `<BaseOutputPath>c:\xyz\bin\</BaseOutputPath>`|  
|BaseIntermediateOutputPath|Tüm özel yapılandırma Ara Çıkış klasörleri oluşturulduğu en üst düzey klasör. Varsayılan değer `obj\` şeklindedir. Aşağıdaki kod örneği verilmiştir: `<BaseIntermediateOutputPath>c:\xyz\obj\</BaseIntermediateOutputPath>`|  
|BuildInParallel|Proje başvuruları yerleşik veya paralel when temizlendi olup olmadığını gösteren bir Boole değeri birden çok işlemci [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] kullanılır. Varsayılan değer `true`, sahip birden çok çekirdek veya işlemci projeleri sistem içinde paralel IF oluşturulacak anlamına gelir.|  
|BuildProjectReferences|Proje başvuruları tarafından oluşturulan olup olmadığını gösteren bir Boole değeri [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Otomatik olarak ayarlamak `false` projenizi oluşturuyorsanız [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE) `true` , aksi takdirde. `/p:BuildProjectReferences=false` Komut satırında başvurulan projeleri güncel denetimi önlemek için belirtilebilir.|  
|CleanFile|"Temiz önbelleği olarak." kullanılacak dosya adı Temizleme işlemi sırasında silinecek oluşturulan dosyaların listesini temiz önbelleğidir. Dosyayı Ara çıkış yolu derleme süreci tarafından yerleştirilir.<br /><br /> Bu özellik yalnızca yol bilgisi olmayan dosya adlarını belirtir.|  
|Kod sayfası|Derlemedeki tüm kaynak kodu dosyaları için kullanılacak kod sayfasını belirtir. Bu özellik eşdeğerdir `/codepage` derleyici anahtar.|  
|CompilerResponseFile|Derleyici görevlere aktarılabilecek bir isteğe yanıt dosyası.|  
|Yapılandırma|Oluşturmakta olduğunuz yapılandırma "Hata ayıklama" veya "Yayın."|  
|CscToolPath|Csc.exe, yol [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] derleyici.|  
|CustomBeforeMicrosoftCommonTargets|Proje dosyası ya da otomatik olarak ortak hedefleri içe önce alınacak hedefleri dosya adı.|  
|DebugSymbols|Simgeler yapı tarafından oluşturulan olup olmadığını gösteren bir Boole değeri.<br /><br /> Ayarı **/p:DebugSymbols = false** komut satırında, program veritabanı (.pdb) simge dosyaları nesil devre dışı bırakır.|  
|DefineConstants|Koşullu derleme sabitleri tanımlar. Sembol/değer çiftleri noktalı virgülle ayırarak ve aşağıdaki sözdizimi kullanılarak belirtilir:<br /><br /> *symbol1 = value1; Simge2 Value2*<br /><br /> Özellik eşdeğerdir `/define` derleyici anahtar.|  
|DefineDebug|Tanımlanan hata ayıklama sabiti isteyip istemediğinizi gösteren bir Boole değeri.|  
|DefineTrace|Tanımlanan izleme sabiti isteyip istemediğinizi gösteren bir Boole değeri.|  
|DebugType|Oluşturulmasını istediğiniz hata ayıklama bilgisi düzeyini tanımlar. Geçerli değerler: "tam," "pdbonly" ve "yok."|  
|DelaySign|Tam oturum yerine geciktirin derleme istediğiniz olup olmadığını gösteren bir Boole değeri.|  
|Belirleyici|Derleyici aynı girişleri için aynı derlemeleri üretmek olup olmadığını gösteren bir Boole değeri. Bu parametre karşılık gelen `/deterministic` geçiş `vbc.exe` ve `csc.exe` derleyicileri.|
|DisabledWarnings|Belirtilen Uyarıları bastırır. Uyarı tanımlayıcı yalnızca sayısal parçası belirtilmelidir. Birden çok uyarıları noktalı virgülle ayrılır. Bu parametre karşılık gelen `/nowarn` vbc.exe derleyici anahtar.|  
|DisableFastUpToDateCheck|Geçerli bir Boole değeri [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yalnızca. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Proje, güncel olması için yeniden oluşturulması olup olmadığını belirlemek için FastUpToDateCheck adlı bir işlem yöneticisi kullanır oluşturun. Bu işlem kullanmaktan daha hızlıdır [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] bunu belirlemek için. DisableFastUpToDateCheck özelliğini ayarlamak `true` atlama olanak sağlayan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Yöneticisi oluşturmak ve kullanmak için zorla [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projenin güncel olup olmadığını belirlemek için.|  
|DocumentationFile|XML belge dosyası oluşturulan dosya adı. Bu ad yalnızca dosya adını içerir ve yol bir bilgi bulunmaz.|  
|ErrorReport|Derleyici görev iç derleyici hataları nasıl bildirmelisiniz belirtir. Geçerli değerler: "sor" "gönderme" veya "hiçbiri." Bu özellik eşdeğerdir `/errorreport` derleyici anahtar.|  
|ExcludeDeploymentUrl|[GenerateDeploymentManifest görevi](../msbuild/generatedeploymentmanifest-task.md) proje dosyası aşağıdaki öğeleri birini içeriyorsa, dağıtım bildirimine deploymentProvider etiketi ekler:<br /><br /> -UpdateUrl<br />-InstallUrl<br />-PublishUrl<br /><br /> ExcludeDeploymentUrl kullanarak, ancak, deploymentProvider etiketi, yukarıdaki URL'ler belirtilmiş olsa bile dağıtım bildirimine eklenmesini engelleyebilirsiniz. Bunu yapmak için aşağıdaki özellik proje dosyanıza ekleyin:<br /><br /> `<ExcludeDeploymentUrl>true</ExcludeDeploymentUrl>` **Not:** ExcludeDeploymentUrl açık değil [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE ve yalnızca el ile proje dosyasını düzenleyerek ayarlayabilirsiniz. Bu özelliği ayarlamak içinde yayımlama etkilemez [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]; diğer bir deyişle, deploymentProvider etiketi hala PublishUrl tarafından belirtilen URL eklenir.|  
|FileAlignment|, Çıktı dosyası bölümlerini hizalamak nereye bayt cinsinden belirtir. Geçerli değerler 512, 1024, 2048, 4096, 8192. Bu özellik eşdeğerdir `/filealignment` derleyici anahtar.|  
|FrameworkPathOverride|Mscorlib.dll ve Microsoft.VisualBasic.dll içinde konumunu belirtir. Bu parametre eşdeğerdir `/sdkpath` vbc.exe derleyici anahtar.|  
|GenerateDocumentation|(Yalnızca Visual Basic) Belge yapı tarafından oluşturulup oluşturulmayacağını belirten bir boolean parametresiyle. Varsa `true`, yapı belgeleri bilgisi oluşturur ve yürütülebilir dosya veya derleme görevi oluşturulan kitaplığı adı ile birlikte bir .xml dosyasına yerleştirir.|
|IntermediateOutputPath|Türetilen gibi tam Ara çıkış yolu `BaseIntermediateOutputPath`yol belirtilmezse,. Örneğin, \obj\debug\\. Bu özellik kılınırsa sonra ayarlayarak `BaseIntermediateOutputPath` hiçbir etkisi olmaz.|  
|AnahtarKapsayıcıAdı|Güçlü ad anahtar kapsayıcısı adı.|  
|KeyOriginatorFile|Güçlü ad anahtar dosyası adı.|  
|ModuleAssemblyName|Derlenmiş modülü birleştirilir derlemesini adı. Özellik eşdeğerdir `/moduleassemblyname` derleyici anahtar.|  
|NoLogo|Kapatılmasına derleyici logosu isteyip istemediğinizi gösteren bir Boole değeri. Bu özellik eşdeğerdir `/nologo` derleyici anahtar.|  
|NoStdLib|Standart Kitaplığı (mscorlib.dll) başvuran önlemek gösterir bir Boole değeri. Varsayılan değer `false` şeklindedir.|  
|NoVBRuntimeReference|Gösteren bir Boole değeri olup olmadığını [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] çalışma zamanı (Microsoft.VisualBasic.dll içinde) bir başvuru proje olarak eklendi.|  
|NoWin32Manifest|Kullanıcı Hesabı Denetimi (UAC) bildirim bilgileri uygulamada ekli olup olmadığını gösteren bir Boole değeri çalıştırılabilir. Yalnızca hedefleyen Visual Studio projelerine yöneliktir [!INCLUDE[windowsver](../deployment/includes/windowsver_md.md)]. Kullanılarak dağıtılan projelerinde [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ve Kayıtsız COM, bu öğe göz ardı edilir. `False` Kullanıcı Hesabı Denetimi (UAC) bildirim bilgileri uygulamanın yürütülebilir dosya gömülmesi (varsayılan değer) belirtir. `True` UAC bildirim bilgileri değil gömülmesi belirtir.<br /><br /> Bu özellik yalnızca geçerlidir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projeleri hedefleyen [!INCLUDE[windowsver](../deployment/includes/windowsver_md.md)]. Kullanılarak dağıtılan projelerinde [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ve Kayıtsız COM, bu özellik yoksayılır.<br /><br /> Yalnızca, istemiyorsanız NoWin32Manifest eklemelisiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] herhangi bildirimi katıştırmak için uygulamasında bilgilerini çalıştırılabilir; bu işlem çağrılırken *sanallaştırma*. Sanallaştırma kullanmak üzere ayarlanmış `<ApplicationManifest>` birlikte `<NoWin32Manifest>` gibi:<br /><br /> -İçin [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projeleri, kaldırma `<ApplicationManifest>` düğümü. (İçinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projeleri, `<NoWin32Manifest>` zaman göz ardı edilir bir `<ApplicationManifest>` düğüm var..)<br />-İçin [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projeleri, ayarlayın `<ApplicationManifest>` için `False` ve `<NoWin32Manifest>` için `True`. (İçinde [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projeleri, `<ApplicationManifest>` geçersiz kılmaları `<NoWin32Manifest>`.)<br /> Bu özellik eşdeğerdir `/nowin32manifest` vbc.exe derleyici anahtarı.|  
|En iyi duruma getirme|Bir Boole değeri, ayarlandığında `true`, derleyici iyileştirmeler sağlar. Bu özellik eşdeğerdir `/optimize` derleyici anahtar.|  
|OptionCompare|Dize karşılaştırmaları nasıl yapılacağını belirtir. Geçerli değerler "ikili" veya "metin": Bu özellik eşdeğerdir `/optioncompare` vbc.exe derleyici anahtarı.|  
|Option Explicit|Bir Boole değeri, ayarlandığında `true`, kaynak kodundaki değişkenlerin açıkça bildirilmesini gerektirir. Bu özellik eşdeğerdir `/optionexplicit` derleyici anahtar.|  
|OptionInfer|Bir Boole değeri, ayarlandığında `true`, etkinleştirir değişkenlerin çıkarım yazın. Bu özellik eşdeğerdir `/optioninfer` derleyici anahtar.|  
|OptionStrict|Bir Boole değeri, ayarlandığında `true`, örtük tür dönüşümleri kısıtlamak için kesin türü anlamları zorlamak derleme görevi neden olur. Bu özellik eşdeğerdir `/optionstrict` vbc.exe derleyici anahtar.|  
|OutputPath|Örneğin, "bin\Debug" proje dizine göreli çıktı dizini yolunu belirtir.|  
|OutputType|Çıkış dosyasının dosya biçimini belirtir. Bu parametre aşağıdaki değerlerden biri olabilir:<br /><br /> -Kitaplığı. Bir kod kitaplığı oluşturur. (Varsayılan değeri.)<br />-Exe. Bir konsol uygulaması oluşturur.<br />-Modül. Bir modül oluşturur.<br />-Winexe. Windows tabanlı bir program oluşturur.<br /><br /> Bu özellik eşdeğerdir `/target` vbc.exe derleyici anahtar.|  
|OverwriteReadOnlyFiles|Salt okunur dosyalar üzerine veya bir hata tetiklemek için yapı etkinleştirmek isteyip istemediğinizi gösteren bir Boole değeri.|  
|PdbFile|Yayma .pdb dosyasının dosya adı. Bu özellik eşdeğerdir `/pdb` csc.exe derleyici anahtar.|  
|Platform|İçin oluşturmakta olduğunuz işletim sistemi. Geçerli değerler "Herhangi bir CPU", "x 86" ve "x64" dir.|  
|ProduceReferenceAssembly|Bir Boole değeri, ayarlandığında `true` üretimini etkinleştirir [başvuru derlemeleri](https://github.com/dotnet/roslyn/blob/master/docs/features/refout.md) geçerli derleme için. `Deterministic` olmalıdır `true` bu özelliği kullanırken. Bu özellik karşılık gelen `/refout` geçiş `vbc.exe` ve `csc.exe` derleyicileri.|
|RemoveIntegerChecks|Tamsayı taşma hatası devre dışı bırakılıp bırakılmayacağını gösteren bir Boole değeri denetler. Varsayılan değer `false` şeklindedir. Bu özellik eşdeğerdir `/removeintchecks` vbc.exe derleyici anahtar.|  
|SGenUseProxyTypes|Proxy türleri SGen.exe tarafından oluşturulan olup olmadığını gösteren bir Boole değeri.<br /><br /> SGen hedef UseProxyTypes bayrağı ayarlamak için bu özelliği kullanır. Bu özellik true olarak Varsayılanları ve bunu değiştirmek için kullanıcı Arabirimi yoktur. Seri hale getirme derlemesi webservice olmayan türleri oluşturmak için bu özellik proje dosyasına ekleyin ve Microsoft.Common.Targets veya C#/VB.targets almadan önce false olarak ayarlayın.|  
|SGenToolPath|SGen.exe geçerli sürümü kılındığında SGen.exe nereden belirten isteğe bağlı aracı yolu.|  
|StartupObject|Sınıf veya Sub Main yordamı ve Main yöntemini içeren modülünü belirtir. Bu özellik eşdeğerdir `/main` derleyici anahtar.|  
|ProcessorArchitecture|Derleme başvurularını çözümlendiği zaman kullanılan işlemci mimarisi. Geçerli değerler: "MSIL", "x86," "amd64" veya "IA64."|  
|RootNamespace|Katıştırılmış bir kaynağı adlandırdığınızda kullanmak için kök ad alanı. Bu ad alanı katıştırılmış kaynak bildirim adını bir parçasıdır.|  
|Satellite_AlgorithmId|Uydu derlemeleri oluşturduğunuzda kullanılacak AL.exe karma algoritma kimliği.|  
|Satellite_BaseAddress|Kültüre özgü uydu derlemelerini kullanılarak oluşturulan sırasında kullanmak için taban adresi `CreateSatelliteAssemblies` hedef.|  
|Satellite_CompanyName|Uydu derleme oluşturma sırasında AL.exe geçirmek için şirket adı.|  
|Satellite_Configuration|Uydu derleme oluşturma sırasında AL.exe geçirmek için yapılandırma adı.|  
|Satellite_Description|Uydu derleme oluşturma sırasında AL.exe geçirmek için açıklama metni.|  
|Satellite_EvidenceFile|Belirtilen dosya bir kaynak adı "Security.Evidence." olan uydu derlemeye katıştırır|  
|Satellite_FileVersion|Dosya sürümü alanı için bir dize uydu derlemesinde belirtir.|  
|Satellite_Flags|Uydu derlemesi içinde bayrak alanı için bir değer belirtir.|  
|Satellite_GenerateFullPaths|Mutlak yollar bir hata iletisi bildirilen tüm dosyalar için kullanılacak derleme görevi neden olur.|  
|Satellite_LinkResource|Belirtilen kaynak dosyaları için bir uydu derleme bağlar.|  
|Satellite_MainEntryPoint|Tam adını (diğer bir deyişle, class.method) bir modülü uydu derleme oluşturma sırasında bir yürütülebilir dosyaya dönüştürüldüğünde bir giriş noktası olarak kullanılacak yöntemi belirtir.|  
|Satellite_ProductName|Ürün alanı için bir dize uydu derlemesinde belirtir.|  
|Satellite_ProductVersion|Bir dize ProductVersion alan için uydu derlemesinde belirtir.|  
|Satellite_TargetType|Uydu derleme çıktı dosyası dosya biçimini belirtir "kitaplığı," "exe" veya "win." Varsayılan değer "." kitaplığıdır|  
|Satellite_Title|Başlık alanı için bir dize uydu derlemesinde belirtir.|  
|Satellite_Trademark|Ticari marka alan için bir dize uydu derlemesinde belirtir.|  
|Satellite_Version|Uydu derlemenin sürüm bilgisi belirtir.|  
|Satellite_Win32Icon|Uydu bütünleştirilmiş kodunda bir .ico simge dosyası ekler.|  
|Satellite_Win32Resource|Win32 kaynak (.res dosyası) uydu derlemesini ekler.|  
|SubsystemVersion|En düşük sürüm oluşturulan yürütülebilir dosyasını kullanabilirsiniz alt sisteminin belirtir. Bu özellik eşdeğerdir `/subsystemversion` derleyici anahtar. Bu özelliğin varsayılan değeri hakkında daha fazla bilgi için bkz: [/subsystemversion (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/subsystemversion) veya [/subsystemversion (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/subsystemversion-compiler-option).|  
|TargetCompactFramework|Oluşturmakta olduğunuz uygulamayı çalıştırmak için gerekli .NET Compact Framework sürümü. Bu belirleme, aksi takdirde başvurmak mümkün olmayabilir belirli framework derlemeleri başvuru sağlar.|  
|targetFrameworkVersion|Sürümü [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] oluşturmakta olduğunuz uygulamayı çalıştırmak için gereklidir. Bu belirleme, aksi takdirde başvurmak mümkün olmayabilir belirli framework derlemeleri başvuru sağlar.|  
|TreatWarningsAsErrors|Boole parametresi, varsa `true`, hata olarak kabul edilmesi tüm uyarıları neden olur. Bu parametre eşdeğerdir `/nowarn` derleyici anahtar.|  
|UseHostCompilerIfAvailable|Boole parametresi, varsa `true`, kullanılabilir durumdaysa işlem içi derleyicisi nesnesini kullanmak derleme görevi neden olur. Bu parametre yalnızca kullanılan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|Utf8Output|Boole parametresi, varsa `true`, Derleyici çıktısı UTF-8 kodlaması kullanarak günlüğe kaydeder. Bu parametre eşdeğerdir `/utf8Output` derleyici anahtar.|  
|VbcToolPath|Vbc.exe geçerli sürümü kılındığında vbc.exe için başka bir konum belirten isteğe bağlı bir yoldur.|  
|VbcVerbosity|Ayrıntı düzeyini belirtir [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] animasyonun derleyici çıktı. Geçerli değerler: "Sessiz," "Normal" (varsayılan değer) veya "Ayrıntılı."|  
|VisualStudioVersion|Bu proje altında çalışıyor olması gerektiğini düşünülmelidir Visual Studio sürümünü belirtir. Bu özellik belirtilmezse, MSBuild için makul varsayılan bir değer ayarlar.<br /><br /> Bu özellik birkaç proje türü, derleme için kullanılan hedefleri kümesini belirtmek için kullanılır. Varsa `ToolsVersion` 4.0 veya üzeri bir proje için ayarlanmış `VisualStudioVersion` kullanmak için hangi alt toolset belirtmek için kullanılır. Daha fazla bilgi için bkz: [araç takımı (ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md).|  
|WarningsAsErrors|Hata olarak değerlendirmek için uyarılar listesini belirtir. Bu parametre eşdeğerdir `/warnaserror` derleyici anahtar.|  
|WarningsNotAsErrors|Hata olarak kabul edilmediği uyarıların listesini belirtir. Bu parametre eşdeğerdir `/warnaserror` derleyici anahtar.|  
|Win32Manifest|Son derlemesinde katıştırılmış bildirim dosyasının adı. Bu parametre eşdeğerdir `/win32Manifest` derleyici anahtar.|  
|Win32Resource|Son derlemesinde katıştırılacak Win32 kaynak dosya adı. Bu parametre eşdeğerdir `/win32resource` derleyici anahtar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yaygın MSBuild Proje Öğeleri](../msbuild/common-msbuild-project-items.md)
