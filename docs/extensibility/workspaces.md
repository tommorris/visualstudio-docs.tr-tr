---
title: Visual Studio çalışma alanları | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 3489592a-dc0c-4cd3-9b08-cd367626980a
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: 0230201677fd2422817ca1fbeab6679a424e5c05
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31145977"
---
# <a name="workspaces"></a>Çalışma Alanları

Nasıl Visual Studio dosyaların herhangi bir koleksiyonu temsil eden bir çalışma alanı olan [Klasör Aç](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md), ve tarafından temsil edilen <xref:Microsoft.VisualStudio.Workspace.IWorkspace> türü. Klasördeki dosyalar ile ilgili özellikler ve içeriği tek başına çalışma anlamıyor. Bunun yerine, oluşturabilir ve diğerleri bağlı davranamaz verileri kullanmak için API'ler özellikler ve uzantılar genel bir dizi sağlar. Üreticileri aracılığıyla oluşurlar [Genişletilebilirlik Çerçevesi ile yönetilen](https://github.com/Microsoft/vs-mef/blob/master/doc/index.md) (MEF) kullanarak çeşitli verme öznitelikleri.

## <a name="workspace-providers-and-services"></a>Çalışma alanı sağlayıcıları ve Hizmetleri

Çalışma sağlayıcı ve Hizmetleri veri ve bir çalışma alanı içeriğini tepki vermek için işlevsellik sağlar. Bağlamsal dosya bilgilerini, kaynak dosyalarında simgeleri veya yapı işlevselliği.

