---
title: Xamarin uygulamalarıyla uygulama yaşam döngüsü yönetimi (ALM) | Microsoft Docs
ms.date: 08/21/2018
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: ff978cc2-5a25-46d6-921b-e51adaa65992
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 0cce9882add1443c2d9187d65b26a25081aac75b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634947"
---
# <a name="devops-with-xamarin-apps"></a>Xamarin uygulamaları ile DevOps

Xamarin Android, iOS ve Windows C#, .NET ve Visual Studio kullanarak hedefleyen platformlar arası mobil uygulamalar oluşturmanıza olanak sağlar. Xamarin platformlarla yalnızca platforma özgü olmalarına gerek küçük bir yüzdesine arasında paylaşılan kod büyük bir kısmı sağlar. Xamarin kendisi hakkında daha fazla bilgi için bkz. [Visual Studio ve Xamarin](../cross-platform/visual-studio-and-xamarin.md).

Modern platformlar için uygulama geliştirme, hemen kod yazmaya daha pek çok daha fazla etkinlik içerir. DevOps (geliştirme + işlem), uygulamanın tam yaşam döngüsü span ve planlama ve izleme çalışması, tasarlama ve uygulama kodu, kaynak kodu deposu, yönetme, çalışan sürekli tümleştirme yönetme dahil olarak başvurulan, bu etkinlikler dağıtımlar, test etme (dahil, birim testleri ve UI testleri) çeşitli türleri Tanılama, hem geliştirme hem de üretim ortamlarında çalışan ve uygulama performansı ve kullanıcı davranışlarını gerçek zamanlı olarak telemetri ve analiz izleme.

Visual Studio Team Services ve Team Foundation Server ile birlikte Visual Studio çeşitli DevOps özellikler sağlar. Bunların çoğu, tamamen platformlar arası projeler için geçerlidir. C# ve .NET araçları bazı hangi DevOps oluşturulmuştur, ile tasarlanmaları nedeniyle bu Xamarin uygulamaları ile özellikle doğrudur. Diğer araçları, derleme ve çalışma zamanı ortamları ile sıkı tümleştirme gerektirir. Xamarin uygulamaları Windows dışı platformlarda çalıştırın ve Mono .NET uygulaması içerdiğinden, Xamarin, belirli özel araçlar gerekir sağlar.

Aşağıdaki tablolarda, iyi bir Xamarin projesi ile çalışması bekleyebilirsiniz Visual Studio'da DevOps özellikleri ve sınırlamaları hangilerinin sahip belirleyin. Özellikleri hakkında daha fazla ayrıntı için bağlantılı belgelerine bakın.

## <a name="agile-tools"></a>Çevik Araçlar

Başvuru bağlantısı:  **[hakkında Çevik araçları ve Çevik proje yönetimi](/vsts/work/backlogs/overview?view=vsts)**

Genel Açıklama: tüm planlama ve izleme özellikleri proje türü ve dilleri kodlama bağımsız olarak çalışır.

|Özellik|Xamarin ile desteklenen|Ek Açıklamalar|
|-------------|----------------------------|-------------------------|
|Kapsamlar ve sprint'ler yönetme|Evet||
|İş izleme|Evet||
|Takım odası işbirliği|Evet||
|Kanban panoları|Evet||
|Rapor ve ilerleme durumunu görselleştirin|Evet||

## <a name="modeling"></a>Modelleme

Başvuru bağlantısı:  **[analiz ve model mimarisi](../modeling/analyze-and-model-your-architecture.md)**

Tasarım özellikleri kodlama dilini bağımsız veya C# .NET dilleri ile çalışır. Bkz: [rolleri mimari ve modelleme diyagramları yazılım geliştirmede](../modeling/scenario-change-your-design-using-visualization-and-modeling.md#ModelingDiagramsTools) hangi yönlerini kodla ilişkili için.

|Özellik|Xamarin ile desteklenen|Ek Açıklamalar|
|-------------|----------------------------|-------------------------|
|Sıralı diyagramlar|Evet||
|Bağımlılık grafikleri|Evet||
|Çağrı hiyerarşisi|Evet||
|Sınıf Tasarımcısı|Evet||
|Mimari Gezgini|Evet||
|UML diyagramlarını (durum, etkinlik, sınıf, bileşen, dizisi ve DSL kullanın)|Evet||
|Katman diyagramları|Evet||
|Katman doğrulama|Evet||

## <a name="code"></a>Kod

