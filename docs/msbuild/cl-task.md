---
title: CL görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.UseUnicodeForAssemblerListing
- vc.task.cl
- VC.Project.VCCLCompilerTool.TreatSpecificWarningsAsErrors
- VC.Project.VCCLCompilerTool.CreateHotpatchableImage
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild (Visual C++), CL task
- CL task (MSBuild (Visual C++))
ms.assetid: 651ba971-b755-4f03-a549-4816beb3cc0d
caps.latest.revision: 18
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5b5609ac97d9322ddf4af5bc5638212a3ccfd045
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="cl-task"></a>CL Görevi
Visual C++ Derleyici aracı sarmalar cl.exe. Derleyici yürütülebilir dosyanın (.exe) dosyaları, dinamik bağlantı kitaplığı (.dll) dosyaları ya da kod Modülü (.netmodule) dosyaları oluşturur. Daha fazla bilgi için bkz: [derleyici seçenekleri](/cpp/build/reference/compiler-options).  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır **CL** görev. Çoğu görevi parametreleri ve parametreleri, birkaç kümelerini bir komut satırı seçeneğine karşılık gelir.  
  
-   **AdditionalIncludeDirectories**  
  
     İsteğe bağlı dize [] parametresi.  
  
     Bir dizin için dosyaları Ekle aranır dizinlerin listesi ekler.  
  
     Daha fazla bilgi için bkz: [/ı (ek içeren dizinler)](/cpp/build/reference/i-additional-include-directories).  
  
-   **AdditionalOptions**  
  
     İsteğe bağlı dizesi parametresi.  
  
     Komut satırı seçeneklerinin listesi. Örneğin, "/*seçenek 1* /*Seçenek2* /*seçeneği #*". Başka bir görev parametre tarafından temsil edilmeyen komut satırı seçeneklerini belirtmek için bu parametreyi kullanın.  
  
     Daha fazla bilgi için bkz: [derleyici seçenekleri](/cpp/build/reference/compiler-options).  
  
-   **AdditionalUsingDirectories**isteğe bağlı dize [] parametresi.  
  
     Derleyici dosya referansları geçirilen çözümlemek için arayacağı bir dizini belirtir **#using** yönergesi.  
  
     Daha fazla bilgi için bkz: [/AI (meta veri dizinlerini belirtin)](/cpp/build/reference/ai-specify-metadata-directories).  
  
-   **AlwaysAppend**  
  
     İsteğe bağlı dizesi parametresi.  
  
     Bir dize her zaman komut satırında yayılan. Varsayılan değer "**/c**".  
  
-   **AssemblerListingLocation**  
  
     Bütünleştirilmiş kodu içeren bir listeyi dosyası oluşturur.  
  
     Daha fazla bilgi için bkz: **/Fa** seçeneğini [/FA, /Fa (listeleme dosyası)](/cpp/build/reference/fa-fa-listing-file).  
  
-   **AssemblerOutput**  
  
     İsteğe bağlı dizesi parametresi.  
  
     Bütünleştirilmiş kodu içeren bir listeyi dosyası oluşturur.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **NoListing** - *\<yok >*  
  
    -   **AssemblyCode** - **/FA**  
  
    -   **AssemblyAndMachineCode** - **/FAc**  
  
    -   **AssemblyAndSourceCode** - **/FAs**  
  
    -   **Tüm** - **/FAcs**  
  
     Daha fazla bilgi için bkz: **/FA**, **/FAc**, **/FAs**, ve **/FAcs** içinde seçenekleri [/FA, /Fa (listeleme dosyası)](/cpp/build/reference/fa-fa-listing-file).  
  
-   **BasicRuntimeChecks**  
  
     İsteğe bağlı dizesi parametresi.  
  
     Birlikte çalışma zamanı hata denetimleri özelliğini devre dışı bırakır ve sağlar [runtime_checks](/cpp/preprocessor/runtime-checks) pragması.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **Varsayılan** -                          *\<yok >*  
  
    -   **StackFrameRuntimeCheck** - **/RTCs**  
  
    -   **UninitializedLocalUsageCheck** - **/RTCu**  
  
    -   **EnableFastChecks** -                          **/RTC1**  
  
     Daha fazla bilgi için bkz: [eş yordamlarla/RTC (çalışma zamanı hata denetler)](/cpp/build/reference/rtc-run-time-error-checks).  
  
