---
title: "Bağlantı görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.ForceFileOutput
- VC.Project.VCLinkerTool.LinkStatus
- VC.Project.VCLinkerTool.CLRUnmanagedCodeCheck
- VC.Project.VCLinkerTool.SpecifySectionAttributes
- VC.Project.VCLinkerTool.SupportNobindOfDelayLoadedDLL
- VC.Project.VCLinkerTool.MinimumRequiredVersion
- VC.Project.VCLinkerTool.PerUserRedirection
- VC.Project.VCLinkerTool.CreateHotPatchableImage
- VC.Project.VCLinkerTool.DataExecutionPrevention
- VC.Project.VCLinkerTool.TreatLinkerWarningsAsErrors
- vc.task.link
- VC.Project.VCLinkerTool.ImageHasSafeExceptionHandlers
- VC.Project.VCLinkerTool.CLRSupportLastError
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild (Visual C++), Link task
- Link task (MSBuild (Visual C++))
ms.assetid: 0a61f168-3113-4fa7-83a3-d9142e2a33f8
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: a5c92a6faa558445bf85637f2e51ab7fb0e7a856
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="link-task"></a>Bağlantı Görevi
Visual C++ bağlayıcı aracı sarmalar link.exe. Bağlayıcı aracı ortak nesne dosyası biçimi (COFF) nesne dosyaları ve kitaplıkları bir yürütülebilir dosyanın (.exe) dosyayı oluşturmak için veya bir dinamik bağlantı kitaplığı (DLL) bağlar. Daha fazla bilgi için bkz: [bağlayıcı seçenekleri](/cpp/build/reference/linker-options).  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır **bağlantı** görev. Çoğu görevi parametreleri ve parametreleri, birkaç kümelerini bir komut satırı seçeneğine karşılık gelir.  
  
-   **AdditionalDependencies**  
  
     İsteğe bağlı **String []** parametresi.  
  
     Komut eklemek için giriş dosyaların bir listesini belirtir.  
  
     Daha fazla bilgi için bkz: [LINK giriş dosyaları](/cpp/build/reference/link-input-files).  
  
-   **AdditionalLibraryDirectories**  
  
     İsteğe bağlı **String []** parametresi.  
  
     Ortam Kitaplığı yol geçersiz kılar. Bir dizin adı belirtin.  
  
     Daha fazla bilgi için bkz: [/Libpath (ek Libpath)](/cpp/build/reference/libpath-additional-libpath).  
  
