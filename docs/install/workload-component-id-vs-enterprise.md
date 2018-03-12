---
title: "Visual Studio Enterprise 2017 iş yükü ve Bileşen kimlikleri | Microsoft Docs"
description: "İş yükü ve Bileşen kimlikleri Visual Studio komut satırını kullanarak yükleme veya bağımlılık VSIX bildirim olarak belirtmek için kullanın"
keywords: 
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.date: 03/05/2018
ms.topic: article
helpviewer_keywords:
- workload ID, Visual Studio
- component ID, Visual Studio
- install Visual Studio, administrator guide
ms.service: 
ms.technology:
- vs-acquisition
ms.assetid: be73e3af-d87b-4d14-bd08-2e4bda074fb3
ms.workload:
- multiple
ms.openlocfilehash: e8ac85cd7a19270692e7b997144f6235fd480bef
ms.sourcegitcommit: 3285243d6c0521266053340fe06505885d12178b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2018
---
# <a name="visual-studio-enterprise-2017-component-directory"></a>Visual Studio Enterprise 2017 bileşen dizini

Tablolar bu sayfa listede kimlikleri, Visual Studio komut satırını kullanarak yüklemek için kullanabileceğiniz veya bağımlılık VSIX bildirim olarak belirtebilirsiniz. Biz yayın güncelleştirmeler Visual Studio gibi ek bileşenleri ekleyeceğiz olduğunu unutmayın.

Ayrıca sayfa hakkında aşağıdakileri unutmayın:

* Her iş yükü iş yükü Kimliğini ve iş yükü için kullanılabilir olan bileşenleri tablosu arkasından kendi bölümü vardır.
* Varsayılan olarak, **gerekli** bileşenleri, iş yükü yüklediğinizde yüklenir.
* İsterseniz, ayrıca yükleyebilirsiniz **önerilen** ve **isteğe bağlı** bileşenleri.
* Herhangi bir iş yükü ile bağlı değil ek bileşenleri listeleyen bir bölüm de ekledik.

VSIX bildiriminizi bağımlılıkları ayarladığınızda, Bileşen kimlikleri yalnızca belirtmeniz gerekir. Bizim minimum Bileşen bağımlılıkları belirlemek için bu sayfadaki tabloları kullanın. Bazı senaryolarda bu bir iş yükü yalnızca bir bileşenden belirttiğiniz anlamına gelebilir. Diğer senaryolarda, tek bir iş yükünü birden çok bileşenlerini veya birden çok iş yükünün birden çok bileşenlerini belirtin gelebilir. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio 2017 genişletilebilirlik projelerine geçirmek](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md) sayfası.

Bu kimlikleri kullanma hakkında daha fazla bilgi için bkz: [Visual Studio 2017 yüklemek için komut satırı parametrelerini kullanmak](use-command-line-parameters-to-install-visual-studio.md) sayfası. Ve iş yükü ve diğer ürünler için Bileşen kimlikleri listesi için bkz: [Visual Studio 2017 iş yükü ve Bileşen kimlikleri](workload-and-component-ids.md) sayfası.

## <a name="visual-studio-core-editor-included-with-visual-studio-enterprise-2017"></a>Visual Studio çekirdek Düzenleyici (Visual Studio Enterprise 2017 ile dahil)

**Kimliği:** Microsoft.VisualStudio.Workload.CoreEditor

**Açıklama:** sözdizimi algılayan kod düzenleme, dahil olmak üzere Visual Studio çekirdek Kabuk deneyimi kaynak kodu denetimi ve yönetim iş öğesi.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.VisualStudio.Component.CoreEditor | Visual Studio çekirdek Düzenleyicisi | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.StartPageExperiment.Cpp | Visual Studio Başlangıç sayfası C++ kullanıcılar için | 15.0.27128.1 | İsteğe Bağlı

## <a name="azure-development"></a>Azure geliştirme

**Kimliği:** Microsoft.VisualStudio.Workload.Azure

**Açıklama:** Azure SDK'ları, araçları ve projeleri geliştirmek için kaynakları oluşturma ve Docker desteği dahil olmak üzere kapsayıcıları oluşturma uygulamaları, bulut.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.Microsoft.VisualStudio.RazorExtension | Razor dili Hizmetleri | 15.0.26720.2 | Gerekli
Component.Microsoft.VisualStudio.Web.AzureFunctions | Microsoft Azure WebJobs Tools | 15.6.27309.0 | Gerekli
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | Gerekli
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.0.27205.0 | Gerekli
Microsoft.Component.MSBuild | MSBuild | 15.6.27309.0 | Gerekli
Microsoft.Component.NetFX.Core.Runtime | .NET çekirdeği çalışma zamanı | 15.0.26208.0 | Gerekli
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 paketi hedefleme | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.NetCore.ComponentGroup.DevelopmentTools | .NET core 2.0 geliştirme araçları | 15.6.27421.1 | Gerekli
Microsoft.NetCore.ComponentGroup.Web | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.0.26621.2 | Gerekli
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure yazma araçları | 15.0.26621.2 | Gerekli
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET için Azure kitaplıkları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Azure işlem öykünücüsü | 15.0.26621.2 | Gerekli
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Azure Storage öykünücüsü | 15.6.27413.0 | Gerekli
Microsoft.VisualStudio.Component.CloudExplorer | Cloud Explorer | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Common.Azure.Tools | Bağlantı ve yayımlama araçları | 1.10.50912.1 | Gerekli
Microsoft.VisualStudio.Component.DockerTools | Kapsayıcı geliştirme araçları | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.FSharp | F # dil desteği | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılama | 15.0.26606.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Yönetilen masaüstü iş yükü çekirdek | 15.6.27323.2 | Gerekli
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir paketi hedefleme kitaplığı | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.0.27205.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL çalışma zamanı | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server komut satırı yardımcı programları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.DataSources | Veri kaynakları için SQL Server desteği | 15.0.26621.2 | Gerekli
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Veri Araçları | 15.0.26906.1 | Gerekli
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TextTemplating | Metin şablonu dönüştürme | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TypeScript.2.6 | TypeScript 2.6 SDK | 15.0.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Web | ASP.NET ve web geliştirme araçları | 15.6.27323.2 | Gerekli
Microsoft.VisualStudio.Component.WebDeploy | Web Dağıtımı | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.Azure.Prerequisites | Azure geliştirme önkoşulları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.AzureFunctions | Microsoft Azure WebJobs Tools | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.Web | Önkoşullar ASP.NET ve web geliştirme araçları | 15.6.27323.2 | Gerekli
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.0.27005.2 | Gerekli
Microsoft.Component.Azure.DataLake.Tools | Azure Data Lake ve akış analiz araçları | 15.0.27005.2 | Önerilen
Microsoft.Net.Component.4.5.1.TargetingPack | .NET framework 4.5.1 hedefleme paketi | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.6.TargetingPack | .NET framework 4.6 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.TargetingPack | .NET framework 4 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET framework 4 – 4.6 geliştirme araçları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.AspNet45 | Gelişmiş ASP.NET özellikleri | 15.6.27428.1 | Önerilen
Microsoft.VisualStudio.Component.Azure.MobileAppsSdk | Azure Mobile Apps SDK | 15.6.27428.1 | Önerilen
Microsoft.VisualStudio.Component.Azure.ResourceManager.Tools | Azure Resource Manager çekirdek araçları | 15.0.27005.2 | Önerilen
Microsoft.VisualStudio.Component.Azure.ServiceFabric.Tools | Service Fabric Araçları | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.Azure.Waverton | Azure bulut Hizmetleri Çekirdek araçları | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.Debugger.Snapshot | Anlık görüntü hata ayıklayıcı | 15.6.27428.1 | Önerilen
Microsoft.VisualStudio.Component.DiagnosticTools | .NET Profil Araçları | 15.6.27421.1 | Önerilen
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.6.27323.2 | Önerilen
Microsoft.VisualStudio.ComponentGroup.Azure.CloudServices | Azure bulut Hizmetleri Araçları | 15.0.26504.0 | Önerilen
Microsoft.VisualStudio.ComponentGroup.Azure.ResourceManager.Tools | Azure Kaynak Yöneticisi Araçları | 15.0.27005.2 | Önerilen
Component.PowerShellTools.VS2017 | PowerShell araçları | 3.0.552 | İsteğe Bağlı
Microsoft.Net.Component.4.6.2.SDK | .NET framework 4.6.2 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.2.TargetingPack | .NET framework 4.6.2 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.SDK | .NET Framework 4.7.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.TargetingPack | .NET framework 4.7.1 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.SDK | .NET framework 4.7 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.TargetingPack | .NET framework 4.7 paketi hedefleme | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET framework 4.6.2 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET framework 4.7.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET framework 4.7 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Core.Component.SDK.1x | .NET core 1.0 1.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.NetCore.1x.ComponentGroup.Web | .NET core Web 1.0 1.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Azure.Storage.AzCopy | Azure depolama AzCopy | 15.0.26906.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 15.0.27205.0 | İsteğe Bağlı

