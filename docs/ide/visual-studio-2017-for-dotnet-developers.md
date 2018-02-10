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
ms.openlocfilehash: a834f9781ff51779b2216bd7de9dd3e449c9360a
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="visual-studio-2017-for-net-developers"></a>.NET geliştiricileri için Visual Studio 2017

## <a name="smart-code-editor"></a>Akıllı Kod Düzenleyicisi

[Belgeler: IntelliSense kullanma](using-intellisense.md)  
[Belgeler: Akıllı Düzenleyicisi özellikleri](writing-code-in-the-code-and-text-editor.md)

Visual Studio olan kodunuzu akıllı düzenleme ile sağlamak için .NET ("Roslyn") derleyici aracılığıyla derin bir anlayış söz dizimi renklendirme gibi özellikleri kod tamamlama, yazım denetimi yanlış yazılan değişkenler, önemli olmayan türü çözümlemesi, anahat oluşturma, yapısı görselleştiriciler, [CodeLens](find-code-changes-and-other-history-with-codelens.md), hiyerarşi, vurgulu mümkün hızlı bilgi, parametre Yardım yanı sıra araçları yeniden düzenleme, hızlı eylemlerini uygulama ve kod oluşturma için çağırın.

![Visual Studio akıllı Kod düzenleyicisinde](../ide/media/VSIDE_Productivity_SmartCodeEditor.png "VSIDE_Productivity_SmartCodeEditor")

## <a name="navigate-and-search-your-codebase"></a>Gidin ve temelinizde arama

[Belgeler: kodda gezinme](navigating-code.md)

Dosya, türü, üye veya sembol bildirimiyle atlayarak .NET kodunuzu hızlı bir şekilde gezinmek *tüm Git* kısayol (**Ctrl + T**). .NET dillerde başvuruları dahil olmak üzere, kodunuzda bir simge veya hazır değer tüm başvuruları Bul (**Shift + F12**). Bizim hedeflenen Gezinti komutları ve doğrudan simge tanımlarını atlama yardımcı olması için kullanma (**F12**) veya uygulamaları (**Ctrl + F12**).

![Tüm gidin ve tüm başvuruları Bul](../ide/media/VSIDE_Productivity_Navigation.png "VSIDE_Productivity_Navigation")

## <a name="live-code-analysis-for-code-quality"></a>Kod kalitesini için Canlı kod analizi

[Belgeler: Yapan yeniden düzenlemeler ve hızlı Eylemler](refactoring-code-generation-quick-actions.md)

Visual Studio hataları ve olası sorunlu kod algılayarak kodunuzun kalitesini arttırma yardımcı olması için dinamik kod tanılama sahiptir. Hızlı Eylemler sağladığımız (**Ctrl +.**) belge, proje veya çözüm algılanan sorunları gidermek için. Etkinleştirme *tam çözüm analizini* olanlar yüklü olmasa bile, tüm çözümünüzü arasında sorunları bulmak için düzenleyicide açık dosya sayısı.

Ayrıca, en iyi yöntemleri öğrenin, saplama veya kodu, yeniden düzenleme kod oluşturmak için kodu önerileri kullanın ve yeni dil özellikleri ile benimsemeyi **Ctrl +.** Kısayol.

![Hızlı düzeltmeler ve ampul menüsünü kullanarak yapan yeniden düzenlemeler uygulama](../ide/media/VSIDE_Productivity_CodeAnalysis.png "VSIDE_Productivity_CodeAnalysis")

## <a name="unit-testing"></a>Birim testi

