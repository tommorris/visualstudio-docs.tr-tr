---
redirect_url: /visualstudio/extensibility/what-s-new-in-the-visual-studio-2017-sdk/
ms.openlocfilehash: 5706797ed88dce5b2f481b17d99e9501b960ddca
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
Başlık: "Basit çözüm yük (LSL) | Microsoft Docs"MS.özel:" "ms.date:" 17/01/2017"ms.reviewer:" "MS.Paket:" "ms.technology: 
  - "vs-IDE-sdk" ms.tgt_pltfrm: "" ms.topic: "makale" helpviewer_keywords: 
  - "VSPackages, basit çözüm yük"
  - "VSPackages, hızlı çözüm yük" ms.assetid: 0a71d91e-dc71-4d6b-bbfe-9e4ecd9e5fd1 caps.latest.revision: 1 Yazar: "gregvanl" ms.author: "gregvanl" Yöneticisi: ghogen
---
# <a name="lightweight-solution-load-lsl"></a>Basit çözüm yük (LSL)

## <a name="background-information-on-lsl"></a>LSL hakkında arka plan bilgileri

Basit çözüm yük, VS çözüm yükleme süresini önemli ölçüde azaltır, hızlı bir şekilde daha üretken olmasına olanak 2017 içinde yeni bir özelliktir. LSL etkinleştirildiğinde, bunlarla çalışmaya başlamadan kadar Visual Studio tamamen projeleri yüklemez.

Visual Studio uzantıları LSL etkileyebilir. Yüklenecek bir proje üzerinde özelliklerine bağlıdır uzantıları değil iş veya yanlış bu belgede ayrıntılı yönergeler uymadan iş.

LSL üzerinde daha ayrıntılı bilgiler için aşağıdaki bağlantıları kullanın:

* [Basit çözüm yük blogu](https://blogs.msdn.microsoft.com/visualstudio/2016/10/11/shorter-solution-load-time-in-visual-studio-15)
* Sorularınız mı var? Bizimle iletişime geçin[lslsupport@microsoft.com](mailto:lslsupport@microsoft.com)

## <a name="enable-the-setting-to-load-projects-in-deferred-mode"></a>Projeleri "Ertelenmiş" modunda yüklemek için bu ayarı etkinleştirin

1. Herhangi bir açık durumdaki çözümü kapatın.
2. Git **Araçları** > **seçeneği** > **projeler ve çözümler** > **genel** ayarları Sayfa.
3. Denetleme **basit çözüm yük** kutusunu ayarını etkinleştirin.

Yukarıdaki ayarıyla açık bir çözüm açıldığında, IDE projeleri düzenli bir görünümünü gösterir ancak projeleri yüklenmedi.

## <a name="differences-between-deferred-load-and-regular-load-of-projects"></a>Ertelenen yükleme ve normal yük projelerinin arasındaki farklar

Basit çözüm yük ile bir çözüm açarken projeleri yüklenmez. Bu "ertelenmiş projeleri için", saplama hiyerarşi oluşturulur. Çözüm Gezgini projelerin bazıları veya tümü "ertelenmiş modunda" olan bir kullanıcı Arabirimi göstergesi simgeler ve adlar projelerin beklenen görünümüyle gösterir.

Etkin LSL ile bir işlem tetiklendiğinde gerekli proje zaten tam olarak yüklenen uzantıları artık bekleyebilirsiniz. Bunlar yüklü projelerde bir bağımlılığa sahip olup olmadığını denetlemek arayanlar gerekir. Uzantı ertelenmiş proje bilgileri gerektiriyorsa, uzantı aşağıdakileri yapın:

1. Proje gerektiği gibi yükleyin.
2. Yeni **çalışma API'leri** yüklenirken olmadan ertelenmiş projeden bilgi almak için.

Yeni **çalışma API'leri** ertelenmiş projeden sahibi olan projenin kaynak dosyasını ve tüm belirtilen proje için kaynak dosyaları gibi bilgileri almak uzantılarına izin ver. Bazı durumlarda, yalnızca sınırlı sayıda projeleri yüklenmesi gerekir. Sağ işlemlerinin sıklığını, alternatif yaklaşımlar ve genel kullanıcı deneyimi kolaylığı arasında bir denge seçenektir.

Tüm proje ve çözüm yük hala LSL modunda olaylar ilgili. Bu beklenen bir davranış VS'den almak bileşenleri sağlar ve bunların ne zaman projeleri yüklenen olarak aynı şekilde davranır. Projenin yüklenmesi ile ilgili çözüm sırasında yapılan iş yine de önemli ölçüde azalır.

## <a name="ui-requirements-and-changes"></a>UI gereksinimler ve değişiklikler

Tüm kullanıcı Arabirimi yüklenen ve ertelenmiş projeleri eşit olarak ele almanız gerekir. Bu, bazı özel durumlar ile yüklenen bir proje üzerinde gerçekleştirilen herhangi bir eylem ertelenmiş projelerine uygulanabilir olması gerektiği anlamına gelir. Bunu başarmak özellikleri yardımcı olmak için yeni API'leri giriş yanı sıra var olan bazı platform API'leri değişiklik yoktur.

### <a name="expectations-for-ui"></a>UI için beklentiler

1. Özellikler projeleri yüklenen ya da ertelenmiş bağlı olarak hiçbir visual farkları göster gerekir.
2. Herhangi bir liste veya numaralandırma çözümün yüklenen projeleri üzerinden ertelenmiş projeleri eklemeniz gerekir.
3. Yüklenen bir proje karşı kullanılabilir herhangi bir eylem ertelenmiş proje karşı kullanılabilir olması gerekir.
4. Gereken özellikleri yüklemek için istek proje yalnızca:
  * Bir özellik ile doğrudan kullanıcı etkileşimi yok. Erken önlem projeleri yüklemez.
  * "Daha fazla sonuç görmek" hareketi kullanıcı tarafından yapılır. Aşağıda bu UI kılavuz için bkz.
  * Yalnızca tam olarak yüklenen proje eylemi karşılamak için kullanılabilir. LSL ve açık proje API'leri mümkün olduğunca kullanın ve özellik isteği işlevselliği eksik olduğunda ister gönderin.

### <a name="changes-in-platform-apis-to-help-drive-ui"></a>Platform sürücü UI yardımcı olmak için API değişiklikleri

1. Yeni API basit çözüm yük modu ve kaç tane projeleri ertelenmiş durumda açıldı, çözüm sormak için sağlanır.
2. Çözümdeki tüm ertelenmiş projeleri yüklendiğinde yeni bir olay için sağlanır.
3. Yeni API ertelenmiş varsa bir proje sormak için sağlanır.
4. Mevcut API'lerini ertelenmiş projeleri için yüklenen projeleri isterken içerecek şekilde güncelleştirildi.
5. Mevcut API'lerini güncelleştirilir çözüm açıldıktan sonra hızlı tam olarak yüklenen bir çözümdür.

### <a name="how-to-add-see-more-results-for-a-feature"></a>"Daha fazla sonuç görmek" bir özellik için ekleme.

Projeleri içeriğine sorgulaması özellikleri, ertelenmiş projeleri etkisini göz önünde bulundurmanız gerekir. Bazı durumlarda, özellikleri, sorgunun sonuçlarını LSL ve çalışma API'leri ertelenmiş proje için elde edebilirsiniz. Diğer durumlarda, bir özelliğin kısıtlamaları yüklenecek projeleri gerektirir. Bu durumlarda hem de kullanıcıların projeleri ve yeniden sorgula tamamen yüklenmesini olanak tanıyan yeni bir "Daha fazla sonuç görmek" hareketi sağlamalıdır. Bu hareketi olduğunda ertelenmiş projeleri projeleri gerçekte yüklü olduğunda mükemmel bir sonuç almak için bir yol kullanıcı verilirken en iyi yaklaşık vermek özellikleri etkinleştirir.

Özellikleri Genel algoritması olmalıdır:

### <a name="when-the-query-is-performed-over-a-single-project"></a>Sorgu tek bir proje üzerinde ne zaman gerçekleştirilir

```csharp
// IsInDeferredState() and EnsureProjectIsLoadedHelper() in this sample can be found in the "Helpful code snippets" section of this document
public void Query(IVsHierarchy projectToQuery)
{
    // 1. Perform calculation/query
    DoQuery(projectToQuery);

    // 2. Present results to the user
    ShowResults();

    // 3. If the project was deferred, then present a "See More Results" UI element
    if (IsInDeferredState(projectToQuery))
    {
        ShowSeeMoreResults();
    }
}

public void OnClick_SeeMoreResults()
{
    // 1. Ask ask for the project to be loaded
    IVsHierarchy projectFromLastQuery = GetProjectFromLastQuery();
    IVsHierarchy loadedProject = EnsureProjectIsLoadedHelper(projectFromLastQuery);

    if (loadedProject != null)
    {
        // 2. Re-run the query on the loaded projects
        Query(loadedProject);
    }
    else
    {
        ShowErrorMessage();
    }
}
```

### <a name="when-the-query-is-performed-over-the-whole-solution"></a>Sorgu tam çözüm üzerinde ne zaman gerçekleştirilir

```csharp
// Requires Microsoft.VisualStudio.Shell.Interop.15.0.DesignTime.dll
public void Query()
{
    // 1. Perform calculation/query
    DoQuery();

    // 2. Present results to the user
    ShowResults();

    // 3. If there were deferred projects, then present a "See More Results from all projects" UI element
    var solution = // the solution
    object deferredCount = 0;
    int hr = ((IVsSolution)solution).GetProperty((int)__VSPROPID7.VSPROPID_DeferredProjectCount, out deferredCount);
    if (ErrorHandler.Succeeded(hr) && ((int)deferredCount > 0))
    {
        ShowSeeMoreResults();
    }
}

public void OnClick_SeeMoreResults()
{
    // 1. Force the solution to load, as requested by the user. This brings up a UI with a "Cancel" button (unless supppresed with __VSBSLFLAGS.VSBSLFLAGS_NotCancelable)
    var solution = // get IVsSolution4
    int hr = ((IVsSolution4)solution).EnsureSolutionIsLoaded((uint)__VSBSLFLAGS.VSBSLFLAGS_None);
    if (ErrorHandler.Succeeded(hr))
    {
        // 2. Re-run the query
        Query();
    }
    else
    {
        ShowErrorMessage();
    }
}
```

## <a name="api-changes"></a>API değişiklikleri

### <a name="new-api"></a>Yeni API

IVsSolution7.IsSolutionLoadDeferred (out ertelenmiş bool)

Geçerli çözümü ertelenmiş modunda yüklerse true döndürür. Ertelenmiş tüm projeleri sonunda olsa bile, çözüm ertelenmiş modunda başlangıçta yüklendiyse, bu özellik geçerli oturumdaki (açık kullanıcı hareketlerini nedeniyle veya işlemleri tarafından zorlanan), yüklenen Not hala true döndürür.

__VSPROPID7. VSPROPID_DeferredProjectCount

Projeleri sayısı, şu anda ertelenmiş modunda döndürür. Bu özellik [0, VSPROPID_ProjectCount] aralığında bir değere sahip olacaktır.

__VSHPROPID9. VSHPROPID_IsDeferred

Bir proje hiyerarşisi ertelenmiş yük durumda ise true döndürür.

__VSENUMPROJFLAGS3 EPF_DEFERRED ve EPF_NOTDEFERRED değerlerle

Bu bayrak için geçirilebilir [IVsSolution.GetProjectEnum()](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivssolution.getprojectenum.aspx) ertelenmiş ve ertelenmiş olmayan projeleri yineleme.

### <a name="new-events"></a>Yeni olaylar

IVsSolutionEvents7.OnAfterLoadAllDeferredProjects()

Tüm ertelenmiş projeleri yüklenen sonra bu olay tetiklenir. Bu noktada VSPROPID_DeferredProjectCount 0'a eşit değil. Bu olay olmadığına dikkat edin çözüm yük bir parçası olarak oluşturulur ve bir oturumda hiç yükseltilmiş değil. Tüm ertelenmiş projeler varsa ve yüklendiğinde yalnızca tetiklenir.

### <a name="changes-to-existing-api"></a>Varolan API yapılan değişiklikler

* Geçirme [__VSENUMPROJFLAGS](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.__vsenumprojflags.aspx). İçin EPF_LOADEDINSOLUTION [IVsSolution.GetProjectEnum()](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivssolution.getprojectenum.aspx) ertelenmiş projeleri döndürür.
* Geçirme [__VSENUMPROJFLAGS](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.__vsenumprojflags.aspx). EPF_UNLOADEDINSOLUTION ertelenmiş projeleri döndürmez.
* [KnownUIContexts.SolutionExistsAndFullyLoadedContext](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.knownuicontexts.solutionexistsandfullyloadedcontext.aspx) ayarlamak çözüm açık true. Ertelenmiş projeleri bu bağlamda çok ayarlanır yüklü olarak kabul edilir öncesi LSL olmayan modda.
* [__VSPROPID](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.__vspropid.aspx). VSPROPID_ProjectCount yüklenir ve ertelenmiş projeleri toplamını döndürür.

## <a name="helpful-code-snippets"></a>Yardımcı kod parçacıkları

### <a name="check-if-a-solution-was-opened-in-deferred-load-mode"></a>Bir çözüm Ertelenen yükleme modunda açılmışsa denetleyin

```csharp
/// <summary>
/// Checks if the solution was opened in LSL mode.
/// </summary>
/// <returns>True if the solution was opened in LSL mode, false otherwise.</returns> public static bool IsSolutionLoadDeferred()
{
    IVsSolution7 vsSolution = ServiceProvider.GlobalProvider.GetService(typeof(SVsSolution)) as IVsSolution7;
    Assumes.Present(vsSolution);

    return vsSolution.IsSolutionLoadDeferred();
}
```

### <a name="check-if-a-project-is-deferred"></a>Bir proje ertelenmiş olmadığını denetleyin

```csharp
/// <summary>
/// Checks to see if a project is deferred.
/// </summary>
/// <param name="projectsToLoad">A set of deferred and/or loaded projects to ensure are loaded.</param>
/// <returns>True if the project is deferred. False if it is any other state, such as loaded, unloaded, or virtual.</returns>
/// <remarks>Requires Microsoft.VisualStudio.Shell.Interop.15.0.DesignTime.dll</remarks>
public static bool IsInDeferredState(IVsHierarchy vsHierarchy)
{
    object deferred;
    int hr = vsHierarchy.GetProperty((uint)VSConstants.VSITEMID.Root, (int)__VSHPROPID9.VSHPROPID_IsDeferred, out deferred);

    if (ErrorHandler.Succeeded(hr))
    {
        return (bool)deferred;
    }

    return false;
}
```

### <a name="load-a-project"></a>Bir proje yükle

```csharp
/// <summary>
/// Ensures a project is fully loaded.
/// </summary> /// <param name="projectToLoad">A deferred or loaded project to ensure is loaded.</param>
/// <remarks>Requires Microsoft.VisualStudio.Shell.15.0.dll and Microsoft.VisualStudio.Shell.Interop.dll</remarks>
public static IVsHierarchy EnsureProjectIsLoadedHelper(IVsHierarchy projectToLoad)
{
    int hr = VSConstants.S_OK;
    var solution = // get the solution

    // 1. Ask the solution to load the required project. To reduce wait time,
    //    we load only the project we need, not the entire solution.
    hr = projectToLoad.GetGuidProperty((uint)VSConstants.VSITEMID.Root, (int)__VSHPROPID.VSHPROPID_ProjectIDGuid, out projectGuid);
    hr = ErrorHandler.ThrowOnFailure(hr);
    hr = ((IVsSolution4)solution).EnsureProjectIsLoaded(projectGuid, (uint)__VSBSLFLAGS.VSBSLFLAGS_None);
    hr = ErrorHandler.ThrowOnFailure(hr);

    // 2. After the project is loaded, grab the latest IVsHierarchy object.
    IVsHierarchy loadedProject = null;
    hr = ((IVsSolution)solution).GetProjectOfGuid(projectGuid, out loadedProject);
    hr = ErrorHandler.ThrowOnFailure(hr);

    return loadedProject;
}
```

### <a name="load-a-set-of-projects"></a>Projeleri kümesi yükleme

```csharp
/// <summary>
/// Ensures a collection of IVsHierarchys are loaded. To be used when deferred projects absolutely cannot be used.
/// </summary>
/// <param name="projectsToLoad">A set of deferred and/or loaded projects to ensure are loaded.</param>
/// <remarks>Requires Microsoft.VisualStudio.Shell.15.0.dll and Microsoft.VisualStudio.Shell.Interop.dll</remarks>
public static IReadOnlyCollection<IVsHierarchy> EnsureProjectsAreLoadedHelper(IReadOnlyCollection<IVsHierarchy> projectsToLoad)
{
    if (projectsToLoad == null || projectsToLoad.Count == 0)
        return projectsToLoad;

    int hr = VSConstants.S_OK;
    List<Guid> projectGuids = new List<Guid>(projectsToLoad.Count);
    List<IVsHierarchy> loadedProjects = new List<IVsHierarchy>(projectsToLoad.Count);
    var solution = // get the solution

    // 1. Collect projects to force load
    foreach (var project in projectsToLoad)
    {
        Guid projectGuid;
        hr = project.GetGuidProperty((uint)VSConstants.VSITEMID.Root, (int)__VSHPROPID.VSHPROPID_ProjectIDGuid, out projectGuid)
        hr = ErrorHandler.ThrowOnFailure(hr);
        projectGuids.Add(projectGuid);
    }

    // 2. Ask the solution to load the required projects. To reduce wait time,
    //    we load only the projects we need, not the entire solution.
    hr = ((IVsSolution4)solution).EnsureProjectsAreLoaded(projectCount, projectGuids.ToArray(), (uint)__VSBSLFLAGS.VSBSLFLAGS_None);
    hr = ErrorHandler.ThrowOnFailure(hr);

    // 3. After the projects are loaded, grab the latest IVsHierarchy objects
    foreach (var projectGuid in projectGuids)
    {
        IVsHierarchy loadedProject = null;
        hr = ((IVsSolution)solution).GetProjectOfGuid(projectGuid, out loadedProject);
        hr = ErrorHandler.ThrowOnFailure(hr);
        loadedProjects.Add(loadedProject);
    }

    return loadedProjects;
}
```

### <a name="checks-if-the-solution-has-deferred-projects"></a>Çözüm projeleri ertelenmiş olmadığını denetler

```csharp
/// <summary>
/// Checks if the solution has deferred projects
/// </summary>
/// <returns>True if the solution has deferred projects, false otherwise.</returns>
public static bool SolutionHasDeferredProjects()
{
    IVsSolution vsSolution = ServiceProvider.GlobalProvider.GetService(typeof(SVsSolution)) as IVsSolution;
    Assumes.Present(vsSolution);
    object varHasDeferredProjects;
    if (ErrorHandler.Succeeded(vsSolution.GetProperty(
        (int)__VSPROPID7.VSPROPID_DeferredProjectCount, out varHasDeferredProjects)))
    {
        return (int)varHasDeferredProjects != 0;
    }

    return false;
}
```

## <a name="getting-detailed-information-with-workspace-apis"></a>Çalışma alanı API'leri ile ayrıntılı bilgileri alınırken

### <a name="how-to-get-detailed-info-on-a-lsl-solution"></a>LSL çözüm üzerinde ayrıntılı bilgi alma

Yeni çalışma API'leri bir çözüm hakkında ayrıntılı bilgi almak amacıyla IVsSolutionWorkspaceService aracılığıyla sunulur.

Bu API, geçerli çalışma alanı, etkin çözüm, yönetilen komut satırı bilgileri yanı sıra çalışma alanı için dizin hizmeti almak için kullanılabilir. Bu API'leri daha fazla ayrıntılı veri almak için dizin hizmeti kaynak projedeki tüm dosyalar bir, bir kaynak dosya sahibi olan projenin geçerli Çözümdeki tüm projeleri proje, vb. tüm P2P başvurularında yararlanabilirsiniz.

Aşağıdaki kod parçacıkları çalışma API'lerin kullanımını göstermektedir.

### <a name="get-ivssolutionworkspaceservice-initially"></a>IVsSolutionWorkspaceService başlangıçta Al

>**Not:** Lütfen IVsSolutionWorkspaceService çalışma API paket yüklenmesini önlemek için LSL senaryolarda yalnızca edinin.

```csharp
private readonly Lazy<IVsSolutionWorkspaceService> _solutionWorkspaceService;

[ImportingConstructor]
public DeferredProjectWorkspaceService(SVsServiceProvider serviceProvider)
{
    _solutionWorkspaceService = new Lazy<IVsSolutionWorkspaceService>(
        () => (IVsSolutionWorkspaceService)serviceProvider.GetService(typeof(SVsSolutionWorkspaceService)));
}
```

>**Not:** _solutionWorkspaceService gevşek zaten başlatılmış aşağıdaki kod parçacıkları varsayalım.

### <a name="get-managed-command-line-info-for-deferred-projects-for-active-solution-configuration"></a>Etkin çözüm yapılandırma Ertelenen Projeler için yönetilen komut satırı bilgilerini al

```csharp
/// <summary>
/// Get the managed command line info for active solution configuration
/// </summary>
/// <param name="cancellationToken"> the cancellation token</param>
/// <returns></returns>
public async Task<IReadOnlyDictionary<string, ManagedCommandLineInfo>> GetManagedCommandLineInfoForConfigurationAsyn(CancellationToken cancellationToken)
{
    var dte = ServiceProvider.GetGlobalService(typeof(EnvDTE.DTE)) as EnvDTE.DTE;
    var solutionConfig = (EnvDTE80.SolutionConfiguration2)dte.Solution.SolutionBuild.ActiveConfiguration;

    // Solution configuration is something like "Debug|Any CPU"
    return await _solutionWorkspaceService.Value.GetManagedCommandLineInfoAsync(
        $"{solutionConfig.Name}|{solutionConfig.PlatformName}", cancellationToken).ConfigureAwait(false);
}
```

### <a name="get-the-active-solution-file-in-lsl"></a>LSL etkin çözüm dosyasında Al

```csharp
/// <summary>
/// Get the active solution file.
/// </summary>
/// <returns>The solution file.</returns>
public string GetActiveSolutionFile()
{
    return _solutionWorkspaceService.Value.SolutionFile;
}
```

### <a name="get-the-owning-project-of-a-source-file"></a>Bir kaynak dosya sahibi olan projenin Al

```csharp
/// <summary>
/// Get the owning projects of a source file.
/// </summary>
/// <param name="filePath">the source file path.</param>
/// <returns></returns>
public async Task<IEnumerable<string>> GetOwningProjectAsync(string filePath)
{
    var workspace = _solutionWorkspaceService.Value.CurrentWorkspace;
    var indexService = workspace.GetIndexWorkspaceService();
    var result = await indexService.GetFileDependantsAsync(filePath, null, String.Empty, (int)FileReferenceInfoType.Source);
    return result.Select(f => f.Path);
}
```

### <a name="get-all-source-files-from-a-project"></a>Tüm kaynak dosyalarının bir projeden alın

```csharp
/// <summary>
/// Get all source files from a project.
/// </summary>
/// <param name="projectFilePath">the project file path.</param>
/// <returns></returns>
public async Task<IEnumerable<string>> GetFileReferenceAsync(string projectFilePath)
{
    var workspace = _solutionWorkspaceService.Value.CurrentWorkspace;
    var indexService = workspace.GetIndexWorkspaceService();
    var fileReferenceResult = await indexService.GetFileReferencesAsync(projectFilePath, referenceTypes: (int)FileReferenceInfoType.Source);
    return fileReferenceResult.Select(f => f.Path);
}
```

### <a name="get-the-p2p-references-in-a-project"></a>Projede P2P başvuruları alma

```csharp
/// <summary>
/// Get outputs of project.
/// </summary>
/// <param name="projectFilePath">the project file path.</param>
/// <returns></returns>
public async Task<IEnumerable<string>> GetFileReferenceAsync(string projectFilePath)
{
    var workspace = _solutionWorkspaceService.Value.CurrentWorkspace;
    var indexService = workspace.GetIndexWorkspaceService();
    var fileReferenceResult = await indexService.GetFileReferencesAsync(projectFilePath, context: "Debug|AnyCPU", referenceTypes: (int)FileReferenceInfoType.Output);
    return fileReferenceResult.Select(f => f.Path);
}
```

### <a name="get-all-the-projects-in-a-solution"></a>Bir çözümde tüm projeleri Al

```csharp
/// <summary>
/// Get the projects in a solution.
/// </summary>
/// <param name="solutionFilePath">the solution file path.</param>
/// <returns></returns>
public async Task<IEnumerable<string>> GetProjectsInSolutionAsync(string solutionFilePath)
{
    var workspace = _solutionWorkspaceService.Value.CurrentWorkspace;
    var indexService = workspace.GetIndexWorkspaceService();

    // Passing the configuration|Platform that projects apply to; passing null will return projects with all configurations.
    var result = await indexService.GetFileReferencesAsync(solutionFilePath, context: "Debug|AnyCPU", referenceTypes: (int)FileReferenceInfoType.ProjectReference);
    return result.Select(f => f.Path);
}
```

## <a name="troubleshooting"></a>Sorun giderme

LSL yapısı nedeniyle, kullanıcılar yüklenir ve ertelenmiş projeler arasında bir fark göremez kasıtlıdır. Bu özelliği geliştirme ve test zorlaştırabilir.

Görsel ipuçları ertelenmiş projeleri için kullanıcı arabiriminde aşağıdakileri yaparak etkinleştirebilirsiniz:

1. Visual Studio’yu kapatın
2. Regedit.exe
3. HKLM seçin
4. Dosya > Hive yükleme
5. `%localappdata%\microsoft\visualstudio\15.0_<instance ID>\privateregistry.bin`
6. "Visual Studio" anahtar adı girin
7. Ayarlama `HKLM\VisualStudio\Software\Microsoft\VisualStudio\15.0_<instanceID>\FeatureFlags\Solution\Loading\Deferred\Hint\Value=1` (DWORD)
8. HKLM\VisualStudio seçin
9. Dosya > Hive kaldırma
10. Visual Studio'yu başlatın

Başka sorunuz için lütfen ulaşmak [ lslsupport@microsoft.com ](mailto:lslsupport@microsoft.com).