-   **AdditionalManifestDependencies**  
  
     İsteğe bağlı **String []** parametresi.  
  
     Yerleştirilecek özniteliklerini belirtir `dependency` bildirim dosyasının bölümü.  
  
     Daha fazla bilgi için bkz: [/MANIFESTDEPENDENCY (bildirim bağımlılıklarını belirtin)](/cpp/build/reference/manifestdependency-specify-manifest-dependencies). "Publisher yapılandırma dosyalarına" Ayrıca bakın [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
-   **AdditionalOptions**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Komut satırında belirtilen bağlayıcı seçenekleri listesi. Örneğin, **"*** / seçenek 1 /option2 /option#*". Diğer tarafından temsil edilmez bağlayıcı seçeneklerini belirtmek için bu parametreyi kullanın **bağlantı** görev parametresi.  
  
     Daha fazla bilgi için bkz: [bağlayıcı seçenekleri](/cpp/build/reference/linker-options).  
  
-   **AddModuleNamesToAssembly**  
  
     İsteğe bağlı **String []** parametresi.  
  
     Bir modül başvurusu bir derleme ekler.  
  
     Daha fazla bilgi için bkz: [/ASSEMBLYMODULE (derlemeye MSIL Modülü Ekle)](/cpp/build/reference/assemblymodule-add-a-msil-module-to-the-assembly).  
  
-   **AllowIsolation**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, işletim sisteminin aramaları bildirim neden olur ve yükler. Varsa `false`, hiçbir bildirim boşmuş gibi DLL'leri yüklendiğini gösterir.  
  
     Daha fazla bilgi için bkz: [/ALLOWISOLATION (bildirim arama)](/cpp/build/reference/allowisolation-manifest-lookup).  
  
-   **AssemblyDebug**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, yayar **DebuggableAttribute** hata ayıklama bilgilerini izleme ve devre dışı bırakır JIT iyileştirmesi birlikte özniteliği. Varsa `false`, yayar **DebuggableAttribute** özniteliği ancak hata ayıklama bilgileri izlemeyi devre dışı bırakır ve JIT iyileştirmeler sağlar.  
  
     Daha fazla bilgi için bkz: [/ASSEMBLYDEBUG (DebuggableAttribute ekleme)](/cpp/build/reference/assemblydebug-add-debuggableattribute).  
  
-   **Assemblylınkresource**  
  
     İsteğe bağlı **String []** parametresi.  
  
     .NET Framework kaynağına bağlantı çıktı dosyasında oluşturur; Kaynak dosyanın çıkış dosyasında yerleştirilmedi. Kaynağın adını belirtin.  
  
     Daha fazla bilgi için bkz: [/ASSEMBLYLINKRESOURCE (.NET Framework kaynağına bağlantı)](/cpp/build/reference/assemblylinkresource-link-to-dotnet-framework-resource).  
  
-   **AttributeFileTracking**  
  
     Örtük **Boolean** parametresi.  
  
     Bağlantı artımlı bir kişinin davranışını yakalamak için izleme daha derin dosyası sağlar. Her zaman döndürür `true`.  
  
-   **BaseAddress**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Program veya oluşturulmakta DLL taban adresi ayarlar. Belirtin `{address[,size] | @filename,key}`.  
  
     Daha fazla bilgi için bkz: [/BASE (Temel adres)](/cpp/build/reference/base-base-address).  
  
-   **BuildingInIDE**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     TRUE ise, MSBuild IDE içinden çağrılan gösterir. Aksi takdirde, MSBuild komut satırından çağrıldığını gösterir.  
  
     Bu parametre eşdeğer bağlayıcı seçeneği vardır.  
  
-   **CLRImageType**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Ortak dil çalışma zamanı (CLR) resim türünü ayarlar.  
  
     Her biri için bir bağlayıcı seçeneği karşılık gelen aşağıdaki değerlerden birini belirtin.  
  
    -   **Varsayılan** - *\<yok >*  
  
    -   **ForceIJWImage** - **/CLRIMAGETYPE:IJW**  
  
    -   **ForcePureILImage** - **/CLRIMAGETYPE:PURE**  
  
    -   **ForceSafeILImage** - **/CLRIMAGETYPE:SAFE**  
  
     Daha fazla bilgi için bkz: [/CLRIMAGETYPE (belirtin, CLR Resim türünde)](/cpp/build/reference/clrimagetype-specify-type-of-clr-image).  
  
-   **CLRSupportLastError**  
  
     İsteğe bağlı **dize** parametresi.  
  
     P/Invoke mekanizma çağrılan işlevler son hata kodunu korur.  
  
     Her biri için bir bağlayıcı seçeneği karşılık gelen aşağıdaki değerlerden birini belirtin.  
  
    -   **Etkin** - **/CLRSupportLastError**  
  
    -   **Devre dışı** - **/CLRSupportLastError:NO**  
  
    -   **SystemDlls** - **/CLRSupportLastError:SYSTEMDLL**  
  
     Daha fazla bilgi için bkz: [/CLRSUPPORTLASTERROR (korumak için son hata kodunu PInvoke çağrıları)](/cpp/build/reference/clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls).  
  
-   **CLRThreadAttribute**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Açıkça CLR programınızın giriş noktası için iş parçacığı özniteliği belirtir.  
  
     Her biri için bir bağlayıcı seçeneği karşılık gelen aşağıdaki değerlerden birini belirtin.  
  
    -   **DefaultThreadingAttribute** - **/CLRTHREADATTRIBUTE: yok**  
  
    -   **MTAThreadingAttribute** - **/CLRTHREADATTRIBUTE:MTA**  
  
    -   **STAThreadingAttribute** - **/CLRTHREADATTRIBUTE:STA**  
  
     Daha fazla bilgi için bkz: [/CLRTHREADATTRIBUTE (CLR iş parçacığı özniteliğini Ayarla)](/cpp/build/reference/clrthreadattribute-set-clr-thread-attribute).  
  
-   **CLRUnmanagedCodeCheck**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Bağlayıcı uygulanıp uygulanmayacağını belirtir **SuppressUnmanagedCodeSecurityAttribute** bağlayıcı oluşturulan P/Invoke çağrılarını yönetilen koddan yerel DLL'leri için.  
  
     Daha fazla bilgi için bkz: [/CLRUNMANAGEDCODECHECK (SupressUnmanagedCodeSecurityAttribute ekleme)](/cpp/build/reference/clrunmanagedcodecheck-add-supressunmanagedcodesecurityattribute).  
  
-   **CreateHotPatchableImage**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Bir görüntü anında düzeltme için hazırlar.  
  
     Bir bağlayıcı seçeneği karşılık gelen aşağıdaki değerlerden birini belirtin.  
  
    -   **Etkin** - **/FUNCTIONPADMIN**  
  
    -   **X86Image** - **/FUNCTIONPADMIN:5**  
  
    -   **X64Image** - **/FUNCTIONPADMIN:6**  
  
    -   **ItaniumImage** - **/FUNCTIONPADMIN:16**  
  
     Daha fazla bilgi için bkz: [/FUNCTIONPADMIN (düzeltme eki eklenebilen görüntü oluşturma)](/cpp/build/reference/functionpadmin-create-hotpatchable-image).  
  
-   **DataExecutionPrevention**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, yürütülebilir bir dosya Windows Veri Yürütme Engellemesi özelliği ile uyumlu olacak şekilde test edilmiştir gösterir.  
  
     Daha fazla bilgi için bkz: [/NXCOMPAT (Veri Yürütme Engellemesi uyumlu)](/cpp/build/reference/nxcompat-compatible-with-data-execution-prevention).  
  
-   **DelayLoadDLLs**  
  
     İsteğe bağlı **String []** parametresi.  
  
     Bu parametre neden *Gecikmeli yüklemesi* dll. Gecikme yükü DLL adını belirtin.  
  
     Daha fazla bilgi için bkz: [/DELAYLOAD (yükü içe aktarmayı Geciktir)](/cpp/build/reference/delayload-delay-load-import).  
  
-   **DelaySign**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, bir derlemeyi kısmen imzalar. Varsayılan değer olan `false`.  
  
     Daha fazla bilgi için bkz: [/delaysign (derlemenin kısmen imzalayın)](/cpp/build/reference/delaysign-partially-sign-an-assembly).  
  
-   **Driver**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Bir Windows NT Çekirdek modu sürücüsü oluşturmak için bu parametreyi belirtin.  
  
     Her biri için bir bağlayıcı seçeneği karşılık gelen aşağıdaki değerlerden birini belirtin.  
  
    -   **NotSet** - *\<none>*  
  
    -   **Sürücü** - **Driver**  
  
    -   **UpOnly** - **/DRIVER:UPONLY**  
  
    -   **WDM** - **/DRIVER:WDM**  
  
     Daha fazla bilgi için bkz: [Driver (Windows NT Çekirdek modu sürücüsü)](/cpp/build/reference/driver-windows-nt-kernel-mode-driver).  
  
-   **EmbedManagedResourceFile**  
  
     İsteğe bağlı **String []** parametresi.  
  
     Kaynak dosyası, bir derlemede katıştırır. Gereken kaynak dosya adı belirtin. İsteğe bağlı olarak kaynak yüklemek için kullanılan mantıksal ad belirtin ve **özel** derleme bildiriminde kaynak dosyası özel gösterir seçeneği.  
  
     Daha fazla bilgi için bkz: [/ASSEMBLYRESOURCE (yönetilen kaynağı katıştır)](/cpp/build/reference/assemblyresource-embed-a-managed-resource).  
  
-   **EnableCOMDATFolding**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, aynı comdat'ı Katlama sağlar.  
  
     Daha fazla bilgi için bkz: `ICF[= iterations]` bağımsız değişkeni [OPT (iyileştirmeler)](/cpp/build/reference/opt-optimizations).  
  
-   **EnableUAC**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, kullanıcı hesabı denetimi (UAC) bilgisi program bildiriminde katıştırılır belirtir.  
  
     Daha fazla bilgi için bkz: [/MANIFESTUAC (bildirimdeki UAC bilgilerini katıştırır)](/cpp/build/reference/manifestuac-embeds-uac-information-in-manifest).  
  
-   **EntryPointSymbol**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Bir .exe dosyası ya da DLL için başlangıç adresi olarak bir giriş noktası işlevi belirtir. İşlev adı parametre değeri olarak belirtin.  
  
     Daha fazla bilgi için bkz: [/Entry (giriş noktası simgesi)](/cpp/build/reference/entry-entry-point-symbol).  
  
-   **FixedBaseAddress**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, bir program veya yüklenebilir DLL yalnızca tercih edilen kendi temel adrese oluşturur.  
  
     Daha fazla bilgi için bkz: [/FIXED (sabit temel adres)](/cpp/build/reference/fixed-fixed-base-address).  
  
-   **ForceFileOutput**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Geçerli .exe dosyası oluşturmak için bağlayıcı söyler veya DLL bir simge başvurulan ancak olsa bile tanımlı, ya da tanımlanmış çarpın.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **Etkin** -   **/ZORLA**  
  
    -   **MultiplyDefinedSymbolOnly** - **/FORCE:MULTIPLE**  
  
    -   **UndefinedSymbolOnly** -   **/FORCE: ÇÖZÜMLENMEMİŞ**  
  
     Daha fazla bilgi için bkz: [/Force (dosya çıktısını zorla)](/cpp/build/reference/force-force-file-output).  
  
-   **ForceSymbolReferences**  
  
     İsteğe bağlı **String []** parametresi.  
  
     Bu parametre, belirtilen bir simgeyi sembol tablosuna eklemek için bağlayıcı söyler.  
  
     Daha fazla bilgi için bkz: [exclude dışlama kuralı belirler (simge başvurularını zorla)](/cpp/build/reference/include-force-symbol-references).  
  
-   **FunctionOrder**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Bu parametre, önceden belirlenmiş bir sırayla görüntüye belirtilen paketlenmiş işlevler (COMDATs) koyarak programınızı iyileştirir.  
  
     Daha fazla bilgi için bkz: [/ORDER (Put işlevleri Sırala)](/cpp/build/reference/order-put-functions-in-order).  
  
-   **GenerateDebugInformation**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, .exe dosya ya da DLL için hata ayıklama bilgileri oluşturur.  
  
     Daha fazla bilgi için bkz: [/Debug (hata ayıklama bilgisi üret)](/cpp/build/reference/debug-generate-debug-info).  
  
-   **GenerateManifest**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, yan yana bildirim dosyası oluşturur.  
  
     Daha fazla bilgi için bkz: [/MANIFEST (oluşturma yan yana derleme bildirimi)](/cpp/build/reference/manifest-create-side-by-side-assembly-manifest).  
  
-   **GenerateMapFile**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, oluşturur bir *eşleme dosyası*. Dosya adı uzantısı, eşleme dosyası .map ' dir.  
  
     Daha fazla bilgi için bkz: [/Map (eşlem dosyası oluştur)](/cpp/build/reference/map-generate-mapfile).  
  
-   **HeapCommitSize**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Aynı anda ayrılacak yığında fiziksel bellek miktarını belirtir.  
  
     Daha fazla bilgi için bkz: `commit` değişkeninde [/HEAP (yığın boyutunu Ayarla)](/cpp/build/reference/heap-set-heap-size). Ayrıca bkz **HeapReserveSize** parametresi.  
  
-   **HeapReserveSize**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Toplam yığın ayırma sanal bellek miktarını belirtir.  
  
     Daha fazla bilgi için bkz: `reserve` değişkeninde [/HEAP (yığın boyutunu Ayarla)](/cpp/build/reference/heap-set-heap-size). Ayrıca bkz **HeapCommitSize** bu tabloda parametresi.  
  
-   **IgnoreAllDefaultLibraries**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, kaldırmak için bağlayıcı söyler veya daha fazla varsayılan kitaplık kitaplıkları listesinden, ne zaman arar dış başvuruları giderir.  
  
     Daha fazla bilgi için bkz: [/NODEFAULTLIB (kitaplıkları yoksay)](/cpp/build/reference/nodefaultlib-ignore-libraries).  
  
-   **IgnoreEmbeddedIDL**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, kaynak kodunda IDL öznitelikleri bir .idl dosyasına işlenmesi gerektiğini değil belirtir.  
  
     Daha fazla bilgi için bkz: [/IGNOREIDL (verme işlemi öznitelikler MIDL)](/cpp/build/reference/ignoreidl-don-t-process-attributes-into-midl).  
  
-   **IgnoreImportLibrary**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, bu yapılandırma tarafından oluşturulan içeri aktarma kitaplığını bağımlı projelerine içeri aktarılması gerektiğini değil olduğunu belirtir.  
  
     Bu parametre için bir bağlayıcı seçeneği karşılık gelmiyor.  
  
-   **IgnoreSpecificDefaultLibraries**  
  
     İsteğe bağlı **String []** parametresi.  
  
     Bir veya daha fazla yok saymak için varsayılan kitaplık adını belirtir. Birden çok kitaplıkları noktalı virgülle ayırın.  
  
     Daha fazla bilgi için bkz: [/NODEFAULTLIB (kitaplıkları yoksay)](/cpp/build/reference/nodefaultlib-ignore-libraries).  
  
-   **ImageHasSafeExceptionHandlers**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, yalnızca, ayrıca görüntünün güvenli özel durum işleyicileri oluşan bir tablo oluşturabilir, bağlayıcı bir görüntü üretiyor.  
  
     Daha fazla bilgi için bkz: [SAFESEH (görüntüde güvenli özel durum işleyicileri vardır)](/cpp/build/reference/safeseh-image-has-safe-exception-handlers).  
  
-   **ImportLibrary**  
  
     Varsayılan kitaplık adını değiştirir kullanıcı tarafından belirtilen içeri aktarma kitaplığı adı.  
  
     Daha fazla bilgi için bkz: [/IMPLIB (içeri aktarma kitaplığını Adlandır)](/cpp/build/reference/implib-name-import-library).  
  
-   **KeyContainer**  
  
     İsteğe bağlı **dize** parametresi.  
  
     İmzalı bir derleme için olan anahtar içeriyor kapsayıcı.  
  
     Daha fazla bilgi için bkz: [/keycontainer (derlemeyi imzalamak için bir anahtar kapsayıcısı belirtin)](/cpp/build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly). Ayrıca bkz **KeyFile** bu tabloda parametresi.  
  
-   **KeyFile**  
  
     İsteğe bağlı **dize** parametresi.  
  
     İmzalı bir derleme için anahtarı içeren dosyayı belirtir.  
  
     Daha fazla bilgi için bkz: [/keyfile (anahtar belirtin veya anahtar çiftini derlemeyi imzalamak için)](/cpp/build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly). Ayrıca bkz **KeyContainer** parametresi.  
  
-   **LargeAddressAware**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, uygulama adresleri 2 gigabayttan büyük işleyebilir.  
  
     Daha fazla bilgi için bkz: [/LARGEADDRESSAWARE (büyük adresleri işlemek)](/cpp/build/reference/largeaddressaware-handle-large-addresses).  
  
-   **LinkDLL**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, DLL ana çıktı dosyası olarak oluşturur.  
  
     Daha fazla bilgi için bkz: [/dll (DLL derleme)](/cpp/build/reference/dll-build-a-dll).  
  
-   **LinkErrorReporting**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Doğrudan Microsoft'a iç derleyici hatası (çok) bilgileri sağlamanıza olanak tanır.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **NoErrorReport** -   **/errorreport: yok**  
  
    -   **PromptImmediately** - **/ERRORREPORT:PROMPT**  
  
    -   **QueueForNextLogin** - **/ERRORREPORT:QUEUE**  
  
    -   **SendErrorReport** - **/ERRORREPORT:SEND**  
  
     Daha fazla bilgi için bkz: [/errorreport (dahili bağlayıcı hatalarını raporla)](/cpp/build/reference/errorreport-report-internal-linker-errors).  
  
-   **LinkIncremental**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, artımlı bağlantılandırma sağlar.  
  
     Daha fazla bilgi için bkz: [/INCREMENTAL (artımlı bağlantı)](/cpp/build/reference/incremental-link-incrementally).  
  
-   **LinkLibraryDependencies**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, proje bağımlılıklarını kitaplığı çıkışlarından içinde otomatik olarak bağlanan belirtir.  
  
     Bu parametre için bir bağlayıcı seçeneği karşılık gelmiyor.  
  
-   **LinkStatus**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, bağlayıcı bağlantıyı yüzdesini tamamlandıktan gösteren bir İlerleme göstergesi görüntülemek için olduğunu belirtir.  
  
     Daha fazla bilgi için bkz: `STATUS` bağımsız değişkeni [/LTCG (bağlama zamanı kodu oluşturma)](/cpp/build/reference/ltcg-link-time-code-generation).  
  
-   **LinkTimeCodeGeneration**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Profil temelli İyileştirme seçeneklerini belirtir.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **Varsayılan** - *\<yok >*  
  
    -   **UseLinkTimeCodeGeneration** - **/LTCG**  
  
    -   **PGInstrument** - **/LTCG:PGInstrument**  
  
    -   **PGOptimization** - **/LTCG:PGOptimize**  
  
    -   **PGUpdate**  
  
         \-**/LTCG:PGUpdate**  
  
     Daha fazla bilgi için bkz: [/LTCG (bağlama zamanı kodu oluşturma)](/cpp/build/reference/ltcg-link-time-code-generation).  
  
-   **Manıfestfıle**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Varsayılan yayılma dosyası adı belirtilen dosya adına değiştirir.  
  
     Daha fazla bilgi için bkz: [/MANIFESTFILE (bildirim dosyasını Adlandır)](/cpp/build/reference/manifestfile-name-manifest-file).  
  
-   **MapExports**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, dışarı aktarılan işlevleri eşleme dosyasında içerecek şekilde bağlayıcı söyler.  
  
     Daha fazla bilgi için bkz: `EXPORTS` bağımsız değişkeni [/MAPINFO (eşlem dosyası bilgileri dahil)](/cpp/build/reference/mapinfo-include-information-in-mapfile).  
  
-   **MapFileName**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Varsayılan eşleme dosya adı belirtilen dosya adına değiştirir.  
  
-   **MergedIDLBaseFileName**  
  
     İsteğe bağlı **dize** parametresi.  
  
     .İdl dosyasının dosya adı uzantısı ve dosya adını belirtir.  
  
     Daha fazla bilgi için bkz: [/IDLOUT (adı MIDL çıktı dosyalarını)](/cpp/build/reference/idlout-name-midl-output-files).  
  
-   **MergeSections**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Bir görüntü bölümlerde birleştirir. Belirtin `from-section=to-section`.  
  
     Daha fazla bilgi için bkz: [/Merge (bölümleri Birleştir)](/cpp/build/reference/merge-combine-sections).  
  
-   **MidlCommandFile**  
  
     İsteğe bağlı **dize** parametresi.  
  
     MIDL komut satırı seçenekleri içeren bir dosya adını belirtin.  
  
     Daha fazla bilgi için bkz: [/MIDL (MIDL komut satırı seçeneklerini belirtin)](/cpp/build/reference/midl-specify-midl-command-line-options).  
  
-   **MinimumRequiredVersion**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Gereken en düşük sürüm alt sisteminin belirtir. Bağımsız değişkenler, 0-65535 aralığında ondalık numaralarıdır.  
  
-   **ModuleDefinitionFile**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Adını belirtir. bir [modül tanım dosyası](/cpp/build/reference/module-definition-dot-def-files).  
  
     Daha fazla bilgi için bkz: [/def (modül tanım dosyasını belirtin)](/cpp/build/reference/def-specify-module-definition-file).  
  
-   **MSDOSStubFileName**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Belirtilen MS-DOS saplama programını bir Win32 programı ekler.  
  
     Daha fazla bilgi için bkz: [/stub (MS-DOS saplama dosyası adı)](/cpp/build/reference/stub-ms-dos-stub-file-name).  
  
-   **NoEntryPoint**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, yalnızca kaynak DLL belirtir.  
  
     Daha fazla bilgi için bkz: [/NOENTRY (No giriş noktası)](/cpp/build/reference/noentry-no-entry-point).  
  
-   **ObjectFiles**  
  
     Örtük **String []** parametresi.  
  
     Bağlantılı nesne dosyaları belirtir.  
  
-   **OptimizeReferences**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, İşlevler ve/veya hiçbir zaman başvurulan veri ortadan kaldırır.  
  
     Daha fazla bilgi için bkz: `REF` değişkeninde [OPT (iyileştirmeler)](/cpp/build/reference/opt-optimizations).  
  
-   **ÇıktıDosyası**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Varsayılan ad ve konum bağlayıcı oluşturur programın geçersiz kılar.  
  
     Daha fazla bilgi için bkz: [/OUT (çıktı dosyası adı)](/cpp/build/reference/out-output-file-name).  
  
-   **PerUserRedirection**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true` ve çıkış kaydedin etkin olduğunda, zorlar kayıt defteri Yazar **HKEY_CLASSES_ROOT** için yönlendirilecek **HKEY_CURRENT_USER**.  
  
-   **PreprocessOutput**  
  
     İsteğe bağlı `ITaskItem[]` parametresi.  
  
     Tüketilen ve görevler tarafından gösterilen önişlemci çıktısı öğeleri dizisi tanımlar.  
  
-   **PreventDllBinding**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, Bind.exe için bağlantılı görüntü bağlı gösterir.  
  
     Daha fazla bilgi için bkz: [/ALLOWBIND (DLL bağlamayı önleme)](/cpp/build/reference/allowbind-prevent-dll-binding).  
  
-   **Profili**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, kullanılabilir bir çıktı dosyası üreten **performans araçları** profil oluşturucu.  
  
     Daha fazla bilgi için bkz: [/profile (performans araçları Profil Oluşturucusu)](/cpp/build/reference/profile-performance-tools-profiler).  
  
-   **ProfileGuidedDatabase**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Çalışan program hakkında bilgi tutmak için kullanılan .pgd dosya adını belirtir  
  
     Daha fazla bilgi için bkz: [/PGD (Profile-Guided iyileştirmeler için veritabanını belirtin)](/cpp/build/reference/pgd-specify-database-for-profile-guided-optimizations).  
  
-   **ProgramDatabaseFile**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Bağlayıcı oluşturur program veritabanı (PDB) için bir ad belirtir.  
  
     Daha fazla bilgi için bkz: [/pdb (Program veritabanını kullan)](/cpp/build/reference/pdb-use-program-database).  
  
-   **RandomizedBaseAddress**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, rastgele yükleme zamanında kullanarak rebased yürütülebilir bir görüntü oluşturur *adres boşluğu düzeni rastgele seçimini* Windows (ASLR) özelliğidir.  
  
     Daha fazla bilgi için bkz: [/DYNAMICBASE (adres boşluğu düzeni rastgele'seçimini kullan)](/cpp/build/reference/dynamicbase-use-address-space-layout-randomization).  
  
-   **RegisterOutput**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, bu yapıyı birincil çıktısı kaydeder.  
  
-   **SectionAlignment**  
  
     İsteğe bağlı **tamsayı** parametresi.  
  
     Her bölümde programının doğrusal adres alanı hizalamasını belirtir. Parametre değeri bayt birim sayısı ve iki gücünü.  
  
     Daha fazla bilgi için bkz: [/ALIGN (bölüm hizalama)](/cpp/build/reference/align-section-alignment).  
  
-   **SetChecksum**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, bir .exe dosyası üstbilgisinde sağlama toplamı ayarlar.  
  
     Daha fazla bilgi için bkz: [/Release (sağlama toplamını Ayarla)](/cpp/build/reference/release-set-the-checksum).  
  
-   **ShowProgress**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Bağlama işlemi için ilerleme durumu raporları ayrıntı düzeyini belirtir.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **NotSet** - *\<none>*  
  
    -   **LinkVerbose** - **/VERBOSE**  
  
    -   **LinkVerboseLib** - **/VERBOSE:Lib**  
  
    -   **LinkVerboseICF** - **/VERBOSE:ICF**  
  
    -   **LinkVerboseREF** - **/VERBOSE:REF**  
  
    -   **LinkVerboseSAFESEH** - **/VERBOSE:SAFESEH**  
  
    -   **LinkVerboseCLR** - **/VERBOSE:CLR**  
  
     Daha fazla bilgi için bkz: [/verbose (ilerleme iletilerini Yazdır)](/cpp/build/reference/verbose-print-progress-messages).  
  
-   **Kaynakları**  
  
     Gerekli `ITaskItem[]` parametresi.  
  
     Tüketilen ve görevler tarafından gösterilen MSBuild kaynak dosya öğeleri dizisi tanımlar.  
  
-   **SpecifySectionAttributes**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Bir bölüm özniteliklerini belirtir. Bu bölümün .obj dosyasını derlendiğinde ayarlanan öznitelikleri geçersiz kılar.  
  
     Daha fazla bilgi için bkz: [/SECTION (Bölüm öznitelikleri belirtin)](/cpp/build/reference/section-specify-section-attributes).  
  
-   **StackCommitSize**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Ek bellek atandığında her tahsisini fiziksel bellek miktarını belirtir.  
  
     Daha fazla bilgi için bkz: `commit` bağımsız değişkeni [/STACK (yığın ayırmaları)](/cpp/build/reference/stack-stack-allocations).  
  
-   **StackReserveSize**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Toplam yığın ayırma boyutu sanal bellek miktarını belirtir.  
  
     Daha fazla bilgi için bkz: `reserve` bağımsız değişkeni [/STACK (yığın ayırmaları)](/cpp/build/reference/stack-stack-allocations).  
  
-   **StripPrivateSymbols**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Dağıtmak için müşterilerinize istediğiniz olmayan simgeler atlar ikinci bir program veritabanı (PDB) dosyası oluşturur. İkinci PDB dosya adını belirtin.  
  
     Daha fazla bilgi için bkz: [/PDBSTRIPPED (özel simgeleri)](/cpp/build/reference/pdbstripped-strip-private-symbols).  
  
-   **Alt sistemi**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Yürütülebilir dosya ortamını belirtir.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **NotSet** - *\<none>*  
  
    -   **Konsol** - **/SUBSYSTEM:CONSOLE**  
  
    -   **Windows** - **/SUBSYSTEM:WINDOWS**  
  
    -   **Yerel** - **/SUBSYSTEM:NATIVE**  
  
    -   **EFI uygulama** - **/SUBSYSTEM:EFI_APPLICATION**  
  
    -   **EFI Önyükleme hizmeti sürücü** - **/SUBSYSTEM:EFI_BOOT_SERVICE_DRIVER**  
  
    -   **EFI ROM** - **/SUBSYSTEM:EFI_ROM**  
  
    -   **EFI çalışma zamanı** - **/SUBSYSTEM:EFI_RUNTIME_DRIVER**  
  
    -   **WindowsCE** - **/SUBSYSTEM:WINDOWSCE**  
  
    -   **POSIX** - **/SUBSYSTEM:POSIX**  
  
     Daha fazla bilgi için bkz: [/SUBSYSTEM (alt sistemi belirtin)](/cpp/build/reference/subsystem-specify-subsystem).  
  
-   **SupportNobindOfDelayLoadedDLL**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, bir bağlanabilirse alma adresi Tablosu'nda (IAT) son görüntüde içermeyecek şekilde bağlayıcı söyler.  
  
     Daha fazla bilgi için bkz: `NOBIND` bağımsız değişkeni [/delay (gecikme yükü içe aktarma ayarları)](/cpp/build/reference/delay-delay-load-import-settings).  
  
-   **SupportUnloadOfDelayLoadedDLL**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, açık DLL'i kaldırma desteklemek için gecikme yükü yardımcı işlevini söyler.  
  
     Daha fazla bilgi için bkz: `UNLOAD` bağımsız değişkeni [/delay (gecikme yükü içe aktarma ayarları)](/cpp/build/reference/delay-delay-load-import-settings).  
  
-   **SuppressStartupBanner**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, görev başladığında telif hakkı ve sürüm numarası iletisini görüntülenmesini engeller.  
  
     Daha fazla bilgi için bkz: [/nologo (Başlangıç başlığını gösterme) (Bağlayıcı)](/cpp/build/reference/nologo-suppress-startup-banner-linker).  
  
-   **SwapRunFromCD**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, işletim sisteminin ilk bağlayıcı çıktısını takas dosyasına kopyalama bildirir ve sonra görüntüyü oradan çalıştırın.  
  
     Daha fazla bilgi için bkz: `CD` bağımsız değişkeni [/SWAPRUN (yük bağlayıcı çıktısını takas dosyasına)](/cpp/build/reference/swaprun-load-linker-output-to-swap-file). Ayrıca bkz **SwapRunFromNET** parametresi.  
  
-   **SwapRunFromNET**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, işletim sisteminin ilk bağlayıcı çıktısını takas dosyasına kopyalama bildirir ve sonra görüntüyü oradan çalıştırın.  
  
     Daha fazla bilgi için bkz: `NET` bağımsız değişkeni [/SWAPRUN (yük bağlayıcı çıktısını takas dosyasına)](/cpp/build/reference/swaprun-load-linker-output-to-swap-file). Ayrıca bkz **SwapRunFromCD** bu tabloda parametresi.  
  
-   **TargetMachine**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Hedef platformu program veya DLL belirtir.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **NotSet** - *\<none>*  
  
    -   **MachineARM** - **/MACHINE:ARM**  
  
    -   **MachineEBC** - **/MACHINE:EBC**  
  
    -   **MachineIA64** - **/MACHINE:IA64**  
  
    -   **MachineMIPS** - **/MACHINE:MIPS**  
  
    -   **MachineMIPS16** - **/MACHINE:MIPS16**  
  
    -   **MachineMIPSFPU** - **/MACHINE:MIPSFPU**  
  
    -   **MachineMIPSFPU16** - **/MACHINE:MIPSFPU16**  
  
    -   **MachineSH4** - **/MACHINE:SH4**  
  
    -   **MachineTHUMB** - **/MACHINE:THUMB**  
  
    -   **MachineX64** - **/MACHINE:X64**  
  
    -   **MachineX86** - **/MACHINE:X86**  
  
     Daha fazla bilgi için bkz: [/MACHINE (hedef platformu belirtin)](/cpp/build/reference/machine-specify-target-platform).  
  
-   **TerminalServerAware**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, program görüntünün isteğe bağlı üstbilgi IMAGE_OPTIONAL_HEADER DllCharacteristics alanında bir bayrak ayarlar. Terminal sunucusu bu bayrağı ayarlandığında, bazı değişiklikler uygulamaya yapmaz.  
  
     Daha fazla bilgi için bkz: [/TSAWARE (Terminal sunucusu kullanan uygulama oluştur)](/cpp/build/reference/tsaware-create-terminal-server-aware-application).  
  
-   **TrackerLogDirectory**  
  
     İsteğe bağlı **dize** parametresi.  
  
     İzleyici günlük dizinini belirtir.  
  
-   **TreatLinkerWarningAsErrors**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, hiçbir çıktı dosyası bağlayıcı bir uyarı oluşturursa oluşturulmasına neden olur.  
  
     Daha fazla bilgi için bkz: [/WX (Bağlayıcı uyarıları hata olarak değerlendir)](/cpp/build/reference/wx-treat-linker-warnings-as-errors).  
  
-   **TurnOffAssemblyGeneration**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, .NET Framework derleme olmadan geçerli çıktı dosyası için bir görüntü oluşturur.  
  
     Daha fazla bilgi için bkz: [/NOASSEMBLY (MSIL modülü Oluştur)](/cpp/build/reference/noassembly-create-a-msil-module).  
  
-   **TypeLibraryFile**  
  
     İsteğe bağlı **dize** parametresi.  
  
     .Tlb dosyası dosya adı uzantısı ve dosya adını belirtir. Bir dosya adı veya yolu ve dosya adı belirtin.  
  
     Daha fazla bilgi için bkz: [/TLBOUT (adı. TLB dosyası)](/cpp/build/reference/tlbout-name-dot-tlb-file).  
  
-   **TypeLibraryResourceID**  
  
     İsteğe bağlı **tamsayı** parametresi.  
  
     Bir bağlayıcı oluşturulan tür kitaplığı için bir kullanıcı tarafından belirtilen değer belirler. 1 ile 65535 arasında bir değer belirtin.  
  
     Daha fazla bilgi için bkz: [/TLBID (kaynak kimliği belirt TypeLib için)](/cpp/build/reference/tlbid-specify-resource-id-for-typelib).  
  
-   **UACExecutionLevel**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Altında kullanıcı hesabı denetimi ile çalışırken uygulama için istenen yürütme düzeyini belirtir.  
  
     Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **AsInvoker** - `level='asInvoker'`  
  
    -   **HighestAvailable** - `level='highestAvailable'`  
  
    -   **RequireAdministrator** - `level='requireAdministrator'`  
  
     Daha fazla bilgi için bkz: `level` bağımsız değişkeni [/MANIFESTUAC (bildirimdeki UAC bilgilerini katıştırır)](/cpp/build/reference/manifestuac-embeds-uac-information-in-manifest).  
  
-   **UACUIAccess**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, uygulama kullanıcı arabirimi koruma düzeyleri atlar ve sürücüleri giriş izni daha yüksek Windows masaüstünde, aksi takdirde `false`.  
  
     Daha fazla bilgi için bkz: `uiAccess` bağımsız değişkeni [/MANIFESTUAC (bildirimdeki UAC bilgilerini katıştırır)](/cpp/build/reference/manifestuac-embeds-uac-information-in-manifest).  
  
-   **UseLibraryDependencyInputs**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, Kitaplığı Aracı girişleri kullanılan yerine kitaplık dosyasının kendisini kitaplığı proje bağımlılıklarını çıkarır zaman bağlanılır.  
  
-   **Sürüm**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Bir sürüm numarası .exe veya .dll dosyası başlığına yerleştirin. Belirtin "`major[.minor]`". `major` Ve `minor` bağımsız değişkenler 0 ile 65535 arasında ondalık sayılar.  
  
     Daha fazla bilgi için bkz: [/VERSION (sürüm bilgileri)](/cpp/build/reference/version-version-information).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)