---
title: ".NET geliştiricileri için Visual Studio 2017 | Microsoft Docs"
description: "Daha iyi .NET kodu daha hızlı yazmanıza yardım etmek için Visual Studio 2017 özelliklerine genel bakış."
author: kuhlenh
ms.author: kaseyu
manager: ghogen
ms.technology: vs-ide-general
ms.date: 01/16/2018
ms.topic: article
helpviewer_keywords:
- editor
ms.workload:
- dotnet
ms.openlocfilehash: 7e910c50682d45d209d993cb883ca01d1ea436f2
ms.sourcegitcommit: 236c250bb97abdab99d00c6525d106fc0035d7d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2018
---
# <a name="visual-studio-2017-productivity-guide-for-net-developers"></a>.NET geliştiricileri için Visual Studio 2017 üretkenlik Kılavuzu

- [Üretkenlik Kılavuzu](#guide)
- [Visual Studio 2017 genel bakış](#overview)

## <a name="a-idguide-productivity-guide"></a><a id="guide"/> Üretkenlik Kılavuzu
[Visual Studio 2017](https://www.visualstudio.com/downloads/) geliştiriciler her zamankinden daha verimli hale getirir! Biz, performans ve güvenilirlik çözüm başlangıç ve yük, test bulma ve gecikme yazmak için geliştirilmiş. Ayrıca eklenen artık ve Gelişmiş özellikleri daha iyi bir kod daha hızlı yazmanıza yardımcı olacak. Bu özelliklerden bazıları şunlardır: Gezinti decompiled derlemelerine, değişken adı önerileri siz yazarken, tüm Git Test Gezgini görünümünde hiyerarşi (**Ctrl + T**) dosyası/tür/üye/simgesi bildirimlerine gitmek için bir Akıllı özel durum Yardımcısı, kod stili yapılandırma ve zorlama ve birçok yapan yeniden düzenlemeler ve kod düzeltmeler. 

Üretkenliğinizi en iyi duruma getirmek için bu kılavuzu uygulayın.

###  <a name="im-used-to-my-keyboard-shortcuts-from-a-different-extensioneditoride"></a>Bir farklı uzantısı/Düzenleyicisi/IDE içinden my klavye kısayolları kullanılan istiyorum.

Başka bir IDE içinden gelen veya ortam kodlama bu uzantıları faydalı birini yükleme bulabilirsiniz:

- [Emacs öykünmesi](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.EmacsEmulation)
- [Visual Studio (ReSharper/Intellij) için kısayol tuşları](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.HotKeys)
- [VSVim](https://marketplace.visualstudio.com/items?itemName=JaredParMSFT.VsVim)

Popüler Visual Studio kısayolları verilmiştir. 

> [!NOTE]
> Aşağıdaki komutları kullanarak geri yüklemeniz gerekir böylece bazı uzantılar varsayılan Visual Studio taşıyan bağlantı kesme. Taşıyan giderek Visual Studio'nun ayarlarına geri yüklemek: **Araçlar > içeri ve dışarı aktarma ayarları... > tüm ayarlara** veya **Araçlar > Seçenekler > klavye > sıfırlama**.

| Kısayol (tüm profilleri) | Komut | Açıklama |
|-|-|-|
| **Ctrl+T** | Tüm gidin | Herhangi dosya/tür/üye/simgesi bildirimine gidin |
| **F12** (aynı zamanda **Ctrl + Click**) | Tanıma gitme | Bir simge tanımlandığı gidin |
| **Ctrl+F12** | Uygulamasına gidin | Bir temel tür veya üye, çeşitli uygulamaları gidin |
| **Shift+F12** | Tüm Başvuruları Bul | Tüm simge veya değişmez değer başvuruları bakın |
| **Ctrl**+**.** (Ayrıca **Alt + girin** profilinde C#) | Hızlı Eylemler ve Yeniden Düzenlemeler | Kod oluşturma eylemleri, yapan yeniden düzenlemeler veya diğer hızlı Eylemler imleç konumu veya kod seçimi daha kullanılabilir, hangi kod giderir bakın |
| **Ctrl**+**D** | Yinelenen satır | İmlecin kod satırı ile yineleme (kullanılabilir **Visual Studio 2017 sürüm 15,6** ve üzeri) |
| **Shift**+**Alt**+**+**/**-** | Seçimi genişletin/sözleşme | Genişletir veya Düzenleyicisi'nde geçerli seçim sözleşmeleri (kullanılabilir **Visual Studio 2017 sürüm 15,5** ve üzeri) |
| **Ctrl+Q** | Hızlı Başlat | Arama tüm Visual Studio ayarları |
| **F5** | Hata ayıklama başlatılamıyor | Uygulamanızı hata ayıklamayı Başlat |
| **Ctrl+F5** | Hata ayıklama olmadan çalıştırma | Uygulamanızı yerel olarak hata ayıklama olmadan çalıştırma |
| **CTRL + K, D** (varsayılan profili) veya **Ctrl + E, D** (C# profili) | Belgeyi Biçimlendir | Yeni satır, aralık ve girinti ayarlarını göre dosyanızdaki ihlalleri biçimlendirme temizler |
| **CTRL +\\, E** (varsayılan profili) veya **Ctrl + W, E** (C# profili) | Görünüm hata listesi | Belge, proje veya çözüm tüm hatalar görebilirsiniz |

### <a name="i-need-a-way-to-quickly-navigate-to-files-or-types"></a>I dosyaları veya türleri için hızlı bir şekilde gitmek için bir yönteme ihtiyacınız vardır.
Visual Studio 2017 adlı bir özelliği olan _tüm Git_ (**Ctrl + T**). Tüm gidin, tüm dosya, türü, üye veya sembol bildirimi hızla atlamak sağlar.
- Bu arama çubuğu konumunu değiştirmek veya 'Canlı Gezinti önizlemeyi' ile Kapat **gear** simgesi
- Bizim sorgu sözdizimini (örneğin, "t mytype") kullanarak sonuçları filtreleyin. Ayrıca, yalnızca geçerli belgede arama kapsamını belirleyebilirsiniz.
- camelCase eşleşen destekleniyor!

![Visual Studio'da tüm gidin](../ide/media/VS2017Guide-go-to-all.png "tüm için VS2017Guide Git")

### <a name="my-team-enforces-code-style-rules-on-our-codebase"></a>Ekibin kod stil kurallarını bizim kod temeli üzerinde zorlar.
Kodlama kuralları kod oluşturma için bir .editorconfig dosyası kullanabilirsiniz. Yüklemenizi öneririz [EditorConfig dil Hizmetleri Uzantısı](https://aka.ms/editorconfig) ekleme ve bir .editorconfig dosyasını düzenlemek için. Kullanıma öneririz [belgelerine](https://aka.ms/editorconfigDocs) kodlama kuralı seçenekleri tüm .NET için.

Out Chck [bu gist](https://gist.github.com/kuhlenh/5471666a7a2c57fea427e81cf0a41da8) bir örnek .editorconfig için.

![Stil zorlama Visual Studio'da kod](../ide/media/VS2017Guide-code-style.png "VS2017Guide kod stili")

### <a name="i-need-more-refactorings-and-code-fixes"></a>Daha fazla yapan yeniden düzenlemeler ve kod düzeltmeleri ihtiyacım.
Visual Studio 2017 gelen nesil Eylemler ile çok sayıda yapan yeniden düzenlemeler, kod ve kod görebilirsiniz düzeltmeleri bizim [belgelerine](https://aka.ms/refactorings). Kırmızı dalgalı çizgiler hataları temsil eder, yeşil dalgalı çizgiler uyarıları temsil eder ve üç gri nokta kodu önerileri temsil eder.

Ampul/tornavida simgesine tıklayarak veya tuşlarına basarak erişim kodu düzeltmeler yapabilirsiniz **Ctrl +.** veya **Alt + girin**. Her Düzelt bir Canlı kod fark düzeltme nasıl çalıştığını gösteren bir önizleme penceresi ile birlikte gelir.

Bazı yaygın hızlı düzeltmeler ve yapan yeniden düzenlemeler şunlardır:, ayıklama yöntemi, değişiklik yöntem imzası, Oluşturucusu oluşturur, yöntem oluşturma, taşıma türü dosyasına eklemek Null-onay, parametre, gereksiz kullanımları kaldırma ekleme yeniden adlandırın.

Yapan yeniden düzenlemeler ve kod düzeltmeleri kolayca yazılabilir ile [Roslyn çözümleyiciler](https://github.com/dotnet/roslyn/wiki/Getting-Started-Writing-a-Custom-Analyzer-&-Code-Fix). Birkaç topluluk üyeleri yazmıştır *ücretsiz* kod incelemeleri ek eklemek uzantıları: Roslynator ve Visual Studio için SonarLint. 

![Visual Studio'da yapan yeniden düzenlemeler](../ide/media/VS2017Guide-refactoring.png "VS2017Guide yeniden düzenleme")

### <a name="i-need-find-usages-go-to-implementation-navigate-to-decompiled-assemblies"></a>Bul kullanımları, uygulama gidin, Decompiled derlemeler gidin almam gerekiyor
Visual Studio 2017 aramak ve tüm başvuruları Bul dahil olmak üzere kod temeliniz--gidin yardımcı olmak üzere birçok özelliklere sahiptir (**Shift + F12**), uygulama gidin (**Ctrl + F12**), Tanıma Git ( **F12** veya **Ctrl + Click**). Decompiled derlemeleri Bul 15,6 sürümünde eklenmiştir. Bu özelliği etkinleştirmek için şu adrese gidin **Araçlar > Seçenekler > Metin Düzenleyicisi > C# > Gelişmiş > etkinleştirmek Gezinti decompiled kaynaklarına**.

![Visual Studio'da decompiled kaynakları gidin](../ide/media/VS2017Guide-navigate-to-source.png "VS2017Guide gidin-için-kaynak")

### <a name="i-want-to-run-and-see-my-unit-tests"></a>Çalıştırın ve my birim testleri görmek istiyorum.
Birim Visual Studio 2017 testi için iki teklifleri sunuyoruz: Test Gezgini ve _Canlı birim testi_. Biz sürüm 15,6 Test Gezgininde test bulma hızını büyük ölçüde geliştirilmiş. Biz de hiyerarşik sıralamaya izin vermek için kullanıcı Arabirimi yeniden tasarlanmıştır.

Visual Studio de olan bir birim olarak adlandırılan özellik testi [Canlı birim testi](/test/live-unit-testing). Dinamik birim testi sürekli arka planda çalışır, kod değişiklikten etkilenen testleri çalıştırır ve testlerinizi durumunu size bildirmek için satır içi Düzenleyicisi simgeler güncelleştirir.

![Visual Studio'da metin Gezgini'nde hiyerarşisi görünümü](../ide/media/VS2017Guide-hiearchy-test-explorer.png "VS2017Guide hiearchy test Gezgini")

### <a name="what-other-features-do-i-need-to-know-about"></a>Hakkında bilgi edinmek hangi diğer özellikleri gerekiyor mu?
Kod yazma daha verimli hale getirmek için Düzenleyicisi ve üretkenlik özelliklerin bir listesi aşağıda verilmiştir. Bazı özellikler-(bunlar makinenizde şeyler dizin, tartışmalı veya şu anda Deneysel) varsayılan olarak kapalı olduğundan etkinleştirilmesi gerekebilir.
- *Çözüm Gezgini'nde dosyasını bulun* Solution Explorer'da etkin dosya vurgular.
  - **Araçlar > Seçenekler > Projeler ve çözümler > izlemek Çözüm Gezgini'nde etkin öğesi**
- *Kullanımları türleri başvuru derlemeleri ve NuGet paketleri ekleme* başvurulmayan türü için NuGet paketini yüklemek için bir kod düzeltmeyle ampul gösterir.
  - **Araçları > Seçenekler > Metin Düzenleyicisi > C# > Gelişmiş > başvuru derlemeleri türlerinde kullanımları önermek** ve **NuGet paketlerini türlerinde kullanımları öneririz**
- *Tam çözüm analizini etkinleştir* hata listesinde çözümünüzdeki tüm hataları görmek için.
  - **Araçlar > Seçenekler > Metin Düzenleyicisi > C# > Gelişmiş > tam çözüm analizini etkinleştir**
- *Gezinti decompiled kaynaklarına etkinleştir* Tanıma Git türleri üyesi dış kaynaklardan etkinleştirmek ve ILSpy decompiler yöntem gövdeleri göstermek için kullanın.
  - **Araçlar > Seçenekler > Metin Düzenleyicisi > C# > Gelişmiş > decompiled kaynaklarına Gezinti etkinleştir**
- *Tamamlama/öneri modu* IntelliSense içinde tamamlama davranışını değiştirir. Intellij arka planlar geliştiricilere eğilimindedir ayarını değiştirmek için varsayılan burada.
  - **Menü > Düzenle > IntelliSense tamamlanma moduna geç ->**
- Bizim *kod parçacıkları* ortak Demirbaş (iki kez basın 'Sekmesini') saplama yardımcı olacak. Bkz: [tam listesi](/ide/visual-csharp-code-snippets).

![Kod parçacıkları Visual Studio'da](../ide/media/VS2017Guide-code-snippet.png "VS2017Guide kod parçacığını")

### <a name="missing-a-feature-that-makes-you-productive-or-experiencing-poor-performance"></a>Üretken veya yaşayan düşük performans sağlayan bir özellik eksik mi?
Bize geri bildirim bırakmak için birkaç yolu vardır:
- .NET özellik istekleri Dosyalanan üzerinde bizim [GitHub deposuna](https://github.com/dotnet/roslyn/issues).
- Visual Studio özellik istekleri, hataları ve performans sorunları Dosyalanan kullanarak **geri bildirim gönder** Visual Studio pencerenizin simgesine tıklayın.


## <a name="a-idoverview-overview-of-visual-studio-2017-for-net-developers"></a><a id="overview"/> .NET geliştiricileri için Visual Studio 2017 genel bakış

### <a name="smart-code-editor"></a>Akıllı Kod Düzenleyicisi

- [Belgeler: IntelliSense kullanma](using-intellisense.md)
- [Belgeler: Akıllı Düzenleyicisi özellikleri](writing-code-in-the-code-and-text-editor.md)

Visual Studio olan kodunuzu akıllı düzenleme ile sağlamak için .NET ("Roslyn") derleyici aracılığıyla derin bir anlayış söz dizimi renklendirme gibi özellikleri kod tamamlama, yazım denetimi yanlış yazılan değişkenler, önemli olmayan türü çözümlemesi, anahat oluşturma, yapısı görselleştiriciler, [CodeLens](find-code-changes-and-other-history-with-codelens.md), hiyerarşi, vurgulu mümkün hızlı bilgi, parametre Yardım yanı sıra araçları yeniden düzenleme, hızlı eylemlerini uygulama ve kod oluşturma için çağırın.

![Visual Studio akıllı Kod düzenleyicisinde](../ide/media/VSIDE_Productivity_SmartCodeEditor.png "VSIDE_Productivity_SmartCodeEditor")

### <a name="navigate-and-search-your-codebase"></a>Gidin ve temelinizde arama

[Belgeler: kodda gezinme](navigating-code.md)

Dosya, türü, üye veya sembol bildirimiyle atlayarak .NET kodunuzu hızlı bir şekilde gezinmek *tüm Git* kısayol (**Ctrl + T**). .NET dillerde başvuruları dahil olmak üzere, kodunuzda bir simge veya hazır değer tüm başvuruları Bul (**Shift + F12**). Bizim hedeflenen Gezinti komutları ve doğrudan simge tanımlarını atlama yardımcı olması için kullanma (**F12**) veya uygulamaları (**Ctrl + F12**).

![Tüm gidin ve tüm başvuruları Bul](../ide/media/VSIDE_Productivity_Navigation.png "VSIDE_Productivity_Navigation")

### <a name="live-code-analysis-for-code-quality"></a>Kod kalitesini için Canlı kod analizi

[Belgeler: Yapan yeniden düzenlemeler ve hızlı Eylemler](refactoring-code-generation-quick-actions.md)

Visual Studio hataları ve olası sorunlu kod algılayarak kodunuzun kalitesini arttırma yardımcı olması için dinamik kod tanılama sahiptir. Hızlı Eylemler sağladığımız (**Ctrl**+**.**) belge, proje veya çözüm algılanan sorunları gidermek için. Etkinleştirme *tam çözüm analizini* olanlar yüklü olmasa bile, tüm çözümünüzü arasında sorunları bulmak için düzenleyicide açık dosya sayısı.

Ayrıca, en iyi yöntemleri öğrenin, saplama veya kodu, yeniden düzenleme kod oluşturmak için kodu önerileri kullanın ve yeni dil özellikleri ile benimsemeyi **Ctrl**+**.** Kısayol.

![Hızlı düzeltmeler ve ampul menüsünü kullanarak yapan yeniden düzenlemeler uygulama](../ide/media/VSIDE_Productivity_CodeAnalysis.png "VSIDE_Productivity_CodeAnalysis")

### <a name="unit-testing"></a>Birim testi

[Belgeler: Visual Studio'da Test birim](../test/improve-code-quality.md)

Mstest'i, NUnit ya da .NET Framework, .NET standart veya .NET Core hedefleme herhangi bir uygulama için çerçeveler test XUnit göre birim testleri hata ayıklama ve çalıştırın. Keşfetmek ve testlerinizde gözden *Test Gezgini* veya kod değişikliklerinden birim testleri düzenleyiciyle içinde nasıl etkiler hemen görmek *Canlı birim testi* (yalnızca Kurumsal SKU için).

![Birim testi Visual Studio'da canlı](../ide/media/VSIDE_Productivity_LiveUnitTesting.png "VSIDE_Productivity_LiveUnitTesting")

### <a name="code-consistency-and-style"></a>Kod tutarlılık ve stili

- [Belgeler: Taşınabilir özel düzenleyici seçenekleri](create-portable-custom-editor-options.md)
- [Belgeleri: .NET EditorConfig kod stili ayarları](editorconfig-code-style-settings-reference.md)

Visual Studio kodlama kuralı yapılandırma sağlar, kodlama stili ihlalleri algılar ve stil sorunları gidermek için hızlı düzeltme sağlayan **Ctrl**+**.** Kısayol. Yapılandırma ve adlandırma, ekibinizin biçimlendirme zorlamak ve kod stil kuralları bir havuz arasında — değerleri proje ve dosya düzeyinde geçersiz kılma izin vererek — kullanarak *EditorConfig*.

![Yapılandırma ve EditorConfig ile kodlama kurallarını zorunlu](../ide/media/VSIDE_Productivity_CodeStyle.png "VSIDE_Productivity_CodeStyle")

### <a name="debugging"></a>Hata Ayıklama

[Belgeler: Visual Studio'da hata ayıklama](../debugger/index.md)

Visual Studio .NET Framework, .NET standart ve .NET Core hedefleme .NET uygulamalarınızda hata ayıklamak izin veren birinci sınıf bir hata ayıklayıcı içerir. Geçiş ve koşullu kesme noktaları ayarlayın (**F9**), adım yöntemi çağrılarını, LINQ ve lambda ifadeleri değerlendirmek, ayarlama değişken saatlerde, işlemler için yeniden bağlayın, çağrı yığınını incelemek veya bile ilehataayıklamasırasındakodudüzenlemeleriCanlıolun *Düzenle ve devam et*.

Hizmetinizi Azure'da çalışan kullanırsanız *anlık görüntü hata ayıklama* canlı, dağıtılan bulut uygulamalarınızda Visual Studio 2017 Enterprise sorunları tanılamak için.

![Visual Studio'da hata ayıklamayı](../ide/media/VSIDE_Productivity_Debugging.png "VSIDE_Productivity_Debugging")

### <a name="version-control"></a>Sürüm denetimi

[Belgeler: Visual Studio'da sürüm denetimi](/vsts/index)

Git veya TFVC'yi depolamak ve Visual Studio kodunuzda güncelleştirmek için kullanın. Düzenleyicisi'ni içinde Takım Gezgini ile yerel değişiklikler düzenleyebilir ve durum çubuğu bekleyen işlemeleri ve değişiklikleri izlemek için kullanın. Sürekli tümleştirme ve teslimat ile Visual Studio içinde ayarlama bizim [Visual Studio için sürekli teslim Araçları](https://marketplace.visualstudio.com/items?itemName=VSIDEDevOpsMSFT.ContinuousDeliveryToolsforVisualStudio) Çevik Geliştirici iş akışı benimsemeyi uzantısı.

![Kaynak denetimi Visual Studio'da](../ide/media/VSIDE_Productivity_SourceControl.png "VSIDE_Productivity_SourceControl")

### <a name="extensibility"></a>Genişletilebilirlik

[Belgeleri: Visual Studio genişletme](../extensibility/index.md)

Visual Studio yükleme veya gereksinim duyduğunuzda oluşturduğunuz uzantıları zengin ekosistemi vardır. Uzantılar'dan yükleme *uzantı Galerisi* veya *Visual Studio Market'te*, kendi Düzenleyicisi eklentisiyle yapı *VS SDK*, veya kendi Canlı kod Çözümleyicisi oluşturun veya kullanarak yeniden düzenleme *.NET derleyici Platform SDK*. Yükleyerek ek kod düzeltmeler ve öneriler bulabilirsiniz [Microsoft Kod Analizi](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2017) uzantısı.

![Visual Studio uzantı Galerisi](../ide/media/VSIDE_Productivity_Extensibility.png "VSIDE_Productivity_Extensibility")