-   **BrowseInformation**  
  
     Boole parametresi isteğe bağlıdır.  
  
     Varsa `true`, gözatma bilgileri dosyası oluşturur.  
  
     Daha fazla bilgi için bkz: **/FR** seçeneğini [/FR, /Fr (oluşturun. SBR dosyası)](/cpp/build/reference/fr-fr-create-dot-sbr-file).  
  
-   **BrowseInformationFile**  
  
     İsteğe bağlı dizesi parametresi.  
  
     Gözatma bilgileri dosyası için bir dosya adı belirtir.  
  
     Daha fazla bilgi için bkz: **BrowseInformation** Bu tablo ve ayrıca bkz: parametresinde [/FR, /Fr (oluşturun. SBR dosyası)](/cpp/build/reference/fr-fr-create-dot-sbr-file).  
  
-   **BufferSecurityCheck**  
  
     Boole parametresi isteğe bağlıdır.  
  
     Varsa `true`, arabellek boyutu kısıtlamaları zorlamaz kod yararlanmasını için ortak bir teknik dönüş adresi üzerine bazı arabellek taşmaları algılar.  
  
     Daha fazla bilgi için bkz: [/GS (arabellek güvenlik denetimi)](/cpp/build/reference/gs-buffer-security-check).  
  
-   **BuildingInIDE**  
  
     Boole parametresi isteğe bağlıdır.  
  
     Varsa `true`, belirten **MSBuild** IDE tarafından çağrılır. Aksi takdirde, **MSBuild** komut satırında çağrılır.  
  
-   **CallingConvention**  
  
     İsteğe bağlı dizesi parametresi.  
  
     Çağıran işlev veya çağrılan işlev çağrısı sonunu yığında bağımsız değişkenleri kaldırır olup olmadığını belirleyen hangi işlev bağımsız değişkenleri gönderilen yığına sırası, çağırma kuralı ve ad dekorasyon kuralı belirtir, Derleyici tekil işlevler tanımlamak için kullanır.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **Cdecl** - **/Gd**  
  
    -   **FastCall** -                          **/Gr**  
  
    -   **StdCall** -                          **/Gz**  
  
     Daha fazla bilgi için bkz: [/Gd, / GV, /Gz (çağırma kuralı)](/cpp/build/reference/gd-gr-gv-gz-calling-convention).  
  
-   **CompileAs**  
  
     İsteğe bağlı dizesi parametresi.  
  
     C veya C++ kaynak dosyası olarak giriş dosyası derlenip derlenmeyeceğini belirler.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **Varsayılan** - *\<yok >*  
  
    -   **CompileAsC** - **/TC**  
  
    -   **CompileAsCpp** - **/TP**  
  
     Daha fazla bilgi için bkz: [TP, /Tp, TP, /TP (kaynak dosya türünü belirtin)](/cpp/build/reference/tc-tp-tc-tp-specify-source-file-type).  
  
-   **CompileAsManaged**  
  
     İsteğe bağlı dizesi parametresi.  
  
     Ortak dil çalışma zamanı (CLR) özellikleri kullanmak için uygulamaları ve bileşenleri sağlar.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **yanlış** - *\<yok >*  
  
    -   **doğru** -   **/CLR**  
  
    -   **Saf** -   **/CLR: pure**  
  
    -   **Safe** - **/clr:safe**  
  
    -   **OldSyntax** - **/clr:oldSyntax**  
  
     Daha fazla bilgi için bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](/cpp/build/reference/clr-common-language-runtime-compilation).  
  
-   **CreateHotpatchableImage**  
  
     Boole parametresi isteğe bağlıdır.  
  
     Varsa `true`, görüntü için hazırlamak üzere derleyici söyler *anında düzeltme*. Bu parametre her işlevinin ilk yönerge iki bayt anında düzeltme için gerekli olduğu olmasını sağlar.  
  
     Daha fazla bilgi için bkz: [/hotpatch (düzeltme eki eklenebilen görüntü oluşturma)](/cpp/build/reference/hotpatch-create-hotpatchable-image).  
  