## <a name="data-storage-and-processing"></a>Veri depolama ve işleme

**Kimliği:** Microsoft.VisualStudio.Workload.Data

**Açıklama:** bağlan, geliştirme ve test etme, SQL Server, Azure Data Lake veya Hadoop ile veri çözümleri.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.Microsoft.VisualStudio.RazorExtension | Razor dili Hizmetleri | 15.0.26720.2 | Önerilen
Component.Redgate.ReadyRoll | Redgate ReadyRoll Core | 1.14.17.5347 | Önerilen
Component.Redgate.SQLPrompt.VsPackage | Redgate SQL Prompt Core | 8.2.5.2924 | Önerilen
Component.Redgate.SQLSearch.VSExtension | Redgate SQL Araması | 2.4.2.1439 | Önerilen
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | Önerilen
Microsoft.Component.Azure.DataLake.Tools | Azure Data Lake ve akış analiz araçları | 15.0.27005.2 | Önerilen
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.0.27205.0 | Önerilen
Microsoft.Component.MSBuild | MSBuild | 15.6.27309.0 | Önerilen
Microsoft.Net.Component.4.5.1.TargetingPack | .NET framework 4.5.1 hedefleme paketi | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 hedefleme paketi | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.6.TargetingPack | .NET framework 4.6 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.TargetingPack | .NET framework 4 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.6.27406.0 | Önerilen
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET framework 4 – 4.6 geliştirme araçları | 15.6.27406.0 | Önerilen
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.0.26621.2 | Önerilen
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure yazma araçları | 15.0.26621.2 | Önerilen
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET için Azure kitaplıkları | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Azure işlem öykünücüsü | 15.0.26621.2 | Önerilen
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Azure Storage öykünücüsü | 15.6.27413.0 | Önerilen
Microsoft.VisualStudio.Component.Azure.Waverton | Azure bulut Hizmetleri Çekirdek araçları | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.CloudExplorer | Cloud Explorer | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.Common.Azure.Tools | Bağlantı ve yayımlama araçları | 1.10.50912.1 | Önerilen
Microsoft.VisualStudio.Component.DockerTools | Kapsayıcı geliştirme araçları | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılama | 15.0.26606.0 | Önerilen
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Yönetilen masaüstü iş yükü çekirdek | 15.6.27323.2 | Önerilen
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir paketi hedefleme kitaplığı | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.0.27205.0 | Önerilen
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL çalışma zamanı | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server komut satırı yardımcı programları | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.SQL.DataSources | Veri kaynakları için SQL Server desteği | 15.0.26621.2 | Önerilen
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Veri Araçları | 15.0.26906.1 | Önerilen
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.TextTemplating | Metin şablonu dönüştürme | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.TypeScript.2.6 | TypeScript 2.6 SDK | 15.0.27406.0 | Önerilen
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Web | ASP.NET ve web geliştirme araçları | 15.6.27323.2 | Önerilen
Microsoft.VisualStudio.Component.WebDeploy | Web Dağıtımı | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.ComponentGroup.Web | Önkoşullar ASP.NET ve web geliştirme araçları | 15.6.27323.2 | Önerilen
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.0.27005.2 | Önerilen
Microsoft.VisualStudio.Component.FSharp.Desktop | F # Masaüstü dil desteği | 15.6.27323.2 | İsteğe Bağlı

## <a name="data-science-and-analytical-applications"></a>Veri bilimi ve analitik uygulamalar

**Kimliği:** Microsoft.VisualStudio.Workload.DataScience

