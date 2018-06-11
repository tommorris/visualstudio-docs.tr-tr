---
title: Visual Studio derleme araçları 2017 iş yükü ve Bileşen kimlikleri
description: Klasik Windows tabanlı uygulamalar oluşturmak için Visual Studio iş yükü ve Bileşen kimlikleri kullanın
keywords: ''
author: TerryGLee
ms.author: tglee
manager: douge
ms.date: 05/07/2018
ms.topic: reference
helpviewer_keywords:
- workload ID, Visual Studio
- component ID, Visual Studio
- install Visual Studio, administrator guide
ms.service: ''
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.assetid: b99298df-0280-47fc-af73-44cd7a8ac553
ms.workload:
- multiple
ms.openlocfilehash: 188070b76337455d5ecb576fc40fac7dab61848b
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256129"
---
# <a name="visual-studio-build-tools-2017-component-directory"></a>Visual Studio derleme araçları 2017 bileşen dizini

Tablolar bu sayfa listede kimlikleri, Visual Studio komut satırını kullanarak yüklemek için kullanabileceğiniz veya bağımlılık VSIX bildirim olarak belirtebilirsiniz. Biz yayın güncelleştirmeler Visual Studio gibi ek bileşenleri ekleyeceğiz olduğunu unutmayın.

Ayrıca sayfa hakkında aşağıdakileri unutmayın:

* Her iş yükü iş yükü Kimliğini ve iş yükü için kullanılabilir olan bileşenleri tablosu arkasından kendi bölümü vardır.
* Varsayılan olarak, **gerekli** bileşenleri, iş yükü yüklediğinizde yüklenir.
* İsterseniz, ayrıca yükleyebilirsiniz **önerilen** ve **isteğe bağlı** bileşenleri.
* Herhangi bir iş yükü ile bağlı değil ek bileşenleri listeleyen bir bölüm de ekledik.

VSIX bildiriminizi bağımlılıkları ayarladığınızda, Bileşen kimlikleri yalnızca belirtmeniz gerekir. Bizim minimum Bileşen bağımlılıkları belirlemek için bu sayfadaki tabloları kullanın. Bazı senaryolarda bu bir iş yükü yalnızca bir bileşenden belirttiğiniz anlamına gelebilir. Diğer senaryolarda, tek bir iş yükünü birden çok bileşenlerini veya birden çok iş yükünün birden çok bileşenlerini belirtin gelebilir. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio 2017 genişletilebilirlik projelerine geçirmek](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md) sayfası.

Bu kimlikleri kullanma hakkında daha fazla bilgi için bkz: [Visual Studio 2017 yüklemek için komut satırı parametrelerini kullanmak](use-command-line-parameters-to-install-visual-studio.md) sayfası. Ve iş yükü ve diğer ürünler için Bileşen kimlikleri listesi için bkz: [Visual Studio 2017 iş yükü ve Bileşen kimlikleri](workload-and-component-ids.md) sayfası.

## <a name="azure-development-build-tools"></a>Azure geliştirme derleme araçları

**Kimliği:** Microsoft.VisualStudio.Workload.AzureBuildTools

**Açıklama:** MSBuild görevleri ve Azure uygulamaları geliştirmek için hedefler.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Net.Component.4.6.1.SDK | .NET framework 4.6.1 SDK | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.7.27520.0 | Gerekli
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure yazma araçları | 15.0.26621.2 | Gerekli
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET için Azure kitaplıkları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.Azure.Waverton.BuildTools | Azure bulut Hizmetleri derleme araçları | 15.7.27617.1 | Gerekli
Microsoft.VisualStudio.Component.DockerTools.BuildTools | Kapsayıcı geliştirme araçları - derleme araçları | 15.7.27617.1 | Gerekli
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet hedefleri ve derleme görevleri | 15.0.26919.1 | Gerekli
Microsoft.VisualStudio.Wcf.BuildTools.ComponentGroup | WCF geliştirme derleme araçları | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Web.BuildTools.ComponentGroup | Web geliştirme derleme araçları | 15.7.27604.0 | Gerekli
Microsoft.Net.Component.4.5.1.TargetingPack | .NET framework 4.5.1 hedefleme paketi | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 hedefleme paketi | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.6.TargetingPack | .NET framework 4.6 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.TargetingPack | .NET framework 4 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET framework 4 – 4.6 geliştirme araçları | 15.6.27406.0 | Önerilen
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.AspNet45 | Gelişmiş ASP.NET özellikleri | 15.7.27625.0 | Önerilen
Microsoft.VisualStudio.Component.TypeScript.2.8 | TypeScript 2.8 SDK | 15.0.27617.1 | Önerilen
Microsoft.Net.Component.3.5.DeveloperTools | .NET framework 3.5 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.2.SDK | .NET framework 4.6.2 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.2.TargetingPack | .NET framework 4.6.2 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.SDK | .NET framework 4.7.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.TargetingPack | .NET framework 4.7.1 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.SDK | .NET framework 4.7 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.TargetingPack | .NET framework 4.7 paketi hedefleme | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET framework 4.6.2 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET framework 4.7.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET framework 4.7 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı

## <a name="net-desktop-build-tools"></a>.NET Masaüstü derleme araçları

**Kimliği:** Microsoft.VisualStudio.Workload.ManagedDesktopBuildTools

**Açıklama:** WPF, Windows Forms ve C#, Visual Basic ve F # kullanarak konsol uygulamaları oluşturmak için Araçlar.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET framework 4.6.1 SDK | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet hedefleri ve derleme görevleri | 15.0.26919.1 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.Component.ClickOnce.MSBuild | ClickOnce derleme araçları | 15.7.27617.1 | Önerilen
Microsoft.Net.Component.4.5.1.TargetingPack | .NET framework 4.5.1 hedefleme paketi | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 hedefleme paketi | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.6.TargetingPack | .NET framework 4.6 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.TargetingPack | .NET framework 4 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET framework 4 – 4.6 geliştirme araçları | 15.6.27406.0 | Önerilen
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.TestTools.BuildTools | Test Araçları çekirdek özellikleri - derleme araçları | 15.7.27625.0 | Önerilen
Microsoft.VisualStudio.Wcf.BuildTools.ComponentGroup | WCF geliştirme derleme araçları | 15.6.27309.0 | Önerilen
Microsoft.Net.Component.3.5.DeveloperTools | .NET framework 3.5 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.2.SDK | .NET framework 4.6.2 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.2.TargetingPack | .NET framework 4.6.2 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.SDK | .NET framework 4.7.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.TargetingPack | .NET framework 4.7.1 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.SDK | .NET framework 4.7 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.TargetingPack | .NET framework 4.7 paketi hedefleme | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET framework 4.6.2 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET framework 4.7.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET framework 4.7 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Core.Component.SDK.1x | .NET core 1.0 1.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.FSharp.MSBuild | F# derleyici | 15.7.27604.0 | İsteğe Bağlı

## <a name="msbuild-tools"></a>MSBuild araçları

**Kimliği:** Microsoft.VisualStudio.Workload.MSBuildTools

**Açıklama:** MSBuild tabanlı uygulamalar oluşturmak için gerekli araçları sağlar.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Gerekli
Microsoft.VisualStudio.Component.CoreBuildTools | Visual Studio Araçları çekirdek derleme | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli

## <a name="net-core-build-tools"></a>.NET core derleme araçları

**Kimliği:** Microsoft.VisualStudio.Workload.NetCoreBuildTools

**Açıklama:** .NET Core ve ASP.NET Core, HTML/JavaScript ve kapsayıcılar kullanarak uygulamaları geliştirmek için Araçlar.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.NetCore.BuildTools.ComponentGroup | .NET core derleme araçları | 15.7.27617.1 | Gerekli
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet hedefleri ve derleme görevleri | 15.0.26919.1 | Gerekli
Microsoft.Net.Core.Component.SDK.1x | .NET core 1.0 1.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı

## <a name="nodejs-build-tools"></a>Node.js derleme araçları

**Kimliği:** Microsoft.VisualStudio.Workload.NodeBuildTools

**Açıklama:** yapı Node.js, bir zaman uyumsuz olay denetimli JavaScript çalışma zamanı kullanarak Ölçeklenebilir Ağ uygulamaları.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.VisualStudio.Component.Node.Build | Node.js desteği | 15.6.27406.0 | Gerekli