-   **DebugInformationFormat**  
  
     İsteğe bağlı dizesi parametresi.  
  
     Hata ayıklama bilgisi için oluşturulan programınızı ve bu bilgiler nesne (.obj) dosyalarında veya program veritabanı (PDB) tutulur türünü seçer.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **OldStyle** - **/Z7**  
  
    -   **ProgramDatabase** -   **/zi**  
  
    -   **EditAndContinue** - **/ZI**  
  
     Daha fazla bilgi için bkz: [/Z7, / zi, /zı (hata ayıklama bilgileri biçimi)](/cpp/build/reference/z7-zi-zi-debug-information-format).  
  
-   **DisableLanguageExtensions**  
  
     Boole parametresi isteğe bağlıdır.  
  
     Varsa **doğru**, ANSI C veya C++ ANSI ile uyumlu olmayan dil yapıları için bir hata yayma bildirir.  
  
     Daha fazla bilgi için bkz: **/Za** seçeneğini [/Za, /Ze (dil uzantılarını devre dışı bırak)](/cpp/build/reference/za-ze-disable-language-extensions).  
  
-   **DisableSpecificWarnings**  
  
     İsteğe bağlı dize [] parametresi.  
  
     Noktalı virgülle ayrılmış bir listede belirtilen uyarı numaralarını devre dışı bırakır.  
  
     Daha fazla bilgi için bkz: `/wd` seçeneğini [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, wln, /wd, / biz, /wo, /Wv, /WX (uyarı düzeyi)](/cpp/build/reference/compiler-option-warning-level).  
  
-   **EnableEnhancedInstructionSet**  
  
     İsteğe bağlı dizesi parametresi.  
  
     Streaming SIMD Extensions 2 (SSE2) yönergeleri ve Streaming SIMD Uzantıları (SSE) kullanan kod oluşturma için Mimari belirtir.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **StreamingSIMDExtensions** - **/arch:SSE**  
  
    -   **StreamingSIMDExtensions2** - **/arch:SSE2**  
  
     Daha fazla bilgi için bkz: [/(x86) arch](/cpp/build/reference/arch-x86).  
  
-   **EnableFiberSafeOptimizations**  
  
     Boole parametresi isteğe bağlıdır.  
  
     Varsa `true`, fiber güvenliği statik iş parçacığı yerel depolama, diğer bir deyişle, kullanarak ayrılan veri kullanarak ayrılan veri Destek `__declspec(thread)`.  
  
     Daha fazla bilgi için bkz: [/GT (Fiber-güvenli iş parçacığı-yerel depolamayı destekle)](/cpp/build/reference/gt-support-fiber-safe-thread-local-storage).  
  
-   **EnablePREfast**  
  
     Boole parametresi isteğe bağlıdır.  
  
     Varsa `true`, kod çözümlemesini etkinleştirin.  
  
     Daha fazla bilgi için bkz: [/ analyze (kod çözümleme)](/cpp/build/reference/analyze-code-analysis).  
  
-   **ErrorReporting**  
  
     İsteğe bağlı dizesi parametresi.  
  
     Doğrudan Microsoft'a iç derleyici hatası (çok) bilgileri sağlamanıza olanak tanır. Varsayılan olarak, IDE derlemeleri ayardır **komut istemi** ve komut satırı derlemeleri ayarında **sıra**.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **None** - **/errorReport:none**  
  
    -   **Prompt** - **/errorReport:prompt**  
  
    -   **Queue** - **/errorReport:queue**  
  
    -   **Send** - **/errorReport:send**  
  
     Daha fazla bilgi için bkz: [/errorreport (dahili derleme hatalarını raporla)](/cpp/build/reference/errorreport-report-internal-compiler-errors).  
  
-   **ExceptionHandling**  
  
     İsteğe bağlı dizesi parametresi.  
  
     Özel durum derleyici tarafından kullanılacak işleme modelini belirtir.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **yanlış** - *\<yok >*  
  
    -   **Async** - **/EHa**  
  
    -   **Sync** - **/EHsc**  
  
    -   **SyncCThrow** - **/EHs**  
  
     Daha fazla bilgi için bkz: [/EH (özel durum işleme modeli)](/cpp/build/reference/eh-exception-handling-model).  
  
