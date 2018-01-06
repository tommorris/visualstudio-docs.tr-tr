---
title: "Xamarin uygulamalarıyla uygulama yaşam döngüsü yönetimi (ALM) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff978cc2-5a25-46d6-921b-e51adaa65992
caps.latest.revision: "14"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: xamarin
ms.openlocfilehash: f744bd9535a4946570267de027e7096b41d274e7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="application-lifecycle-management-alm-with-xamarin-apps"></a>Xamarin uygulamalarıyla uygulama yaşam döngüsü yönetimi (ALM)
Xamarin Android, iOS ve C#, .NET ve Visual Studio kullanarak Windows hedefleme platformlar arası mobil uygulamalar oluşturmanıza olanak sağlar. Xamarin platformlarıyla yalnızca platforma özgü olmasını gerektiren küçük bir yüzdesi arasında paylaşılmak üzere kod büyük bir kısmı sağlar. Xamarin kendisi hakkında daha fazla bilgi için bkz: [Visual Studio ve Xamarin](../cross-platform/visual-studio-and-xamarin.md).  
  
 Modern platformlar için uygulama geliştirme yeni kod yazma daha pek çok daha fazla etkinlik içerir. DevOps (geliştirme + işlemleri), uygulamanın tam yaşam döngüsü span ve planlama ve iş izleme, tasarlama ve uygulama kodu, bir kaynak kod deposu yönetme derlemeleri, çalışan sürekli tümleştirmeler yönetme dahil olarak başvurulan bu etkinlikler dağıtımlar, test (dahil, birim testleri ve UI testleri) tanılama çeşitli biçimlerde hem geliştirme hem de üretim ortamlarında çalışan ve uygulama performansı ve kullanıcı davranışlarını telemetri ve analiz ile gerçek zamanlı izleme.  
  
 Visual Studio Team Services ve Team Foundation Server ile birlikte Visual Studio uygulama yaşam döngüsü yönetimi veya ALM da bilinir DevOps özellikleri, çeşitli sağlar. Bunların çoğu, tamamen platformlar arası projeler için geçerlidir.  
  
 C# ve hangi bazı ALM araçları oluşturulmuş .NET ile oluşturulur çünkü Xamarin uygulamaları ile özellikle geçerlidir. Diğer araçları derleme ve çalışma zamanı ortamları ile sıkı tümleştirme gerektirir. Xamarin uygulamaları olmayan Windows platformlarında çalışan ve .NET Mono uyarlamasını kullandığından, Xamarin özel araçlar belirli gereken sağlar.  
  
 Aşağıdaki tablolarda tanımlayan hangi Visual Studio ALM özellikleri iyi bir Xamarin projeniz iş beklediğiniz ve hangilerinin sınırlamaları vardır. Özellikleri hakkında ayrıntılı bilgi için bağlantılı belgelerine bakın.  
  