|Özellik|Xamarin ile desteklenen|Ek Açıklamalar|
|-------------|----------------------------|-------------------------|
|[Team Foundation sürüm denetimi kullanın](/vsts/tfvc/overview?view=vsts) veya Visual Studio Team Services|Evet||
|[Team Services'da Git ile çalışmaya başlama](/vsts/git/gitquickstart?view=vsts&tabs=visual-studio)|Evet||
|[Kod Kalitesini Geliştirme](../test/improve-code-quality.md)|Evet||
|[Kod değişikliklerini ve diğer geçmişi bulma](../ide/find-code-changes-and-other-history-with-codelens.md)|Evet|Uygulama çalışma zamanına kadar çözülmüş değildir burada platforma özgü sınırları dışında.|
|[Uygulamalarınızda hata ayıklamak için kod haritalarını kullanma](../modeling/use-code-maps-to-debug-your-applications.md)|Evet||

## <a name="build"></a>Derleme

Başvuru bağlantısı:  **[derleme ve yayın](/vsts/pipelines/index?view=vsts)**

|Özellik|Xamarin ile desteklenen|Ek Açıklamalar|
|-------------|----------------------------|-------------------------|
|Şirket içi TFS sunucusu|Evet|Derleme makinesi Xamarin yüklü olması ve iOS için oluşturmak için bir OSX bilgisayara bağlanabilir. Bkz: [TFVC kullanın](/vsts/tfvc/overview?view=vsts)|
|Visual Studio Team Services bağlı şirket içi yapı sunucusu|Evet|Bkz: [derleme ve yayın aracıları](/vsts/pipelines/agents/agents?view=vsts) yönergeler için.|
|Visual Studio Team Services, barındırılan denetleyici hizmeti|Evet|Bkz: [Xamarin uygulamanızı derleyin](/vsts/pipelines/apps/mobile/xamarin?view=vsts&tabs=vsts).|
|Tanımlarla öncesi ve sonrası betikleri oluşturun|Evet||
|Sürekli Tümleştirme dahil olmak üzere Geçitli iade|Evet|TFVC için Geçitli iade yalnızca Git iadeler yerine bir çekme isteği model üzerinde çalışır.|

## <a name="test"></a>Test

|Özellik|Xamarin ile desteklenen|Ek Açıklamalar|
|-------------|----------------------------|-------------------------|
|Testleri planlama, test çalışmaları oluşturma ve test paketlerini düzenleme|Evet||
|El ile test etme|Evet||
|Test Yöneticisi'ni (kayıt ve kayıttan yürütme testleri)|Evet|Windows cihazları ve Android öykünücüleri Visual Studio'dan yalnızca. Tüm cihazlar için kaydı ile mümkündür [Xamarin Test Recorder](/appcenter/test-cloud/uitest/).|
|Kod kapsamı|yok||
|[Birim testi kod](../test/unit-test-your-code.md)|Evet|Windows ve Android hedefleri için yerleşik MSTest Araçlar kullanılabilir. Windows, Android ve iOS üzerinde birim testlerini çalıştırmak için Xamarin NUnit önerir. Bkz: [TFVC kullanan](/vsts/tfvc/overview?view=vsts).|
|[UI otomasyonunu kullanarak kodunuzu test etme](../test/use-ui-automation-to-test-your-code.md)|Yalnızca Windows|Visual Studio'nun kullanıcı Arabirimi Testi Kaydedicisi, yalnızca Windows olur. Tüm platformlar için bkz [Xamarin.UITest](/appcenter/test-cloud/uitest/).|

## <a name="improve-code-quality"></a>Kod kalitesini geliştirme

Başvuru bağlantısı:  **[kod kalitesini iyileştirmek](../test/improve-code-quality.md)**

|Özellik|Xamarin ile desteklenen|Ek Açıklamalar|
|-------------|----------------------------|-------------------------|
|[Yönetilen kod kalitesini analiz etme](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)|Evet||
|[Kod kopyası algılamayı kullanarak yinelenen kodu bulun](http://msdn.microsoft.com/Library/a97cd5a6-5ffa-4104-9627-8e59e513654d)|Evet||
|[Ölçüm karmaşıklığı ve yönetilen kod bakımı](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)|Evet||
|[Performans Gezgini](../profiling/performance-explorer.md)|Hayır|Kullanım [Xamarin Profiler](/xamarin/cross-platform/deploy-test/) Xamarin Studio üzerinden yerine. Xamarin Profiler şu anda önizlemededir ve henüz Windows hedefleri için çalışmaz unutmayın.|
|[.NET Framework bellek sorunlarını çözümleme](https://msdn.microsoft.com/en-us/library/dn342825.aspx)|Hayır|Visual Studio Araçları, profil oluşturma için Mono framework uygulamasına kancaları yoktur.|

## <a name="release-management"></a>Yayın yönetimi

Başvuru bağlantısı:  **[derleme ve yayın VSTS ve TFS](/vsts/pipelines/overview?view=vsts)**

|Özellik|Xamarin ile desteklenen|Ek Açıklamalar|
|-------------|----------------------------|-------------------------|
|Sürüm işlemlerini yönetme|Evet||
|Dağıtım için dışarıdan yükleme betikleri aracılığıyla sunucularına|Evet||
|App Store'a yükle|Kısmi|Kullanılabilir uzantılar bazı uygulama mağazaları için bu işlemi otomatikleştirmek.  Bkz: [için Visual Studio Team Services uzantıları](https://marketplace.visualstudio.com/VSTS); Örneğin, [uzantısı için Google Play](https://marketplace.visualstudio.com/items?itemName=ms-vsclient.google-play).|

## <a name="monitor-with-hockeyapp"></a>HockeyApp ile izleme

Başvuru bağlantısı:  **[HockeyApp ile izleme](https://www.hockeyapp.net/features/)**

|Özellik|Xamarin ile desteklenen|Ek Açıklamalar|
|-------------|----------------------------|-------------------------|
|Kilitlenme analizi, telemetri ve beta dağıtım|Evet||