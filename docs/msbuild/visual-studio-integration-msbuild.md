---
title: Visual Studio tümleştirmesi (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, reference resolution
- MSBuild, well-known target names
- MSBuild, hosting
- MSBuild, editing project files
- MSBuild, Visual Studio integration
- MSBuild, IntelliSense
- MSBuild, output groups
- MSBuild, in-process compilers
- MSBuild, design-time target execution
ms.assetid: 06cd6d7f-8dc1-4e49-8a72-cc9e331d7bca
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dd9dd101508fc55ff6287af534ee57e53e95d4e8
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31575942"
---
# <a name="visual-studio-integration-msbuild"></a>Visual Studio Tümleştirmesi (MSBuild)
Visual Studio konakları [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] yüklemek ve yönetilen projeler derlemek için. Çünkü [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projesi, neredeyse her proje için sorumlu [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] biçimi başarıyla kullanılabilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]proje farklı bir aracı tarafından yönetilmiyor ve özelleştirilmiş derleme sürecinde sahip olsa bile.  
  
 Bu konuda, belirli yönleri açıklanmaktadır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]'s [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] , barındırma sayılacağı projeleri ve yük ve yapı içinde istiyor .targets dosyaları özelleştirirken [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Bunlar emin olun yardımcı olacak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IntelliSense ve iş özel projeniz için hata ayıklama gibi özellikler.  
  
 C++ projeleri hakkında daha fazla bilgi için bkz: [proje dosyalarını](/cpp/ide/project-files).  
  
## <a name="project-file-name-extensions"></a>Proje Dosya Adı Uzantıları  
 MSBuild.exe desen eşleştirme proje dosya adı uzantısını tanır. * proj. Ancak, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yalnızca bir alt kümesini projeye yükler dile özgü proje sistem belirlemek bu proje dosya adı uzantılarını tanır. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir dilden yok [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje sistemi tabanlı.  
  
 Örneğin, [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] proje sistem .csproj dosyaları yükler ancak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] .xxproj dosyasını yüklemek mümkün değil. Rastgele bir dilde kaynak dosyaları için bir proje dosyası olarak aynı uzantı kullanmalısınız [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] veya [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] proje içinde yüklenecek dosyaları [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="well-known-target-names"></a>İyi Bilinen Hedef Adları  
 Tıklatarak **yapı** komutunu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] varsayılan hedef projede yürütülür. Genellikle, bu hedef aynı zamanda adlı `Build`. Seçme **yeniden** veya **temiz** komut aynı ada sahip bir hedef projede yürütme deneyecek. Tıklatarak **Yayımla** adlı bir hedef yürütecek `PublishOnly` projesinde.  
  
## <a name="configurations-and-platforms"></a>Yapılandırmalar ve Platformlar  
 Yapılandırmaları temsil içinde [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projeleri özelliklerine göre gruplandırılmış bir `PropertyGroup` içeren öğe bir `Condition` özniteliği. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Proje yapılandırmaları ve görüntülemek için platformlar listesini oluşturmak için bu koşullar arar. Bu liste başarılı biçimde koşulları aşağıdakine benzer bir biçimde olmalıdır:  
  
```  
Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' "  
Condition=" '$(Configuration)' == 'Release' "   
Condition=" '$(Something)|$(Configuration)|$(SomethingElse)' == 'xxx|Debug|yyy' "  
```  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] koşullar görünür `PropertyGroup`, `ItemGroup`, `Import`, özellik ve bu amaçla öğesi öğeleri.  
  
## <a name="additional-build-actions"></a>Ek Yapı Eylemleri  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir dosyanın sahip bir proje öğesi türü adı değiştirmenize izin verir **yapı eylemi** özelliği [dosya özelliklerini](http://msdn.microsoft.com/en-us/013c4aed-08d6-4dce-a124-ca807ca08959) penceresi. `Compile`, `EmbeddedResource`, `Content`, ve `None` öğesi türü adları projenizdeki zaten başka bir öğe türü adları ile birlikte bu menüsünde her zaman listelenir. Tüm özel öğe türü adları bu menüde kullanılabilir her zaman emin olmak için adlı bir öğe türü adları ekleyebilirsiniz. `AvailableItemName`. Örneğin, aşağıdaki proje dosyanıza ekleme özel tür ekler `JScript` almak tüm projeleri için bu menüyü için:  
  
```xml  
<ItemGroup>  
    <AvailableItemName Include="JScript"/>  
</ItemGroup>  
```  
  
> [!NOTE]
>  Bazı öğesi türü adları özel [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ancak bu açılır listede değil.  
  
## <a name="in-process-compilers"></a>İşlem İçi Derleyiciler  
 Mümkün olduğunda, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] işlemdeki sürümünü kullanmayı dener [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] performansı artırmak için derleyicisi. (Uygulanamaz [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)].) Bu doğru çalışması, aşağıdaki koşullar karşılanmalıdır:  
  