## <a name="officesharepoint-build-tools"></a>Office/SharePoint derleme araçları

**Kimliği:** Microsoft.VisualStudio.Workload.OfficeBuildTools

**Açıklama:** Office ve SharePoint eklentiler ve VSTO eklentileri oluşturma.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Component.ClickOnce.MSBuild | ClickOnce derleme araçları | 15.7.27617.1 | Gerekli
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Gerekli
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 paketi hedefleme | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET framework 4.6.1 SDK | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.TargetingPack | .NET framework 4 paketi hedefleme | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.7.27520.0 | Gerekli
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet hedefleri ve derleme görevleri | 15.0.26919.1 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Sharepoint.BuildTools | Office/SharePoint geliştirme derleme araçları | 15.7.27617.1 | Gerekli
Microsoft.VisualStudio.Wcf.BuildTools.ComponentGroup | WCF geliştirme derleme araçları | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Web.BuildTools.ComponentGroup | Web geliştirme derleme araçları | 15.7.27604.0 | Gerekli
Microsoft.VisualStudio.Component.TeamOffice.BuildTools | Visual Studio Araçları için Office (VSTO) derleme araçları | 15.7.27617.1 | Önerilen
Microsoft.Net.Component.4.6.2.SDK | .NET framework 4.6.2 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.2.TargetingPack | .NET framework 4.6.2 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.SDK | .NET framework 4.7.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.TargetingPack | .NET framework 4.7.1 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.SDK | .NET framework 4.7 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.TargetingPack | .NET framework 4.7 paketi hedefleme | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET framework 4.6.2 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET framework 4.7.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET framework 4.7 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı

## <a name="universal-windows-platform-build-tools"></a>Evrensel Windows platformu derleme araçları

**Kimliği:** Microsoft.VisualStudio.Workload.UniversalBuildTools

