---
title: "AL (derleme bağlayıcı) görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#AL
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- AL task [MSBuild]
- MSBuild, AL task
ms.assetid: 2ddefbf2-5662-4d55-99a6-ac383bf44560
caps.latest.revision: "22"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 233946c0c46f9ee053f3497e7d6aa856315c3dfd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="al-assembly-linker-task"></a>AL (Derleme Bağlayıcı) Görevi
AL görevi AL.exe, ile dağıtılmış bir aracı sarmalar [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]. Bu derleme bağlayıcı aracı, bir derlemeyi ya da modüller bir veya daha fazla dosya veya kaynak dosyaları bildirimden oluşturmak için kullanılır. Bu görevi doğrudan kullanmak gerekli olan genelde şekilde derleyicileri ve geliştirme ortamlarını zaten bu yetenekleri sağlayabilir. Derleme Bağlayıcı tek bir derleme karışık dil geliştirme üretilen olanlar gibi birden çok bileşen dosyaları oluşturmak ihtiyaç duyan geliştiriciler için kullanışlıdır. Bu görev, bir tek derleme dosyasına modülleri birleştirmek değil; tek tek modülleri hala dağıtılmış ve doğru bir şekilde yüklemek sonuçta elde edilen derleme sırada kullanılabilir olması gerekir. AL.exe hakkında daha fazla bilgi için bkz: [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `AL` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`AlgorithmID`|İsteğe bağlı `String` parametresi.<br /><br /> Derleme bildirimini içeren dosya hariç, çok dosyalı bir derlemede tüm dosyaları karma yapmak için bir algoritma belirtir. Daha fazla bilgi için belgelerine bakın `/algid` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`BaseAddress`|İsteğe bağlı `String` parametresi.<br /><br /> Çalışma zamanında kullanıcının bilgisayarına DLL yüklenecek adresi belirtir. İşlem alanı DLL'lerde taşımanızı işletim sistemi izin vererek yerine DLL'leri taban adresi belirtirseniz, uygulamaları daha hızlı yük. Bu parametre için /base karşılık gelen[adresi](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`CompanyName`|İsteğe bağlı `String` parametresi.<br /><br /> Bir dize belirtir `Company` derlemesindeki alan. Daha fazla bilgi için belgelerine bakın `/comp[any]` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Configuration`|İsteğe bağlı `String` parametresi.<br /><br /> Bir dize belirtir `Configuration` derlemesindeki alan. Daha fazla bilgi için belgelerine bakın `/config[uration]` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Copyright`|İsteğe bağlı `String` parametresi.<br /><br /> Bir dize belirtir `Copyright` derlemesindeki alan. Daha fazla bilgi için belgelerine bakın `/copy[right]` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Culture`|İsteğe bağlı `String` parametresi.<br /><br /> Derleme ile ilişkilendirilecek için kültür dizeyini belirtir. Daha fazla bilgi için belgelerine bakın `/c[ulture]` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`DelaySign`|İsteğe bağlı `Boolean` parametresi.<br /><br /> `true`yalnızca ortak anahtar derlemede yerleştirmek için; `false` tam olarak derlemeyi imzalamak için. Daha fazla bilgi için belgelerine bakın `/delay[sign]` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Description`|İsteğe bağlı `String` parametresi.<br /><br /> Bir dize belirtir `Description` derlemesindeki alan. Daha fazla bilgi için belgelerine bakın `/descr[iption]` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`EmbedResources`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Belirtilen kaynakları içeren derleme bildirimi görüntüyü katıştırır. Bu görev görüntüsüne kaynak dosyasının içeriği kopyalar. Bu parametreye geçirilen öğeleri iliştirilmiş adlı isteğe bağlı meta veriler olabilir `LogicalName` ve `Access`. `LogicalName` Meta veri kaynağı için iç tanımlayıcı belirtmek için kullanılır.  `Access` Meta verileri ayarlanabilir `private` kaynak diğer derlemelerden görünür yapmak için. Daha fazla bilgi için belgelerine bakın `/embed[resource]` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`EvidenceFile`|İsteğe bağlı `String` parametresi.<br /><br /> Derleme kaynak adı ile belirtilen dosya katıştırır `Security.Evidence`.<br /><br /> Kullanamazsınız `Security.Evidence` normal kaynaklar için. Bu parametre karşılık gelen `/e[vidence]` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`ExitCode`|İsteğe bağlı `Int32` çıkış parametresi salt okunur.<br /><br /> Yürütülen komutun tarafından sağlanan çıkış kodu belirtir.|  
|`FileVersion`|İsteğe bağlı `String` parametresi.<br /><br /> Bir dize belirtir `File Version` derlemesindeki alan. Daha fazla bilgi için belgelerine bakın `/fileversion` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Flags`|İsteğe bağlı `String` parametresi.<br /><br /> İçin bir değer belirtir `Flags` derlemesindeki alan. Daha fazla bilgi için belgelerine bakın `/flags` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`GenerateFullPaths`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Bir hata iletisi bildirilen herhangi bir dosya için mutlak yolu kullanmak üzere görev neden olur. Bu parametre karşılık gelen `/fullpaths` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`KeyContainer`|İsteğe bağlı `String` parametresi.<br /><br /> Anahtar çifti içeren bir kapsayıcıyı belirtir. Bu, derleme bildirimine ortak anahtar ekleyerek derlemeyi imzalar (ona tanımlayıcı ad verir). Görev, sonra son derlemeyi özel anahtarla imzalar. Daha fazla bilgi için belgelerine bakın `/keyn[ame]` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`KeyFile`|İsteğe bağlı `String` parametresi.<br /><br /> Derlemeyi imzalamak için bir anahtar çifti ya da yeni bir ortak anahtar içeren dosyayı belirtir. Derleyici ortak anahtarı derleme bildirimine ekler ve ardından son derlemeyi özel anahtarla imzalar. Daha fazla bilgi için belgelerine bakın `/keyf[ile]` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`LinkResources`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Belirtilen kaynak dosyaları derleme bağlar. Kaynak assembly parçası haline gelir, ancak dosya kopyalanmaz. Bu parametreye geçirilen öğeleri iliştirilmiş adlı isteğe bağlı meta veriler olabilir `LogicalName`, `Target`, ve `Access`. `LogicalName` Meta veri kaynağı için iç tanımlayıcı belirtmek için kullanılır. `Target` Meta verileri görev kopyalar geçmesi derlendiğinden bu yeni dosya derlemeye dosyanın dosya adı ve yolu belirtebilirsiniz. `Access` Meta verileri ayarlanabilir `private` kaynak diğer derlemelerden görünür yapmak için. Daha fazla bilgi için belgelerine bakın `/link[resource]` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`MainEntryPoint`|İsteğe bağlı `String` parametresi.<br /><br /> Tam adı belirtir (*class.method*) yönteminin bir modül için yürütülebilir bir dosyanın dönüştürülürken bir giriş noktası olarak kullanmak için. Bu parametre karşılık gelen `/main` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`OutputAssembly`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> çıkış parametresi.<br /><br /> Bu görevi tarafından oluşturulan dosya adını belirtir. Bu parametre karşılık gelen `/out` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Platform`|İsteğe bağlı `String` parametresi.<br /><br /> Bu kodu çalıştırmak hangi platform sınırlar; biri olmalıdır `x86`, `Itanium`, `x64`, veya `anycpu`. Varsayılan, `anycpu` değeridir. Bu parametre karşılık gelen `/platform` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`ProductName`|İsteğe bağlı `String` parametresi.<br /><br /> Bir dize belirtir `Product` derlemesindeki alan. Daha fazla bilgi için belgelerine bakın `/prod[uct]` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`ProductVersion`|İsteğe bağlı `String` parametresi.<br /><br /> Bir dize belirtir `ProductVersion` derlemesindeki alan. Daha fazla bilgi için belgelerine bakın `/productv[ersion]` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`ResponseFiles`|İsteğe bağlı `String[]` parametresi.<br /><br /> Derleme Bağlayıcı geçişi için ek seçenekler içeren yanıt dosyaları belirtir.|  
|`SdkToolsPath`|İsteğe bağlı `String` parametresi.<br /><br /> Resgen.exe gibi SDK Araçları yolunu belirtir.|  
|`SourceModules`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Bir derlemeye derlenmesi için bir veya daha fazla modül. Modülleri elde edilen derlemeyi bildiriminde listelenen ve yine dağıtılmış ve yüklemek derleme sırada kullanılabilir gerekir. Bu parametre geçirilen öğe adlı ek meta veri olabilir `Target`, görev kopyalar geçmesi derlendiğinden bu yeni dosya derlemeye dosya, dosya adını ve yolunu belirtir. Daha fazla bilgi için belgelerine bakın [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker). Bu parametre, belirli bir anahtar Al.exe geçirilen modüllerin listesini karşılık gelir.|  
|`TargetType`|İsteğe bağlı `String` parametresi.<br /><br /> Çıkış dosyasının dosya biçimini belirtir: `library` (kod kitaplığı) `exe` (konsol uygulaması), veya `win` (Windows tabanlı bir uygulama). Varsayılan, `library` değeridir. Bu parametre karşılık gelen `/t[arget]` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`TemplateFile`|İsteğe bağlı `String` parametresi.<br /><br /> Tüm derleme meta verilerini, kültür alanı dışında devralmak derleme belirtir. Belirtilen derleme güçlü bir adı olması gerekir.<br /><br /> İle oluşturduğunuz bir derlemeyi `TemplateFile` parametresi bir uydu derleme olacaktır. Bu parametre karşılık gelen `/template` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Timeout`|İsteğe bağlı `Int32` parametresi.<br /><br /> Süresini, daha sonra çalıştırılabilir görev sonlandırıldığından milisaniye cinsinden belirtir. Varsayılan değer `Int.MaxValue`, hiçbir zaman aşımı süresi olduğunu gösterir.|  
|`Title`|İsteğe bağlı `String` parametresi.<br /><br /> Bir dize belirtir `Title` derlemesindeki alan. Daha fazla bilgi için belgelerine bakın `/title` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`ToolPath`|İsteğe bağlı `String` parametresi.<br /><br /> Görev temel yürütülebilir dosya (Al.exe) burada yükler konumdaki belirtir. Bu parametre belirtilmezse, görevin çalıştığı framework sürümüne karşılık gelen SDK yükleme yolunu kullanır [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)].|  
|`Trademark`|İsteğe bağlı `String` parametresi.<br /><br /> Bir dize belirtir `Trademark` derlemesindeki alan. Daha fazla bilgi için belgelerine bakın `/trade[mark]` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Version`|İsteğe bağlı `String` parametresi.<br /><br /> Bu derleme sürüm bilgilerini belirtir. Dize biçimi *major.minor.build.revision*. Varsayılan değer 0’dır. Daha fazla bilgi için belgelerine bakın `/v[ersion]` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Win32Icon`|İsteğe bağlı `String` parametresi.<br /><br /> Derlemeye bir .ico simge dosyası ekler. .ico dosyası, çıktı dosyasına Dosya Gezgini'nde istenen görünümü verir. Bu parametre karşılık gelen `/win32icon` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
|`Win32Resource`|İsteğe bağlı `String` parametresi.<br /><br /> Çıktı dosyasına bir Win32 kaynağı (.res dosyası) ekler. Daha fazla bilgi için belgelerine bakın `/win32res` seçeneğini [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.ToolTaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.ToolTask> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [ToolTaskExtension taban sınıfı](../msbuild/tooltaskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, belirtilen seçeneklerle bir bütünleştirilmiş kod oluşturur.  
  
```xml  
<AL  
    EmbedResources="@(EmbeddedResource)"  
    Culture="%(EmbeddedResource.Culture)"  
    TemplateFile="@(IntermediateAssembly)"  
    KeyContainer="$(KeyContainerName)"  
    KeyFile="$(KeyOriginatorFile)"  
    DelaySign="$(DelaySign)"  
  
    OutputAssembly=  
       "%(EmbeddedResource.Culture)\$(TargetName).resources.dll">  
  
    <Output TaskParameter="OutputAssembly"  
        ItemName="SatelliteAssemblies"/>  
</AL>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Görevler](../msbuild/msbuild-tasks.md)