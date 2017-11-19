---
title: "Bağlantı noktası, geçirme ve yükseltme Visual Studio projeleri | Microsoft Docs"
ms.custom: 
ms.date: 07/24/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Win8ExpressDesktopBlock
- w8trefactor
- VS.ReviewProjectAndSolutionChangesDialog.UpgradeRetarget
- ProjectCompatibilityDlgHelpTopic
- VS.ReviewProjectAndSolutionChangesDialog.Upgrade
helpviewer_keywords:
- conversion, projects
- asset compatibility
- projects, conversion
ms.assetid: bee759bd-6ff5-4c2e-913a-ea7d3c906c29
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: ef005f6456c532ade108299f556c8ef7211e6055
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="port-migrate-and-upgrade-visual-studio-projects"></a>Bağlantı noktası, geçirme ve Visual Studio projelerini yükseltme

Her yeni sürümü Visual Studio, genellikle çoğu önceki tür projeleri, dosyaları ve diğer varlıklar destekler. Bunlarla çalışmak [her zaman sahip](../ide/solutions-and-projects-in-visual-studio.md), ve daha yeni özelliklere bağımlı yok olması koşuluyla, Visual Studio Visual Studio 2015, Visual Studio 2013 ve Visual Studio gibi önceki sürümleriyle uyumluluğunu geriye doğru korur. 2012. (Bkz [sürüm notları](https://www.visualstudio.com/vs/release-notes/) için hangi özelliklerin hangi sürümlerine özeldir.)

Bazı türleri değişiklik zaman içerisinde, ancak destekler. Visual Studio'nun daha yeni bir sürümü artık belirli türlerini desteklemek veya bunlar olarak geçirilen ve bunlar artık geriye dönük olarak uyumlu şekilde güncelleştirilmiş olduğunu gerektirir. Geçiş sorunları için geçerli durumunu almak için bkz [Visual Studio Geliştirici topluluğu site](https://developercommunity.visualstudio.com).

> [!Important]
> Mevcut bu konuda ayrıntıları geçiş ile ilgili yalnızca proje türleri için Visual Studio 2017 de sağlar. Geçiş sorunlarını desteklenen proje türleri içermez; Bu liste bulunan bulunan [Platform desteği ve Uyumluluk](https://www.visualstudio.com/productinfo/vs2017-compatibility-vs). Ayrıca, bazı proje türleri artık Visual Studio 2017 içinde hiç desteklenmiyor ve bu nedenle geçirilemez unutmayın.

> [!Important]
> Visual Studio'da uygun iş yüklerini ekleme yükleyici belirli proje türleri açmak için gereklidir. Yüklü iş yükü yoksa, Visual Studio bir bilinmeyen ya da uyumsuz proje türü rapor eder. Bu durumda, yükleme seçeneklerinizi denetleyin ve yeniden deneyin. Yeniden bkz [Platform desteği ve Uyumluluk](https://www.visualstudio.com/productinfo/vs2017-compatibility-vs) Visual Studio 2017 proje desteği hakkında ayrıntılı bilgi için konu.

## <a name="projects"></a>Projeler

Aşağıdaki listede, önceki sürümlerde oluşturulan projeleri için Visual Studio 2017 desteği açıklanmaktadır.

Bir proje görmüyorum veya dosya türü listelenen Burada, lütfen bakın olmalıdır [bu konunun Visual Studio 2015 sürümü](https://msdn.microsoft.com/library/hh266747.aspx) ve açıklamaları not edin.

| Proje Türü | Destek |
| --- | --- |
| .NET core projeleri (artık.xproj) | Visual Studio 2015 ile oluşturulan projeleri artık.xproj proje dosyasını içeren tooling Önizleme kullanılır. Visual Studio 2017 ile artık.xproj dosya açtığınızda, dosya (artık.xproj dosya yedeğini yapılan) .csproj biçimine geçirmek için istenir. .NET Core projeler için bu .csproj biçim VS2015 ve daha önceki sürümlerde desteklenmiyor.  Artık.xproj biçimi dışında Visual Studio 2017 içinde geçiş .csproj için desteklenmiyor. Daha fazla bilgi için bkz: [geçirme .NET Core projeleri .csproj biçimine](https://docs.microsoft.com/dotnet/core/migration/#visual-studio-2017).|
| ASP.NET Web uygulaması ve etkin Application Insights ile ASP.NET çekirdek Web uygulaması | Her bir Visual Studio kullanıcı için kaynak bilgileri kullanıcı örneği başına kayıt defterinde depolanır. Bu kullanılan zaman kullanıcı değilsiniz açılmış bir proje ve Azure Application Insights verileri aramak için istediği. Visual Studio 2015, Visual Studio 2017'den farklı kayıt defteri konumu kullanır ve çakışıp çakışmadığını.<br/><br/>Bir kullanıcı bir ASP.NET Web uygulaması veya ASP.NET çekirdek Web uygulaması oluşturulduktan sonra kaynak .suo dosyasında depolanır. Kullanıcı projeyi Visual Studio 2015 veya 2017 açabilir ve Visual Studio projeler ve çözümler hem sürümleri arasında kullanılan desteklediği sürece kaynak bilgileri her ikisi için kullanılır. Kullanıcıların bir kez bulunan her ürün kimliğini doğrulaması gerekir. Örneğin, bir projeyi Visual Studio 2015 ile oluşturulan ve Visual Studio 2017 içinde açılan, kullanıcının Visual Studio 2017 üzerinde kimlik doğrulaması gerekir. |
| C#/Visual Basic Webform veya Windows Form | Projeyi Visual Studio 2015 ve Visual Studio 2017 de açabilirsiniz. |
| Veritabanı birim testi projelerini (.csproj, .vbproj)    | Eski veri test projeleri Visual Studio 2017 yüklenir ancak GAC kullanacağı birimi bağımlılıkların sürümünü 'd. Kullanılacak birim testi projesi yükseltmek için en son bağımlılıkları sağ seçip Çözüm Gezgini proje tıklayın **SQL Server birim testi projesi için Dönüştür...** . |
| F# | Visual Studio 2017 2015 ve Visual Studio 2013 ile oluşturulan projeleri açabilirsiniz. Bu projelerinde Visual Studio 2017 özellikleri etkinleştirmek için ancak proje özelliklerini açın ve F # 4.1 için hedef fsharp.core değiştirin. Ayrıca **F # dili desteği** Visual Studio yükleyicisi seçeneğinde, varsayılan .NET iş yükleri ile seçili; bu seçeneği iş yükünün veya ondan seçerek içermelidir  **Bileşenleri tek tek** altında sekmesinde **geliştirme etkinlikleri**. |
| InstallShield<br/>MSI Kurulumu | Visual Studio 2010'da oluşturulan yükleyici projeleri yardımıyla sonraki sürümlerinde açılabilir [Visual Studio yükleyici projeleri uzantısı](https://marketplace.visualstudio.com/items?itemName=UnniRavindranathan-MSFT.MicrosoftVisualStudio2013InstallerProjects). Ayrıca bkz. [WiX Toolset Visual Studio 2017 uzantısı](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension). InstallShield Limited Edition artık Visual Studio ile dahil edilir. Danışın [Flexera yazılım](http://learn.flexerasoftware.com/content/IS-EVAL-InstallShield-Limited-Edition-Visual-Studio) Visual Studio 2017 kullanılabilirliği hakkında. |
| LightSwitch | LightSwitch Visual Studio 2017 artık desteklenmiyor. Visual Studio 2013'te Visual Studio 2012 ve önceki oluşturulan projeleri açılamıyor veya Visual Studio 2015 yükseltilir ve bundan sonra yalnızca Visual Studio 2013 veya Visual Studio 2015'te açılabilir. |
| Visual Studio için Microsoft Azure Araçları | Bu proje türleri'ni açmak için ilk yükleme [.NET için Azure SDK](http://azure.microsoft.com/downloads/), projeyi açın. Gerekirse, projenizin güncelleştirilir. |
| Model-View-Controller framework (ASP.NET MVC) | MVC sürümleri ve Visual Studio için destek:<ul><li>Visual Studio 2010 SP1 MVC 2 ve MVC 3 destekler; MVC 4 Destek aracılığıyla eklenir [ASP.NET 4 MVC 4 Visual Studio 2010 SP1'i yüklemek için](https://www.microsoft.com/download/details.aspx?id=30683)</li><li>Visual Studio 2012 yalnızca MVC 3 ve MVC 4 destekler</li><li>Yalnızca MVC 4 ve MVC 5 Visual Studio 2013'ü destekler</li><li>Visual Studio 2017 ve Visual Studio 2015 MVC (var olan projeleri açın ancak yenilerini oluşturmaz) 4 ve MVC 5 destekler</li></ul><br/><br/>MVC sürümleri yükseltme:<ul><li>Otomatik olarak MVC 2'den MCV 3'e yükseltme hakkında daha fazla bilgi için bkz: [ASP.NET MVC 3 uygulama Upgrader](http://go.microsoft.com/fwlink/?LinkID=238178).</li><li>El ile MVC 2'den MVC 3'e yükseltme hakkında daha fazla bilgi için bkz: [bir ASP.NET MVC 2 proje için ASP.NET MVC 3 araçları güncelleştirme yükseltme](http://go.microsoft.com/fwlink/?linkid=238178).</li><li>El ile MVC3 MVC 4'e yükseltme hakkında daha fazla bilgi için bkz: [bir ASP.NET MVC 3 projesinin ASP.NET MVC 4'e yükseltme](http://www.asp.net/whitepapers/mvc4-release-notes). Projeniz .NET Framework 3.5 SP1 hedefliyorsa, .NET Framework 4 kullanacak şekilde yeniden hedefleyin gerekir.</li><li>El ile MVC 4'ten MVC 5'e yükseltme hakkında daha fazla bilgi için bkz: [bir ASP.NET MVC 4 ve Web API projesi ASP.NET MVC 5 ve Web API 2'ye yükseltme](https://www.asp.net/mvc/overview/releases/how-to-upgrade-an-aspnet-mvc-4-and-web-api-project-to-aspnet-mvc-5-and-web-api-2)</li></ul> |
| Modelleme | Visual Studio projesini otomatik olarak güncelleştirmek izin verirseniz, Visual Studio 2015, Visual Studio 2013 veya Visual Studio 2012 açabilirsiniz.<br/><br/>Modelleme projesi biçimi, Visual Studio 2015 ve Visual Studio 2017 arasında değişmemiştir ve projeyi açılabilir ve her iki sürümde değiştirildi. Ancak, Visual Studio 2017 davranışındaki farklılıklar vardır:<ul><li>Modelleme projeleri şimdi "Bağımlılık doğrulama" projelerinde menüleri ve şablonları denir.</li><li>UML diyagramları artık Visual Studio 2017 içinde desteklenir. UML dosyaları önce Çözüm Gezgini'nde listelenen ancak XML dosyaları olarak açılacak. Visual Studio 2015 görüntülemek, oluşturmak veya UML diyagramları düzenlemek için kullanın.</li><li>Visual Studio 2017 ' mimari bağımlılıkları doğrulanması artık modelleme projesi yapılandırıldığında gerçekleştirilir. Her kod projesi yerleşik olarak bunun yerine, doğrulama gerçekleştirilir. Bu değişiklik modelleme projesi etkilemez, ancak Doğrulanmakta olan kod projeleri değişiklikler gerektirir. Visual Studio 2017 otomatik olarak kod projelerine gerekli değişiklikleri yapabilir ([daha fazla bilgi](http://go.microsoft.com/fwlink/?LinkId=827800)).</li></ul> |
| MSI kurulumu (.vdproj) | Yukarıdaki InstallShield projeleri bakın. | 
| Office 2007 VSTO | Tek yönlü bir yükseltme için Visual Studio 2017 gerektirir. |
| Office 2010 VSTO | Projeniz .NET Framework 4 hedefliyorsa, Visual Studio 2010 SP1 ve sonraki sürümlerinde açabilirsiniz. Tüm diğer projeler tek yönlü yükseltme gerektirir. |
| SharePoint 2010 | Bir SharePoint çözüm proje ile Visual Studio 2017 açıldığında, SharePoint 2013 veya SharePoint 2016 için yükseltilir. ".NET masaüstü geliştirme" iş yükü yükseltme için Visual Studio 2017 içinde yüklü olması gerekir.<br/><br/>SharePoint projeleri yükseltme hakkında daha fazla bilgi için bkz: [SharePoint 2013'e yükseltme](https://technet.microsoft.com/library/cc303420.aspx), [güncelleştirme iş akışını SharePoint Server 2013'te](https://technet.microsoft.com/library/dn133867.aspx), ve [SharePoint Server 2016 grubu oluşturma bir veritabanı için yükseltme ekleme](https://technet.microsoft.com/library/cc263026(v=office.16).aspx). |
| SharePoint 2016 | Office geliştirici araçları Önizleme 2'de oluşturulan SharePoint eklentisi projeleri Visual Studio 2017 açılamaz. Güncellemeniz gerekir bu sorunu çözmek için `MinimumVisualStudioVersion` 12.0 için ve `MinimumOfficeToolsVersion` içinde 12.2 için `.csproj` veya `.vbproj` dosyası. |
| Silverlight | Silverlight projeleri Visual Studio 2017 desteklenmiyor. Silverlight uygulamalarını korumak için Visual Studio 2015 kullanmaya devam edin. |
| SQL Server Reporting Services ve SQL Server Analysis Services (SSRS SSDT, SSAS, MSA'lar) | Destek bu proje türleri için sağlanan Visual Studio Galerisi iki uzantıları aracılığıyla: [Microsoft Analysis Services modelleme projeleri](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftAnalysisServicesModelingProjects) ve [Microsoft Reporting Services projeleri](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftReportProjectsforVisualStudio). SSDT desteği Visual Studio 2017 veri depolama ve işlem iş yükü de bulunmaktadır. |
| SQL Server Integration Services (SSIS) | Desteği henüz Visual Studio 2017 için kullanılabilir değildir. Üzerinde duyurulacaktır [SQL Server Integration Services blog](https://blogs.msdn.microsoft.com/ssis/). Mevcut SSIS için Visual Studio 2015 kullanmaya devam etmek için önerilir. |
| Visual C++ | Visual Studio 2017 çözümler ve Visual Studio 2015'te oluşturulmuş projeler açmak için kullanabileceğiniz-olduğu, ancak Visual Studio'nun eski sürümlerinde oluşturulan projeleri proje yükseltme veya Visual ile oluşturmak için daha yeni bir araç takımı yeniden hedefleme gerektirebilir Studio 2017. Daha fazla bilgi için bkz: [Visual C++ taşıma ve yükseltme Kılavuzu](https://docs.microsoft.com/cpp/porting/visual-cpp-porting-and-upgrading-guide). |
| Visual Studio genişletilebilirlik/VSIX | Projeleri MinimumVersion 14.0 veya daha az projeyi Visual Studio'nun önceki sürümleri açılmasını engelleyen MinimumVersion 15.0 bildirmek için güncelleştirilir. MinimumVersion önceki sürümlerde açmak bir proje izin vermek için kümesine `$(VisualStudioVersion)`. Ayrıca bkz. [nasıl yapılır: Visual Studio 2017 genişletilebilirlik projeleri geçirmek](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md). |
| Visual Studio Laboratuvar Yönetimi | Microsoft Test Yöneticisi'ni veya Visual Studio 2010 SP1'i kullanabilirsiniz ve daha sonra bu sürümleri hiçbirinde oluşturulan ortamları açın. Ancak, ortamları oluşturabilmeniz için önce Visual Studio 2010 SP1 için Team Foundation Server sürümü Microsoft Test Yöneticisi'nin sürümü eşleşmelidir. |
| Apache Cordova için Visual Studio Araçları |Bu projeyi Visual Studio 2017 içinde açılabilir ancak geriye dönük olarak uyumlu değildir. Visual Studio 2015'ten bir proje açıldığında, değişiklikleri projenize izin istenir. Bunun yerine toolsets kullanmak için proje yükseltmeleri bir `taco.json` Cordova kitaplığı, kendi platformları ve eklentileri yanı sıra düğümü/npm bağımlılıklarını sürümünü oluşturmaya yönetmek için dosya. Bkz: [Geçiş Kılavuzu](https://docs.microsoft.com/visualstudio/cross-platform/tools-for-cordova/first-steps/migrate-from-visual-studio-2015) daha fazla bilgi için. |
| Windows Communication Foundation, Windows Workflow Foundation | Bu projeyi Visual Studio 2017, Visual Studio 2015, Visual Studio 2013 ve Visual Studio 2012 açabilirsiniz |
| Windows Presentation Foundation | Bu projeyi Visual Studio 2013, Visual Studio 2012 ve Visual Studio 2010 SP1'i açabilirsiniz. |
| Windows mağazası/telefon uygulamaları | Windows mağazası 8.1 ve 8.0 ve Windows Phone 8.1 ve 8.0 projeleri Visual Studio 2017 desteklenmez. Bu uygulamaları korumak için Visual Studio 2015 kullanmaya devam edin. Windows Phone 7.x projelerini korumak için Visual Studio 2012 kullanın. |