-   Proje bir hedef olmalıdır adında bir görev `Vbc` için [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projeleri.  
  
-   `UseHostCompilerIfAvailable` Görevinin parametresi ayarlanmalıdır true.  
  
## <a name="design-time-intellisense"></a>Tasarım Zamanı IntelliSense  
 IntelliSense destek almak için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir yapı çıkış bütünleştirilmiş üretti önce aşağıdaki koşulların karşılanması gerekir:  
  
-   Adlı bir hedefi olmalıdır `Compile`.  
  
-   Her iki `Compile` hedef veya bağımlılıklarından biri çağırmalıdır derleyici görev proje için gibi `Csc` veya `Vbc`.  
  
-   Her iki `Compile` hedef veya bağımlılıklarından biri tüm gerekli parametreleri için IntelliSense, özellikle tüm başvurularını almak derleyici neden gerekir.  
  
-   "İşlem içi derleyiciler" bölümünde listelenen koşulların karşılanması gerekir.  
  
## <a name="building-solutions"></a>Çözümler Oluşturma  
 İçinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], çözüm dosyasını ve yapı proje sipariş tarafından denetlenen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] kendisi. Komut satırında msbuild.exe çözümüyle oluştururken [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] çözüm dosyasını ayrıştırır ve projeyi derlemeler sıralar. Her iki durumda da projeleri tek tek bağımlılık sırayla yerleşiktir ve proje için proje başvuruları çapraz geçiş değil. Tek tek projeler msbuild.exe ile yapılandırıldığında, buna karşılık, proje için proje başvuruları geçiş.  
  
 İçinde oluştururken [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], özellik `$(BuildingInsideVisualStudio)` ayarlanır `true`. Bu proje veya .targets dosyalarında farklı şekilde davranmasına yapı neden kullanılabilir.  
  
## <a name="displaying-properties-and-items"></a>Özellikleri ve Öğeleri Görüntüleme  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] belirli özellik adları ve değerleri algılar. Örneğin, aşağıdaki özellik projesinde neden olacak **Windows uygulaması** görünmesi **uygulama türü** kutusunda **Proje Tasarımcısı**.  
  
```xml  
<OutputType>WinExe</OutputType>  
```  
  
 Özellik değeri düzenlenebilecek **Proje Tasarımcısı** ve proje dosyasında kaydedilir. Böyle bir özellik elle düzenlemeye tarafından geçersiz bir değer verilirse, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projeye yüklendiğinde bir uyarı gösterir ve varsayılan bir değerle geçersiz değerini değiştirin.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Bazı özellikler için varsayılan değerleri bilir. Varsayılan olmayan değerleri sahip oldukları sürece bu özellikler proje dosyasına kalıcı değildir.  
  
 İçinde rastgele adlar özelliklerle görüntülenmez [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Rastgele özelliklerini değiştirmek için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], proje dosyasını XML düzenleyicisinde açın ve bunları el ile düzenleyin. Daha fazla bilgi için bkz: [Visual Studio proje dosyalarını düzenleme](#BKMK_EditingProjects) bu konunun ilerleyen bölümlerinde.  
  
 Proje rasgele öğesi türü adları ile tanımlanan varsayılan olarak, proje düğümünün altında Çözüm Gezgini'nde görüntülenen öğelerdir. Görüntü bir öğeden gizlenecek şekilde ayarlanmış `Visible` meta verileri `false`. Örneğin, aşağıdaki öğeyi Yapı işleminde katılacak olan ancak Çözüm Gezgini'nde gösterilmeyecek.  
  
```xml  
<ItemGroup>  
    <IntermediateFile Include="cache.temp">  
        <Visible>false</Visible>  
    </IntermediateFile>  
</ItemGroup>  
```  
  
 Projesine içeri aktarılan dosyalar bildirilen öğeler varsayılan olarak görüntülenmez. Oluşturma işlemi sırasında oluşturulan öğeleri hiçbir zaman Çözüm Gezgini'nde görüntülenir.  
  
## <a name="conditions-on-items-and-properties"></a>Öğeler ve Özellikler İle İlgili Koşullar  
 Derleme sırasında tüm koşulların tam olarak kullanılır.  
  
 Özellik değerlerini görüntülemek için özellikler belirlerken, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yapılandırma bağımlı farklı değerlendirilir göz önünde bulundurur özellikleri da yapılandırma bağımsız olarak değerlendirir. Özellikleri, yapılandırma bağımlı göz önünde bulundurur [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ayarlar `Configuration` ve `Platform` özellikleri uygun şekilde ve bildirir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projeyi yeniden değerlendirmek için. Özellikleri, yapılandırma bağımsız olarak, koşullar nasıl değerlendirilir belirsiz göz önünde bulundurur.  
  
 Koşullu deyimler öğeler üzerinde her zaman Çözüm Gezgininde öğenin görüntülenip görüntülenmeyeceğini karar verme amacıyla göz ardı edilir.  
  
## <a name="debugging"></a>Hata Ayıklama  
 Bul ve çıkış derlemesi başlatın ve hata ayıklayıcısını için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] özelliklere sahip olması `OutputPath`, `AssemblyName`, ve `OutputType` doğru tanımlanmadı. Hata ayıklayıcı yapı işlemi .pdb dosyasını oluşturmak derleyici neden değil, iliştirmek başarısız olur.  
  
## <a name="design-time-target-execution"></a>Tasarım Zamanı Hedef Yürütme  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir projeye yüklendiğinde hedefleri belirli adlarıyla yürütmek çalışır. Bu hedeflerde dahil `Compile`, `ResolveAssemblyReferences`, `ResolveCOMReferences`, `GetFrameworkPaths`, ve `CopyRunEnvironmentFiles`. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Bu hedeflerde derleyici IntelliSense sağlamak için başlatılabilir, hata ayıklayıcı başlatılabilir ve Çözüm Gezgini'nde görüntülenen başvuruları çözümlenebilir çalışır. Bu hedeflerde mevcut değilse, proje yük ve tasarım zamanı deneyimi ancak doğru şekilde derlenmesi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tam olarak işlevsel olmayacak.  
  
##  <a name="BKMK_EditingProjects"></a> Visual Studio proje dosyalarını düzenleme  
 Düzenlemek için bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] doğrudan proje, proje dosyası Visual Studio XML düzenleyicisinde açın.  
  