-   **ExpandAttributedSource**  
  
     Boole parametresi isteğe bağlıdır.  
  
     Varsa `true`, kaynak dosyasına eklenen öznitelikler genişletilmiştir bir listeyi dosyası oluşturur.  
  
     Daha fazla bilgi için bkz: [/Fx (eklenen kodu Birleştir)](/cpp/build/reference/fx-merge-injected-code).  
  
-   **FavorSizeOrSpeed**  
  
     İsteğe bağlı dizesi parametresi.  
  
     Kod boyutu ya da kod hızı favor belirtir.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **Ne** - *\<yok >*  
  
    -   **Boyutu** - **/Os**  
  
    -   **Hızı** - **/Ot**  
  
     Daha fazla bilgi için bkz: [/Os, /Ot (küçük koda, ayrıcalık hızlı koda ayrıcalık tanı)](/cpp/build/reference/os-ot-favor-small-code-favor-fast-code).  
  
-   **FloatingPointExceptions**  
  
     Boole parametresi isteğe bağlıdır.  
  
     Varsa `true`, güvenilir kayan nokta özel durumu modeli sağlar. Özel durumlar tetiklenen hemen sonra gerçekleştirilecektir.  
  
     Daha fazla bilgi için /**fp: dışında** seçeneğini [/fp (Floating-Point davranış belirtin)](/cpp/build/reference/fp-specify-floating-point-behavior).  
  
-   **FloatingPointModel**  
  
     İsteğe bağlı dizesi parametresi.  
  
     Kayan ayarlar noktası modeli.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **Precise** - **/fp:precise**  
  
    -   **Strict** - **/fp:strict**  
  
    -   **Fast** - **/fp:fast**  
  
     Daha fazla bilgi için bkz: [/fp (Floating-Point davranış belirtin)](/cpp/build/reference/fp-specify-floating-point-behavior).  
  
-   **ForceConformanceInForLoopScope**  
  
     Boole parametresi isteğe bağlıdır.  
  
     Varsa `true`, standart C++ davranışını uygulayan [için](/cpp/cpp/for-statement-cpp) Microsoft uzantıları kullanmak döngüleri ([/Ze](/cpp/build/reference/za-ze-disable-language-extensions)).  
  
     Daha fazla bilgi için bkz: [/ZC: forscope (zorla döngü kapsamında uyumluluğu)](/cpp/build/reference/zc-forscope-force-conformance-in-for-loop-scope).  
  
-   **ForcedIncludeFiles**  
  
     İsteğe bağlı `String[]` parametresi.  
  
     Bir veya daha fazla belirtilen üstbilgi dosyalarını işlemek önişlemci neden olur.  
  
     Daha fazla bilgi için bkz: [/FI (zorla dahil dosyasını Adlandır)](/cpp/build/reference/fi-name-forced-include-file).  
  