## <a name="agile-tools"></a>Çevik Araçlar  
 Başvuru bağlantısı:  **[iş](http://msdn.microsoft.com/Library/52aa8bc9-fc7e-4fae-9946-2ab255ca7503)**  (Visual Studio Team Services veya TFS Takım Gezgini her yerde dahil olmak üzere, kullanarak)  
  
 Genel Açıklama: tüm planlama ve izleme özellikleri proje türüne ve dilleri kodlama bağımsızdır.  
  
|Özellik|Xamarin ile desteklenen|Ek Açıklamalar|  
|-------------|----------------------------|-------------------------|  
|Biriktirme listelerini ve sprint yönetme|Evet||  
|İş izleme|Evet||  
|Takım odası işbirliği|Evet||  
|Kanban Panosu|Evet||  
|Rapor ve ilerlemeyi Görselleştirme|Evet||  
  
## <a name="modeling"></a>Modelleme  
 Başvuru bağlantısı:  **[çözümleme ve modelleme mimarisi](../modeling/analyze-and-model-your-architecture.md)**  
  
 Tasarım özellikleri dil kodlama bağımsız veya C# .NET dilleri ile çalışır. Bkz: [rol mimarisi ve modelleme diyagramları yazılım geliştirme](../modeling/scenario-change-your-design-using-visualization-and-modeling.md#ModelingDiagramsTools) hangi yönlerini koduyla ilgili için.  
  
|Özellik|Xamarin ile desteklenen|Ek Açıklamalar|  
|-------------|----------------------------|-------------------------|  
|Sıralı diyagramlar|Evet||  
|Bağımlılık grafikleri|Evet||  
|Çağrı hiyerarşisi|Evet||  
|Sınıf Tasarımcısı|Evet||  
|Mimari Gezgini|Evet||  
|UML diyagramları (çalışması, etkinlik, sınıf, bileşen, dizisi ve DSL kullanın)|Evet||  
|Katman diyagramları|Evet||  
|Katman doğrulaması|Evet||  
  
## <a name="code"></a>Kod  
  
|Özellik|Xamarin ile desteklenen|Ek Açıklamalar|  
|-------------|----------------------------|-------------------------|  
|[Team Foundation sürüm denetimini kullanma](http://msdn.microsoft.com/Library/1d629052-c65d-4c5d-81eb-eaa4413fe285) veya Visual Studio Team Services|Evet||  
|[Git Team Services ile çalışmaya başlama](http://msdn.microsoft.com/Library/32f46ecd-1b03-4ef0-a9c4-8a120da2b03f)|Evet||  
|[Kod Kalitesini Geliştirme](/visualstudio/test/improve-code-quality)|Evet||  
|[Kod değişikliklerini ve diğer geçmişi bulma](../ide/find-code-changes-and-other-history-with-codelens.md)|Evet|Uygulama çalışma zamanına kadar çözülmüş değil burada platforma özgü sınırları dışında.|  
|[Uygulamalarınızda hata ayıklamak için kod haritalarını kullanma](../modeling/use-code-maps-to-debug-your-applications.md)|Evet||  
  
## <a name="build"></a>Derleme  
 Başvuru bağlantısı:  **[derleme](http://msdn.microsoft.com/Library/a971b0f9-7c28-479d-a37b-8fd7e27ef692)**  
  
|Özellik|Xamarin ile desteklenen|Ek Açıklamalar|  
|-------------|----------------------------|-------------------------|  
|Şirket içi TFS sunucusu|Evet|Yapı makineleri Xamarin yüklü olması gerekir ve iOS için yapı için bir OSX bilgisayara bağlanır. Bkz: [yapılandırma TFS xamarin](http://developer.xamarin.com/guides/cross-platform/ci/configuring_tfs/) (Xamarin Web sitesi)|  
|Visual Studio Team Services bağlantılı sunucu şirket içi derleme|Evet|Bkz: [yapı sunucu](http://msdn.microsoft.com/Library/2d258a0a-f178-4e93-9da1-eba61151af3c) yönergeler için.|  
|Visual Studio Team Services barındırılan denetleyicisi hizmeti|Evet|Bkz: [Xamarin uygulamanızı derleyin](https://www.visualstudio.com/en-us/docs/build/apps/mobile/xamarin).|  
|Yapı tanımlarla öncesi ve sonrası betikleri|Evet||  
|Sürekli tümleştirme de dahil olmak üzere iadeler geçişli|Evet|Yalnızca Git iadeler yerine bir çekme isteği modeli çalışırken iadeler TFVC'yi için geçişli.|  
  
## <a name="testing"></a>Sınama  
 Başvuru bağlantısı:  **[uygulamayı test etme](/devops-test-docs/test/test-apps-early-and-often)**  
  
|Özellik|Xamarin ile desteklenen|Ek Açıklamalar|  
|-------------|----------------------------|-------------------------|  
|Test paketleri testleri planlama, test çalışmaları oluşturma ve düzenleme|Evet||  
|El ile test etme|Evet||  
|Test Yöneticisi'ni (kaydı ve kayıttan yürütme testleri)|Evet|Windows cihazlar ve yalnızca Visual Studio'dan Android öykünücüsünü. Tüm aygıtlar için kayıt ile olası [Xamarin Testi Kaydedicisi](https://www.xamarin.com/test-cloud/recorder).|  
|Kod kapsamı|yok||  
|[Kodunuza Birim Testi Uygulama](../test/unit-test-your-code.md)|Evet|Windows ve Android hedefleri için yerleşik mstest'i Araçlar kullanılabilir. Windows, Android ve iOS üzerinde birim testleri çalıştırmak için Xamarin NUnit önerir. Bkz: [yapılandırma TFS xamarin](http://developer.xamarin.com/guides/cross-platform/ci/configuring_tfs/) (Xamarin Web sitesi).|  
|[Kodunuzu Test Etmek için UI Otomasyonunu Kullanma](../test/use-ui-automation-to-test-your-code.md)|Yalnızca Windows|Visual Studio'nun UI Testi Kaydedicisi Windows Only'dir. Tüm platformlar için bkz: [Xamarin Testi Kaydedicisi](https://www.xamarin.com/test-cloud/recorder).|  
  
## <a name="improve-code-quality"></a>Kod kalitesini geliştirme  
 Başvuru bağlantısı:  **[kod kalitesini geliştirmek](/visualstudio/test/improve-code-quality)**  
  
|Özellik|Xamarin ile desteklenen|Ek Açıklamalar|  
|-------------|----------------------------|-------------------------|  
|[Yönetilen kod kalitesini analiz etme](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)|Evet||  
|[Kod kopyası algılamayı kullanarak yinelenen kodları bulma](http://msdn.microsoft.com/Library/a97cd5a6-5ffa-4104-9627-8e59e513654d)|Evet||  
|[Yönetilen Kodun Ölçüm Karmaşıklığı ve Bakımı](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)|Evet||  
|[Performans Gezgini](../profiling/performance-explorer.md)|Hayır|Kullanım [Xamarin profil oluşturucu](http://developer.xamarin.com/guides/cross-platform/deployment,_testing,_and_metrics/) Xamarin Studio aracılığıyla yerine. Xamarin profil oluşturucu şu anda önizlemede değil ve henüz Windows hedefler için çalışmaz unutmayın.|  
|[.NET Framework bellek sorunlarını çözümleme](https://msdn.microsoft.com/en-us/library/dn342825.aspx)|Hayır|Visual Studio Araçları kancaları profil oluşturma için Mono framework uygulamasına sahip değilsiniz.|  
  
## <a name="release-management"></a>Yayın yönetimi  
 Başvuru bağlantısı:  **[yayın yönetimi ile dağıtımları otomatikleştirme](https://msdn.microsoft.com/library/vs/alm/release/overview)**  
  
|Özellik|Xamarin ile desteklenen|Ek Açıklamalar|  
|-------------|----------------------------|-------------------------|  
|Yayın işlemlerini yönetme|Evet||  
|Dağıtım için dışarıdan yükleme komut dosyaları aracılığıyla sunucularına|Evet||  
|Uygulama deposuna karşıya yükleme|Kısmi|Uzantıları mevcut bazı uygulama depoları için bu işlemi otomatikleştirmek.  Bkz: [Visual Studio Team Services uzantıları](https://marketplace.visualstudio.com/VSTS); Örneğin, [Google Play için uzantı](https://marketplace.visualstudio.com/items?itemName=ms-vsclient.google-play).|  
  
## <a name="monitor-with-hockeyapp"></a>HockeyApp izleme  
 Başvuru bağlantısı:  **[HockeyApp izlemesi](https://www.hockeyapp.net/features/)**  
  
|Özellik|Xamarin ile desteklenen|Ek Açıklamalar|  
|-------------|----------------------------|-------------------------|  
|Kilitlenme analizi, telemetri ve beta dağılımı|Evet||