#### <a name="to-unload-and-edit-a-project-file-in-visual-studio"></a>Visual Studio'da bir proje dosyasının yüklemesini kaldırmak ve düzenlemek için  
  
1.  İçinde **Çözüm Gezgini**projesi için kısayol menüsünü açın ve ardından **projeyi**.  
  
     Proje işaretlenmiş **(kullanılamaz)**.  
  
2.  İçinde **Çözüm Gezgini**kullanılamaz proje için kısayol menüsünü açın ve ardından **Düzenle \<proje dosyası >**.  
  
     Proje dosyası Visual Studio XML Düzenleyicisi'nde açar.  
  
3.  Düzenleme, kaydedin ve ardından Proje dosyasını kapatın.  
  
4.  İçinde **Çözüm Gezgini**kullanılamaz proje için kısayol menüsünü açın ve ardından **projeyi yeniden yükle**.  
  
## <a name="intellisense-and-validation"></a>IntelliSense ve Doğrulama  
 Proje dosyalarını düzenlemek için XML Düzenleyicisi'ni kullanırken, IntelliSense ve doğrulama güdümlü tarafından [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] şema dosyaları. Bu bulunabilir şema önbelleğinde yüklendiğinden  *\<Visual Studio yükleme dizini >* \Xml\Schemas\1033\MSBuild.  
  
 Çekirdek [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] türleri tanımlanmış Microsoft.Build.Core.xsd ve genel türleri tarafından kullanılan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Microsoft.Build.CommonTypes.xsd tanımlanır. Böylece özel öğe türü adları, özellikler ve görevler için IntelliSense ve doğrulama sahip şemaları özelleştirmek için Microsoft.Build.xsd düzenleyin veya CommonTypes veya çekirdek şemaları içeren kendi şeması oluşturun. Düzenleyicisi'ni kullanarak bulmak için XML yönlendirmek için olacaktır kendi şema oluşturursanız **özellikleri** penceresi.  
  
## <a name="editing-loaded-project-files"></a>Yüklenmiş Proje Dosyalarını Düzenleme  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Proje dosyaları ve proje dosyalarını tarafından içeri aktarılan dosyaların içeriğini önbelleğe alır. Yüklenen proje dosyası düzenlerseniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] otomatik olarak değişikliklerin etkili olması için projeyi yeniden yüklemek isteyip istemediğinizi sorar. Ancak tarafından yüklenen bir proje alınan bir dosyayı düzenlerseniz, yeniden yükleme istemini olacaktır ve kaldırma ve el ile etkili değişiklikler yapmak için projeyi yeniden yükleyin.  
  
## <a name="output-groups"></a>Çıkış Grupları  
 Microsoft.Common.targets içinde tanımlanan birkaç hedefler biten adlara sahip `OutputGroups` veya `OutputGroupDependencies`. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proje çıktıları belirli listesini almak için bu hedeflerde çağırır. Örneğin, `SatelliteDllsProjectOutputGroup` hedef bir yapı oluşturur tüm uydu derlemelerinin bir liste oluşturur. Bu çıktı grupları, yayımlama ve dağıtım projesi için proje başvuruları gibi özellikler tarafından kullanılır. Bunları tanımlamayın projeleri yüklemek ve yapı içinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], ancak bazı özellikler çalışmayabilir.  
  