Her iki kavramları kullanın bir [Fabrika düzeni](https://en.wikipedia.org/wiki/Factory_method_pattern) ve MEF çalışma tarafından üzerinden aktarılır. Tüm verme öznitelikleri uygulamak `IProviderMetadataBase` veya `IWorkspaceServiceFactoryMetadata`, ancak uzantıları verilen türleri için kullanması gereken somut türleri.

Sağlayıcı ve Hizmetleri arasındaki tek fark ilişkilerini çalışma alanı ' dir. Bir çalışma alanı belirli bir türdeki birçok sağlayıcısı olabilir, ancak yalnızca bir hizmeti belirli bir türdeki çalışma alanında oluşturulur. Örneğin, bir çalışma alanı çok sayıda dosya tarayıcısı sağlayıcıları ancak çalışma çalışma yalnızca bir dizin oluşturma hizmeti içeriyor.

Başka bir anahtar verilerini sağlayıcıları ve Hizmetleri tüketimini farktır. Çalışma alanı, birkaç nedenlerle sağlayıcılardan veri almak için giriş noktasıdır. İlk olarak, sağlayıcılar genellikle oluşturdukları veri dar bazı kümesine sahiptir. Verileri bir C# kaynak dosyası simgelerini olabilir veya dosya bağlamları için yapı bir _CMakeLists.txt_ dosya. Çalışma alanı, meta verileri hizalama istekle sağlayıcıları için bir tüketicinin isteği ile eşleşir. İkinci olarak, bazı senaryolar için birçok izin diğerlerinin isteğine senaryoları katkıda bulunmak için sağlayıcıları ile en yüksek öncelikli sağlayıcı kullanın.

Buna karşılık, uzantıları örnekleri alın ve doğrudan çalışma alanı Hizmetleri ile etkileşim. Genişletme yöntemleri `IWorkspace` gibi Visual Studio tarafından sağlanan hizmetlerin kullanılabilir <xref:Microsoft.VisualStudio.Workspace.WorkspaceServiceHelper.GetFileWatcherService%2A>. Uzantınızı çalışma hizmet bileşenlerinin uzantınızı içinde veya diğer uzantıları kullanmak için sunabilir. Tüketiciler kullanması gereken <xref:Microsoft.VisualStudio.Workspace.WorkspaceServiceHelper.GetServiceAsync%2A> veya sağladığınız üzerinde bir genişletme yöntemi `IWorkspace` türü.

>[!WARNING]
> Visual Studio ile çakışan Hizmetleri Yazar değil. Beklenmeyen sorunlarına yol açabilir.

## <a name="disposal-on-workspace-closure"></a>Çalışma alanı kapatma çıkışında

Bir çalışma alanı kapatması üzerinde Extender'larının dispose ancak zaman uyumsuz çağrı gerekebilir kodu. <xref:Microsoft.VisualStudio.Threading.IAsyncDisposable> Arabirimi, bu kod kolay yazma yapmak için kullanılabilir.

## <a name="related-types"></a>İlgili türleri

- <xref:Microsoft.VisualStudio.Workspace.IWorkspace> açılan bir klasörü gibi açılmış bir çalışma alanı için merkezi varlıktır.
- <xref:Microsoft.VisualStudio.Workspace.IWorkspaceProviderFactory`1> Çalışma alanı örneği başına bir sağlayıcı oluşturur.
- <xref:Microsoft.VisualStudio.Workspace.IWorkspaceServiceFactory> Çalışma alanı örneği başına bir hizmet oluşturur.
- <xref:Microsoft.VisualStudio.Threading.IAsyncDisposable> sağlayıcıları ve çıkarma sırasında zaman uyumsuz kodu çalıştırmak için gereken hizmetleri uygulanmalıdır.
- <xref:Microsoft.VisualStudio.Workspace.WorkspaceServiceHelper> iyi bilinen hizmetleri veya rasgele Hizmetleri erişmek için yardımcı yöntemleri sağlar.

## <a name="workspace-settings"></a>Çalışma ayarları

Çalışma alanları sahip bir <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsManager> bir çalışma alanı üzerinden basit ancak güçlü denetimi ile hizmet. Ayarları temel bir genel bakış için bkz: [yapı özelleştirebilir ve hata ayıklama görevleri](../ide/customize-build-and-debug-tasks-in-visual-studio.md).

Çoğu ayarlarını `SettingsType` türleri _.json_ dosyaları, gibi _VSWorkspaceSettings.json_ ve _tasks.vs.json_.

Basit yollar çalışma alanı içindeki "kapsamlar" Geçici çalışma alanı ayarları güç merkezi. Bir tüketici çağırdığında <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsManager.GetAggregatedSettings%2A>, ayar türü ve istenen yolunu dahil tüm kapsamlar toplanır. Kapsam toplama öncelik aşağıdaki gibidir:

1. "Çalışma alanı kökün genellikle olan yerel ayarları", `.vs` dizin.
1. İstenen yol kendisi.
1. İstenen yol üst dizini.
1. Tüm dizinleri kadar ve çalışma alanı kök dahil olmak üzere daha fazla üst.
1. "Kullanıcı dizinindedir genel ayarları",.

Sonuç örneği olan <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettings>. Bu nesne belirli bir tür için ayarları tutar ve anahtar adları ayarı olarak depolanan için sorgulanabilir `string`. <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettings.GetProperty%2A> Yöntemleri ve <xref:Microsoft.VisualStudio.Workspace.Settings.WorkspaceSettingsExtensions> genişletme yöntemleri beklediğiniz istenen ayarı değerin türünü bilmeniz çağıran. Çoğu ayarları dosyaları olarak kalıcı olarak _.json_ dosyaları, birçok çağrılarını kullanacağınız `string`, `bool`, `int`ve bu türlerin dizileri. Nesne türleri de desteklenir. Bu durumda, kullandığınız `IWorkspaceSettings` tür bağımsız değişkeni olarak kendisini. Örneğin:

```json
{
  "intValue": 1,
  "stringValue": "s",
  "boolValue": true,
  "stringArray": [
    "s1",
    "s2"
  ],
  "nestedIWorkspaceSettings": {
    "nestedString": "ns"
  }
}
```

Bu ayarları varsayılarak olan bir kullanıcının _VSWorkspaceSettings.json_, verileri olarak erişilebilir:

```csharp
using System.Collections.Generic;
using Microsoft.VisualStudio.Workspace;
using Microsoft.VisualStudio.Workspace.Settings;

private static void ReadSettings(IWorkspace workspace)
{
    IWorkspaceSettingsManager settingsManager = workspace.GetSettingsManager();
    IWorkspaceSettings settings = settingsManager.GetAggregatedSettings(SettingsTypes.Generic);

    // result == WorkspaceSettingsResult.Success
    WorkspaceSettingsResult result = settings.GetProperty("intValue", out int intValue);
    result = settings.GetProperty("stringValue", out string stringValue);
    result = settings.GetProperty("boolValue", out bool boolValue);
    result = settings.GetProperty("stringArray", out string[] stringArray);
    result = settings.GetProperty("nestedIWorkspaceSettings", out IWorkspaceSettings nestedIWorkspaceSettings);
    result = nestedIWorkspaceSettings.GetProperty("nestedString", out string nestedString);

    // Extension method alternative using default values.
    int intValueOrDefault = settings.Property("intValue", /* default */ 42);

    // Missing key. result == WorkspaceSettingsResult.Undefined
    result = settings.GetProperty("missing", out string missing);

    // Wrong type for a key. result == WorkspaceSettingsResult.Error
    result = settings.GetProperty("intValue", out IWorkspaceSettings notSettings);

    // Special ability to union "stringArray" across all scopes.
    IEnumerable<string> allStringArray = settings.UnionPropertyArray<string>("stringArray");
}
```

>[!NOTE]
>Bu ayarları API'leri kullanılabilen API'leri için ilgisiz `Microsoft.VisualStudio.Settings` ad alanı. Çalışma alanı ayarları ana belirsiz ve çalışma özgü ayarları dosyaları veya dinamik ayarları sağlayıcılarını kullanabilirsiniz.

### <a name="providing-dynamic-settings"></a>Dinamik ayarlarını sağlama

Uzantıları sağlayabilir <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsProvider>s. Bu bellek içi sağlayıcıları uzantılarının ayarlarını ekleyin veya başkalarının geçersiz kılma olanak sağlar.

Dışarı aktarma bir `IWorkspaceSettingsProvider` diğer çalışma sağlayıcıları farklı. Fabrika değil `IWorkspaceProviderFactory` ve özel öznitelik türü yok. Bunun yerine, uygulama <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsProviderFactory> ve `[Export(typeof(IWorkspaceSettingsProviderFactory))]`.

```csharp
// Common workspace provider factory pattern
[ExportFeatureProvider(some, args, to, export)]
internal class MyProviderFactory : IWorkspaceProviderFactory<IFeatureProvider>
{
     IFeatureProvider CreateProvider(IWorkspace workspace) => new Provider(workspace);
}

// IWorkspaceSettingsProvider pattern
[Export(typeof(IWorkspaceSettingsProviderFactory))]
internal class MySettingsProviderFactory : IWorkspaceSettingsProviderFactory
{
    // 100 is typically the value used by built-in settings providers. Lower value is higher priority.
    int Priority => 100;

    IWorkspaceSettingsProvider CreateSettingsProvider(IWorkspace workspace) => new MySettingsProvider(workspace);
}
```

>[!TIP]
>Döndüren yöntemler uygularken `IWorkspaceSettingsSource` (gibi `IWorkspaceSettingsProvider.GetSingleSettings`), bir örneğini döndürmek `IWorkspaceSettings` yerine `IWorkspaceSettingsSource`. `IWorkspaceSettings` Bazı ayarlar toplamalar sırasında yararlı olabilecek daha fazla bilgi sağlar.

### <a name="settings-related-apis"></a>Ayarları ilgili API'ler

- <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsManager> okur ve çalışma alanı için ayarları toplar.
- <xref:Microsoft.VisualStudio.Workspace.WorkspaceServiceHelper.GetSettingsManager%2A> alır `IWorkspaceSettingsManager` bir çalışma alanı için.
- <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsManager.GetAggregatedSettings%2A> Tüm çakışan kapsamlara toplanan belirli bir kapsam için ayarları alır.
- <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettings> belirli bir kapsam için ayarları içerir.

## <a name="workspace-suggested-practices"></a>Uygulamalar çalışma alanı önerilen

- Nesnelerden dönmek `IWorkspaceProviderFactory.CreateProvider` veya unutmayın benzer API'leri kendi `Workspace` oluşturduğunuzda bağlamı. Bu nesne üzerinde oluşturmayı tutulur bekleniyor sağlayıcıları arabirimleri yazılır.
- Çalışma alanı özgü önbellekleri veya "Yerel ayarları" yolun çalışma alanının içindeki ayarları kaydedin. Dosyayı kullanmak için bir yol oluşturmak `Microsoft.VisualStudio.Workspace.WorkspaceHelper.MakeRootedUnderWorkingFolder` Visual Studio 2017 15.6 veya sonraki bir sürümü de. 15,6. sürümden önceki sürümler için aşağıdaki kod parçacığında kullanın:

```csharp
using System.IO;
using Microsoft.VisualStudio.Workspace;
using Microsoft.VisualStudio.Workspace.Settings;

private static string MakeRootedUnderWorkingFolder(IWorkspace workspace, string relativePath)
{
    string workingFolder = workspace.GetSettingsManager().GetAggregatedSettings(SettingsTypes.WorkspaceControlSettings).Property<string>("WorkingFolder");
    return Path.Combine(workingFolder, relativePath);
}
```

## <a name="solution-events-and-package-auto-load"></a>Çözüm olayları ve paket otomatik yük

Yüklü paketler uygulayabilirsiniz `IVsSolutionEvents7` ve çağırma `IVsSolution.AdviseSolutionEvents`. Açma ve Visual Studio klasöründe kapatma olay içerir.

Bir kullanıcı Arabirimi bağlamı otomatik yük paketiniz için kullanılabilir. Değer `4646B819-1AE0-4E79-97F4-8A8176FDD664`.

## <a name="troubleshooting"></a>Sorun giderme

### <a name="the-sourceexplorerpackage-package-did-not-load-correctly"></a>SourceExplorerPackage paketi düzgün yüklenemedi

Çalışma alanı genişletilebilirlik yoğun MEF tabanlıdır ve birleşim hataları yüklenemedi için açık klasörü barındıran paket neden olur. Örneğin, bir uzantı türü ile aktarır `ExportFileContextProviderAttribute`, ancak türü yalnızca uygulayan `IWorkspaceProviderFactory<IFileContextActionProvider>`, Visual Studio'da bir klasör açmaya çalışırken bir hata oluşur. Hata ayrıntılarını bulunabilir _%LOCALAPPDATA%\Microsoft\VisualStudio\15.0_id\ComponentModelCache\Microsoft.VisualStudio.Default.err_. Uzantısı tarafından uygulanan türleri için hataları çözümleyin.

## <a name="next-steps"></a>Sonraki adımlar

* [Dosya içerikleri](workspace-file-contexts.md) -dosya bağlam sağlayıcıları Klasör Aç çalışma alanları için kod Intelligence getirin. 
* [Dizin oluşturma](workspace-indexing.md) -çalışma dizinini toplar ve çalışma alanı hakkında bilgi devam ettirir.
