---
title: Visual Studio derleme araçları 2017 iş yükü ve Bileşen kimlikleri | Microsoft Docs
description: Klasik Windows tabanlı uygulamalar oluşturmak için Visual Studio iş yükü ve Bileşen kimlikleri kullanın
keywords: ''
author: TerryGLee
ms.author: tglee
manager: douge
ms.date: 03/05/2018
ms.topic: reference
helpviewer_keywords:
- workload ID, Visual Studio
- component ID, Visual Studio
- install Visual Studio, administrator guide
ms.service: ''
ms.technology:
- vs-acquisition
ms.assetid: b99298df-0280-47fc-af73-44cd7a8ac553
ms.workload:
- multiple
ms.openlocfilehash: 415ad88d9ef51a5002c7e64dcd4abf76f97167c3
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/03/2018
---
# <a name="visual-studio-build-tools-2017-component-directory"></a>Visual Studio derleme araçları 2017 bileşen dizini

Bu sayfada tablolar Visual Studio komut satırını kullanarak yüklemek için kullanabileceğiniz kimliklerini listeler. Biz yayın güncelleştirmeler Visual Studio gibi ek bileşenleri ekleyeceğiz olduğunu unutmayın.

Ayrıca bu sayfa hakkında aşağıdakileri unutmayın:

* Her iş yükü iş yükü Kimliğini ve iş yükü için kullanılabilir olan bileşenleri tablosu arkasından kendi bölümü vardır.
* Varsayılan olarak, **gerekli** bileşenleri, iş yükü yüklediğinizde yüklenir. İsterseniz, ayrıca yükleyebilirsiniz **önerilen** ve **isteğe bağlı** bileşenleri.
* Herhangi bir iş yükü ile bağlı değil ek bileşenleri listeleyen bir bölüm de ekledik.

Bu kimlikleri kullanma hakkında daha fazla bilgi için bkz: [Visual Studio 2017 yüklemek için komut satırı parametrelerini kullanmak](use-command-line-parameters-to-install-visual-studio.md) sayfası. Ve iş yükü ve diğer ürünler için Bileşen kimlikleri listesi için bkz: [Visual Studio 2017 iş yükü ve Bileşen kimlikleri](workload-and-component-ids.md) sayfası.

## <a name="msbuild-tools"></a>MSBuild araçları

**Kimliği:** Microsoft.VisualStudio.Workload.MSBuildTools

**Açıklama:** MSBuild tabanlı uygulamalar oluşturmak için gerekli araçları sağlar.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.CoreBuildTools | Visual Studio Araçları çekirdek derleme | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.FSharp.MSBuild | F# derleyici | 15.6.27406.0 | İsteğe Bağlı

## <a name="net-core-build-tools"></a>.NET core derleme araçları

**Kimliği:** Microsoft.VisualStudio.Workload.NetCoreBuildTools

**Açıklama:** .NET Core uygulamaları oluşturmak için Araçlar.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet hedefleri ve derleme görevleri | 15.0.26919.1 | Gerekli
Microsoft.Net.Core.Component.SDK.1x | .NET core 1.0 1.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı

## <a name="nodejs-build-tools"></a>Node.js derleme araçları

**Kimliği:** Microsoft.VisualStudio.Workload.NodeBuildTools

**Açıklama:** yapı Node.js, bir zaman uyumsuz olay denetimli JavaScript çalışma zamanı kullanarak Ölçeklenebilir Ağ uygulamaları.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.VisualStudio.Component.Node.Build | Node.js desteği | 15.6.27406.0 | Gerekli

## <a name="visual-c-build-tools"></a>Visual C++ derleme araçları

**Kimliği:** Microsoft.VisualStudio.Workload.VCTools

