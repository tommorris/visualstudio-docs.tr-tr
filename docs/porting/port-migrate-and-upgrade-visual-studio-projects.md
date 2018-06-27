---
title: Bağlantı noktası, geçirme ve projelerini yükseltme
description: Visual Studio ve ne zaman bir proje geçirmek gereken Visual Studio karar önceki sürümlerinde oluşturulan projeleri için Visual Studio 2017 desteği için bir başvuru.
ms.date: 06/19/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload: multiple
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
ms.openlocfilehash: ea7f001179a206e3dfcf8e7026b54d6da6ebffbd
ms.sourcegitcommit: 4e605891d0dfb3ab83150c17c074bb98dba29d15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36947186"
---
# <a name="project-migration-and-upgrade-reference-for-visual-studio-2017"></a>Visual Studio 2017 proje geçiş ve yükseltme başvurusu

Her yeni sürümü Visual Studio, genellikle çoğu önceki tür projeleri, dosyaları ve diğer varlıklar destekler. Bunlarla çalışmak [her zaman sahip](../ide/solutions-and-projects-in-visual-studio.md), ve daha yeni özelliklere bağımlı yok olması koşuluyla, Visual Studio genellikle geriye doğru Visual Studio 2015, Visual Studio 2013 gibi önceki sürümleriyle uyumluluğunu korumak çalışır ve Visual Studio 2012. (Bkz [sürüm notları](https://visualstudio.microsoft.com/vs/release-notes/) için hangi özelliklerin hangi sürümlerine özeldir.)

Bazı proje türleri için destek de zaman içinde değişir. Visual Studio'nun daha yeni bir sürümü artık belirli projeler hiç destekleyebilir ya da artık geriye dönük olarak uyumlu olacak şekilde, bir proje güncelleştirilmesini gerektirir. Geçiş sorunları için geçerli durumunu almak için bkz [Visual Studio Geliştirici topluluğu site](https://developercommunity.visualstudio.com).

Mevcut bu makalede, Visual Studio 2017 geçirebileceğiniz proje türleri için Ayrıntılar sağlar. Makale, Visual Studio 2017 içinde artık desteklenmemektedir ve bu nedenle geçirilemez proje türleri dışlar. Makale ayrıca hiçbir geçiş sorunları olan desteklenen proje türleri dışlar; Bu liste bulunan [Platform desteği ve Uyumluluk](https://www.visualstudio.com/productinfo/vs2017-compatibility-vs).

> [!Important]
> Belirli proje türleri aracılığıyla Visual Studio yükleyicisi uygun iş yüklerini yükleme gerektirir. Yüklü iş yükü yoksa, Visual Studio bir bilinmeyen ya da uyumsuz proje türü bildirir. Bu durumda, yükleme seçeneklerinizi denetleyin ve yeniden deneyin. Yeniden bkz [Platform desteği ve Uyumluluk](/visualstudio/productinfo/vs2017-compatibility-vs) makalede Visual Studio 2017 proje desteği hakkında ayrıntılı bilgi için.

## <a name="project-types"></a>Proje türleri

Aşağıdaki listede, önceki sürümlerde oluşturulan projeleri için Visual Studio 2017 desteği açıklanmaktadır.

Bir proje görmüyorum veya dosya türü listelenen Burada, olması, başvurun [bu makalenin Visual Studio 2015 sürümü](https://msdn.microsoft.com/library/hh266747.aspx) ve, projenizin ayrıntılarını sağlamak için bu sayfanın altındaki "belgelerine görüş" seçeneğini kullanın. (Bir yanıt isterseniz, belgeleri geri bildirim kullanmak yerine "Bu sayfayı yararlı anonimdir?" Denetim.)

| Proje Türü | Destek |
| --- | --- |
| .NET core projeleri (xproj) | Visual Studio 2015 ile oluşturulan projeleri xproj proje dosyası dahil önizleme araç kullanılır. Visual Studio 2017 ile bir xproj dosyayı açtığınızda, dosya (xproj dosyanızın bir yedeğini yapılan) csproj biçimine geçirmek istenir. Bu csproj biçimi .NET Core projeleri için Visual Studio 2015 ve daha önceki sürümlerde desteklenmiyor.  Xproj biçimi dışında Visual Studio 2017 içinde geçiş csproj için desteklenmiyor. Daha fazla bilgi için bkz: [geçirme .NET Core projeleri csproj biçimine](/dotnet/core/migration/#visual-studio-2017).|
| ASP.NET Web uygulaması ve etkin Application Insights ile ASP.NET çekirdek Web uygulaması | Her bir Visual Studio kullanıcı için kaynak bilgileri kullanıcı örneği başına kayıt defterinde depolanır. Bu bilgiler, kullanıcının açılır bir proje sahip olmadığında kullanılır ve Azure Application Insights verileri aramak istiyor. Visual Studio 2015, Visual Studio 2017'den farklı kayıt defteri konumu kullanır ve çakışıp çakışmadığını.<br/><br/>Bir kullanıcı bir ASP.NET Web uygulaması veya ASP.NET çekirdek Web uygulaması oluşturulduktan sonra kaynak .suo dosyasında depolanır. Kullanıcı projeyi Visual Studio 2015 veya 2017 açabilir ve Visual Studio projeler ve çözümler hem sürümleri arasında kullanılan desteklediği sürece kaynak bilgileri her ikisi için kullanılır. Kullanıcıların bir kez bulunan her ürün kimlik doğrulaması gerekir. Bir proje Visual Studio 2015 ile oluşturulan ve Visual Studio 2017 açılmış, örneğin, kullanıcının Visual Studio 2017 üzerinde kimlik doğrulaması gerekir. |
| C#/Visual Basic Webform veya Windows Form | Projeyi Visual Studio 2015 ve Visual Studio 2017 de açabilirsiniz. |
| Veritabanı birim testi projelerini (csproj, .vbproj) | Eski veri test projeleri Visual Studio 2017 yükledi, ancak GAC kullanmak birimi bağımlılıkların sürümünü 'd. En son bağımlılıkları kullanmak için birim testi projesi yükseltmek için Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **SQL Server birim testi projesi için Dönüştür...** . |
| F# | Visual Studio 2017 2015 ve Visual Studio 2013 ile oluşturulan projeleri açabilirsiniz. Bu projelerinde Visual Studio 2017 özellikleri etkinleştirmek için ancak proje özelliklerini açın ve F # 4.1 için hedef fsharp.core değiştirin. Ayrıca **F # dili desteği** Visual Studio yükleyicisi seçeneğinde, varsayılan .NET iş yükleri ile seçili; bu seçeneği iş yükünün veya ondan seçerek içermelidir  **Bileşenleri tek tek** altında sekmesinde **geliştirme etkinlikleri**. |
| InstallShield<br/>MSI Kurulumu | Visual Studio 2010'da oluşturulan yükleyici projeleri yardımıyla sonraki sürümlerinde açılabilir [Visual Studio yükleyici projeleri uzantısı](https://marketplace.visualstudio.com/items?itemName=UnniRavindranathan-MSFT.MicrosoftVisualStudio2013InstallerProjects). Ayrıca bkz. [WiX Toolset Visual Studio 2017 uzantısı](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension). InstallShield Limited Edition artık Visual Studio ile dahil edilir. Danışın [Flexera yazılım](http://learn.flexerasoftware.com/content/IS-EVAL-InstallShield-Limited-Edition-Visual-Studio) Visual Studio 2017 kullanılabilirliği hakkında. |
| LightSwitch | LightSwitch Visual Studio 2017 artık desteklenmiyor. Visual Studio 2012 ile oluşturulan ve daha önceki Visual Studio 2013 veya Visual Studio 2015 açılan projeleri yükseltilir ve bundan sonra yalnızca Visual Studio 2013 veya Visual Studio 2015'te açılabilir. |
| Visual Studio için Microsoft Azure Araçları | Bu proje türleri'ni açmak için ilk yükleme [.NET için Azure SDK](http://azure.microsoft.com/downloads/), projeyi açın. Gerekirse, projenizin güncelleştirilir. |
| Model-View-Controller framework (ASP.NET MVC) | MVC sürümleri ve Visual Studio için destek:<ul><li>Visual Studio 2010 SP1 MVC 2 ve MVC 3 destekler; MVC 4 Destek aracılığıyla eklenir [ASP.NET 4 MVC 4 Visual Studio 2010 SP1'i yüklemek için](https://www.microsoft.com/download/details.aspx?id=30683)</li><li>Visual Studio 2012 yalnızca MVC 3 ve MVC 4 destekler</li><li>Yalnızca MVC 4 ve MVC 5 Visual Studio 2013'ü destekler</li><li>Visual Studio 2017 ve Visual Studio 2015 MVC (var olan projeleri açın ancak yenilerini oluşturmaz) 4 ve MVC 5 destekler</li></ul><br/>MVC sürümleri yükseltme:<ul><li>Otomatik olarak MVC 2'den MVC 3'e yükseltme hakkında daha fazla bilgi için bkz: [ASP.NET MVC 3 uygulama Upgrader](http://go.microsoft.com/fwlink/?LinkID=238178).</li><li>El ile MVC 2'den MVC 3'e yükseltme hakkında daha fazla bilgi için bkz: [bir ASP.NET MVC 2 proje için ASP.NET MVC 3 araçları güncelleştirme yükseltme](http://go.microsoft.com/fwlink/?linkid=238178).</li><li>El ile MVC3 MVC 4'e yükseltme hakkında daha fazla bilgi için bkz: [bir ASP.NET MVC 3 projesinin ASP.NET MVC 4'e yükseltme](http://www.asp.net/whitepapers/mvc4-release-notes). Projeniz .NET Framework 3.5 SP1 hedefliyorsa, .NET Framework 4 kullanacak şekilde yeniden hedefleyin gerekir.</li><li>El ile MVC 4'ten MVC 5'e yükseltme hakkında daha fazla bilgi için bkz: [bir ASP.NET MVC 4 ve Web API projesi ASP.NET MVC 5 ve Web API 2'ye yükseltme](https://www.asp.net/mvc/overview/releases/how-to-upgrade-an-aspnet-mvc-4-and-web-api-project-to-aspnet-mvc-5-and-web-api-2).</li></ul> |
| Modelleme | Visual Studio projesini otomatik olarak güncelleştirmek izin verirseniz, Visual Studio 2015, Visual Studio 2013 veya Visual Studio 2012 açabilirsiniz.<br/><br/>Modelleme projesi biçimi, Visual Studio 2015 ve Visual Studio 2017 arasında değişmemiştir ve projeyi açılabilir ve her iki sürümde değiştirildi. Ancak, Visual Studio 2017 davranışındaki farklılıklar vardır:<ul><li>Modelleme projeleri şimdi "Bağımlılık doğrulama" projelerinde menüleri ve şablonları denir.</li><li>UML diyagramları artık Visual Studio 2017 içinde desteklenir. UML dosyaları önce Çözüm Gezgini'nde listelenen ancak XML dosyaları olarak açılır. Visual Studio 2015 görüntülemek, oluşturmak veya UML diyagramları düzenlemek için kullanın.</li><li>Visual Studio 2017 ' mimari bağımlılıkları doğrulanması artık modelleme projesi yapılandırıldığında gerçekleştirilir. Her kod projesi yerleşik olarak bunun yerine, doğrulama gerçekleştirilir. Bu değişiklik modelleme projesi etkilemez, ancak Doğrulanmakta olan kod projeleri değişiklikler gerektirir. Visual Studio 2017 otomatik olarak kod projelerine gerekli değişiklikleri yapabilir ([daha fazla bilgi](http://go.microsoft.com/fwlink/?LinkId=827800)).</li></ul> |
| MSI kurulumu (vdproj) | InstallShield projeleri bakın. |
| Office 2007 VSTO | Tek yönlü bir yükseltme için Visual Studio 2017 gerektirir. |
| Office 2010 VSTO | Projeniz .NET Framework 4 hedefliyorsa, Visual Studio 2010 SP1 ve sonraki sürümlerinde açabilirsiniz. Tüm diğer projeler tek yönlü yükseltme gerektirir. |
| Service Fabric (sfproj) | Bir ASP.NET Core hizmeti projesi Service Fabric uygulaması proje başvuru sürece Service Fabric uygulaması projeleri, Visual Studio 2015 veya Visual Studio 2017 açılabilir. Visual Studio 2015 Visual Studio 2017 açıldığından projelerden Service Fabric xproj biçiminden csproj için geçirilen yönlüdür. ".NET Core projeleri (xproj)" Bu tablodaki önceki bakın. |
| SharePoint 2010 | Bir SharePoint çözüm proje ile Visual Studio 2017 açıldığında, SharePoint 2013 veya SharePoint 2016 için yükseltilir. ".NET masaüstü geliştirme" iş yükü yükseltme için Visual Studio 2017 içinde yüklü olması gerekir.<br/><br/>SharePoint projeleri yükseltme hakkında daha fazla bilgi için bkz: [SharePoint 2013'e yükseltme](https://technet.microsoft.com/library/cc303420.aspx), [güncelleştirme iş akışını SharePoint Server 2013'te](https://technet.microsoft.com/library/dn133867.aspx), ve [SharePoint Server 2016 grubu oluşturma bir veritabanı için yükseltme ekleme](https://technet.microsoft.com/library/cc263026(v=office.16).aspx). |
| SharePoint 2016 | Office geliştirici araçları Önizleme 2'de oluşturulan SharePoint eklentisi projeleri Visual Studio 2017 açılamaz. Bu sınırlamaya geçici bir çözüm için güncelleştirme `MinimumVisualStudioVersion` 12.0 için ve `MinimumOfficeToolsVersion` csproj vbproj dosyasında 12.2 için. |
| Silverlight | Silverlight projeleri Visual Studio 2017 desteklenmiyor. Silverlight uygulamalarını korumak için Visual Studio 2015 kullanmaya devam edin. |
| SQL Server Reporting Services ve SQL Server Analysis Services (SSRS SSDT, SSAS, MSA'lar) | Destek bu proje türleri için sağlanan Visual Studio Galerisi iki uzantıları aracılığıyla: [Microsoft Analysis Services modelleme projeleri](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftAnalysisServicesModelingProjects) ve [Microsoft Reporting Services projeleri](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftReportProjectsforVisualStudio). SSDT desteği Visual Studio 2017 veri depolama ve işlem iş yükü de bulunmaktadır. |
| SQL Server Integration Services (SSIS) | Visual Studio 2017 desteği SQL Server veri Araçları (SSDT) üzerinden kullanılabilir. Daha fazla bilgi için bkz: [SQL Server Integration Services blog](https://blogs.msdn.microsoft.com/ssis/2017/08/23/ssis-designer-is-now-available-for-visual-studio-2017/). |
| Visual C++ | Visual Studio 2010 Visual Studio'ya geri önceki sürümlerinde oluşturulmuş projelerde çalışmak için Visual Studio 2017 kullanabilirsiniz. Proje ilk açtığınızda, en son derleyici ve araç takımı yükseltmek için veya özgün olanları kullanmaya devam etmek için seçeneğiniz vardır. Özgün olanları kullanmaya devam etmek isterseniz, Visual Studio 2017 proje dosyası değiştirmez ve araç takımı önceki Visual Studio yükleme projenizi derleme için kullanır. Özgün seçenekleri anlamına gelir tutma, hala projeyi Visual Studio özgün sürümünde gerekirse açabilirsiniz. Daha fazla bilgi için bkz: [yerel çoklu sürüm desteği eski projeler derlemek için Visual Studio'da kullanın](/cpp/porting/use-native-multi-targeting). |
| Visual Studio genişletilebilirlik/VSIX | Projeleri MinimumVersion 14.0 veya daha az projeyi Visual Studio'nun önceki sürümleri açılmasını engelleyen MinimumVersion 15.0 bildirmek için güncelleştirilmiştir. MinimumVersion önceki sürümlerde açmak bir proje izin vermek için kümesine `$(VisualStudioVersion)`. Ayrıca bkz. [nasıl yapılır: Visual Studio 2017 genişletilebilirlik projeleri geçirmek](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md). |
| Visual Studio Laboratuvar Yönetimi | Microsoft Test Yöneticisi'ni veya Visual Studio 2010 SP1'i kullanabilirsiniz ve daha sonra bu sürümleri hiçbirinde oluşturulan ortamları açın. Ancak, ortamları oluşturabilmeniz için önce Visual Studio 2010 SP1 için Team Foundation Server sürümü Microsoft Test Yöneticisi'nin sürümü eşleşmelidir. |
| Apache Cordova için Visual Studio Araçları | Projeleri Visual Studio 2017 açılabilir, ancak geriye dönük olarak uyumlu değildir. Visual Studio 2015'ten bir proje açıldığında, değişiklikleri projenize izin istenir. Bu değişikliği toolsets yerine kullanmak için proje yükseltmeleri bir `taco.json` Cordova kitaplığı, kendi platformları, kendi eklentileri ve düğüm/npm bağımlılıklarını sürüm yönetmek için dosya. Bkz: [Geçiş Kılavuzu](https://docs.microsoft.com/visualstudio/cross-platform/tools-for-cordova/first-steps/migrate-from-visual-studio-2015) daha fazla bilgi için. |
| Web dağıtımı (wdproj) | Destek Web dağıtımı için projeleri kaldırıldı Visual Studio 2012'de yayımlama profili desteği eklenmesi. Visual Studio 2017 içinde eşdeğeri olduğundan bu tür projeler için otomatik geçiş yol yoktur. Bunun yerine, wdproj dosyasını bir metin düzenleyicisinde açın ve özelleştirmeler içine pubxml kopyala-yapıştır (Yayımlama profili) açıklandığı gibi dosya [StackOverflow](https://stackoverflow.com/a/12061065/1203388). Ayrıca bkz. [planları ile ilgili Web sitesini ve web dağıtım projeleri (MSDN bloglarında)](https://blogs.msdn.microsoft.com/webdev/2012/08/06/plans-regarding-website-projects-and-web-deployment-projects). |
| Windows Communication Foundation, Windows Workflow Foundation | Bu projeyi Visual Studio 2017, Visual Studio 2015, Visual Studio 2013 ve Visual Studio 2012 açabilirsiniz |
| Windows Presentation Foundation | Bu projeyi Visual Studio 2013, Visual Studio 2012 ve Visual Studio 2010 SP1'i açabilirsiniz. |
| Windows mağazası/telefon uygulamaları | Windows mağazası 8.1 ve 8.0 ve Windows Phone 8.1 ve 8.0 projeleri Visual Studio 2017 desteklenmez. Bu uygulamaları korumak için Visual Studio 2015 kullanmaya devam edin. Windows Phone 7.x projelerini korumak için Visual Studio 2012 kullanın. |

## <a name="how-visual-studio-decides-when-to-migrate-a-project"></a>Visual Studio Proje geçirmek ne zaman nasıl karar verir

Her yeni sürümü Visual Studio'nun sağlayacak şekilde aynı proje açılır, değiştirilebilir ve farklı sürümleri arasında yerleşik önceki sürümleriyle uyumluluğunu korumak genellikle arar. Ancak, kaçınılmaz değişiklik yoktur zamanla sağlayacak şekilde bazı proje türleri artık desteklenmiyor olabilir. (Bkz [Platform desteği ve Uyumluluk](/visualstudio/productinfo/vs2017-compatibility-vs) hangi projesi için Visual Studio 2017 içinde türleri desteklenir.) Bu durumlarda, Visual Studio'nun daha yeni bir sürümü proje yüklenmiyor ve bir geçiş yolu sağlamaz; önceki bir sürümünü destekleyen Visual Studio bu projede korumak için gerekir.

Diğer durumlarda, Visual Studio'nun daha yeni sürümünü bir proje açabileceğiniz ancak gerekir güncelleştirmek veya önceki sürümleriyle uyumlu hale getirebilir bir şekilde projesinde geçirme. Visual Studio gibi geçiş gerekli olup olmadığını belirlemek için bir dizi ölçüte kullanır:

- Visual Studio 2013 RTM için geri platformları hedef sürümleriyle uyumluluk.

- Visual Studio'nun önceki sürümleriyle uyumluluğunu tasarım zamanı varlıklar. (Yani farklı kanalları Visual Studio 2017; Visual Studio 2015 RTM ve güncelleştirme 3; Visual Studio 2013 RTM ve güncelleştirme 5; Visual Studio 2012 güncelleştirme 4; Visual Studio 2010 SP 1.) Visual Studio 2017 önceki sürümler proje hala açabilirsiniz, düzgün biçimde kullanım dışı tasarım zamanı varlıklarla bunları bozulmasını olmadan başarısız amaçlar.

- Olup yeni tasarım zamanı varlıklarının Visual Studio 2013 RTM ve güncelleştirme 5 kadar önceki sürümleriyle uyumluluğunu çalışmamasına neden.

Söz konusu proje türü mühendislik sahibi bu ölçütler bakar ve burada desteği, uyumluluk, çağrı yapar ve geçiş açısından. Yeniden, Visual Studio sürümleri arasında saydam uyumluluk Mümkünse, bir anlamı oluşturabilir ve bir sürümünü Visual Studio projelerinde değiştirebilirsiniz ve yalnızca diğer sürümlerde çalışır korumak Visual Studio çalışır.

Bu tür uyumluluk mümkün değilse, ancak olarak bazı bu makalede açıklanan proje türleri ile sonra Visual Studio gerekli tek yönlü değişiklik yapmak için Yükseltme Sihirbazı açılır.

Tek yönlü değişikliğe değiştirilmektedir `ToolsVersion` MSBuild tam olarak hangi sürümü gösterir proje dosyasında özellik sonuçta istediğiniz runnable ve dağıtılabilir yapıları projenin kaynak kodu kapatma. Diğer bir deyişle, hangi proje Visual Studio'nun önceki sürümleri ile uyumsuz işler değil *Visual Studio* sürümü, ancak *MSBuild* tarafından belirlenen Sürüm `ToolsVersion`. Visual Studio sürümünüzle eşleşen MSBuild araç zinciri içerir sürece `ToolsVersion` bir proje ile Visual Studio projesi oluşturmak için bu araç zinciri çağırabilirsiniz.

Eski sürümlerinde oluşturulan projeleri maksimum uyumluluğu korumak için Visual Studio 2017 desteklemek için gerekli MSBuild toolchains içeren `ToolsVersion` 15, 14, 12 ve 4. Aşağıdakilerden herhangi birini kullanan projelerin `ToolsVersion` değerleri başarılı bir yapı içinde neden. (Yeniden, Visual Studio 2017 proje türü hiç açıklandığı gibi destekleyip desteklemediğini için konu [Platform desteği ve Uyumluluk](/visualstudio/productinfo/vs2017-compatibility-vs).)

El ile güncelleştirmek veya yeni bir proje geçirmek denemelisiniz olup olmadığını bu bağlamda soru doğal olarak ortaya `ToolsVersion` değeri. Bu tür bir değişiklik yapmadan gerekli değildir ve büyük olasılıkla çok sayıda hata ve yeniden oluşturmak için proje almak düzeltme gerek uyarılar oluşturur. Ayrıca, Visual Studio için belirli bir destek düşerse `ToolsVersion` gelecekte proje açma proje geçiş işlemi olduğundan, özellikle tetikleyecek `ToolsVersion` değer değiştirilmelidir. Böyle bir durumda, belirli bir proje türü için alt sistem tam olarak ne değiştirilmesi, gereken bilir ve bu değişiklikleri otomatik olarak bu makalenin önceki bölümlerinde açıklandığı gibi yapabilirsiniz.

Daha fazla açıklama için aşağıdaki makalelere bakın:

- [ToolsVersion Kılavuzu](../msbuild/msbuild-toolset-toolsversion.md)
- [Framework hedefleme Kılavuzu](../ide/visual-studio-multi-targeting-overview.md)
