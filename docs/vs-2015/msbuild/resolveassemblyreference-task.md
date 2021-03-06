---
title: ResolveAssemblyReference görevi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ResolveAssemblyReference
- MSBuild.ResolveAssemblyReference.TurnOnAutoGenerateBindingRedirects
- MSBuild.ResolveAssemblyReference.FoundConflict
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ResolveAssemblyReference task [MSBuild]
- MSBuild, ResolveAssemblyReference task
ms.assetid: 4d56d848-b29b-4dff-86a2-0a96c9e4a170
caps.latest.revision: 32
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f1405b9675827e01628c8bb976500bfcba34ec99
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687930"
---
# <a name="resolveassemblyreference-task"></a>ResolveAssemblyReference Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ResolveAssemblyReference görevi](https://docs.microsoft.com/visualstudio/msbuild/resolveassemblyreference-task).  
  
  
Belirtilen derlemelerini bağımlı derlemelerin belirler. Bu ikinci içerir ve `n`th sırası bağımlılıkları.  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri aşağıdaki tabloda açıklanmıştır `ResolveAssemblyReference` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`AllowedAssemblyExtensions`|İsteğe bağlı `String[]` parametresi.<br /><br /> Başvuruları çözümlenirken kullanılacak derleme dosya adı uzantıları. Varsayılan dosya adı uzantıları, .exe ve .dll ' dir.|  
|`AllowedRelatedFileExtensions`|İsteğe bağlı `String[]` parametresi.<br /><br /> Bir arama birbirleriyle ilişkili dosyaları için kullanılacak dosya adı uzantıları. Varsayılan .pdb ve .xml uzantılarıdır.|  
|`AppConfigFile`|İsteğe bağlı `String` parametresi.<br /><br /> BindingRedirect eşlemeleri ayıklayın ve ayrıştırmak için bir app.config dosyası belirtir. Bu parametre belirtilmezse, `AutoUnify` parametresi olmalıdır `false`.|  
|`AutoUnify`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Bu parametre, normal bir App.Config dosyasına sahip olamayacağını DLL'ler gibi derlemeleri oluşturmak için kullanılır.<br /><br /> Zaman `true`, ortaya çıkan bağımlılık grafiği AppConfigFile parametresi için geçirilen anApp.Config dosya değilmiş gibi otomatik olarak kabul edilir. En yüksek sürüm derleme seçilir, bu sanal App.Config dosyasına bindingRedirect giriş derlemeleri çakışan kümelerine sahiptir. Hiçbir zaman olacağına dair bir uyarı çakışan derlemeler hakkında her çakışma çözüldü çünkü bu bir sonuç olur.<br /><br /> Zaman `true`, her ayrı yeniden eşleme, eski ve yeni sürümler ve, gösteren yüksek öncelikli açıklamada neden olacak `AutoUnify` olan `true`.<br /><br /> Zaman `true`, AppConfigFile parametresi boş olmalıdır<br /><br /> Zaman `false`, hiçbir derleme sürümü yeniden eşleme otomatik olarak gerçekleştirilir. Bir derlemeyi iki sürümü varsa, bir uyarı verilir.<br /><br /> Zaman `false`, aynı derleme sonuçları bir yüksek öncelikli yorum farklı sürümleri arasında farklı her çakışma. Bu açıklamalar, tek bir uyarı tarafından izlenir. Uyarı benzersiz hata koduna sahip ve okuyan metni içeren "başvuru farklı sürümleri ve bağımlı derlemeler arasında çakışmalar bulundu".|  
|`Assemblies`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Kendisi için tam yollarını ve bağımlılıkları tanımlanmalıdır öğeleri belirtir. Bu öğeleri ya da "Sistem" gibi basit adları gibi güçlü adlar olabilir "System, Version 2.0.3500.0, Culture = neutral, PublicKeyToken = b77a5c561934e089."<br /><br /> Bu parametreye geçirilen öğeleri isteğe bağlı olarak aşağıdaki öğe meta verilerine de sahip:<br /><br /> -   `Private`: `Boolean` değeri. Varsa `true`, öğe yerel olarak kopyalanır. Varsayılan değer `true` şeklindedir.<br />-   `HintPath`: `String` değeri. Referans olarak kullanılacak yol ve dosya adını belirtir. {HintPathFromItem} belirtildiğinde kullanılır `SearchPaths` parametresi. Varsayılan değer boş bir dizedir.<br />-   `SpecificVersion`: `Boolean` değeri. Varsa `true`, belirtilen tam ad `Include` özniteliği aynı olmalıdır. Varsa `false`, basit aynı ada sahip herhangi bir derleme çalışmayacaktır. Varsa `SpecificVersion` değeri görev inceler, belirtilmişse değil `Include` öğesinin özniteliği. Basit bir ad özniteliği ise davrandığını gibi `SpecificVersion` olan `false`. Öznitelik bir tanımlayıcı ad ise davrandığını gibi `SpecificVersion` olan `true`.<br />     Bir başvuru öğe türü ile kullanıldığında `Include` özniteliği çözülmesi derlemenin tam Füzyon adı olması gerekir. Derleme yalnızca çözülene fusion tam olarak eşleşmesi durumunda `Include` özniteliği.<br />     Bir proje .NET Framework sürümünü hedefler ve daha yüksek bir .NET Framework sürümü için derlenmiş bir derlemeyi başvuruyor olup olmadığını başvuru yalnızca çözümler `SpecificVersion` kümesine `true`.<br />     Bir proje hedefleyen bir profil ve profilde yer almayan bir derlemeye başvuran olup olmadığını başvuru yalnızca çözümler `SpecificVersion` kümesine `true`.<br />-   `ExecutableExtension`: `String` değeri. Çözümlenen derlemenin, varsa, bu uzantıya sahip olmalıdır. Zaman yok, .dll examined her dizin için .exe arkasından ilk olarak kabul edilir.<br />-   `SubType`: `String` değeri. Yalnızca boş alt meta veri olan öğeleri, tam bütünleştirilmiş kodu yolları çözülecektir. Öğe boş olmayan alt meta verilerle göz ardı edilir.<br />-   `AssemblyFolderKey`: `String` değeri. Bu meta veriler, eski amaçları için desteklenir. Bir kullanıcı tanımlı kayıt defteri anahtarı gibi belirtir "hklm\\*VendorFolder*", bu `Assemblies` derleme başvurularını çözümlemek için kullanmanız gerekir.|  
|`AssemblyFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Bağımlılık bulmak tam derlemelerin bir listesini belirtir.<br /><br /> Bu parametreye geçirilen öğeleri isteğe bağlı olarak aşağıdaki öğe meta verilerine de sahip:<br /><br /> -   `Private`: isteğe bağlı `Boolean` değeri. TRUE ise öğe yerel olarak kopyalanır.<br />-   `FusionName`: isteğe bağlı `String` meta verileri. Bu öğe için basit veya güçlü adını belirtir. Bu öznitelik varsa, derleme dosya adı alınmaya için açılacak olmadığından zamandan tasarruf edebilirsiniz.|  
|`AutoUnify`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, ortaya çıkan bağımlılık grafiği AppConfigFile parametresi için geçirilen bir App.Config dosyası değilmiş gibi otomatik olarak kabul edilir. Bu sanal App.Config dosyasına bindingRedirect giriş derlemeleri çakışan kümelerine sahiptir; böylece en yüksek sürüm derleme seçilir. Hiçbir zaman olacağına dair bir uyarı çakışan derlemeler hakkında her çakışma çözüldü çünkü bu oluşur. Her ayrı yeniden eşleme, eski ve yeni sürümler ve bu olduğundan otomatik olarak yapıldığı olgu gösteren yüksek öncelikli yorum neden olacak `AutoUnify` olan `true`.<br /><br /> Varsa `false`, hiçbir derleme sürümü yeniden eşleme otomatik olarak gerçekleştirilir. Bir derlemeyi iki sürümü varsa, bir uyarı olacaktır. Aynı derlemenin farklı sürümleri arasında farklı her çakışma yüksek öncelikli yorum neden olur. Bu açıklamalar görüntülendikten sonra benzersiz bir hata ile tek bir uyarı olacak kod ve okuyan metin "buldum başvuru farklı sürümleri ve bağımlı derlemeler arasındaki çakışmaları".<br /><br /> Varsayılan değer `false` şeklindedir.|  
|`CandidateAssemblyFiles`|İsteğe bağlı `String[]` parametresi.<br /><br /> Arama ve çözümleme işlemi için kullanılacak derlemelerin bir listesini belirtir. Bu parametreye geçirilen değerlerin, mutlak dosya adı veya proje göreli dosya adları olması gerekir.<br /><br /> Bu listedeki derlemeleri ne zaman değerlendirilir `SearchPaths` parametresi dikkate alınması gereken yollardan biri {CandidateAssemblyFiles} içerir.|  
|`CopyLocalDependenciesWhenParentReferenceInGac`|İsteğe bağlı [Boolean] (<!-- TODO: review code entity reference <xref:assetId:///Boolean?qualifyHint=False&amp;autoUpgrade=True>  -->) parametre.<br /><br /> TRUE ise bir bağımlılık yerel olarak kopyalanmalıdır, yapılan denetimler birini üst başvuru proje dosyasında özel meta verileri olup olmadığını belirlemek üzere ayarlayın. Özel değer kümesi bağımlılık olarak kullanılıyorsa.<br /><br /> Ardından meta verileri ayarlanmazsa, bağımlılık aynı denetimleri üst başvuru olarak geçer. Bu denetimler başvurusu GAC içinde olup olmadığını görmek için biridir. Bir başvuru GAC'de ise, hedef makinede GAC'deki olmasını varsayıldığından ardından bunu yerel olarak kopyalanmaz. Bu, yalnızca belirli bir başvuru ve onun bağımlılıklarını için geçerlidir.<br /><br /> Örneğin, bir başvuru GAC içinde proje dosyasında yerel olarak kopyalanmaz, ancak GAC'de olmadıklarından bağımlılıklarını yerel olarak kopyalanır.<br /><br /> False ise, bunlar GAC'de ve yerel olarak uygun şekilde kopyalandığından emin olup proje dosya başvuruları denetlenir.<br /><br /> Bağımlılıklar GAC içinde olup olmadığını görmek için denetlenir ve proje dosyasında üst başvuru GAC içinde olup olmadığını görmek için denetlenir.<br /><br /> Proje dosyasında üst başvuru GAC'de ise, bağımlılık yerel olarak kopyalanır değil.<br /><br /> Sonra bunların tümünü bu parametre birden çok üst başvuru vardır ve bunlardan herhangi birini GAC'de değilse true veya false olup olmadığını, yerel olarak kopyalanır.|  
|`CopyLocalFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` salt okunur çıkış parametresi.<br /><br /> Her bir dosyanın döndürür `ResolvedFiles`, `ResolvedDependencyFiles`, `RelatedFiles`, `SatelliteFiles`, ve `ScatterFiles` olan parametreleri `CopyLocal` değerine sahip öğe meta verileri `true`.|  
|`FilesWritten`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Yazılan öğeleri içeren diske.|  
|`FindDependencies`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, bağımlılıkları bulunabilir. Aksi takdirde, yalnızca birincil başvuru bulunur. Varsayılan değer `true` şeklindedir.|  
|`FindRelatedFiles`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, ilgili .pdb dosyaları ve .xml dosyaları gibi dosyaları bulunabilir. Varsayılan değer `true` şeklindedir.|  
|`FindSatellites`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, uydu derlemeleri bulunabilir. Varsayılan değer: `true.`|  
|`FindSerializationAssemblies`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, görev için serileştirme derlemelerini sonra arama yapar. Varsayılan değer `true` şeklindedir.|  
|`FullFrameworkAssemblyTables`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Yeniden dağıtılabilir dosya listesini bir belirli framework dizin ile ilişkilendirmek için "FrameworkDirectory" meta verilerine de sahip öğeleri belirtir. İlişkilendirme yapılmazsa, bir hata günlüğe kaydedilir. Bir FrameworkDirectory ayarlanmamışsa Çözümle bütünleştirilmiş kod başvurusu (RAR) mantığı hedef çerçeve dizininde kullanır...|  
|`FullFrameworkFolders`|İsteğe bağlı [String] (<!-- TODO: review code entity reference <xref:assetId:///String?qualifyHint=False&amp;autoUpgrade=True>  -->)`[]` parametresi.<br /><br /> RedistList dizin içeren klasörleri kümesini belirtir. Bu dizin, belirtilen istemci profili, örneğin, %programfiles%\reference assemblies\microsoft\framework\v4.0 framework tam temsil eder.|  
|`FullTargetFrameworkSubsetNames`|İsteğe bağlı `String[]` parametresi.<br /><br /> Hedef framework alt kümesi adlarının bir listesini içerir. Bir alt ad listesinde birinde eşleşip eşleşmediğini `TargetFrameworkSubset` name özelliği, sonra sistem, oluşturma zamanında bu belirli hedef framework alt dışlar.|  
|`IgnoreDefaultInstalledAssemblyTables`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, görev için arama yapar ve ek kullanımlar yüklü derleme tabloları (veya "Redist listeler") altındaki \RedistList dizininde bulunan `TargetFrameworkDirectories`. Varsayılan değer: `false.`|  
|`IgnoreDefaultInstalledAssemblySubsetTables`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, görev için arama yapar ve ek kullanımlar yüklü derleme alt tablolar (veya "Alt listeler") altındaki \SubsetList dizininde bulunan `TargetFrameworkDirectories`. Varsayılan değer: `false.`|  
|`InstalledAssemblySubsetTables`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Hedef alt kümesinde olması bekleniyor derlemeler belirlediğiniz XML dosyalarının bir listesini içerir.<br /><br /> Bir seçenek olarak, bu listedeki öğelerin ilişkilendirmek için "FrameworkDirectory" meta veri belirtebilirsiniz bir `InstalledAssemblySubsetTable`<br /><br /> belirli framework dizinle.<br /><br /> Varsa yalnızca `TargetFrameworkDirectories` öğesi, ardından bu listede "FrameworkDirectory" meta veriler eksik öğeleri geçirilen benzersiz değere ayarlanmış olsa edilir `TargetFrameworkDirectories`.|  
|`InstalledAssemblyTables`|İsteğe bağlı `String` parametresi.<br /><br /> Hedef bilgisayarda yüklü olması beklenen derlemeler belirlediğiniz XML dosyalarının bir listesini içerir.<br /><br /> Zaman `InstalledAssemblyTables` , derlemeler listesi önceki sürümlerinde, XML dosyasında listelenen daha yeni sürümler halinde birleştirilir, ayarlanmış. Ayrıca, InGAC ayarı olan derlemeler = 'true' önkoşul olarak kabul edilir ve CopyLocal için ayarlanmış olan = 'false' açıkça geçersiz kılınmadığı sürece.<br /><br /> Bir seçenek olarak, bu listedeki öğelerin ilişkilendirmek için "FrameworkDirectory" meta veri belirtebilirsiniz bir `InstalledAssemblyTable` belirli framework dizinine sahip.  Ancak, yeniden dağıtılabilir dosya adı ile başlayan sürece bu ayar yoksayılır<br /><br /> "Microsoft-Windows-CLRCoreComp".<br /><br /> Varsa yalnızca `TargetFrameworkDirectories` öğesi, ardından bu listede "FrameworkDirectory" meta veriler eksik öğeleri geçirilen benzersiz değerine ayarlandıysa gibi edilir<br /><br /> için `TargetFrameworkDirectories`.|  
|`LatestTargetFrameworkDirectories`|İsteğe bağlı `String[]` parametresi.<br /><br /> Makinede hedeflenen en güncel framework için redist listesi içeren dizinler listesini belirtir. Ardından bu ayarlanmamışsa belirtilen hedef çerçeve tanımlayıcısı için makinede yüklü yüksek framework kullanılır.|  
|`ProfileName`|İsteğe bağlı <!-- TODO: review code entity reference <xref:assetId:///String?qualifyHint=False&amp;autoUpgrade=True>  --> parametresi.<br /><br /> -Hedeflenecek framework profili adını belirtir. Örneğin, istemci, Web veya ağ.|  
|`RelatedFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` salt okunur çıkış parametresi.<br /><br /> İlgili dosyalar bir başvuru olarak aynı temel ada sahip XML ve .pdb dosyalarını içerir.<br /><br /> Bu parametrede listelenen dosyaların isteğe bağlı olarak aşağıdaki öğe meta verisi içerebilir:<br /><br /> -   `Primary`: `Boolean` değeri. Varsa `true`, dosya öğesi tarafından diziye kullanarak geçirildi sonra `Assemblies` parametresi. Varsayılan değer `false`.<br />-   `CopyLocal`: `Boolean` değeri. Belirtilen başvurunun çıkış dizinine kopyalanmasının gerekip gerekmediğini gösterir.|  
|`ResolvedDependencyFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` salt okunur çıkış parametresi.<br /><br /> İçeren *n*bağımlılıkları th sipariş yolları. Bu parametre, bulunan ilk sırada birincil başvuruları içermez `ResolvedFiles` parametresi.<br /><br /> Bu parametre öğeleri isteğe bağlı olarak aşağıdaki öğe meta verileri içerir:<br /><br /> -   `CopyLocal`: `Boolean` değeri. Belirtilen başvurunun çıkış dizinine kopyalanmasının gerekip gerekmediğini gösterir.<br />-   `FusionName`: `String` değeri. Bu bağımlılık adını belirtir.<br />-   `ResolvedFrom`: `String` değeri. Bu dosya, gelen çözümlendiği değişmez değer arama yolunu belirtir.|  
|`ResolvedFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` salt okunur çıkış parametresi.<br /><br /> Tam yollara çözülen tüm birincil başvuru listesini içerir.<br /><br /> Bu parametre öğeleri isteğe bağlı olarak aşağıdaki öğe meta verileri içerir:<br /><br /> -   `CopyLocal`: `Boolean` değeri. Belirtilen başvurunun çıkış dizinine kopyalanmasının gerekip gerekmediğini gösterir.<br />-   `FusionName`: `String` değeri. Bu bağımlılık adını belirtir.<br />-   `ResolvedFrom`: `String` değeri. Bu dosya, gelen çözümlendiği değişmez değer arama yolunu belirtir.|  
|`SatelliteFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` salt okunur çıkış parametresi.<br /><br /> Bulunan tüm uydu dosyaları belirtir. Bunlar CopyLocal olacaktır CopyLocal başvurusu ya da mevcut için bu öğeyi neden bağımlılık ise = true = true.<br /><br /> Bu parametre öğeleri isteğe bağlı olarak aşağıdaki öğe meta verileri içerir:<br /><br /> -   `CopyLocal`: `Boolean` değeri. Belirtilen başvurunun çıkış dizinine kopyalanmasının gerekip gerekmediğini gösterir. Bu değer `true` başvuru ya da mevcut için bu öğeyi neden bir bağımlılık olup olmadığını bir `CopyLocal` değerini `true`.<br />-   `DestinationSubDirectory`: `String` değeri. Bu öğeyi kopyalamak için göreli hedef dizini belirtir.|  
|`ScatterFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` salt okunur çıkış parametresi.<br /><br /> Verilen derlemelerin biriyle ilişkili dağılım dosyaları içerir.<br /><br /> Bu parametre öğeleri isteğe bağlı olarak aşağıdaki öğe meta verileri içerir:<br /><br /> -   `CopyLocal`: `Boolean` değeri. Belirtilen başvurunun çıkış dizinine kopyalanmasının gerekip gerekmediğini gösterir.|  
|`SearchPaths`|Gerekli `String[]` parametresi.<br /><br /> Dizinleri veya derlemeleri temsil eden disk dosyalarını bulmak için arama özel konumları belirtir. Arama yollarını listelendiği sıralama önemlidir. Her derleme için yolları listesine soldan sağa doğru aranır. Derleme temsil eden bir dosya bulunduğunda durur ve sonraki derleme başladığında arayın, arayın.<br /><br /> Bu parametreyi kabul eden aşağıdaki türde değerler:<br /><br /> -Bir dizin yolu.<br />-{HintPathFromItem}: görev inceleyeceği belirtir `HintPath` temel öğe meta verileri.<br />-{CandidateAssemblyFiles}: görev aracılığıyla geçirilen dosyaları inceleyeceği belirtir `CandidateAssemblyFiles` parametresi.<br />-{Kayıt defteri: _AssemblyFoldersBase\_, _RuntimeVersion\_, _AssemblyFoldersSuffix\_}:<br />-{AssemblyFolders}: görevi, Visual Studio.NET 2003 bulma derlemeleri gelen kayıt düzeni kullanacağı belirtir.<br />-{GAC}: görev GAC'de arama yapacağı belirtir.<br />-{RawFileName}: görev dikkate alınır belirtir `Include` öğesinin tam yol ve dosya adı değeri.|  
|`SerializationAssemblyFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` salt okunur çıkış parametresi.<br /><br /> Bulunan tüm XML serileştirme derlemelerini içerir. Bu öğeleri CopyLocal işaretli = true ise ve yalnızca başvuru ya da mevcut için bu öğeyi neden bağımlılık CopyLocal ise = true.<br /><br /> `Boolean` Meta verileri CopyLocal belirtilen başvurunun çıkış dizinine kopyalanmasının gerekip gerekmediğini belirtir.|  
|`Silent`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, günlüğe ileti kaydetmedi. Varsayılan değer `false` şeklindedir.|  
|`StateFile`|İsteğe bağlı `String` parametresi.<br /><br /> Derleme Durumu Bu görev için Ara kaydedileceği konumu belirtir bir dosya adı belirtir.|  
|`SuggestedRedirects`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` salt okunur çıkış parametresi.<br /><br /> Her ayrı çakışan derleme kimliği için değerinden bağımsız olarak bir öğeyi içeren `AutoUnify` parametresi. Bu, her bir kültür ve uygulama yapılandırma dosyasında bir uygun bindingRedirect girdisi yok bulundu PKT içerir.<br /><br /> Her öğe, isteğe bağlı olarak aşağıdaki bilgileri içerir:<br /><br /> -   `Include` Öznitelik: derleme ailesi 0.0.0.0 sürüm alan değerine sahip tam adını içerir<br />-   `MaxVersion` öğe meta verileri: en yüksek sürüm numarasını içerir.|  
|`TargetedRuntimeVersion`|İsteğe bağlı `String` parametresi.<br /><br /> Hedef, örneğin, 2.0.57027 veya v2.0.57027 çalışma zamanı sürümünü belirtir.|  
|`TargetFrameworkDirectories`|İsteğe bağlı `String[]` parametresi.<br /><br /> Hedef framework dizinin yolunu belirtir. Bu parametre, sonuçta elde edilen öğeleri CopyLocal durumunu belirlemek için gereklidir.<br /><br /> Bu parametre belirtilmezse, sonuçta elde edilen öğe olması olacaktır CopyLocal değerini `true` açıkça sahip olmadıkları sürece bir `Private` meta veri değeri `true` kendi kaynak öğe üzerinde.|  
|`TargetFrameworkMoniker`|İsteğe bağlı `String` parametresi.<br /><br /> Varsa, izlemek için TargetFrameworkMoniker. Bu, günlüğe kaydetme için kullanılır.|  
|`TargetFrameworkMonikerDisplayName`|İsteğe bağlı `String` parametresi.<br /><br /> Varsa, izlemek için TargetFrameworkMoniker görünen adı. Bu, günlüğe kaydetme için kullanılır.|  
|`TargetFrameworkSubsets`|İsteğe bağlı `String[]` parametresi.<br /><br /> Hedef framework dizinler için aranacak hedef framework alt kümesi adlarının bir listesini içerir.|  
|`TargetFrameworkVersion`|İsteğe bağlı `String` parametresi.<br /><br /> Proje hedef framework sürümü. Varsayılan değer boş olduğu için hedef framework'ü temel başvuruları filtre anlamına gelir.|  
|`TargetProcessorArchitecture`|İsteğe bağlı `String` parametresi.<br /><br /> Tercih edilen hedef İşlemci mimarisi. Genel Derleme Önbelleği (GAC) başvurular çözümlemek için kullanılır.<br /><br /> Bu parametre değerini alabilir `x86`, `IA64` veya `AMD64`.<br /><br /> Bu parametre yoksa, görevi şu anda çalışan işlem mimarisiyle derlemeleri ilk olarak değerlendirir. Derleme yok bulunursa görev olan derlemeler GAC içindeki göz önünde bulundurur `ProcessorArchitecture` değerini `MSIL` veya hiç `ProcessorArchitecture` değeri.|  
  
## <a name="warnings"></a>Uyarılar  
 Aşağıdaki uyarılar kaydedilir:  
  
-   `ResolveAssemblyReference.TurnOnAutoGenerateBindingRedirects`  
  
-   `ResolveAssemblyReference.SuggestedRedirects`  
  
-   `ResolveAssemblyReference.FoundConflicts`  
  
-   `ResolveAssemblyReference.AssemblyFoldersExSearchLocations`  
  
-   `ResolveAssemblyReference.UnifiedPrimaryReference`  
  
-   `ResolveAssemblyReference.PrimaryReference`  
  
-   `ResolveAssemblyReference.UnifiedDependency`  
  
-   `ResolveAssemblyReference.UnificationByAutoUnify`  
  
-   `ResolveAssemblyReference.UnificationByAppConfig`  
  
-   `ResolveAssemblyReference.UnificationByFrameworkRetarget`  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametrelerin yanı sıra, bu görev parametreleri devralan <xref:Microsoft.Build.Tasks.TaskExtension> kendisi sınıfının devraldığı <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametrelerin ve Tanımlamaların bir listesi için bkz. [TaskExtension temel sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevleri](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)