## <a name="reference-resolution"></a>Başvuru Çözümleme  
 Başvuru çözümlemesi gerçek derlemeleri bulmak için bir proje dosyasında depolanan başvuru öğelerini kullanarak işlemidir. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Her başvurusunda ayrıntılı özelliklerini göstermek için başvuru çözümlemesi tetiklemek gerekir **özellikleri** penceresi. Aşağıdaki listede üç tür başvuruları ve nasıl çözümleneceğini açıklar.  
  
-   Derleme başvuruları:  
  
     İyi bilinen ada sahip bir hedef proje sistemi çağırır `ResolveAssemblyReferences`. Bu hedef öğe türü adı öğeleriyle üretmesi gerekir `ReferencePath`. Bu öğelerin her biri bir öğe belirtimi olmalıdır (değerini `Include` öznitelik bir öğenin) başvuru tam yolunu içeren. Ek olarak aşağıdaki yeni meta geçtiğini giriş öğelerinden tüm meta veri öğeleri olmalıdır:  
  
    -   `CopyLocal`, derleme çıktı klasöre kopyalanan olup olmadığını gösteren ayarlamak true veya false.  
  
    -   `OriginalItemSpec`, özgün öğesi belirtimi başvuru içeren.  
  
    -   `ResolvedFrom`, gelen çözümlendiği "{TargetFrameworkDirectory}" ayarlamanız [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] dizin.  
  
-   COM başvurular:  
  
     İyi bilinen ada sahip bir hedef proje sistemi çağırır `ResolveCOMReferences`. Bu hedef öğe türü adı öğeleriyle üretmesi gerekir `ComReferenceWrappers`. Bu öğelerin her birini birlikte çalışma derlemesi COM başvuru için tam yolunu içeren bir öğeyi belirtimi olması gerekir. Öğeleri ada sahip kullanıcı girişi öğelerini aracılığıyla geçirilen, ayrıca yeni meta verilerden tüm meta veriler olmalıdır `CopyLocal`, derleme çıktı klasöre kopyalanan olup olmadığını gösteren true veya false ayarlayın  
  
-   Yerel başvuruları  
  
     İyi bilinen ada sahip bir hedef proje sistemi çağırır `ResolveNativeReferences`. Bu hedef öğe türü adı öğeleriyle üretmesi gerekir `NativeReferenceFile`. Öğeleri geçtiğini, meta verileri adlı yeni bir parçasını yanı sıra giriş öğelerinden tüm meta veriler olmalıdır `OriginalItemSpec`, özgün öğesi belirtimi başvuru içeren.  
  
## <a name="performance-shortcuts"></a>Performans Kısayolları  
 Visual STUDİO'da hata ayıklama başlatırsanız (F5 tuşuna seçerek veya seçerek **hata ayıklama**, **hata ayıklamayı Başlat** menü çubuğunda), oluşturma işlemi, performansı artırmak için hızlı güncelleştirme denetimi kullanır. Burada özelleştirilmiş derlemeleri sırayla yerleşik dosyaları oluşturmak bazı durumlarda, hızlı güncelleştirme denetimi doğru şekilde değişen dosyaları tanımlamaz. Daha kapsamlı güncelleştirmesi denetimleri gereken projeleri kapatma hızlı ortam değişkenini ayarlayarak denetimini devre dışı `DISABLEFASTUPTODATECHECK=1`. Alternatif olarak, projeleri bu proje veya projesine aktarır dosyasında bir MSBuild özelliği olarak ayarlayabilirsiniz.  
  
 Normal yapılar Visual Studio için hızlı güncelleştirme denetimi uygulanmaz ve bir komut isteminde yapı çağrılan sanki projesi oluşturacaksınız.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Visual Studio derleme işlemini genişletme](../msbuild/how-to-extend-the-visual-studio-build-process.md)   
 [IDE içinden derleme başlatma](../msbuild/starting-a-build-from-within-the-ide.md)   
 [.NET Framework uzantılarını kaydetme](../msbuild/registering-extensions-of-the-dotnet-framework.md)   
 [MSBuild kavramları](../msbuild/msbuild-concepts.md)   
 [Öğe unsuru (MSBuild)](../msbuild/item-element-msbuild.md)   
 [Özellik öğesi (MSBuild)](../msbuild/property-element-msbuild.md)   
 [Hedef öğe (MSBuild)](../msbuild/target-element-msbuild.md)   
 [CSC görevi](../msbuild/csc-task.md)   
 [Vbc Görevi](../msbuild/vbc-task.md)