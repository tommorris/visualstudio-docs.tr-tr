---
title: Visual Studio Masaüstü Express 2017 iş yükü ve Bileşen kimlikleri | Microsoft Docs
description: İş yükü ve Bileşen kimlikleri Visual Studio komut satırını kullanarak yükleme veya bağımlılık VSIX bildirim olarak belirtmek için kullanın
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
ms.assetid: a3c0cc76-e3ce-435c-a1af-a6318b5a4dbe
ms.workload:
- multiple
ms.openlocfilehash: 651b2901c87e99d19c86edfe81e1767d64674a25
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/03/2018
---
# <a name="visual-studio-desktop-express-2017-workload-and-component-ids"></a>Visual Studio Masaüstü Express 2017 iş yükü ve Bileşen kimlikleri

Tablolar bu sayfa listede kimlikleri, Visual Studio komut satırını kullanarak yüklemek için kullanabileceğiniz veya bağımlılık VSIX bildirim olarak belirtebilirsiniz. Biz yayın güncelleştirmeler Visual Studio gibi ek bileşenleri ekleyeceğiz olduğunu unutmayın.

Ayrıca sayfa hakkında aşağıdakileri unutmayın:

* Her iş yükü iş yükü Kimliğini ve iş yükü için kullanılabilir olan bileşenleri tablosu arkasından kendi bölümü vardır.
* Varsayılan olarak, **gerekli** bileşenleri, iş yükü yüklediğinizde yüklenir. İsterseniz, ayrıca yükleyebilirsiniz **önerilen** ve **isteğe bağlı** bileşenleri.
* Herhangi bir iş yükü ile bağlı değil ek bileşenleri listeleyen bir bölüm de ekledik.

VSIX bildiriminizi bağımlılıkları ayarladığınızda, Bileşen kimlikleri yalnızca belirtmeniz gerekir. Bizim minimum Bileşen bağımlılıkları belirlemek için bu sayfadaki tabloları kullanın. Bazı senaryolarda bu bir iş yükü yalnızca bir bileşenden belirttiğiniz anlamına gelebilir. Diğer senaryolarda, tek bir iş yükünü birden çok bileşenlerini veya birden çok iş yükünün birden çok bileşenlerini belirtin gelebilir. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio 2017 genişletilebilirlik projelerine geçirmek](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md) sayfası.

Bu kimlikleri kullanma hakkında daha fazla bilgi için bkz: [Visual Studio 2017 yüklemek için komut satırı parametrelerini kullanmak](use-command-line-parameters-to-install-visual-studio.md) sayfası. Ve iş yükü ve diğer ürünler için Bileşen kimlikleri listesi için bkz: [Visual Studio 2017 iş yükü ve Bileşen kimlikleri](workload-and-component-ids.md) sayfası.

## <a name="express-for-windows-desktop"></a>Windows Desktop için Express

**Kimliği:** Microsoft.VisualStudio.Workload.WDExpress

**Açıklama:** , kaynak kodu denetimi düzenleme sözdizimi algılayan koduyla WPF, WinForms ve Win32 gibi yerel ve yönetilen uygulamalar oluşturun ve yönetim iş öğesi. C#, Visual Basic ve Visual C++ için destek içerir.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.0.27205.0 | Gerekli
Microsoft.Component.HelpViewer | Yardım Görüntüleyicisi | 15.6.27323.2 | Gerekli
Microsoft.Component.MSBuild | MSBuild | 15.6.27309.0 | Gerekli
Microsoft.Component.VC.Runtime.OSSupport | UWP için Visual C++ çalışma zamanı | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.5.1.TargetingPack | .NET framework 4.5.1 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 paketi hedefleme | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 hedefleme paketi | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.TargetingPack | .NET framework 4.6 paketi hedefleme | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.TargetingPack | .NET framework 4 paketi hedefleme | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET framework 4 – 4.6 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Common.Azure.Tools | Bağlantı ve yayımlama araçları | 1.10.50912.1 | Gerekli
Microsoft.VisualStudio.Component.CoreEditor | Visual Studio çekirdek Düzenleyicisi | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.EntityFramework | Entity Framework 6 araçları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.6.27309.0 | Gerekli
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
Microsoft.VisualStudio.Component.VC.CLI.Support | C + +/ CLI desteği | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.VC.Tools.ARM | Visual C++ Derleyicileri ve ARM için kitaplıkları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VC.Tools.ARM64 | Visual C++ Derleyicileri ve ARM64 için kitaplıkları | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK (10.0.14393.0) | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop | Windows 10 Masaüstü C++ [x86 hem x64] için SDK (10.0.16299.0) | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop.arm | Windows 10 Masaüstü C++ [ARM ve ARM64] için SDK (10.0.16299.0) | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | Windows 10 için SDK'sı (10.0.16299.0) UWP: C#, VB, JS | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP.Native | Windows 10 için SDK'sı (10.0.16299.0) UWP: C++ | 15.6.27406.0 | Gerekli

## <a name="unaffiliated-components"></a>Unaffiliated bileşenleri

Bu, herhangi bir iş yükü ile dahil değildir, ancak ayrı bir bileşen olarak seçilebilir bileşenleridir.

Bileşen kimliği | Ad | Sürüm
--- | --- | ---
yok | yok | yok

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