-   **ForcedUsingFiles**  
  
     İsteğe bağlı **String []** parametresi.  
  
     Önişlemci işleme bir veya daha fazla belirtilen neden **#using** dosyaları.  
  
     Daha fazla bilgi için bkz: [/FU (zorlanan adı #using)](/cpp/build/reference/fu-name-forced-hash-using-file).  
  
-   **FunctionLevelLinking**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, paketlenmiş işlevler (COMDATs) biçiminde paket tekil işlevler için derleyicisi tanır.  
  
     Daha fazla bilgi için bkz: [/Gy (işlev düzeyi bağlamayı etkinleştir)](/cpp/build/reference/gy-enable-function-level-linking).  
  
-   **GenerateXMLDocumentationFiles**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, belgeleri işlemek için derleyici yorumları, kaynak kodu dosyaları ve her kaynak için bir .xdc dosyası oluşturmak için kod dosyası nedeni belge açıklamaları vardır.  
  
     Daha fazla bilgi için bkz: [/doc (işlem belgesi açıklamaları) (C/C++)](/cpp/build/reference/doc-process-documentation-comments-c-cpp). Ayrıca bkz. **XMLDocumentationFileName** bu tabloda parametresi.  
  
-   **IgnoreStandardIncludePath**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, yol ve INCLUDE ortam değişkenleri belirtilen dizinlerdeki içerme dosyaları için arama derleyici engeller.  
  
     Daha fazla bilgi için bkz: [/X (Yoksay standart yol eklemeyi)](/cpp/build/reference/x-ignore-standard-include-paths).  
  
-   **InlineFunctionExpansion**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Satır içi işlev genişletmesi derleme için düzeyini belirtir.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **Varsayılan** - *\<yok >*  
  
    -   **Devre dışı** - **/Ob0**  
  
    -   **OnlyExplicitInline** - **/Ob1**  
  
    -   **AnySuitable** - **/Ob2**  
  
     Daha fazla bilgi için bkz: [/Ob (satır içi işlev genişletmesi)](/cpp/build/reference/ob-inline-function-expansion).  
  
-   **IntrinsicFunctions**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, değiştirir bazı işlevi çağırır ile iç veya aksi halde, uygulamanızın Yardım özel forms işlevinin daha hızlı çalışır.  
  
     Daha fazla bilgi için bkz: [/Oi (iç işlevler Oluştur)](/cpp/build/reference/oi-generate-intrinsic-functions).  
  
-   **MinimalRebuild**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, değiştirilen C++ dahil C++ kaynak dosyaları (Üstbilgi (.h) dosyalarında depolanır) tanımları sınıfı olup olmadığını belirleyen en az yeniden derleme gerekir yeniden derlenmesi etkinleştirir.  
  
     Daha fazla bilgi için bkz: [/GM derlemeyi (etkinleştirmek en az yeniden derleme)](/cpp/build/reference/gm-enable-minimal-rebuild).  
  
-   **MultiProcessorCompilation**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, derlemek için birden çok işlemci kullanacak. Bu parametre bir işlem etkin her işlemci için bilgisayarınızda oluşturur.  
  
     Daha fazla bilgi için bkz: [/MP (birden çok süreçle derleme)](/cpp/build/reference/mp-build-with-multiple-processes). Ayrıca bkz **ProcessorNumber** bu tabloda parametresi.  
  
-   **ObjectFileName**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Bir nesne (.obj) dosya adı veya varsayılan yerine kullanılacak dizini belirtir.  
  
     Daha fazla bilgi için bkz: [/Fo (nesne dosya adı)](/cpp/build/reference/fo-object-file-name).  
  
-   **ObjectFiles**  
  
     İsteğe bağlı **String []** parametresi.  
  
     Nesne dosyaların listesi.  
  
-   **OmitDefaultLibName**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, nesne (.obj) dosyası varsayılan C çalışma zamanı kitaplığı adından atlar. Varsayılan olarak, derleyici kitaplığının adı doğru kitaplık bağlayıcıya yönlendirmek için .obj dosyasına yerleştirir.  
  
     Daha fazla bilgi için bkz: [/Zl (varsayılan kitaplık adını atla)](/cpp/build/reference/zl-omit-default-library-name).  
  
-   **OmitFramePointers**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, çerçeve işaretçisi çağrı yığınında oluşturulmasını önler.  
  
     Daha fazla bilgi için bkz: [/Oy (Çerçeve işaretçisini atlama)](/cpp/build/reference/oy-frame-pointer-omission).  
  
-   **OpenMPSupport**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, OpenMP yan tümceleri ve yönergeleri işlemek derleyici neden olur.  
  
     Daha fazla bilgi için bkz: [/OpenMP (OpenMP 2.0 desteğini etkinleştir)](/cpp/build/reference/openmp-enable-openmp-2-0-support).  
  
-   **En iyi duruma getirme**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Çeşitli kod iyileştirmelerini hızı ve boyutunu belirtir.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **Devre dışı** - **/Od**  
  
    -   **MinSpace** - **/O1**  
  
    -   **MaxSpeed** - **O2**  
  
    -   **Tam** - **/Ox**  
  
     Daha fazla bilgi için bkz: [/O seçenekler (kodu İyileştir)](/cpp/build/reference/o-options-optimize-code).  
  
-   **PrecompiledHeader**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Oluşturabilir veya derleme sırasında önceden derlenmiş üst bilgi (.pch) dosyasını kullanabilirsiniz.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **NotUsing** - *\<yok >*  
  
    -   **Oluşturma** - **/Yc**  
  
    -   **Kullanım** - **/Yu**  
  
     Daha fazla bilgi için bkz: [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](/cpp/build/reference/yc-create-precompiled-header-file) ve [/Yu (önceden derlenmiş üst bilgi dosyasını kullanma)](/cpp/build/reference/yu-use-precompiled-header-file). Ayrıca bkz **PrecompiledHeaderFile** ve **PrecompiledHeaderOutputFile** bu tabloda parametreler.  
  
-   **PrecompiledHeaderFile**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Oluşturmak veya kullanmak için önceden derlenmiş üstbilgi dosyası adı belirtir.  
  
     Daha fazla bilgi için bkz: [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](/cpp/build/reference/yc-create-precompiled-header-file) ve [/Yu (önceden derlenmiş üst bilgi dosyasını kullanma)](/cpp/build/reference/yu-use-precompiled-header-file).  
  
-   **PrecompiledHeaderOutputFile**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Varsayılan yol adı yerine bir önceden derlenmiş üst bilgisi için bir yol adı belirtir.  
  
     Daha fazla bilgi için bkz: [/Fp (adı. PCH dosyası)](/cpp/build/reference/fp-name-dot-pch-file).  
  
-   **PreprocessKeepComments**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, ön işleme sırasında açıklamaları korur.  
  
     Daha fazla bilgi için bkz: [/C (korumak açıklamaları sırasındaki)](/cpp/build/reference/c-preserve-comments-during-preprocessing).  
  
-   **PreprocessorDefinitions**  
  
     İsteğe bağlı `String[]` parametresi.  
  
     Kaynak dosyanızı önişlem simgesi tanımlar.  
  
     Daha fazla bilgi için bkz: [/D (önişlemci tanımları)](/cpp/build/reference/d-preprocessor-definitions).  
  
-   **PreprocessOutput**  
  
     İsteğe bağlı `ITaskItem[]` parametresi.  
  
     Tüketilen ve görevler tarafından gösterilen önişlemci çıktısı öğeleri dizisi tanımlar.  
  
-   **PreprocessOutputPath**  
  
     İsteğe bağlı `String` parametresi.  
  
     Çıktı dosyasına adını belirtir **PreprocessToFile** parametresi önceden işlenmiş çıktısı yazar.  
  
     Daha fazla bilgi için bkz: [/Fi (çıktı dosyası adını Önişle)](/cpp/build/reference/fi-preprocess-output-file-name).  
  
-   **PreprocessSuppressLineNumbers**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, C ve C++ kaynak dosyalarını preprocesses ve standart çıktı aygıtına önceden işlenmiş dosyalarını kopyalar.  
  
     Daha fazla bilgi için bkz: [/EP (#line yönergeleri olmadan stdout'ta Önişle)](/cpp/build/reference/ep-preprocess-to-stdout-without-hash-line-directives).  
  
-   **PreprocessToFile**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, C ve C++ kaynak dosyalarını preprocesses ve önceden işlenmiş çıktıyı bir dosyaya yazar.  
  
     Daha fazla bilgi için bkz: [/P (dosyaya Önişle)](/cpp/build/reference/p-preprocess-to-a-file).  
  
-   **ProcessorNumber**  
  
     İsteğe bağlı `Integer` parametresi.  
  
     En fazla çok işlemcili bir derlemede kullanmak için işlemci sayısını belirtir. Bu parametre ile birlikte kullanmak **MultiProcessorCompilation** parametresi.  
  
-   **ProgramDataBaseFileName**  
  
     İsteğe bağlı `String` parametresi.  
  
     Program veritabanı (PDB) dosyası için bir dosya adı belirtir.  
  
     Daha fazla bilgi için bkz: [/Fd (Program veritabanı dosya adı)](/cpp/build/reference/fd-program-database-file-name).  
  
-   **RuntimeLibrary**  
  
     İsteğe bağlı `String` parametresi.  
  
     Birden çok iş parçacıklı bir modül DLL ve çalışma zamanı kitaplığı tekil veya hata ayıklama sürümleri seçer olup olmadığını gösterir.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **MultiThreaded** - **/MT**  
  
    -   **MultiThreadedDebug** - **/MTd**  
  
    -   **MultiThreadedDLL** - **/MD**  
  
    -   **MultiThreadedDebugDLL** - **/MDd**  
  
     Daha fazla bilgi için bkz: [/MD, / MT, /LD (çalışma zamanı kitaplığını kullan)](/cpp/build/reference/md-mt-ld-use-run-time-library).  
  
-   **RuntimeTypeInfo**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, çalışma zamanında (çalışma zamanı türü bilgileri) C++ nesne türlerini denetlemek için kod ekler.  
  
     Daha fazla bilgi için bkz: [/GR (çalışma zamanı türü bilgileri etkinleştir)](/cpp/build/reference/gr-enable-run-time-type-information).  
  
-   **Showıncludes**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, dosyaları Ekle listesini çıkarmak derleyici neden olur.  
  
     Daha fazla bilgi için bkz: [/showıncludes (liste dosyaları içerir)](/cpp/build/reference/showincludes-list-include-files).  
  
-   **SmallerTypeCheck**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, bir değer küçük bir veri türü için atanan ve veri kaybına neden olan bir çalışma zamanı hata bildirir.  
  
     Daha fazla bilgi için bkz: **/RTCc** seçeneğini [eş yordamlarla/RTC (çalışma zamanı hata denetler)](/cpp/build/reference/rtc-run-time-error-checks).  
  
-   **Kaynakları**  
  
     Gerekli `ITaskItem[]` parametresi.  
  
     Kaynak dosyaları boşluklarla ayrılmış listesini belirtir.  
  
-   **StringPooling**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, program görüntüde aynı dize bir kopyasını oluşturmak derleyici sağlar.  
  
     Daha fazla bilgi için bkz: [/GF (yinelenen dizeleri ortadan)](/cpp/build/reference/gf-eliminate-duplicate-strings).  
  
-   **StructMemberAlignment**  
  
     İsteğe bağlı `String` parametresi.  
  
     Tüm üyeler için bayt hizalama bir yapısında belirtir.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **Default** - **/Zp1**  
  
    -   **1Byte** - **/Zp1**  
  
    -   **2Bytes** - **/Zp2**  
  
    -   **4Bytes** - **/Zp4**  
  
    -   **8Bytes** - **/Zp8**  
  
    -   **16Bytes** - **/Zp16**  
  
     Daha fazla bilgi için bkz: [/Zp (yapı üyesi hizalama)](/cpp/build/reference/zp-struct-member-alignment).  
  
-   **SuppressStartupBanner**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, görev başladığında telif hakkı ve sürüm numarası iletisini görüntülenmesini engeller.  
  
     Daha fazla bilgi için bkz: [/nologo (Başlangıç başlığını gösterme) (C/C++)](/cpp/build/reference/nologo-suppress-startup-banner-c-cpp).  
  
-   **TrackerLogDirectory**  
  
     İsteğe bağlı `String` parametresi.  
  
     Bu görev için izleme günlüklerinin depolandığı Ara dizini belirtir.  
  
     Daha fazla bilgi için bkz: **TLogReadFiles** ve **TLogWriteFiles** bu tabloda parametreler.  
  
-   **TreatSpecificWarningsAsErrors**  
  
     İsteğe bağlı **String []** parametresi.  
  
     Belirtilen listesi derleyici uyarıları hata olarak değerlendirir.  
  
     Daha fazla bilgi için bkz: **/we** `n` seçeneğini [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, wln, /wd, / biz, /wo, /Wv, /WX (uyarı düzeyi)](/cpp/build/reference/compiler-option-warning-level).  
  
-   **TreatWarningAsError**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, tüm derleyici uyarıları hata olarak ele alın.  
  
     Daha fazla bilgi için bkz: **/WX** seçeneğini [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, wln, /wd, / biz, /wo, /Wv, /WX (uyarı düzeyi)](/cpp/build/reference/compiler-option-warning-level).  
  
-   **TreatWChar_tAsBuiltInType**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, işle `wchar_t` yerel tür türü.  
  
     Daha fazla bilgi için bkz: [/ZC: wchar_t (wchar_t yerel tür olan)](/cpp/build/reference/zc-wchar-t-wchar-t-is-native-type).  
  
-   **UndefineAllPreprocessorDefinitions**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, derleyici tanımlar Microsoft özgü simgeleri undefines.  
  
     Daha fazla bilgi için bkz: **/u** seçeneğini [/U, /u (simge tanımlarını Kaldır)](/cpp/build/reference/u-u-undefine-symbols).  
  
-   **UndefinePreprocessorDefinitions**  
  
     İsteğe bağlı `String[]` parametresi.  
  
     Tanımsız için bir veya daha fazla önişlemci sembolleri listesini belirtir.  
  
     Daha fazla bilgi için bkz: **/U** seçeneğini [/U, /u (simge tanımlarını Kaldır)](/cpp/build/reference/u-u-undefine-symbols).  
  
-   **UseFullPaths**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, kaynak kodu dosyaları tam yolunu geçirilen tanılama derleyici görüntüler.  
  
     Daha fazla bilgi için bkz: [/FC (tam yolu, kaynak kodu dosyasının tanılamadaki)](/cpp/build/reference/fc-full-path-of-source-code-file-in-diagnostics).  
  
-   **UseUnicodeForAssemblerListing**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, çıkış dosyasının UTF-8 biçiminde oluşturulmasına neden olur.  
  
     Daha fazla bilgi için bkz: **/FAu** seçeneğini [/FA, /Fa (listeleme dosyası)](/cpp/build/reference/fa-fa-listing-file).  
  
-   **WarningLevel**  
  
     İsteğe bağlı `String` parametresi.  
  
     Derleyici tarafından üretilen bir uyarı düzeyini belirtir.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **TurnOffAllWarnings** - **/W0**  
  
    -   **Level1** - **/W1**  
  
    -   **Level2** - **/W2**  
  
    -   **Level3** - **/W3**  
  
    -   **Level4** - **/W4**  
  
    -   **EnableAllWarnings** - **/Wall**  
  
     Daha fazla bilgi için bkz: **/W***n* seçeneğini [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, wln, /wd, / biz, /wo, /Wv, /WX (uyarı düzeyi)](/cpp/build/reference/compiler-option-warning-level).  
  
-   **WholeProgramOptimization**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, bütün program iyileştirmesi sağlar.  
  
     Daha fazla bilgi için bkz: [/GL (bütün Program iyileştirmesi)](/cpp/build/reference/gl-whole-program-optimization).  
  
-   **XMLDocumentationFileName**  
  
     İsteğe bağlı `String` parametresi.  
  
     Oluşturulan XML belge dosyalarını adını belirtir. Bu parametre bir dosya veya dizin adı olabilir.  
  
     Daha fazla bilgi için bkz: `name` değişkeninde [/doc (işlem belgesi açıklamaları) (C/C++)](/cpp/build/reference/doc-process-documentation-comments-c-cpp). Ayrıca bkz. **GenerateXMLDocumentationFiles** bu tabloda parametresi.  
  
-   **MinimalRebuildFromTracking**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, izlenen bir artımlı derleme; yapılır `false`, yeniden gerçekleştirilir.  
  
-   **TLogReadFiles**  
  
     İsteğe bağlı `ITaskItem[]` parametresi.  
  
     Temsil eden öğelerinin bir dizisini belirtir *günlükleri izleme dosyasını okumak*.  
  
     Dosyayı oku izleme günlüğü (.tlog), bir görev tarafından okunur ve artımlı derlemeler desteklemek için proje oluşturma sistemi tarafından kullanılan giriş dosyaların adlarını içerir. Daha fazla bilgi için bkz: **TrackerLogDirectory** ve **TrackFileAccess** bu tabloda parametreler.  
  
-   **TLogWriteFiles**  
  
     İsteğe bağlı `ITaskItem[]` parametresi.  
  
     Temsil eden öğelerinin bir dizisini belirtir *günlükleri izleme dosyasına yazma*.  
  
     Bir yazma dosya izleme günlüğü (.tlog), bir görev tarafından yazılır ve Proje yapı sistem tarafından artımlı derlemeler desteklemek için kullanılır ve çıkış dosyalarının adını içerir. Daha fazla bilgi için bkz: **TrackerLogDirectory** ve **TrackFileAccess** bu tabloda parametreler.  
  
-   **TrackFileAccess**  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, dosya erişimi desenleri izler.  
  
     Daha fazla bilgi için bkz: **TLogReadFiles** ve **TLogWriteFiles** bu tabloda parametreler.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)