[Belgeler: Visual Studio'da Test birim](../test/improve-code-quality.md)

Mstest'i, NUnit ya da .NET Framework, .NET standart veya .NET Core hedefleme herhangi bir uygulama için çerçeveler test XUnit göre birim testleri hata ayıklama ve çalıştırın. Keşfetmek ve testlerinizde gözden *Test Gezgini* veya kod değişikliklerinden birim testleri düzenleyiciyle içinde nasıl etkiler hemen görmek *Canlı birim testi* (yalnızca Kurumsal SKU için). 

![Birim testi Visual Studio'da canlı](../ide/media/VSIDE_Productivity_LiveUnitTesting.png "VSIDE_Productivity_LiveUnitTesting")

## <a name="code-consistency-and-style"></a>Kod tutarlılık ve stili

[Belgeler: Taşınabilir özel düzenleyici seçenekleri](create-portable-custom-editor-options.md)  
[Belgeleri: .NET EditorConfig kod stili ayarları](editorconfig-code-style-settings-reference.md)

Visual Studio kodlama kuralı yapılandırma sağlar, kodlama stili ihlalleri algılar ve stil sorunları gidermek için hızlı düzeltme sağlayan **Ctrl +.** Kısayol. Yapılandırma ve adlandırma, ekibinizin biçimlendirme zorlamak ve kod stil kuralları bir havuz arasında — değerleri proje ve dosya düzeyinde geçersiz kılma izin vererek — kullanarak *EditorConfig*.

![Yapılandırma ve EditorConfig ile kodlama kurallarını zorunlu](../ide/media/VSIDE_Productivity_CodeStyle.png "VSIDE_Productivity_CodeStyle")

## <a name="debugging"></a>Hata Ayıklama

[Belgeler: Visual Studio'da hata ayıklama](../debugger/index.md)

Visual Studio .NET Framework, .NET standart ve .NET Core hedefleme .NET uygulamalarınızda hata ayıklamak izin veren birinci sınıf bir hata ayıklayıcı içerir. Geçiş ve koşullu kesme noktaları ayarlayın (**F9**), adım yöntemi çağrılarını, LINQ ve lambda ifadeleri değerlendirmek, ayarlama değişken saatlerde, işlemler için yeniden bağlayın, çağrı yığınını incelemek veya bile ilehataayıklamasırasındakodudüzenlemeleriCanlıolun *Düzenle ve devam et*.

Hizmetinizi Azure'da çalışan kullanırsanız *anlık görüntü hata ayıklama* canlı, dağıtılan bulut uygulamalarınızda Visual Studio 2017 Enterprise sorunları tanılamak için.

![Visual Studio'da hata ayıklamayı](../ide/media/VSIDE_Productivity_Debugging.png "VSIDE_Productivity_Debugging")

## <a name="version-control"></a>Sürüm denetimi

[Belgeler: Visual Studio'da sürüm denetimi](/vsts/index)

Git veya TFVC'yi depolamak ve Visual Studio kodunuzda güncelleştirmek için kullanın. Düzenleyicisi'ni içinde Takım Gezgini ile yerel değişiklikler düzenleyebilir ve durum çubuğu bekleyen işlemeleri ve değişiklikleri izlemek için kullanın. Sürekli tümleştirme ve teslimat ile Visual Studio içinde ayarlama bizim [Visual Studio için sürekli teslim Araçları](https://marketplace.visualstudio.com/items?itemName=VSIDEDevOpsMSFT.ContinuousDeliveryToolsforVisualStudio) Çevik Geliştirici iş akışı benimsemeyi uzantısı.

![Kaynak denetimi Visual Studio'da](../ide/media/VSIDE_Productivity_SourceControl.png "VSIDE_Productivity_SourceControl")

## <a name="extensibility"></a>Genişletilebilirlik

[Belgeleri: Visual Studio genişletme](../extensibility/index.md)

Visual Studio yükleme veya gereksinim duyduğunuzda oluşturduğunuz uzantıları zengin ekosistemi vardır. Uzantılar'dan yükleme *uzantı Galerisi* veya *Visual Studio Market'te*, kendi Düzenleyicisi eklentisiyle yapı *VS SDK*, veya kendi Canlı kod Çözümleyicisi oluşturun veya kullanarak yeniden düzenleme *.NET derleyici Platform SDK*. Yükleyerek ek kod düzeltmeler ve öneriler bulabilirsiniz [Microsoft Kod Analizi](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2017) uzantısı.

![Visual Studio uzantı Galerisi](../ide/media/VSIDE_Productivity_Extensibility.png "VSIDE_Productivity_Extensibility")

## <a name="popular-extensions--shortcuts"></a>Popüler uzantıları & kısayolları

Başka bir IDE içinden gelen veya ortam kodlama bu uzantıları faydalı birini yükleme bulabilirsiniz:

- [Emacs öykünmesi](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.EmacsEmulation )
- [Visual Studio (ReSharper/Intellij) için kısayol tuşları](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.HotKeys)
- [VSVim](https://marketplace.visualstudio.com/items?itemName=JaredParMSFT.VsVim)

Popüler Visual Studio kısayolları verilmiştir. Bazı uzantılar varsayılan Visual Studio taşıyan bağlantısını ve komutlarını kullanmak için taşıyan geri unutmayın. Taşıyan Visual Studio'nun ayarlarına geri yüklemek için şu adrese gidin **Araçlar > içeri ve dışarı aktarma ayarları... > tüm ayarlara**.

| Kısayol (tüm profilleri) | Komut | Açıklama |
|-|-|-|
| **Ctrl+T** | Tüm gidin | Herhangi dosya/tür/üye/simgesi bildirimine gidin |
| **F12** (aynı zamanda **Ctrl + Click**) | Tanıma gitme | Bir simge tanımlandığı gidin |
| **Ctrl+F12** | Uygulamasına gidin | Bir temel tür veya üye, çeşitli uygulamaları gidin |
| **Shift+F12** | Tüm Başvuruları Bul | Tüm simge veya değişmez değer başvuruları bakın |
| **Ctrl+.** (Ayrıca **Alt + girin** profilinde C#) | Hızlı Eylemler ve Yeniden Düzenlemeler | Kod oluşturma eylemleri, yapan yeniden düzenlemeler veya diğer hızlı Eylemler imleç konumu veya kod seçimi daha kullanılabilir, hangi kod giderir bakın |
| **Ctrl**+**E**,**V** | Yinelenen satır | İmlecin kod satırı ile yineleme (kullanılabilir **Visual Studio 2017 sürüm 15,6 Önizleme 2** ve üzeri) |
| **Ctrl**+**W** | Seçimi genişletin | Bir Yapısal birim geçerli seçimi genişletir (kullanılabilir **Visual Studio 2017 sürüm 15,5**) |
| **Ctrl**+**Shift**+**W** | Sözleşme seçimi | Sözleşmeleri (azaltır) bir Yapısal birim geçerli seçim (kullanılabilir **Visual Studio 2017 sürüm 15,5**) |
| **Ctrl+Q** | Hızlı Başlat | Arama tüm Visual Studio ayarları |
| **F5** | Hata ayıklama başlatılamıyor | Uygulamanızı hata ayıklamayı Başlat |
| **Ctrl+F5** | Hata ayıklama olmadan çalıştırma | Uygulamanızı yerel olarak hata ayıklama olmadan çalıştırma |
| **CTRL + K, D** (varsayılan profili) veya **Ctrl + E, D** (C# profili) | Belgeyi Biçimlendir | Yeni satır, aralık ve girinti ayarlarını göre dosyanızdaki ihlalleri biçimlendirme temizler |
| **CTRL +\\, E** (varsayılan profili) veya **Ctrl + W, E** (C# profili) | Görünüm hata listesi | Belge, proje veya çözüm tüm hatalar görebilirsiniz |