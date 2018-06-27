---
title: Vbc görevi | Microsoft Docs
ms.custom: ''
ms.date: 04/12/2018
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Vbc
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Vbc task [MSBuild]
- MSBuild, Vbc task
ms.assetid: 595278b1-2782-4577-b1ba-b4b5ab5625a3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 511e980b8c312803a82692042d7f88f389265c3a
ms.sourcegitcommit: c842955aa9ee9f149bb63e66e46c5c29be6e9881
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36962586"
---
# <a name="vbc-task"></a>Vbc görevi
Sarmalar *vbc.exe*, yürütülebilir dosyaları üretir (*.exe*), dinamik bağlantı kitaplıkları (*.dll*), veya kod modülleri (*.netmodule*). Daha fazla bilgi için *vbc.exe*, bkz: [Visual Basic komut satırı derleyicisi](/dotnet/visual-basic/reference/command-line-compiler/index).  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `Vbc` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`AdditionalLibPaths`|İsteğe bağlı `String[]` parametresi.<br /><br /> Derleme başvuruları özniteliğinde belirtilen aramak ek klasörler belirtir.|  
|`AddModules`|İsteğe bağlı `String[]` parametresi.<br /><br /> Tüm hale getirmesine neden olur. şu anda derlediğiniz proje için belirtilen dosya veya dosyalar kullanılabilir bilgileri yazın. Bu parametre karşılık gelen [- addmodule](/dotnet/visual-basic/reference/command-line-compiler/addmodule) geçiş *vbc.exe* derleyici.|  
|`BaseAddress`|İsteğe bağlı `String` parametresi.<br /><br /> DLL'nin temel adresini belirtir. Bu parametre karşılık gelen [- baseaddress](/dotnet/visual-basic/reference/command-line-compiler/baseaddress) geçiş *vbc.exe* derleyici.|  
|`CodePage`|İsteğe bağlı `Int32` parametresi.<br /><br /> Derlemedeki tüm kaynak kodu dosyaları için kullanmak üzere kod sayfasını belirtir. Bu parametre karşılık gelen [- codepage](/dotnet/visual-basic/reference/command-line-compiler/codepage) geçiş *vbc.exe* derleyici.|  
|`DebugType`|İsteğe bağlı `String[]` parametresi.<br /><br /> Hata ayıklama bilgileri oluşturmak derleyici neden olur. Bu parametre aşağıdaki değerlere sahip olabilir:<br /><br /> -   `full`<br />-   `pdbonly`<br /><br /> Varsayılan değer `full`, sağlayan bir hata ayıklayıcısı çalışan programa ekleniyor. Değerini `pdbonly` program hata ayıklayıcısı'ndaki başlatılır, ancak yalnızca çalışan program için hata ayıklayıcı iliştirildiğinde derleme dil kodu görüntüler kaynak kodda hata ayıklama sağlar. Daha fazla bilgi için bkz: [-debug (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/debug).|  
|`DefineConstants`|İsteğe bağlı `String[]` parametresi.<br /><br /> Koşullu derleme sabitleri tanımlar. Sembol/değer çiftleri noktalı virgülle ayırarak ve aşağıdaki sözdizimi ile belirtilir:<br /><br /> *symbol1* `=` *value1* `;` *Simge2* `=` *value2*<br /><br /> Bu parametre karşılık gelen [-tanımlamak](/dotnet/visual-basic/reference/command-line-compiler/define) geçiş *vbc.exe* derleyici.|  
|`DelaySign`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, görev ortak anahtarı derlemede yerleştirir. Varsa `false`, görev derleme tam olarak imzalar. Varsayılan değer `false`. Bu parametre ile kullanılmadığı sürece etkisizdir `KeyFile` parametresi veya `KeyContainer` parametresi. Bu parametre karşılık gelen [- delaysign](/dotnet/visual-basic/reference/command-line-compiler/delaysign) geçiş *vbc.exe* derleyici.|  
|`Deterministic`|İsteğe bağlı `Boolean` parametresi.<br/><br/> Varsa `true`, ikili içeriği aynı derlemeleri arasında girişleri özdeş ise bir derleme çıktı derleyicinin neden olur.<br/><br/>Daha fazla bilgi için bkz: [-belirleyici](/dotnet/visual-basic/reference/command-line-compiler/deterministic).|
|`DisabledWarnings`|İsteğe bağlı `String` parametresi.<br /><br /> Belirtilen Uyarıları bastırır. Yalnızca uyarı tanımlayıcı sayısal parçası belirtmeniz gerekir. Birden çok uyarıları noktalı virgülle ayrılır. Bu parametre karşılık gelen [- nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn) geçiş *vbc.exe* derleyici.|  
|`DocumentationFile`|İsteğe bağlı `String` parametresi.<br /><br /> Belge açıklamaları için belirtilen XML dosyası işler. Bu parametre geçersiz kılar `GenerateDocumentation` özniteliği. Daha fazla bilgi için bkz: [-doc](/dotnet/visual-basic/reference/command-line-compiler/doc).|  
|`EmitDebugInformation`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, görev hata ayıklama bilgisi oluşturur ve bir .pdb dosyasına yerleştirir. Daha fazla bilgi için bkz: [-debug (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/debug).|  
|`ErrorReport`|İsteğe bağlı `String` parametresi.<br /><br /> Görev iç derleyici hataları nasıl bildirmelisiniz belirtir. Bu parametre aşağıdaki değerlere sahip olabilir:<br /><br /> -   `prompt`<br />-   `send`<br />-   `none`<br /><br /> Varsa `prompt` belirtilir ve bir iç derleyici hatası oluşur, kullanıcıdan olup hata verileri Microsoft'a göndermek bir seçenek ile istenir.<br /><br /> Varsa `send` belirtilir ve bir iç derleyici hatası oluşur, görev hata verileri Microsoft'a gönderir.<br /><br /> Varsayılan değer `none`, yalnızca çıktı metin hataları bildirir.<br /><br /> Bu parametre karşılık gelen [- errorreport](/dotnet/visual-basic/reference/command-line-compiler/errorreport) geçiş *vbc.exe* derleyici.|  
|`FileAlignment`|İsteğe bağlı `Int32` parametresi.<br /><br /> , Çıktı dosyası bölümlerini hizalamak nereye bayt cinsinden belirtir. Bu parametre aşağıdaki değerlere sahip olabilir:<br /><br /> -   `512`<br />-   `1024`<br />-   `2048`<br />-   `4096`<br />-   `8192`<br /><br /> Bu parametre karşılık gelen [- filealign](/dotnet/visual-basic/reference/command-line-compiler/filealign) geçiş *vbc.exe* derleyici.|  
|`GenerateDocumentation`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, belge bilgisi oluşturur ve yürütülebilir dosya veya görev oluşturma kitaplığın adında bir XML dosyasına yerleştirir. Daha fazla bilgi için bkz: [-doc](/dotnet/visual-basic/reference/command-line-compiler/doc).|  
|`Imports`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Belirtilen öğe koleksiyonlarından ad alanlarını alır. Bu parametre karşılık gelen [-Imports](/dotnet/visual-basic/reference/command-line-compiler/imports) geçiş *vbc.exe* derleyici.|  
|`KeyContainer`|İsteğe bağlı `String` parametresi.<br /><br /> Şifreleme anahtarı kapsayıcısının adını belirtir. Bu parametre karşılık gelen [- keycontainer](/dotnet/visual-basic/reference/command-line-compiler/keycontainer) geçiş *vbc.exe* derleyici.|  
|`KeyFile`|İsteğe bağlı `String` parametresi.<br /><br /> Şifreleme anahtarını içeren dosya adını belirtir. Daha fazla bilgi için bkz: [- keyfile](/dotnet/visual-basic/reference/command-line-compiler/keyfile).|  
|`LangVersion`|İsteğe bağlı <xref:System.String?displayProperty=fullName> parametresi.<br /><br /> "9" veya "10", dil sürümünü belirtir.|  
|`LinkResources`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> .NET Framework kaynağına bağlantı çıktı dosyasında oluşturur; Kaynak dosyanın çıkış dosyasında yerleştirilmedi. Bu parametre karşılık gelen [- linkresource](/dotnet/visual-basic/reference/command-line-compiler/linkresource) geçiş *vbc.exe* derleyici.|  
|`MainEntryPoint`|İsteğe bağlı `String` parametresi.<br /><br /> Sınıf veya içeren modülünü belirtir `Sub Main` yordamı. Bu parametre karşılık gelen [-ana](/dotnet/visual-basic/reference/command-line-compiler/main) geçiş *vbc.exe* derleyici.|  
|`ModuleAssemblyName`|İsteğe bağlı `String` parametresi.<br /><br /> Bu modül bir parçası olan derleme belirtir.|  
|`NoConfig`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Derleyici değil kullanması gerektiğini belirtir *vbc.rsp* dosya. Bu parametre karşılık gelen [- noconfig](/dotnet/visual-basic/reference/command-line-compiler/noconfig) parametresinin *vbc.exe* derleyici.|  
|`NoLogo`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, derleyici başlık bilgilerini görüntülenmesini engeller. Bu parametre karşılık gelen [- nologo](/dotnet/visual-basic/reference/command-line-compiler/nologo) geçiş *vbc.exe* derleyici.|  
|`NoStandardLib`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Standart kitaplıkları değil, başvuru için derleyici neden olur. Bu parametre karşılık gelen [- nostdlib](/dotnet/visual-basic/reference/command-line-compiler/nostdlib) geçiş *vbc.exe* derleyici.|  
|`NoVBRuntimeReference`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Yalnızca dahili kullanım. TRUE ise, Microsoft.VisualBasic.dll içinde otomatik referansı engeller...|  
|`NoWarnings`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, görevin tüm uyarıları bastırır. Daha fazla bilgi için bkz: [- nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn).|  
|`Optimize`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, derleyici iyileştirmeler sağlar. Bu parametre karşılık gelen [-en iyi duruma getirme](/dotnet/visual-basic/reference/command-line-compiler/optimize) geçiş *vbc.exe* derleyici.|  
|`OptionCompare`|İsteğe bağlı `String` parametresi.<br /><br /> Dize karşılaştırmaları nasıl yapılacağını belirtir. Bu parametre aşağıdaki değerlere sahip olabilir:<br /><br /> -   `binary`<br />-   `text`<br /><br /> Değer `binary` görev ikili dize karşılaştırmaları kullandığını belirtir. Değer `text` görev metin dize karşılaştırmaları kullandığını belirtir. Bu parametrenin varsayılan değeri `binary`. Bu parametre karşılık gelen [- optioncompare](/dotnet/visual-basic/reference/command-line-compiler/optioncompare) geçiş *vbc.exe* derleyici.|  
|`OptionExplicit`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, değişkenlerin açıkça bildirilmesini gereklidir. Bu parametre karşılık gelen [- optionexplicit](/dotnet/visual-basic/reference/command-line-compiler/optionexplicit) geçiş *vbc.exe* derleyici.|  
|`OptionInfer`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, değişkenlerin tür çıkarımı sağlar.|  
|`OptionStrict`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, görev örtük tür dönüşümleri kısıtlamak için kesin türü anlamları zorlar. Bu parametre karşılık gelen [- optionstrict](/dotnet/visual-basic/reference/command-line-compiler/optionstrict) geçiş *vbc.exe* derleyici.|  
|`OptionStrictType`|İsteğe bağlı `String` parametresi.<br /><br /> Hangi katı türü anlamları bir uyarı üretir belirtir. Şu anda yalnızca "özel" desteklenir. Bu parametre karşılık gelen [- optionstrict](/dotnet/visual-basic/reference/command-line-compiler/optionstrict) geçiş *vbc.exe* derleyici.|  
|`OutputAssembly`|İsteğe bağlı `String` çıkış parametresi.<br /><br /> Çıktı dosyası adını belirtir. Bu parametre karşılık gelen [-out](/dotnet/visual-basic/reference/command-line-compiler/out) geçiş *vbc.exe* derleyici.|  
|`Platform`|İsteğe bağlı `String` parametresi.<br /><br /> Çıkış dosyası tarafından hedeflenecek işlemci platformunu belirtir. Bu parametre değerini olabilir `x86`, `x64`, `Itanium`, veya `anycpu`. Varsayılan değer `anycpu`. Bu parametre karşılık gelen [-platform](/dotnet/visual-basic/reference/command-line-compiler/platform) geçiş *vbc.exe* derleyici.|  
|`References`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Geçerli projede belirtilen öğelerden genel tür bilgileri almak görev neden olur. Bu parametre karşılık gelen [-başvuru](/dotnet/visual-basic/reference/command-line-compiler/reference) geçiş *vbc.exe* derleyici.|  
|`RemoveIntegerChecks`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, tamsayı taşma hatası denetimleri devre dışı bırakır. Varsayılan değer `false` şeklindedir. Bu parametre karşılık gelen [- removeintchecks](/dotnet/visual-basic/reference/command-line-compiler/removeintchecks) geçiş *vbc.exe* derleyici.|  
|`Resources`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> .NET Framework kaynağı çıkış dosyası içine katıştırır. Bu parametre karşılık gelen [-kaynak](/dotnet/visual-basic/reference/command-line-compiler/resource) geçiş *vbc.exe* derleyici.|  
|`ResponseFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Bu görev için komutlar içerir yanıt dosyasını belirtir. Bu parametre karşılık gelen [@ (yanıt dosyasını belirtin)](/dotnet/visual-basic/reference/command-line-compiler/specify-response-file) seçeneği *vbc.exe* derleyici.|  
|`RootNamespace`|İsteğe bağlı `String` parametresi.<br /><br /> Tüm tür bildirimleri için kök ad alanını belirtir. Bu parametre karşılık gelen [- rootnamespace](/dotnet/visual-basic/reference/command-line-compiler/rootnamespace) geçiş *vbc.exe* derleyici.|  
|`SdkPath`|İsteğe bağlı `String` parametresi.<br /><br /> Konumunu belirten *mscorlib.dll* ve *Microsoft.VisualBasic.dll içinde*. Bu parametre karşılık gelen [- sdkpath](/dotnet/visual-basic/reference/command-line-compiler/sdkpath) geçiş *vbc.exe* derleyici.|  
|`Sources`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Bir veya daha fazla Visual Basic kaynak dosyalarını belirtir.|  
|`TargetCompactFramework`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, görev hedefleri [!INCLUDE[Compact](../extensibility/includes/compact_md.md)]. Bu anahtara karşılık gelen [- netcf](/dotnet/visual-basic/reference/command-line-compiler/netcf) geçiş *vbc.exe* derleyici.|  
|`TargetType`|İsteğe bağlı `String` parametresi.<br /><br /> Çıkış dosyasının dosya biçimini belirtir. Bu parametre değerini olabilir `library`, bir kod kitaplığı oluşturan `exe`, bir konsol uygulaması oluşturan `module`, bir modül oluşturur veya `winexe`, bir Windows programı oluşturur. Varsayılan değer `library`. Bu parametre karşılık gelen [-hedef](/dotnet/visual-basic/reference/command-line-compiler/target) geçiş *vbc.exe* derleyici.|  
|`Timeout`|İsteğe bağlı `Int32` parametresi.<br /><br /> Süresini, daha sonra çalıştırılabilir görev sonlandırıldığından milisaniye cinsinden belirtir. Varsayılan değer `Int.MaxValue`, hiçbir zaman aşımı süresi olduğunu gösterir.|  
|`ToolPath`|İsteğe bağlı `String` parametresi.<br /><br /> Temel alınan yürütülebilir dosya görev burada yükler konumdaki belirtir (*vbc.exe*). Bu parametre belirtilmezse, görevin çalıştığı framework sürümüne karşılık gelen SDK yükleme yolunu kullanır [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)].|  
|`TreatWarningsAsErrors`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, tüm uyarıları hata olarak kabul edilir. Daha fazla bilgi için bkz: [- warnaserror (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/warnaserror).|  
|`UseHostCompilerIfAvailable`|İsteğe bağlı `Boolean` parametresi.<br /><br /> İşlem içi derleyicisi nesnesini kullanmak için görev varsa bildirir. Yalnızca kullanılan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|`Utf8Output`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Derleyici çıktı UTF-8 kodlaması kullanarak günlüğe kaydeder. Bu parametre karşılık gelen [-utf8output](/dotnet/visual-basic/reference/command-line-compiler/utf8output) geçiş *vbc.exe* derleyici.|  
|`Verbosity`|İsteğe bağlı `String` parametresi.<br /><br /> Derleyicinin çıktı ayrıntı düzeyini belirtir. Ayrıntı olabilir `Quiet`, `Normal` (varsayılan) veya `Verbose`.|  
|`WarningsAsErrors`|İsteğe bağlı `String` parametresi.<br /><br /> Hata olarak değerlendirmek için uyarılar listesini belirtir. Daha fazla bilgi için bkz: [- warnaserror (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/warnaserror).<br /><br /> Bu parametre geçersiz kılar `TreatWarningsAsErrors` parametresi.|  
|`WarningsNotAsErrors`|İsteğe bağlı `String` parametresi.<br /><br /> Hata olarak kabul edilmediği uyarıların listesini belirtir. Daha fazla bilgi için bkz: [- warnaserror (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/warnaserror).<br /><br /> Bu parametre yalnızca yararlıdır varsa `TreatWarningsAsErrors` parametrenin ayarlanmış `true`.|  
|`Win32Icon`|İsteğe bağlı `String` parametresi.<br /><br /> Ekler bir *.ico* çıkış dosyasının dosya Gezgini'nde istenen çalışmasıdır derleme dosyasında. Bu parametre karşılık gelen [-win32icon](/dotnet/visual-basic/reference/command-line-compiler/win32icon) geçiş *vbc.exe* derleyici.|  
|`Win32Resources`|İsteğe bağlı `String` parametresi.<br /><br /> Win32 kaynak ekler (*.res*) çıktı dosyası dosyasında. Bu parametre karşılık gelen [-win32resource](/dotnet/visual-basic/reference/command-line-compiler/win32resource) geçiş *vbc.exe* derleyici.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.ToolTaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.ToolTask> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [ToolTaskExtension taban sınıfı](../msbuild/tooltaskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek Visual Basic projesinde derler.  
  
```xml  
<VBC  
   Sources="@(sources)"  
   Resources="strings.resources"  
   Optimize="true"  
   OutputAssembly="out.exe"/>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Visual Basic komut satırı derleyicisi](/dotnet/visual-basic/reference/command-line-compiler/index)   
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)
