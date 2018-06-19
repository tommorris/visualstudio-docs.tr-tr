---
title: CSC görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Csc
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Csc task [MSBuild]
- MSBuild, Csc task
ms.assetid: d8c19b36-f5ca-484b-afa6-8ff3b90e103a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d35f1dee5c2f3d4f91a6d59e001bc9f16fd7b52a
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31575663"
---
# <a name="csc-task"></a>Csc Görevi
CSC.exe sarmalar ve yürütülebilir dosyalar (.exe dosyaları), dinamik bağlantı kitaplıkları (.dll dosyaları) veya kod modülleri (.netmodule dosyaları) üretir. CSC.exe hakkında daha fazla bilgi için bkz: [C# Derleyici Seçenekleri](/dotnet/csharp/language-reference/compiler-options/index).  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `Csc` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`AdditionalLibPaths`|İsteğe bağlı `String[]` parametresi.<br /><br /> Başvuruların aranacağı ek dizinler belirtir. Daha fazla bilgi için bkz: [/lib (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/lib-compiler-option).|  
|`AddModules`|İsteğe bağlı `String` parametresi.<br /><br /> Derlemenin parçası olarak bir veya daha fazla modül belirtir. Daha fazla bilgi için bkz: [/addmodule (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/addmodule-compiler-option).|  
|`AllowUnsafeBlocks`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, kullanan kodu derler [güvensiz](/dotnet/csharp/language-reference/keywords/unsafe) anahtar sözcüğü. Daha fazla bilgi için bkz: [/ unsafe (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/unsafe-compiler-option).|  
|`ApplicationConfiguration`|İsteğe bağlı `String` parametresi.<br /><br /> Derleme bağlama ayarları içeren uygulama yapılandırma dosyasını belirtir.|  
|`BaseAddress`|İsteğe bağlı `String` parametresi.<br /><br /> Tercih edilen temel adrese DLL yükleneceği belirtir. Bir DLL için varsayılan taban adresi belirlediği [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] ortak dil çalışma zamanı. Daha fazla bilgi için bkz: [/baseaddress (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/baseaddress-compiler-option).|  
|`CheckForOverflowUnderflow`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Tamsayı veri türü sınırlarına taşar aritmetik çalışma zamanında bir özel durum neden olup olmayacağını belirtir. Daha fazla bilgi için bkz: [/ checked (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/checked-compiler-option).|  
|`CodePage`|İsteğe bağlı `Int32` parametresi.<br /><br /> Derlemedeki tüm kaynak kodu dosyaları için kullanmak üzere kod sayfasını belirtir. Daha fazla bilgi için bkz: [/codepage (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/codepage-compiler-option).|  
|`DebugType`|İsteğe bağlı `String` parametresi.<br /><br /> Hata ayıklama türünü belirtir. `DebugType` olabilir `full` veya `pdbonly`. Varsayılan değer `full`, çalışan bir program eklenmesi gereken bir hata ayıklayıcısı sağlar. Belirtme `pdbonly` etkinleştirir kaynak program hata ayıklayıcısı'ndaki başlatılır, ancak çalışan program hata ayıklayıcıya eklendiğinde yalnızca assembler görüntüler kodda hata ayıklama.<br /><br /> Bu parametre geçersiz kılar `EmitDebugInformation` parametresi.<br /><br /> Daha fazla bilgi için bkz: [/Debug (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/debug-compiler-option).|  
|`DefineConstants`|İsteğe bağlı `String` parametresi.<br /><br /> Önişlemci simgelerini tanımlar. Daha fazla bilgi için bkz: [/ define (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/define-compiler-option).|  
|`DelaySign`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, tam imzalı bir derleme istediğinizi belirtir. Varsa `false`, yalnızca ortak anahtar derlemede yerleştirmek istediğinizi belirtir.<br /><br /> Bu parametre ile birlikte kullanılan sürece herhangi bir etkisi olmaz `KeyFile` veya `KeyContainer` parametresi.<br /><br /> Daha fazla bilgi için bkz: [/delaysign (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/delaysign-compiler-option).|  
|`DisabledWarnings`|İsteğe bağlı `String` parametresi.<br /><br /> Devre dışı bırakılması uyarıların listesini belirtir. Daha fazla bilgi için bkz: [/nowarn (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/nowarn-compiler-option).|  
|`DocumentationFile`|İsteğe bağlı `String` parametresi.<br /><br /> Belge açıklamaları bir XML dosyasına işler. Daha fazla bilgi için bkz: [/doc (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/doc-compiler-option).|  
|`EmitDebugInformation`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, görev hata ayıklama bilgisi oluşturur ve bir program veritabanı (.pdb) dosyasına yerleştirir. Varsa `false`, görev hiçbir hata ayıklama bilgisi yayar. Varsayılan değer `false`. Daha fazla bilgi için bkz: [/Debug (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/debug-compiler-option).|  
|`ErrorReport`|İsteğe bağlı `String` parametresi.<br /><br /> Bir C# iç hatası Microsoft'a bildirmek için kolay bir yol sağlar. Bu parametre değerini olabilir `prompt`, `send`, veya `none`. Parametre ayarlanmışsa `prompt`, bir iç derleyici hatası oluştuğunda bir ileti alacaksınız. İstemi, bir hata raporu elektronik olarak Microsoft'a gönder olanak tanır. Parametre ayarlanmışsa `send`, bir hata raporu otomatik olarak gönderilir. Parametre ayarlanmışsa `none`, yalnızca derleyici metin çıktısı hata bildirdi. Varsayılan değer `none`. Daha fazla bilgi için bkz: [/errorreport (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/errorreport-compiler-option).|  
|`FileAlignment`|İsteğe bağlı `Int32` parametresi.<br /><br /> Çıktı dosyasında bölümlerin boyutunu belirtir. Daha fazla bilgi için bkz: [/filealign (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/filealign-compiler-option).|  
|`GenerateFullPaths`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, derleyici çıktısında mutlak dosya yolunu belirtir. Varsa `false`, dosya adını belirtir. Varsayılan değer `false`. Daha fazla bilgi için bkz: [/fullpaths (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/fullpaths-compiler-option).|  
|`KeyContainer`|İsteğe bağlı `String` parametresi.<br /><br /> Şifreleme anahtarı kapsayıcısının adını belirtir. Daha fazla bilgi için bkz: [/keycontainer (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/keycontainer-compiler-option).|  
|`KeyFile`|İsteğe bağlı `String` parametresi.<br /><br /> Şifreleme anahtarını içeren dosya adını belirtir. Daha fazla bilgi için bkz: [/keyfile (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/keyfile-compiler-option).|  
|`LangVersion`|İsteğe bağlı `String` parametresi.<br /><br /> Kullanılacak dili sürümünü belirtir. Daha fazla bilgi için bkz: [/langversion (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/langversion-compiler-option).|  
|`LinkResources`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Bir bağlantı oluşturur bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] kaynak çıktı dosyasında; kaynak dosyası çıktı dosyasına yerleştirilmedi.<br /><br /> Bu parametre geçirilen öğe adlı isteğe bağlı meta veriler girdiler olabilir `LogicalName` ve `Access`. `LogicalName` karşılık gelen `identifier` parametresinin `/linkresource` geçin, ve `Access` karşılık gelen `accessibility-modifier` parametresi. Daha fazla bilgi için bkz: [/linkresource (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/linkresource-compiler-option).|  
|`MainEntryPoint`|İsteğe bağlı `String` parametresi.<br /><br /> Konumunu belirten `Main` yöntemi. Daha fazla bilgi için bkz: [/Main (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/main-compiler-option).|  
|`ModuleAssemblyName`|İsteğe bağlı `String` parametresi.<br /><br /> Bu modül bir parçası olacak bütünleştirilmiş kodun adını belirtir.|  
|`NoConfig`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, csc.rsp dosyasıyla derleme değil bildirir. Daha fazla bilgi için bkz: [/noconfig (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/noconfig-compiler-option).|  
|`NoLogo`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, derleyici başlık bilgilerini görüntülenmesini engeller. Daha fazla bilgi için bkz: [/nologo (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/nologo-compiler-option).|  
|`NoStandardLib`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, tüm sistem ad alanını tanımlayan mscorlib.dll alma engeller. Tanımlayın veya kendi sistem ad alanı ve nesneleri oluşturmak istiyorsanız bu parametreyi kullanın. Daha fazla bilgi için bkz: [/nostdlib (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/nostdlib-compiler-option).|  
|`NoWin32Manifest`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, varsayılan Win32 bildirimi dahil etmeyin.|  
|`Optimize`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, iyileştirmeler sağlar. Varsa `false`, en iyi duruma getirme devre dışı bırakır. Daha fazla bilgi için bkz: [/ optimize (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/optimize-compiler-option).|  
|`OutputAssembly`|İsteğe bağlı `String` çıkış parametresi.<br /><br /> Çıktı dosyası adını belirtir. Daha fazla bilgi için bkz: [/out (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/out-compiler-option).|  
|`OutputRefAssembly`|İsteğe bağlı `String` parametresi.<br /><br /> Çıktı başvurusu derleme dosyası adını belirtir. Daha fazla bilgi için bkz: [/refout (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/refout-compiler-option).|  
|`PdbFile`|İsteğe bağlı `String` parametresi.<br /><br /> Hata ayıklama bilgileri dosya adını belirtir. Çıktı dosyası adını .pdb uzantılı varsayılan addır.|  
|`Platform`|İsteğe bağlı `String` parametresi.<br /><br /> Çıkış dosyası tarafından hedeflenecek işlemci platformunu belirtir. Bu parametre değerini olabilir `x86`, `x64`, veya `anycpu`. Varsayılan değer `anycpu`. Daha fazla bilgi için bkz: [/Platform (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/platform-compiler-option).|  
|`References`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Geçerli projede belirtilen öğelerden genel tür bilgileri almak görev neden olur. Daha fazla bilgi için bkz: [/Reference (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/reference-compiler-option).<br /><br /> Belirleyebileceğiniz bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] başvuru diğer adı içinde bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] meta veriler ekleyerek dosya `Aliases` özgün "Başvurusu" öğesine. Örneğin, diğer adı "LS1" aşağıdaki CSC komut satırında ayarlamak için şunu yazın:<br /><br /> `csc /r:LS1=MyCodeLibrary.dll /r:LS2=MyCodeLibrary2.dll *.cs`<br /><br /> kullanırsınız:<br /><br /> `<Reference Include="MyCodeLibrary"> <Aliases>LS1</Aliases> </Reference>`|  
|`Resources`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Katıştırır bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] çıktı dosyasına kaynak.<br /><br /> Bu parametre geçirilen öğe adlı isteğe bağlı meta veriler girdiler olabilir `LogicalName` ve `Access`. `LogicalName` karşılık gelen `identifier` parametresinin `/resource` geçin, ve `Access` karşılık gelen `accessibility-modifier` parametresi. Daha fazla bilgi için bkz: [/Resource (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/resource-compiler-option).|  
|`ResponseFiles`|İsteğe bağlı `String` parametresi.<br /><br /> Bu görev için komutlar içerir yanıt dosyasını belirtir. Daha fazla bilgi için bkz: [@ (yanıt dosyasını belirtin)](/dotnet/csharp/language-reference/compiler-options/response-file-compiler-option).|  
|`Sources`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Bir veya daha fazla belirtir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] kaynak dosyaları.|  
|`TargetType`|İsteğe bağlı `String` parametresi.<br /><br /> Çıkış dosyasının dosya biçimini belirtir. Bu parametre değerini olabilir `library`, bir kod kitaplığı oluşturan `exe`, bir konsol uygulaması oluşturan `module`, bir modül oluşturur veya `winexe`, bir Windows programı oluşturur. Varsayılan değer `library` şeklindedir. Daha fazla bilgi için bkz: [/target (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/target-compiler-option).|  
|`TreatWarningsAsErrors`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, tüm uyarıları hata olarak kabul eder. Daha fazla bilgi için bkz: [/warnaserror (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/warnaserror-compiler-option).|  
|`UseHostCompilerIfAvailable`|İsteğe bağlı `Boolean` parametresi.<br /><br /> İşlem içi derleyicisi nesnesini kullanmak için görev varsa bildirir. Yalnızca kullanılan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|`Utf8Output`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Derleyici çıktı UTF-8 kodlaması kullanarak günlüğe kaydeder. Daha fazla bilgi için bkz: [/utf8output (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/utf8output-compiler-option).|  
|`WarningLevel`|İsteğe bağlı `Int32` parametresi.<br /><br /> Derleyicinin görüntülenecek uyarı düzeyini belirtir. Daha fazla bilgi için bkz: [/ warn (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/warn-compiler-option).|  
|`WarningsAsErrors`|İsteğe bağlı `String` parametresi.<br /><br /> Hata olarak değerlendirmek için uyarılar listesini belirtir. Daha fazla bilgi için bkz: [/warnaserror (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/warnaserror-compiler-option).<br /><br /> Bu parametre geçersiz kılar `TreatWarningsAsErrors` parametresi.|  
|`WarningsNotAsErrors`|İsteğe bağlı `String` parametresi.<br /><br /> Hata olarak kabul edilmediği uyarıların listesini belirtir. Daha fazla bilgi için bkz: [/warnaserror (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/warnaserror-compiler-option).<br /><br /> Bu parametre yalnızca yararlıdır varsa `TreatWarningsAsErrors` parametrenin ayarlanmış `true`.|  
|`Win32Icon`|İsteğe bağlı `String` parametresi.<br /><br /> Çıkış dosyasının dosya Gezgini'nde istenen çalışmasıdır bütünleştirilmiş kodunda bir .ico dosyasını ekler. Daha fazla bilgi için bkz: [/win32icon (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/win32icon-compiler-option).|  
|`Win32Manifest`|İsteğe bağlı `String` parametresi.<br /><br /> Win32 bildirimi dahil edilecek belirtir.|  
|`Win32Resource`|İsteğe bağlı `String` parametresi.<br /><br /> Win32 kaynak (.res) dosyası çıktı dosyasına ekler. Daha fazla bilgi için bkz: [/win32res (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/win32res-compiler-option).|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır `Microsoft.Build.Tasks.ManagedCompiler` devraldığı sınıfı <xref:Microsoft.Build.Tasks.ToolTaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.ToolTask> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [ToolTaskExtension taban sınıfı](../msbuild/tooltaskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `Csc` bir yürütülebilir dosya kaynak dosyalarından derlemek için görev `Compile` öğe koleksiyonu.  
  
```xml  
<CSC  
    Sources="@(Compile)"  
    OutputAssembly="$(AppName).exe"  
    EmitDebugInformation="true" />  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Görevler](../msbuild/msbuild-tasks.md)