**Açıklama:** Microsoft C++ araç takımı, ATL ve MFC kullanarak Windows Masaüstü uygulamaları oluşturun.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.VC.CoreBuildTools | Visual C++ derleme araçları çekirdek Özellikler | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VC.Redist.14.Latest | Visual C++ 2017 yeniden dağıtılabilir güncelleştirme | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 v141 araç takımı (x86, x64) | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Windows10SDK | Windows Evrensel C çalışma zamanı | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VC.CMake.Project | CMake için Visual C++ Araçları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop | Windows 10 Masaüstü C++ [x86 hem x64] için SDK (10.0.16299.0) | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | Windows 10 için SDK'sı (10.0.16299.0) UWP: C#, VB, JS | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP.Native | Windows 10 için SDK'sı (10.0.16299.0) UWP: C++ | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.0.27005.2 | Önerilen
Microsoft.Component.VC.Runtime.UCRTSDK | Windows Evrensel CRT SDK'sı | 15.6.27309.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.140 | VC ++ 2015.3 v140 araç takımı Masaüstü (x86, x64) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.ATL | Visual C++ ATL desteği | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.ATLMFC | MFC ve ATL desteği (x86 hem x64) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.ClangC2 | Clang/C2 (Deneysel) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.CLI.Support | C + +/ CLI desteği | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Modules.x86.x64 | Standart Kitaplığı (Deneysel) modülleri | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Tools.ARM | Visual C++ Derleyicileri ve ARM için kitaplıkları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Tools.ARM64 | Visual C++ Derleyicileri ve ARM64 için kitaplıkları | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Windows 10 SDK'sı (10.0.10240.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK'sı (10.0.10586.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK (10.0.14393.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.Desktop | Windows 10 Masaüstü C++ [x86 hem x64] için SDK (10.0.15063.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | Windows 10 için SDK'sı (10.0.15063.0) UWP: C#, VB, JS | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP.Native | Windows 10 için SDK'sı (10.0.15063.0) UWP: C++ | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop.arm | Windows 10 Masaüstü C++ [ARM ve ARM64] için SDK (10.0.16299.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows81SDK | Windows 8.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.WinXP | C++ için Windows XP desteği | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Win81 | Windows 8.1 SDK'sı ve UCRT SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.WinXP | C++ için Windows XP desteği | 15.6.27406.0 | İsteğe Bağlı

## <a name="web-development-build-tools"></a>Web geliştirme derleme araçları

**Kimliği:** Microsoft.VisualStudio.Workload.WebBuildTools

**Açıklama:** MSBuild görevleri ve hedefleri oluşturma web uygulamaları.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Wcf.BuildTools.ComponentGroup | WCF geliştirme derleme araçları | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Web.BuildTools.ComponentGroup | Web geliştirme derleme araçları | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.5.1.TargetingPack | .NET framework 4.5.1 hedefleme paketi | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 hedefleme paketi | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.6.TargetingPack | .NET framework 4.6 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.TargetingPack | .NET framework 4 paketi hedefleme | 15.6.27406.0 | Önerilen
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET framework 4 – 4.6 geliştirme araçları | 15.6.27406.0 | Önerilen
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.AspNet45 | Gelişmiş ASP.NET özellikleri | 15.6.27428.1 | Önerilen
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet hedefleri ve derleme görevleri | 15.0.26919.1 | Önerilen
Microsoft.VisualStudio.Component.TypeScript.2.6 | TypeScript 2.6 SDK | 15.0.27406.0 | Önerilen
Microsoft.Net.Component.3.5.DeveloperTools | .NET framework 3.5 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.2.SDK | .NET framework 4.6.2 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.2.TargetingPack | .NET framework 4.6.2 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.SDK | .NET Framework 4.7.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.TargetingPack | .NET framework 4.7.1 hedefleme paketi | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.SDK | .NET framework 4.7 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.TargetingPack | .NET framework 4.7 paketi hedefleme | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET framework 4.6.2 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET framework 4.7.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET framework 4.7 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı

## <a name="unaffiliated-components"></a>Unaffiliated bileşenleri

Bu, herhangi bir iş yükü ile dahil değildir, ancak ayrı bir bileşen olarak seçilebilir bileşenleridir.

Bileşen kimliği | Ad | Sürüm
--- | --- | ---
Microsoft.VisualStudio.Component.TypeScript.2.0 | TypeScript 2.0 SDK'sı | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.1 | TypeScript 2.1 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.2 | TypeScript 2.2 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.3 | TypeScript 2.3 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.5 | TypeScript 2.5 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.VC.Tools.14.11 | VC ++ 2017 sürüm 15.4 v14.11 araç takımı | 15.0.27406.0
Microsoft.VisualStudio.Component.VC.Tools.14.12 | VC ++ 2017 sürüm 15,5 v14.12 araç takımı | 15.0.27406.0

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