**Açıklama:** diller ve Python, R ve F # gibi veri bilimi uygulamaları oluşturmak için araç.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.Anaconda3.x64 | Anaconda3 64-bit (5.0.0) | 5.0.0 | Önerilen
Microsoft.Component.CookiecutterTools | Cookiecutter şablon desteği | 15.0.26621.2 | Önerilen
Microsoft.Component.PythonTools | Python dil desteği | 15.0.26823.1 | Önerilen
Microsoft.Component.PythonTools.Web | Python web desteği | 15.0.27005.2 | Önerilen
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Common.Azure.Tools | Bağlantı ve yayımlama araçları | 1.10.50912.1 | Önerilen
Microsoft.VisualStudio.Component.FSharp.Desktop | F # Masaüstü dil desteği | 15.6.27323.2 | Önerilen
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.R.Open | Microsoft R istemci (3.3.2) | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.RHost | R geliştirme araçları çalışma zamanı desteği | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.0.27205.0 | Önerilen
Microsoft.VisualStudio.Component.RTools | R dil desteği | 15.0.26919.1 | Önerilen
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.TypeScript.2.6 | TypeScript 2.6 SDK | 15.0.27406.0 | Önerilen
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.WebDeploy | Web Dağıtımı | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.0.27005.2 | Önerilen
Component.Anaconda2.x64 | Anaconda2 64-bit (5.0.0) | 5.0.0 | İsteğe Bağlı
Component.Anaconda2.x86 | Anaconda2 32-bit (5.0.0) | 5.0.0 | İsteğe Bağlı
Component.Anaconda3.x86 | Anaconda3 32-bit (5.0.0) | 5.0.0 | İsteğe Bağlı
Microsoft.Component.VC.Runtime.UCRTSDK | Windows Evrensel CRT SDK'sı | 15.6.27309.0 | İsteğe Bağlı
Microsoft.ComponentGroup.PythonTools.NativeDevelopment | Python yerel geliştirme araçları | 15.0.27005.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Graphics.Tools | Grafik hata ayıklayıcı ve DirectX GPU Profil Oluşturucu | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Graphics.Win81 | Grafik araçları Windows 8.1 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.140 | VC ++ 2015.3 v140 araç takımı Masaüstü (x86, x64) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ çekirdek Özellikler | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.DiagnosticTools | C++ Profil Araçları | 15.0.26823.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 v141 araç takımı (x86, x64) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK | Windows Evrensel C çalışma zamanı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop | Windows 10 Masaüstü C++ [x86 hem x64] için SDK (10.0.16299.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | Windows 10 için SDK'sı (10.0.16299.0) UWP: C#, VB, JS | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP.Native | Windows 10 için SDK'sı (10.0.16299.0) UWP: C++ | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows81SDK | Windows 8.1 SDK | 15.6.27406.0 | İsteğe Bağlı

## <a name="net-desktop-development"></a>.NET masaüstü geliştirme

**Kimliği:** Microsoft.VisualStudio.Workload.ManagedDesktop

**Açıklama:** WPF, Windows Forms ve C#, Visual Basic ve F # kullanarak konsol uygulamaları oluşturma.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.0.27205.0 | Gerekli
Microsoft.Component.MSBuild | MSBuild | 15.6.27309.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Yönetilen masaüstü iş yükü çekirdek | 15.6.27323.2 | Gerekli
Microsoft.VisualStudio.Component.ManagedDesktop.Prerequisites | .NET masaüstü geliştirme araçları | 15.0.27205.0 | Gerekli
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir paketi hedefleme kitaplığı | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.0.27205.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TextTemplating | Metin şablonu dönüştürme | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Gerekli
Microsoft.ComponentGroup.Blend | Visual Studio için Blend | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.5.1.TargetingPack | .NET framework 4.5.1 hedefleme paketi | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 hedefleme paketi | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.6.TargetingPack | .NET framework 4.6 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.TargetingPack | .NET framework 4 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET framework 4 – 4.6 geliştirme araçları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Debugger.JustInTime | Tam zamanında hata ayıklayıcı | 15.0.27005.2 | Önerilen
Microsoft.VisualStudio.Component.DiagnosticTools | .NET Profil Araçları | 15.6.27421.1 | Önerilen
Microsoft.VisualStudio.Component.EntityFramework | Entity Framework 6 araçları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.6.27323.2 | Önerilen
Microsoft.VisualStudio.Component.LiveUnitTesting | Live Unit Testing | 15.0.26720.2 | Önerilen
Component.Dotfuscator | PreEmptive Protection - Dotfuscator | 15.0.26208.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.2.SDK | .NET framework 4.6.2 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.2.TargetingPack | .NET framework 4.6.2 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.SDK | .NET Framework 4.7.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.TargetingPack | .NET framework 4.7.1 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.SDK | .NET framework 4.7 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.TargetingPack | .NET framework 4.7 paketi hedefleme | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET framework 4.6.2 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET framework 4.7.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET framework 4.7 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Core.Component.SDK.1x | .NET core 1.0 1.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.NetCore.ComponentGroup.DevelopmentTools | .NET core 2.0 geliştirme araçları | 15.6.27421.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeClone | Kodu Kopyala | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeMap | Kod Haritası | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | Canlı bağımlılık doğrulama | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.FSharp | F # dil desteği | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.FSharp.Desktop | F # Masaüstü dil desteği | 15.6.27323.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.GraphDocument | DGML Düzenleyicisi | 15.0.27005.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 15.0.27205.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.WebDeploy | Web Dağıtımı | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | Mimari ve çözümleme araçları | 15.0.26208.0 | İsteğe Bağlı

## <a name="game-development-with-unity"></a>Unity ile oyun geliştirme

**Kimliği:** Microsoft.VisualStudio.Workload.ManagedGame

**Açıklama:** 2B ve 3B oyunlar Unity, güçlü bir platformlar arası geliştirme ortamı oluşturun.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Net.Component.3.5.DeveloperTools | .NET framework 3.5 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.0.27205.0 | Gerekli
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.Unity | Unity için Visual Studio Araçları | 15.6.27309.0 | Gerekli
Component.UnityEngine.x64 | Unity 2017.2 64-bit Düzenleyicisi | 15.6.27406.0 | Önerilen
Component.UnityEngine.x86 | Unity 5.6 32-bit Düzenleyicisi | 15.6.27406.0 | Önerilen

## <a name="linux-development-with-c"></a>C++ ile Linux geliştirmesi

**Kimliği:** Microsoft.VisualStudio.Workload.NativeCrossPlat

**Açıklama:** Linux ortamında çalışan oluşturma ve hata ayıklama uygulamaları.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.MDD.Linux | Linux geliştirmesi için Visual C++ | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ çekirdek Özellikler | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Windows10SDK | Windows Evrensel C çalışma zamanı | 15.6.27406.0 | Gerekli
Component.Linux.CMake | CMake ve Linux için Visual C++ Araçları | 15.0.27005.2 | Önerilen
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 v141 araç takımı (x86, x64) | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop | Windows 10 Masaüstü C++ [x86 hem x64] için SDK (10.0.16299.0) | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | Windows 10 için SDK'sı (10.0.16299.0) UWP: C#, VB, JS | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP.Native | Windows 10 için SDK'sı (10.0.16299.0) UWP: C++ | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.0.27005.2 | Önerilen
Component.MDD.Linux.GCC.arm | Katıştırılmış ve IOT geliştirme | 15.6.27309.0 | İsteğe Bağlı

## <a name="desktop-development-with-c"></a>C++ ile masaüstü geliştirme

**Kimliği:** Microsoft.VisualStudio.Workload.NativeDesktop

**Açıklama:** Microsoft C++ araç takımı, ATL ve MFC kullanarak Windows Masaüstü uygulamaları oluşturun.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.ClassDesigner | Sınıf Tasarımcısı | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.CodeMap | Kod Haritası | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.GraphDocument | DGML Düzenleyicisi | 15.0.27005.2 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TextTemplating | Metin şablonu dönüştürme | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ çekirdek Özellikler | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VC.Redist.14.Latest | Visual C++ 2017 yeniden dağıtılabilir güncelleştirme | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Native | C++ için Mimari Araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Core | Visual C++ temel masaüstü özellikleri | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Debugger.JustInTime | Tam zamanında hata ayıklayıcı | 15.0.27005.2 | Önerilen
Microsoft.VisualStudio.Component.Graphics.Tools | Grafik hata ayıklayıcı ve DirectX GPU Profil Oluşturucu | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Graphics.Win81 | Grafik araçları Windows 8.1 SDK'sı | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.VC.ATL | Visual C++ ATL desteği | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.VC.CMake.Project | CMake için Visual C++ Araçları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.VC.DiagnosticTools | C++ Profil Araçları | 15.0.26823.1 | Önerilen
Microsoft.VisualStudio.Component.VC.TestAdapterForBoostTest | Test bağdaştırıcısı Boost.Test için | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.VC.TestAdapterForGoogleTest | Google testi için test bağdaştırıcısı | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 v141 araç takımı (x86, x64) | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop | Windows 10 Masaüstü C++ [x86 hem x64] için SDK (10.0.16299.0) | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | Windows 10 için SDK'sı (10.0.16299.0) UWP: C#, VB, JS | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP.Native | Windows 10 için SDK'sı (10.0.16299.0) UWP: C++ | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.0.27005.2 | Önerilen
Component.Incredibuild | IncrediBuild - yapı hızlandırma | 15.6.27406.0 | İsteğe Bağlı
Component.IncredibuildMenu | IncrediBuildMenu | 1.5.0.2 | İsteğe Bağlı
Microsoft.Component.VC.Runtime.UCRTSDK | Windows Evrensel CRT SDK'sı | 15.6.27309.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.140 | VC ++ 2015.3 v140 araç takımı Masaüstü (x86, x64) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.ATLMFC | MFC ve ATL desteği (x86 hem x64) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.ClangC2 | Clang/C2 (Deneysel) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.CLI.Support | C + +/ CLI desteği | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Modules.x86.x64 | Standart Kitaplığı (Deneysel) modülleri | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Windows 10 SDK'sı (10.0.10240.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK'sı (10.0.10586.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK (10.0.14393.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.Desktop | Windows 10 Masaüstü C++ [x86 hem x64] için SDK (10.0.15063.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | Windows 10 için SDK'sı (10.0.15063.0) UWP: C#, VB, JS | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP.Native | Windows 10 için SDK'sı (10.0.15063.0) UWP: C++ | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows81SDK | Windows 8.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.WinXP | C++ için Windows XP desteği | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Win81 | Windows 8.1 SDK'sı ve UCRT SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.WinXP | C++ için Windows XP desteği | 15.6.27406.0 | İsteğe Bağlı

## <a name="game-development-with-c"></a>C++ ile oyun geliştirme

**Kimliği:** Microsoft.VisualStudio.Workload.NativeGame

**Açıklama:** C++ gücünü DirectX, gerçekleşmemiş hesabı ya da Cocos2d gücü profesyonel oyun oluşturmak için kullanın.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ çekirdek Özellikler | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VC.Redist.14.Latest | Visual C++ 2017 yeniden dağıtılabilir güncelleştirme | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 v141 araç takımı (x86, x64) | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Windows10SDK | Windows Evrensel C çalışma zamanı | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Graphics.Tools | Grafik hata ayıklayıcı ve DirectX GPU Profil Oluşturucu | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Graphics.Win81 | Grafik araçları Windows 8.1 SDK'sı | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.VC.DiagnosticTools | C++ Profil Araçları | 15.0.26823.1 | Önerilen
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop | Windows 10 Masaüstü C++ [x86 hem x64] için SDK (10.0.16299.0) | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | Windows 10 için SDK'sı (10.0.16299.0) UWP: C#, VB, JS | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP.Native | Windows 10 için SDK'sı (10.0.16299.0) UWP: C++ | 15.6.27406.0 | Önerilen
Component.Android.NDK.R12B | Android NDK (R12B) | 12.1.9 | İsteğe Bağlı
Component.Android.SDK23.Private | Android SDK kurulumu (API düzeyi 23) (yerel yükleme) | 15.6.27413.0 | İsteğe Bağlı
Component.Ant | Apache Ant (1.9.3) | 1.9.3.7 | İsteğe Bağlı
Component.Cocos | Cocos | 15.0.26906.1 | İsteğe Bağlı
Component.Incredibuild | IncrediBuild - yapı hızlandırma | 15.6.27406.0 | İsteğe Bağlı
Component.IncredibuildMenu | IncrediBuildMenu | 1.5.0.2 | İsteğe Bağlı
Component.JavaJDK | Java SE Geliştirme Seti (8.0.1120.15) | 15.6.27406.0 | İsteğe Bağlı
Component.MDD.Android | C++ Android geliştirme araçları | 15.0.26606.0 | İsteğe Bağlı
Component.Unreal | Unreal Engine yükleyici | 15.6.27406.0 | İsteğe Bağlı
Component.Unreal.Android | Unreal Engine için Visual Studio Android desteği | 15.0.27005.2 | İsteğe Bağlı
Microsoft.Component.VC.Runtime.UCRTSDK | Windows Evrensel CRT SDK'sı | 15.6.27309.0 | İsteğe Bağlı
Microsoft.Net.Component.4.5.1.TargetingPack | .NET framework 4.5.1 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 paketi hedefleme | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.TargetingPack | .NET framework 4.6 paketi hedefleme | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.TargetingPack | .NET framework 4 paketi hedefleme | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET framework 4 – 4.6 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.0.27205.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Windows 10 SDK'sı (10.0.10240.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK'sı (10.0.10586.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK (10.0.14393.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.Desktop | Windows 10 Masaüstü C++ [x86 hem x64] için SDK (10.0.15063.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | Windows 10 için SDK'sı (10.0.15063.0) UWP: C#, VB, JS | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP.Native | Windows 10 için SDK'sı (10.0.15063.0) UWP: C++ | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows81SDK | Windows 8.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Win81 | Windows 8.1 SDK'sı ve UCRT SDK'sı | 15.6.27406.0 | İsteğe Bağlı

## <a name="mobile-development-with-c"></a>C++ ile Mobil Geliştirme

**Kimliği:** Microsoft.VisualStudio.Workload.NativeMobile

**Açıklama:** iOS, Android veya C++ kullanarak Windows için platformlar arası uygulamalar oluşturma.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ çekirdek Özellikler | 15.6.27406.0 | Gerekli
Component.Android.NDK.R15C | Android NDK (R15C) | 15.2 | Önerilen
Component.Android.SDK19 | Android SDK kurulumu (API düzeyi 19 ve 21) | 15.6.27413.0 | Önerilen
Component.Android.SDK22 | Android SDK kurulumu (API düzeyi 22) | 15.6.27413.0 | Önerilen
Component.Android.SDK23 | Android SDK kurulumu (API düzeyi 23) (genel yükleme) | 15.6.27413.0 | Önerilen
Component.Android.SDK25 | Android SDK kurulumu (API düzeyi 25) | 15.6.27413.0 | Önerilen
Component.Ant | Apache Ant (1.9.3) | 1.9.3.7 | Önerilen
Component.JavaJDK | Java SE Geliştirme Seti (8.0.1120.15) | 15.6.27406.0 | Önerilen
Component.MDD.Android | C++ Android geliştirme araçları | 15.0.26606.0 | Önerilen
Component.Android.NDK.R12B | Android NDK (R12B) | 12.1.9 | İsteğe Bağlı
Component.Android.NDK.R12B_3264 | Android NDK (R12B) (32 bit) | 12.1.10 | İsteğe Bağlı
Component.Android.NDK.R13B | Android NDK (R13B) | 13.1.6 | İsteğe Bağlı
Component.Android.NDK.R13B_3264 | Android NDK (R13B) (32 bit) | 13.1.7 | İsteğe Bağlı
Component.Android.NDK.R15C_3264 | Android NDK (R15C) (32 bit) | 15.2 | İsteğe Bağlı
Component.Google.Android.Emulator.API23.V2 | Google Android öykünücüsü (API düzeyi 23) (genel yükleme) | 15.6.27413.0 | İsteğe Bağlı
Component.HAXM | Intel donanım hızlandırılmış yürütme Yöneticisi'ni (HAXM) (genel yükleme) | 15.6.27413.0 | İsteğe Bağlı
Component.Incredibuild | IncrediBuild - yapı hızlandırma | 15.6.27406.0 | İsteğe Bağlı
Component.IncredibuildMenu | IncrediBuildMenu | 1.5.0.2 | İsteğe Bağlı
Component.MDD.IOS | C++ iOS geliştirme araçları | 15.0.26621.2 | İsteğe Bağlı

## <a name="net-core-cross-platform-development"></a>.NET core platformlar arası geliştirme

**Kimliği:** Microsoft.VisualStudio.Workload.NetCoreTools

**Açıklama:** .NET Core ve ASP.NET Core, HTML/JavaScript ve Docker desteği dahil olmak üzere kapsayıcıları kullanan platformlar arası uygulamalar oluşturma.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.Microsoft.VisualStudio.RazorExtension | Razor dili Hizmetleri | 15.0.26720.2 | Gerekli
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | Gerekli
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.0.27205.0 | Gerekli
Microsoft.Component.MSBuild | MSBuild | 15.6.27309.0 | Gerekli
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 paketi hedefleme | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.NetCore.ComponentGroup.DevelopmentTools | .NET core 2.0 geliştirme araçları | 15.6.27421.1 | Gerekli
Microsoft.NetCore.ComponentGroup.Web | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.0.26621.2 | Gerekli
Microsoft.VisualStudio.Component.Common.Azure.Tools | Bağlantı ve yayımlama araçları | 1.10.50912.1 | Gerekli
Microsoft.VisualStudio.Component.FSharp | F # dil desteği | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılama | 15.0.26606.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Yönetilen masaüstü iş yükü çekirdek | 15.6.27323.2 | Gerekli
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir paketi hedefleme kitaplığı | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.0.27205.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL çalışma zamanı | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server komut satırı yardımcı programları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.DataSources | Veri kaynakları için SQL Server desteği | 15.0.26621.2 | Gerekli
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Veri Araçları | 15.0.26906.1 | Gerekli
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TextTemplating | Metin şablonu dönüştürme | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TypeScript.2.6 | TypeScript 2.6 SDK | 15.0.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.WebDeploy | Web Dağıtımı | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.Web | Önkoşullar ASP.NET ve web geliştirme araçları | 15.6.27323.2 | Gerekli
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.0.27005.2 | Gerekli
Component.Microsoft.VisualStudio.Web.AzureFunctions | Microsoft Azure WebJobs Tools | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure yazma araçları | 15.0.26621.2 | Önerilen
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET için Azure kitaplıkları | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Azure işlem öykünücüsü | 15.0.26621.2 | Önerilen
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Azure Storage öykünücüsü | 15.6.27413.0 | Önerilen
Microsoft.VisualStudio.Component.CloudExplorer | Cloud Explorer | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.Debugger.Snapshot | Anlık görüntü hata ayıklayıcı | 15.6.27428.1 | Önerilen
Microsoft.VisualStudio.Component.DiagnosticTools | .NET Profil Araçları | 15.6.27421.1 | Önerilen
Microsoft.VisualStudio.Component.DockerTools | Kapsayıcı geliştirme araçları | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.6.27323.2 | Önerilen
Microsoft.VisualStudio.Component.LiveUnitTesting | Live Unit Testing | 15.0.26720.2 | Önerilen
Microsoft.VisualStudio.Component.Web | ASP.NET ve web geliştirme araçları | 15.6.27323.2 | Önerilen
Microsoft.VisualStudio.ComponentGroup.AzureFunctions | Microsoft Azure WebJobs Tools | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.ComponentGroup.Web.CloudTools | Web geliştirme için bulut araçları | 15.6.27323.2 | Önerilen
Microsoft.Net.Core.Component.SDK.1x | .NET core 1.0 1.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.NetCore.1x.ComponentGroup.Web | .NET core Web 1.0 1.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.IISDevelopment | Geliştirme zaman IIS desteği | 15.0.26720.2 | İsteğe Bağlı

## <a name="mobile-development-with-net"></a>.NET ile Mobil Geliştirme

**Kimliği:** Microsoft.VisualStudio.Workload.NetCrossPlat

**Açıklama:** iOS, Android veya Xamarin kullanan Windows için platformlar arası uygulamalar oluşturma.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.Android.SDK25 | Android SDK kurulumu (API düzeyi 25) | 15.6.27413.0 | Gerekli
Component.Google.Android.Emulator.API25 | Google Android öykünücüsü (API düzeyi 25) | 15.6.27413.0 | Gerekli
Component.HAXM | Intel donanım hızlandırılmış yürütme Yöneticisi'ni (HAXM) (genel yükleme) | 15.6.27413.0 | Gerekli
Component.JavaJDK | Java SE Geliştirme Seti (8.0.1120.15) | 15.6.27406.0 | Gerekli
Component.Microsoft.VisualStudio.RazorExtension | Razor dili Hizmetleri | 15.0.26720.2 | Gerekli
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | Gerekli
Component.Xamarin | Xamarin | 15.6.27323.2 | Gerekli
Component.Xamarin.RemotedSimulator | Xamarin düğümlerde Simulator | 15.6.27323.2 | Gerekli
Component.Xamarin.SdkManager | Xamarin SDK Yöneticisi | 15.6.27323.2 | Gerekli
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.0.27205.0 | Gerekli
Microsoft.Component.MSBuild | MSBuild | 15.6.27309.0 | Gerekli
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 paketi hedefleme | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.NetCore.ComponentGroup.DevelopmentTools | .NET core 2.0 geliştirme araçları | 15.6.27421.1 | Gerekli
Microsoft.NetCore.ComponentGroup.Web | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.0.26621.2 | Gerekli
Microsoft.VisualStudio.Component.Common.Azure.Tools | Bağlantı ve yayımlama araçları | 1.10.50912.1 | Gerekli
Microsoft.VisualStudio.Component.FSharp | F # dil desteği | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılama | 15.0.26606.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Yönetilen masaüstü iş yükü çekirdek | 15.6.27323.2 | Gerekli
Microsoft.VisualStudio.Component.Merq | Ortak Xamarin iç araçları | 15.0.26720.2 | Gerekli
Microsoft.VisualStudio.Component.MonoDebugger | Mono hata ayıklayıcı | 15.0.26720.2 | Gerekli
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir paketi hedefleme kitaplığı | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.0.27205.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL çalışma zamanı | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server komut satırı yardımcı programları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.DataSources | Veri kaynakları için SQL Server desteği | 15.0.26621.2 | Gerekli
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Veri Araçları | 15.0.26906.1 | Gerekli
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TextTemplating | Metin şablonu dönüştürme | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TypeScript.2.6 | TypeScript 2.6 SDK | 15.0.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.WebDeploy | Web Dağıtımı | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.Web | Önkoşullar ASP.NET ve web geliştirme araçları | 15.6.27323.2 | Gerekli
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.0.27005.2 | Gerekli
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions.TemplateEngine | ASP.NET şablon motoru | 15.6.27323.2 | Gerekli
Component.Xamarin.Inspector | Xamarin Workbooks | 15.0.26606.0 | Önerilen
Component.Xamarin.Profiler | Xamarin Profiler | 15.0.27005.2 | Önerilen
Microsoft.Component.NetFX.Native | .NET Yerel | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeClone | Kodu Kopyala | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeMap | Kod Haritası | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | Canlı bağımlılık doğrulama | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DiagnosticTools | .NET Profil Araçları | 15.6.27421.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.GraphDocument | DGML Düzenleyicisi | 15.0.27005.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Graphics | Görüntü ve 3B modeli düzenleyiciler | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | Windows 10 için SDK'sı (10.0.16299.0) UWP: C#, VB, JS | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | Mimari ve çözümleme araçları | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.UWP.Xamarin | Xamarin için evrensel Windows platformu araçları | 15.6.27406.0 | İsteğe Bağlı

## <a name="aspnet-and-web-development"></a>ASP.NET ve web geliştirme

**Kimliği:** Microsoft.VisualStudio.Workload.NetWeb

**Açıklama:** derleme ASP.NET, ASP.NET Core, HTML/JavaScript ve Docker desteği dahil olmak üzere kapsayıcıları kullanarak web uygulamaları.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.Microsoft.VisualStudio.RazorExtension | Razor dili Hizmetleri | 15.0.26720.2 | Gerekli
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | Gerekli
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.0.27205.0 | Gerekli
Microsoft.Component.MSBuild | MSBuild | 15.6.27309.0 | Gerekli
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 paketi hedefleme | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.NetCore.ComponentGroup.DevelopmentTools | .NET core 2.0 geliştirme araçları | 15.6.27421.1 | Gerekli
Microsoft.NetCore.ComponentGroup.Web | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.0.26621.2 | Gerekli
Microsoft.VisualStudio.Component.Common.Azure.Tools | Bağlantı ve yayımlama araçları | 1.10.50912.1 | Gerekli
Microsoft.VisualStudio.Component.DockerTools | Kapsayıcı geliştirme araçları | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.FSharp | F # dil desteği | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılama | 15.0.26606.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Yönetilen masaüstü iş yükü çekirdek | 15.6.27323.2 | Gerekli
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir paketi hedefleme kitaplığı | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.0.27205.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL çalışma zamanı | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server komut satırı yardımcı programları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.DataSources | Veri kaynakları için SQL Server desteği | 15.0.26621.2 | Gerekli
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Veri Araçları | 15.0.26906.1 | Gerekli
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TextTemplating | Metin şablonu dönüştürme | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TypeScript.2.6 | TypeScript 2.6 SDK | 15.0.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Web | ASP.NET ve web geliştirme araçları | 15.6.27323.2 | Gerekli
Microsoft.VisualStudio.Component.WebDeploy | Web Dağıtımı | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.Web | Önkoşullar ASP.NET ve web geliştirme araçları | 15.6.27323.2 | Gerekli
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.0.27005.2 | Gerekli
Component.Microsoft.VisualStudio.Web.AzureFunctions | Microsoft Azure WebJobs Tools | 15.6.27309.0 | Önerilen
Microsoft.Net.Component.4.5.1.TargetingPack | .NET framework 4.5.1 hedefleme paketi | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.6.TargetingPack | .NET framework 4.6 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.TargetingPack | .NET framework 4 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET framework 4 – 4.6 geliştirme araçları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.AspNet45 | Gelişmiş ASP.NET özellikleri | 15.6.27428.1 | Önerilen
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure yazma araçları | 15.0.26621.2 | Önerilen
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET için Azure kitaplıkları | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Azure işlem öykünücüsü | 15.0.26621.2 | Önerilen
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Azure Storage öykünücüsü | 15.6.27413.0 | Önerilen
Microsoft.VisualStudio.Component.CloudExplorer | Cloud Explorer | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.Debugger.Snapshot | Anlık görüntü hata ayıklayıcı | 15.6.27428.1 | Önerilen
Microsoft.VisualStudio.Component.DiagnosticTools | .NET Profil Araçları | 15.6.27421.1 | Önerilen
Microsoft.VisualStudio.Component.EntityFramework | Entity Framework 6 araçları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.6.27323.2 | Önerilen
Microsoft.VisualStudio.Component.LiveUnitTesting | Live Unit Testing | 15.0.26720.2 | Önerilen
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 15.0.27205.0 | Önerilen
Microsoft.VisualStudio.ComponentGroup.AzureFunctions | Microsoft Azure WebJobs Tools | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.ComponentGroup.Web.CloudTools | Web geliştirme için bulut araçları | 15.6.27323.2 | Önerilen
Microsoft.Net.Component.4.6.2.SDK | .NET framework 4.6.2 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.2.TargetingPack | .NET framework 4.6.2 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.SDK | .NET Framework 4.7.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.TargetingPack | .NET framework 4.7.1 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.SDK | .NET framework 4.7 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.TargetingPack | .NET framework 4.7 paketi hedefleme | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET framework 4.6.2 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET framework 4.7.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET framework 4.7 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Core.Component.SDK.1x | .NET core 1.0 1.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.NetCore.1x.ComponentGroup.Web | .NET core Web 1.0 1.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeClone | Kodu Kopyala | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeMap | Kod Haritası | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | Canlı bağımlılık doğrulama | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.GraphDocument | DGML Düzenleyicisi | 15.0.27005.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.TestTools.WebLoadTest | Web performans ve Yük Test Araçları | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | Mimari ve çözümleme araçları | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.IISDevelopment | Geliştirme zaman IIS desteği | 15.0.26720.2 | İsteğe Bağlı
Microsoft.VisualStudio.Web.Mvc4.ComponentGroup | ASP.NET MVC 4 | 15.6.27406.0 | İsteğe Bağlı

## <a name="nodejs-development"></a>Node.js geliştirme

**Kimliği:** Microsoft.VisualStudio.Workload.Node

**Açıklama:** yapı Node.js, bir zaman uyumsuz olay denetimli JavaScript çalışma zamanı kullanarak Ölçeklenebilir Ağ uygulamaları. 

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılama | 15.0.26606.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Node.Build | Node.js desteği | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Node.Tools | Node.js desteği | 15.6.27323.2 | Gerekli
Microsoft.VisualStudio.Component.TypeScript.2.6 | TypeScript 2.6 SDK | 15.0.27406.0 | Gerekli
Microsoft.VisualStudio.Component.WebDeploy | Web Dağıtımı | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.0.27005.2 | Gerekli
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.0.26621.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Common.Azure.Tools | Bağlantı ve yayımlama araçları | 1.10.50912.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ çekirdek Özellikler | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 v141 araç takımı (x86, x64) | 15.6.27406.0 | İsteğe Bağlı

## <a name="officesharepoint-development"></a>Office/SharePoint geliştirme

**Kimliği:** Microsoft.VisualStudio.Workload.Office

**Açıklama:** Create Office ve SharePoint eklentiler, SharePoint çözümleri ve VSTO eklentilerini C#, VB ve JavaScript kullanarak.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.Microsoft.VisualStudio.RazorExtension | Razor dili Hizmetleri | 15.0.26720.2 | Gerekli
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | Gerekli
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.0.27205.0 | Gerekli
Microsoft.Component.MSBuild | MSBuild | 15.6.27309.0 | Gerekli
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 paketi hedefleme | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.TargetingPack | .NET framework 4 paketi hedefleme | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.0.26621.2 | Gerekli
Microsoft.VisualStudio.Component.Common.Azure.Tools | Bağlantı ve yayımlama araçları | 1.10.50912.1 | Gerekli
Microsoft.VisualStudio.Component.DockerTools | Kapsayıcı geliştirme araçları | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılama | 15.0.26606.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Yönetilen masaüstü iş yükü çekirdek | 15.6.27323.2 | Gerekli
Microsoft.VisualStudio.Component.ManagedDesktop.Prerequisites | .NET masaüstü geliştirme araçları | 15.0.27205.0 | Gerekli
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir paketi hedefleme kitaplığı | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.0.27205.0 | Gerekli
Microsoft.VisualStudio.Component.Sharepoint.Tools | Visual Studio için Office Geliştirici Araçları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL çalışma zamanı | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server komut satırı yardımcı programları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.DataSources | Veri kaynakları için SQL Server desteği | 15.0.26621.2 | Gerekli
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Veri Araçları | 15.0.26906.1 | Gerekli
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TextTemplating | Metin şablonu dönüştürme | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TypeScript.2.6 | TypeScript 2.6 SDK | 15.0.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 15.0.27205.0 | Gerekli
Microsoft.VisualStudio.Component.Web | ASP.NET ve web geliştirme araçları | 15.6.27323.2 | Gerekli
Microsoft.VisualStudio.Component.WebDeploy | Web Dağıtımı | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.Workflow | Windows Workflow Foundation | 15.0.27005.2 | Gerekli
Microsoft.VisualStudio.ComponentGroup.Web | Önkoşullar ASP.NET ve web geliştirme araçları | 15.6.27323.2 | Gerekli
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.0.27005.2 | Gerekli
Microsoft.VisualStudio.Component.TeamOffice | Visual Studio Tools for Office (VSTO) | 15.0.26606.0 | Önerilen
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.6.27323.2 | İsteğe Bağlı

## <a name="python-development"></a>Python geliştirme

**Kimliği:** Microsoft.VisualStudio.Workload.Python

**Açıklama:** düzenleme, hata ayıklama, Python için etkileşimli geliştirme ve kaynak denetimi.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Component.PythonTools | Python dil desteği | 15.0.26823.1 | Gerekli
Component.CPython3.x64 | Python 3 64-bit (3.6.3) | 3.6.3.2 | Önerilen
Microsoft.Component.CookiecutterTools | Cookiecutter şablon desteği | 15.0.26621.2 | Önerilen
Microsoft.Component.PythonTools.Web | Python web desteği | 15.0.27005.2 | Önerilen
Microsoft.VisualStudio.Component.Common.Azure.Tools | Bağlantı ve yayımlama araçları | 1.10.50912.1 | Önerilen
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.TypeScript.2.6 | TypeScript 2.6 SDK | 15.0.27406.0 | Önerilen
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.WebDeploy | Web Dağıtımı | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.0.27005.2 | Önerilen
Component.Anaconda2.x64 | Anaconda2 64-bit (5.0.0) | 5.0.0 | İsteğe Bağlı
Component.Anaconda2.x86 | Anaconda2 32-bit (5.0.0) | 5.0.0 | İsteğe Bağlı
Component.Anaconda3.x64 | Anaconda3 64-bit (5.0.0) | 5.0.0 | İsteğe Bağlı
Component.Anaconda3.x86 | Anaconda3 32-bit (5.0.0) | 5.0.0 | İsteğe Bağlı
Component.CPython2.x64 | Python 2 64-bit (2.7.14) | 2.7.14 | İsteğe Bağlı
Component.CPython2.x86 | Python 2 32-bit (2.7.14) | 2.7.14 | İsteğe Bağlı
Component.CPython3.x86 | Python 3 32-bit (3.6.3) | 3.6.3.2 | İsteğe Bağlı
Component.Microsoft.VisualStudio.RazorExtension | Razor dili Hizmetleri | 15.0.26720.2 | İsteğe Bağlı
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | İsteğe Bağlı
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.0.27205.0 | İsteğe Bağlı
Microsoft.Component.MSBuild | MSBuild | 15.6.27309.0 | İsteğe Bağlı
Microsoft.Component.NetFX.Native | .NET Yerel | 15.0.26208.0 | İsteğe Bağlı
Microsoft.Component.PythonTools.UWP | Python IOT desteği | 15.0.26606.0 | İsteğe Bağlı
Microsoft.Component.VC.Runtime.UCRTSDK | Windows Evrensel CRT SDK'sı | 15.6.27309.0 | İsteğe Bağlı
Microsoft.ComponentGroup.PythonTools.NativeDevelopment | Python yerel geliştirme araçları | 15.0.27005.2 | İsteğe Bağlı
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 paketi hedefleme | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.0.26621.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure yazma araçları | 15.0.26621.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET için Azure kitaplıkları | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Azure işlem öykünücüsü | 15.0.26621.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Azure Storage öykünücüsü | 15.6.27413.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Azure.Waverton | Azure bulut Hizmetleri Çekirdek araçları | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.ClassDesigner | Sınıf Tasarımcısı | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeClone | Kodu Kopyala | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeMap | Kod Haritası | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DiagnosticTools | .NET Profil Araçları | 15.6.27421.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DockerTools | Kapsayıcı geliştirme araçları | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.GraphDocument | DGML Düzenleyicisi | 15.0.27005.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Graphics | Görüntü ve 3B modeli düzenleyiciler | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Graphics.Tools | Grafik hata ayıklayıcı ve DirectX GPU Profil Oluşturucu | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Graphics.Win81 | Grafik araçları Windows 8.1 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.6.27323.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılama | 15.0.26606.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Yönetilen masaüstü iş yükü çekirdek | 15.6.27323.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir paketi hedefleme kitaplığı | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.0.27205.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL çalışma zamanı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server komut satırı yardımcı programları | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.DataSources | Veri kaynakları için SQL Server desteği | 15.0.26621.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Veri Araçları | 15.0.26906.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.TextTemplating | Metin şablonu dönüştürme | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.140 | VC ++ 2015.3 v140 araç takımı Masaüstü (x86, x64) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ çekirdek Özellikler | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.DiagnosticTools | C++ Profil Araçları | 15.0.26823.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 v141 araç takımı (x86, x64) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Web | ASP.NET ve web geliştirme araçları | 15.6.27323.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK | Windows Evrensel C çalışma zamanı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK'sı (10.0.10586.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop | Windows 10 Masaüstü C++ [x86 hem x64] için SDK (10.0.16299.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | Windows 10 için SDK'sı (10.0.16299.0) UWP: C#, VB, JS | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP.Native | Windows 10 için SDK'sı (10.0.16299.0) UWP: C++ | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows81SDK | Windows 8.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.Web | Önkoşullar ASP.NET ve web geliştirme araçları | 15.6.27323.2 | İsteğe Bağlı

## <a name="universal-windows-platform-development"></a>Evrensel Windows platformu geliştirme

**Kimliği:** Microsoft.VisualStudio.Workload.Universal

**Açıklama:** uygulamaları Evrensel Windows platformu için C#, VB, JavaScript ya da C++ isteğe bağlı olarak oluşturun.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | Gerekli
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.0.27205.0 | Gerekli
Microsoft.Component.NetFX.Native | .NET Yerel | 15.0.26208.0 | Gerekli
Microsoft.ComponentGroup.Blend | Visual Studio için Blend | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 paketi hedefleme | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | Gerekli
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.0.26621.2 | Gerekli
Microsoft.VisualStudio.Component.DiagnosticTools | .NET Profil Araçları | 15.6.27421.1 | Gerekli
Microsoft.VisualStudio.Component.Graphics | Görüntü ve 3B modeli düzenleyiciler | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılama | 15.0.26606.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir paketi hedefleme kitaplığı | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.0.27205.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TypeScript.2.6 | TypeScript 2.6 SDK | 15.0.27406.0 | Gerekli
Microsoft.VisualStudio.Component.UWP.Support | Evrensel Windows platformu araçları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | Windows 10 için SDK'sı (10.0.16299.0) UWP: C#, VB, JS | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.UWP.Cordova | Cordova için evrensel Windows platformu araçları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.UWP.NetCoreAndStandard | .NET yerel ve .NET standardı | 15.6.27421.1 | Gerekli
Microsoft.VisualStudio.ComponentGroup.UWP.Xamarin | Xamarin için evrensel Windows platformu araçları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.0.27005.2 | Gerekli
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.6.27323.2 | Önerilen
Microsoft.Component.VC.Runtime.OSSupport | UWP için Visual C++ çalışma zamanı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.SDK | .NET Framework 4.7.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeClone | Kodu Kopyala | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeMap | Kod Haritası | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | Canlı bağımlılık doğrulama | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.GraphDocument | DGML Düzenleyicisi | 15.0.27005.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Graphics.Tools | Grafik hata ayıklayıcı ve DirectX GPU Profil Oluşturucu | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Graphics.Win81 | Grafik araçları Windows 8.1 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Phone.Emulator.15254 | Windows 10 mobil öykünücü (kalan oluşturucuları güncelleştirme) | 15.0.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ çekirdek Özellikler | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Tools.ARM | Visual C++ Derleyicileri ve ARM için kitaplıkları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 v141 araç takımı (x86, x64) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Windows 10 SDK'sı (10.0.10240.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK'sı (10.0.10586.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK (10.0.14393.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | Windows 10 için SDK'sı (10.0.15063.0) UWP: C#, VB, JS | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP.Native | Windows 10 için SDK'sı (10.0.16299.0) UWP: C++ | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | Mimari ve çözümleme araçları | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.UWP.VC | C++ Evrensel Windows platformu araçları | 15.6.27323.2 | İsteğe Bağlı

## <a name="visual-studio-extension-development"></a>Visual Studio uzantısı geliştirme

**Kimliği:** Microsoft.VisualStudio.Workload.VisualStudioExtension

**Açıklama:** oluşturma eklentileri ve uzantıları yeni komutları dahil olmak üzere Visual Studio için kod Çözümleyicileri ve aracı windows.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.0.27205.0 | Gerekli
Microsoft.Component.MSBuild | MSBuild | 15.6.27309.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.TargetingPack | .NET framework 4.6 paketi hedefleme | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir paketi hedefleme kitaplığı | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.0.27205.0 | Gerekli
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.VSSDK | Visual Studio SDK | 15.0.26919.1 | Gerekli
Microsoft.VisualStudio.ComponentGroup.VisualStudioExtension.Prerequisites | Visual Studio uzantısı geliştirme önkoşulları | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.DiagnosticTools | .NET Profil Araçları | 15.6.27421.1 | Önerilen
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.6.27323.2 | Önerilen
Microsoft.VisualStudio.Component.TextTemplating | Metin şablonu dönüştürme | 15.0.26208.0 | Önerilen
Component.Dotfuscator | PreEmptive Protection - Dotfuscator | 15.0.26208.0 | İsteğe Bağlı
Microsoft.Component.CodeAnalysis.SDK | .NET Compiler Platform SDK’sı | 15.0.27323.2 | İsteğe Bağlı
Microsoft.Component.VC.Runtime.OSSupport | UWP için Visual C++ çalışma zamanı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.0.26621.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.ClassDesigner | Sınıf Tasarımcısı | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeClone | Kodu Kopyala | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeMap | Kod Haritası | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | Canlı bağımlılık doğrulama | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DslTools | SDK Modelleme | 15.0.27005.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.GraphDocument | DGML Düzenleyicisi | 15.0.27005.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.ATL | Visual C++ ATL desteği | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.ATLMFC | MFC ve ATL desteği (x86 hem x64) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ çekirdek Özellikler | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 v141 araç takımı (x86, x64) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | Mimari ve çözümleme araçları | 15.0.26208.0 | İsteğe Bağlı

## <a name="mobile-development-with-javascript"></a>JavaScript ile Mobil Geliştirme

**Kimliği:** Microsoft.VisualStudio.Workload.WebCrossPlat

**Açıklama:** yapı Apache Cordova için Araçlar kullanarak Android, iOS ve UWP uygulamaları.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.CordovaToolset.6.3.1 | Cordova 6.3.1 araç takımı | 15.6.27406.0 | Gerekli
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | Gerekli
Microsoft.VisualStudio.Component.Cordova | JavaScript çekirdek özellikleri Mobil Geliştirme | 15.0.26606.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılama | 15.0.26606.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.ProjectSystem | JavaScript ProjectSystem ve paylaşılan araçları | 15.0.26606.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.TypeScript.2.3 | TypeScript 2.3 SDK | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.TypeScript.2.6 | TypeScript 2.6 SDK | 15.0.27406.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.0.27005.2 | Gerekli
Component.Android.SDK23.Private | Android SDK kurulumu (API düzeyi 23) (yerel yükleme) | 15.6.27413.0 | İsteğe Bağlı
Component.Google.Android.Emulator.API23.Private | Google Android öykünücüsü (API düzeyi 23) (yerel yükleme) | 15.6.27413.0 | İsteğe Bağlı
Component.HAXM.Private | Intel donanım hızlandırılmış yürütme Yöneticisi'ni (HAXM) (yerel yükleme) | 15.6.27413.0 | İsteğe Bağlı
Component.JavaJDK | Java SE Geliştirme Seti (8.0.1120.15) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.0.27205.0 | İsteğe Bağlı
Microsoft.Component.NetFX.Native | .NET Yerel | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.0.26621.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DiagnosticTools | .NET Profil Araçları | 15.6.27421.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Git | Windows için Git | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Graphics | Görüntü ve 3B modeli düzenleyiciler | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Phone.Emulator.15254 | Windows 10 mobil öykünücü (kalan oluşturucuları güncelleştirme) | 15.0.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | Windows 10 için SDK'sı (10.0.16299.0) UWP: C#, VB, JS | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.UWP.Cordova | Cordova için evrensel Windows platformu araçları | 15.6.27406.0 | İsteğe Bağlı

## <a name="unaffiliated-components"></a>Unaffiliated bileşenleri

Bu, herhangi bir iş yükü ile dahil değildir, ancak ayrı bir bileşen olarak seçilebilir bileşenleridir.

Bileşen kimliği | Ad | Sürüm
--- | --- | ---
Component.Android.Emulator | Android için Visual Studio Öykünücüsü | 15.6.27413.0
Component.Android.NDK.R11C | Android NDK (R11C) | 11.3.13
Component.Android.NDK.R11C_3264 | Android NDK (R11C) (32 bit) | 11.3.15
Component.GitHub.VisualStudio | Visual Studio için GitHub uzantısı | 2.2.0.10
Microsoft.Component.Blend.SDK.WPF | .NET için Visual Studio SDK'sı için blend | 15.6.27406.0
Microsoft.Component.HelpViewer | Yardım Görüntüleyicisi | 15.6.27323.2
Microsoft.VisualStudio.Component.LinqToSql | LINQ-SQL araçları | 15.6.27406.0
Microsoft.VisualStudio.Component.Phone.Emulator | Windows 10 mobil öykünücü (Anniversary Edition) | 15.6.27406.0
Microsoft.VisualStudio.Component.Phone.Emulator.15063 | Windows 10 mobil öykünücü (oluşturucuları güncelleştirme) | 15.6.27406.0
Microsoft.VisualStudio.Component.Runtime.Node.x86.6.4.0 | Node.js v6.4.0 (x86) tabanlı bileşenleri için çalışma zamanı | 15.6.27323.2
Microsoft.VisualStudio.Component.Runtime.Node.x86.7.4.0 | Node.js v7.4.0 (x86) tabanlı bileşenleri için çalışma zamanı | 15.6.27323.2
Microsoft.VisualStudio.Component.TestTools.CodedUITest | Kodlanmış UI testi | 15.0.26606.0
Microsoft.VisualStudio.Component.TestTools.Core | Test Araçları çekirdek Özellikler | 15.0.26606.0
Microsoft.VisualStudio.Component.TestTools.FeedbackClient | Microsoft Geri Bildirim İstemcisi | 15.6.27406.0
Microsoft.VisualStudio.Component.TestTools.MicrosoftTestManager | Microsoft Test Manager | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.0 | TypeScript 2.0 SDK'sı | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.1 | TypeScript 2.1 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.2 | TypeScript 2.2 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.5 | TypeScript 2.5 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.UWP.VC.ARM64 | ARM64 için C++ Evrensel Windows platformu araçları | 15.0.27323.2
Microsoft.VisualStudio.Component.VC.Tools.14.11 | VC ++ 2017 sürüm 15.4 v14.11 araç takımı | 15.0.27406.0
Microsoft.VisualStudio.Component.VC.Tools.14.12 | VC ++ 2017 sürüm 15,5 v14.12 araç takımı | 15.0.27406.0
Microsoft.VisualStudio.Component.VC.Tools.ARM64 | Visual C++ Derleyicileri ve ARM64 için kitaplıkları | 15.6.27309.0
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop.arm | Windows 10 Masaüstü C++ [ARM ve ARM64] için SDK (10.0.16299.0) | 15.6.27406.0

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:
* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun.
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio).  (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.

* [Visual Studio iş yükü ve bileşen kimlikleri](workload-and-component-ids.md)
* [Visual Studio Yönetici Kılavuzu](visual-studio-administrator-guide.md)
* [Komut satırı parametrelerini kullanarak Visual Studio'yu yükleme](use-command-line-parameters-to-install-visual-studio.md)
  * [Komut satırı parametresi örnekleri](command-line-parameter-examples.md)
* [Visual Studio’nun çevrimdışı yüklemesini oluşturma](create-an-offline-installation-of-visual-studio.md)