**Açıklama:** Evrensel Windows platformu uygulamaları oluşturmak için gerekli araçları sağlar.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Gerekli
Microsoft.Component.NetFX.Native | .NET Yerel | 15.0.26208.0 | Gerekli
Microsoft.Component.VC.Runtime.OSSupport | UWP için Visual C++ çalışma zamanı | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.7.1.SDK | .NET framework 4.7.1 SDK | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet hedefleri ve derleme görevleri | 15.0.26919.1 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.VC.Tools.ARM | Visual C++ Derleyicileri ve ARM için kitaplıkları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 sürüm 15.7 v14.14 son v141 araçları | 15.7.27625.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.UWP.BuildTools | Evrensel Windows platformu yapı önkoşulları | 15.7.27703.1 | Gerekli
Microsoft.VisualStudio.Component.Windows10SDK.17134 | Windows 10 SDK'sı (10.0.17134.0) | 15.7.27703.1 | Önerilen
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Windows 10 SDK'sı (10.0.10240.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK'sı (10.0.10586.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK'sı (10.0.14393.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | Windows 10 için SDK'sı (10.0.15063.0) UWP: C#, VB, JS | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | Windows 10 için SDK'sı (10.0.16299.0) UWP: C#, VB, JS | 15.6.27406.0 | İsteğe Bağlı

## <a name="visual-c-build-tools"></a>Visual C++ derleme araçları

**Kimliği:** Microsoft.VisualStudio.Workload.VCTools

**Açıklama:** Microsoft C++ araç takımı, ATL ve MFC kullanarak Windows Masaüstü uygulamaları oluşturun.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.VC.CoreBuildTools | Visual C++ derleme araçları çekirdek Özellikler | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VC.Redist.14.Latest | Visual C++ 2017 yeniden dağıtılabilir güncelleştirme | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 sürüm 15.7 v14.14 son v141 araçları | 15.7.27625.0 | Gerekli
Microsoft.VisualStudio.Component.Windows10SDK | Windows Evrensel C çalışma zamanı | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.TestTools.BuildTools | Test Araçları çekirdek özellikleri - derleme araçları | 15.7.27625.0 | Önerilen
Microsoft.VisualStudio.Component.Windows10SDK.17134 | Windows 10 SDK'sı (10.0.17134.0) | 15.7.27703.1 | Önerilen
Microsoft.Component.VC.Runtime.UCRTSDK | Windows Evrensel CRT SDK'sı | 15.6.27309.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.1.SDK | .NET framework 4.6.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.140 | Masaüstü için VC ++ 2015.3 v14.00 (v140) araç takımı | 15.7.27617.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.ATL | Visual C++ ATL x86 hem x64 için | 15.7.27625.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.ATLMFC | Visual C++ MFC x86 hem x64 için | 15.7.27625.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.CLI.Support | C + +/ CLI desteği | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Modules.x86.x64 | Standart Kitaplığı (Deneysel) modülleri | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Tools.ARM | Visual C++ Derleyicileri ve ARM için kitaplıkları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Tools.ARM64 | Visual C++ Derleyicileri ve ARM64 için kitaplıkları | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Windows 10 SDK'sı (10.0.10240.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK'sı (10.0.10586.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK'sı (10.0.14393.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.Desktop | Windows 10 Masaüstü C++ [x86 hem x64] için SDK (10.0.15063.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | Windows 10 için SDK'sı (10.0.15063.0) UWP: C#, VB, JS | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP.Native | Windows 10 için SDK'sı (10.0.15063.0) UWP: C++ | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop | Windows 10 Masaüstü C++ [x86 hem x64] için SDK (10.0.16299.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | Windows 10 için SDK'sı (10.0.16299.0) UWP: C#, VB, JS | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP.Native | Windows 10 için SDK'sı (10.0.16299.0) UWP: C++ | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows81SDK | Windows 8.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.WinXP | C++ için Windows XP desteği | 15.7.27703.1 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Win81 | Windows 8.1 SDK'sı ve UCRT SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.WinXP | C++ için Windows XP desteği | 15.7.27703.1 | İsteğe Bağlı

## <a name="web-development-build-tools"></a>Web geliştirme derleme araçları

**Kimliği:** Microsoft.VisualStudio.Workload.WebBuildTools

**Açıklama:** MSBuild görevleri ve hedefleri oluşturma web uygulamaları.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Net.Component.4.6.1.SDK | .NET framework 4.6.1 SDK | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.7.27520.0 | Gerekli
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet hedefleri ve derleme görevleri | 15.0.26919.1 | Gerekli
Microsoft.VisualStudio.Web.BuildTools.ComponentGroup | Web geliştirme derleme araçları | 15.7.27604.0 | Gerekli
Microsoft.Component.ClickOnce.MSBuild | ClickOnce derleme araçları | 15.7.27617.1 | Önerilen
Microsoft.Net.Component.4.5.1.TargetingPack | .NET framework 4.5.1 hedefleme paketi | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 hedefleme paketi | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.6.TargetingPack | .NET framework 4.6 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.TargetingPack | .NET framework 4 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET framework 4 – 4.6 geliştirme araçları | 15.6.27406.0 | Önerilen
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.AspNet45 | Gelişmiş ASP.NET özellikleri | 15.7.27625.0 | Önerilen
Microsoft.VisualStudio.Component.DockerTools.BuildTools | Kapsayıcı geliştirme araçları - derleme araçları | 15.7.27617.1 | Önerilen
Microsoft.VisualStudio.Component.TestTools.BuildTools | Test Araçları çekirdek özellikleri - derleme araçları | 15.7.27625.0 | Önerilen
Microsoft.VisualStudio.Component.TypeScript.2.8 | TypeScript 2.8 SDK | 15.0.27617.1 | Önerilen
Microsoft.VisualStudio.Wcf.BuildTools.ComponentGroup | WCF geliştirme derleme araçları | 15.6.27309.0 | Önerilen
Microsoft.Net.Component.3.5.DeveloperTools | .NET framework 3.5 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.2.SDK | .NET framework 4.6.2 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.2.TargetingPack | .NET framework 4.6.2 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.SDK | .NET framework 4.7.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.TargetingPack | .NET framework 4.7.1 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.SDK | .NET framework 4.7 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.TargetingPack | .NET framework 4.7 paketi hedefleme | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET framework 4.6.2 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET framework 4.7.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET framework 4.7 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Core.Component.SDK.1x | .NET core 1.0 1.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı

## <a name="mobile-development-with-net"></a>.NET ile Mobil Geliştirme

**Kimliği:** Microsoft.VisualStudio.Workload.XamarinBuildTools

**Açıklama:** iOS, Android ve C# ve F # kullanan Windows için platformlar arası uygulamaları oluşturmak için Araçlar.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET framework 4.6.1 SDK | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet hedefleri ve derleme görevleri | 15.0.26919.1 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Component.JavaJDK | Java SE Geliştirme Seti (8.0.1120.15) | 15.6.27406.0 | Önerilen
Component.Android.SDK25 | Android SDK kurulumu (API düzeyi 25) | 15.6.27413.0 | İsteğe Bağlı

## <a name="unaffiliated-components"></a>Unaffiliated bileşenleri

Bu, herhangi bir iş yükü ile dahil değildir, ancak ayrı bir bileşen olarak seçilebilir bileşenleridir.

Bileşen kimliği | Ad | Sürüm
--- | --- | ---
Microsoft.VisualStudio.Component.TypeScript.2.0 | TypeScript 2.0 SDK'sı | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.1 | TypeScript 2.1 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.2 | TypeScript 2.2 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.3 | TypeScript 2.3 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.5 | TypeScript 2.5 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.6 | TypeScript 2.6 SDK | 15.0.27520.0
Microsoft.VisualStudio.Component.VC.ATL.ARM | Visual C++ ATL ARM için | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATL.ARM.Spectre | Visual C++ ATL ARM Spectre Azaltıcı ile için | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATL.ARM64 | Visual C++ ATL ARM64 için | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATL.ARM64.Spectre | Visual C++ ATL Spectre Azaltıcı ile ARM64 için | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATL.Spectre | Visual C++ ATL (x86/x64) Spectre Azaltıcı ile | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATLMFC.Spectre | Visual C++ MFC x86/x64 için Spectre Azaltıcı ile | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ClangC2 | Clang/C2 (Deneysel) | 15.7.27520.0
Microsoft.VisualStudio.Component.VC.MFC.ARM | Visual C++ MFC ARM için | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.MFC.ARM.Spectre | Visual C++ MFC ARM Spectre Azaltıcı ile için | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.MFC.ARM64 | Visual C++ MFC ARM64 için | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.MFC.ARM64.Spectre | ARM64 Spectre Azaltıcı ile Visual C++ MFC desteği | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.Runtimes.ARM.Spectre | VC ++ 2017 sürüm 15.7 v14.14 kitaplıklar için Spectre (ARM) | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.Runtimes.ARM64.Spectre | VC ++ 2017 sürüm 15.7 v14.14 Spectre (ARM64) için kitaplıklar | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.Runtimes.x86.x64.Spectre | VC ++ 2017 sürüm 15.7 v14.14 Spectre (x86 hem x64) için kitaplıklar | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.Tools.14.11 | VC ++ 2017 sürüm 15.4 v14.11 araç takımı | 15.0.27406.0
Microsoft.VisualStudio.Component.VC.Tools.14.12 | VC ++ 2017 sürüm 15,5 v14.12 araç takımı | 15.0.27406.0
Microsoft.VisualStudio.Component.VC.Tools.14.13 | VC ++ 2017 sürüm 15,6 v14.13 araç takımı | 15.0.27625.0

## <a name="get-support"></a>Destek alma

Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:

* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunlarını izlemek ve yanıtlar bulmak [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/).
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio). (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.

* [Derleme araçları Visual Studio 2017 için](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017#build-tools-for-visual-studio-2017)
* [Visual Studio iş yükü ve bileşen kimlikleri](workload-and-component-ids.md)
* [Visual Studio Yönetici Kılavuzu](visual-studio-administrator-guide.md)
* [Komut satırı parametrelerini kullanarak Visual Studio'yu yükleme](use-command-line-parameters-to-install-visual-studio.md)
  * [Komut satırı parametresi örnekleri](command-line-parameter-examples.md)
* [Visual Studio’nun çevrimdışı yüklemesini oluşturma](create-an-offline-installation-of-visual-studio.md)
