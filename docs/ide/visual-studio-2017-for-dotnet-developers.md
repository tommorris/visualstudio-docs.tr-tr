---
title: .NET geliştiricileri için Visual Studio 2017 | Microsoft Docs
description: Daha iyi .NET kodu daha hızlı yazmanıza yardım etmek için Visual Studio 2017 özelliklerine genel bakış.
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
ms.openlocfilehash: 78e9245df26a2de747414a91b9024fde9325ef22
ms.sourcegitcommit: 67374acb6d24019a434d96bf705efdab99d335ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="visual-studio-2017-productivity-guide-for-net-developers"></a>.NET geliştiricileri için Visual Studio 2017 üretkenlik Kılavuzu

[Visual Studio 2017](https://www.visualstudio.com/downloads/) geliştiriciler her zamankinden daha verimli hale getirir! Biz, performans ve güvenilirlik çözüm başlangıç ve yük, test bulma ve gecikme yazmak için geliştirilmiş. Ayrıca eklenen artık ve Gelişmiş özellikleri daha iyi bir kod daha hızlı yazmanıza yardımcı olacak. Bu özelliklerden bazıları şunlardır: Gezinti decompiled derlemelerine, değişken adı önerileri siz yazarken, tüm Git Test Gezgini görünümünde hiyerarşi (**Ctrl + T**) dosyası/tür/üye/simgesi bildirimlerine gitmek için bir Akıllı özel durum Yardımcısı, kod stili yapılandırma ve zorlama ve birçok yapan yeniden düzenlemeler ve kod düzeltmeler. 

Üretkenliğinizi en iyi duruma getirmek için bu kılavuzu uygulayın.

##  <a name="im-used-to-my-keyboard-shortcuts-from-a-different-extensioneditoride"></a>Bir farklı uzantısı/Düzenleyicisi/IDE içinden my klavye kısayolları kullanılan istiyorum.

Başka bir IDE içinden gelen veya ortam kodlama bu uzantıları faydalı birini yükleme bulabilirsiniz:

- [Emacs öykünmesi](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.EmacsEmulation)
- [Visual Studio (ReSharper/Intellij) için kısayol tuşları](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.HotKeys)
- [VSVim](https://marketplace.visualstudio.com/items?itemName=JaredParMSFT.VsVim)

![Visual Studio uzantı Galerisi](../ide/media/VSIDE_Productivity_Extensibility.png)

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

## <a name="i-need-a-way-to-quickly-navigate-to-files-or-types"></a>I dosyaları veya türleri için hızlı bir şekilde gitmek için bir yönteme ihtiyacınız vardır.
Visual Studio 2017 adlı bir özelliği olan _tüm Git_ (**Ctrl + T**). Tüm gidin, tüm dosya, türü, üye veya sembol bildirimi hızla atlamak sağlar.
- Bu arama çubuğu konumunu değiştirmek veya 'Canlı Gezinti önizlemeyi' ile Kapat **gear** simgesi
- Bizim sorgu sözdizimini (örneğin, "t mytype") kullanarak sonuçları filtreleyin. Ayrıca, yalnızca geçerli belgede arama kapsamını belirleyebilirsiniz.
- camelCase eşleşen destekleniyor!

![Tüm Visual Studio gidin](../ide/media/VS2017Guide-go-to-all.png)

## <a name="my-team-enforces-code-style-rules-on-our-codebase"></a>Ekibin kod stil kurallarını bizim kod temeli üzerinde zorlar.
Kodlama kuralları kod oluşturma için bir .editorconfig dosyası kullanabilirsiniz. Yüklemenizi öneririz [EditorConfig dil Hizmetleri Uzantısı](https://aka.ms/editorconfig) ekleme ve bir .editorconfig dosyasını düzenlemek için. Kullanıma öneririz [belgelerine](https://aka.ms/editorconfigDocs) kodlama kuralı seçenekleri tüm .NET için.

Kullanıma [bu gist](https://gist.github.com/kuhlenh/5471666a7a2c57fea427e81cf0a41da8) bir örnek .editorconfig için.

![Visual Studio'da kod stili zorlama](../ide/media/VSGuide_CodeStyle.png)

## <a name="i-need-more-refactorings-and-code-fixes"></a>Daha fazla yapan yeniden düzenlemeler ve kod düzeltmeleri ihtiyacım.
Visual Studio 2017 gelen nesil Eylemler ile çok sayıda yapan yeniden düzenlemeler, kod ve kod görebilirsiniz düzeltmeleri bizim [belgelerine](https://aka.ms/refactorings). Kırmızı dalgalı çizgiler hataları temsil eder, yeşil dalgalı çizgiler uyarıları temsil eder ve üç gri nokta kodu önerileri temsil eder.

Ampul/tornavida simgesine tıklayarak veya tuşlarına basarak erişim kodu düzeltmeler yapabilirsiniz **Ctrl +.** veya **Alt + girin**. Her Düzelt bir Canlı kod fark düzeltme nasıl çalıştığını gösteren bir önizleme penceresi ile birlikte gelir.

Bazı yaygın hızlı düzeltmeler ve yapan yeniden düzenlemeler şunlardır: *yeniden adlandırma*, *ayıklama yöntemi*, *değişiklik yöntemi imza*, *oluşturmak Oluşturucusu*, *Üretme yöntemi*, *dosyasına türüne taşımak*, *Null denetimi ekleme*, *parametresini ekleyin*, *Kaldır Gereksiz kullanımları*.

Yapan yeniden düzenlemeler ve kod düzeltmeleri kolayca yazılabilir ile [Roslyn çözümleyiciler](https://github.com/dotnet/roslyn/wiki/Getting-Started-Writing-a-Custom-Analyzer-&-Code-Fix). Birkaç topluluk üyeleri yazmıştır *ücretsiz* kod incelemeleri ek eklenmesi uzantıları: [Roslynator](https://marketplace.visualstudio.com/items?itemName=josefpihrt.Roslynator2017), [Visual Studio için SonarLint](https://marketplace.visualstudio.com/items?itemName=SonarSource.SonarLintforVisualStudio2017), ve [ StyleCopAnalyzers](https://www.nuget.org/packages/stylecop.analyzers/). 

![Visual Studio'da yapan yeniden düzenlemeler](../ide/media/VSGuide_CodeAnalysis.png "VSGuide_CodeAnalysis")

## <a name="i-need-find-usages-go-to-implementation-navigate-to-decompiled-assemblies"></a>Bul kullanımları, uygulama gidin, Decompiled derlemeler gidin almam gerekiyor
Visual Studio 2017 aramak ve tüm başvuruları Bul dahil olmak üzere kod temeliniz--gidin yardımcı olmak üzere birçok özelliklere sahiptir (**Shift + F12**), uygulama gidin (**Ctrl + F12**), Tanıma Git ( **F12** veya **Ctrl + Click**). VS2017 bu özellikler birçok geliştirmeler yaptık, örneğin, tüm başvuruları Bul şimdi renklendirilen ve özel gruplandırma için izin verir. *Decompiled derlemeleri Bul* Tanıma Git üzerinde 15,6 sürümünde eklenmiştir. Bu özelliği etkinleştirmek için şu adrese gidin **Araçlar > Seçenekler > Metin Düzenleyicisi > C# > Gelişmiş > etkinleştirmek Gezinti decompiled kaynaklarına**.

Diğer ortak gezinti araçları içerir: Gözat tanımı (**Alt + F12**), yapısı Görselleştirici (hoverable noktalı satırları ayraçlar arasında), ve [daha fazla](../ide/navigating-code.md).

![Tüm gidin ve tüm başvuruları Bul](../ide/media/VSIDE_Productivity_Navigation.png)

## <a name="i-want-to-run-and-see-my-unit-tests"></a>Çalıştırın ve my birim testleri görmek istiyorum.
Birim Visual Studio 2017 testi için iki teklifleri sunuyoruz: Test Gezgini ve _Canlı birim testi_ (her ikisi de mstest'i v1, v2 mstest'i, NUnit ve XUnit destekler). Biz test bulma (en iyi sonuçlar için test bağdaştırıcınızı en son sürümüne yükseltme) sürüm 15,6 Test Gezgininde hızını büyük ölçüde geliştirilmiş. Biz de hiyerarşik sıralamaya izin vermek için kullanıcı Arabirimi yeniden tasarlanmıştır.

Visual Studio 2017 Enterprise de sahip bir birim olarak adlandırılan özellik testi [Canlı birim testi](../test/live-unit-testing.md). Dinamik birim testi sürekli arka planda çalışır, kod değişiklikten etkilenen testleri çalıştırır ve testlerinizi durumunu size bildirmek için satır içi Düzenleyicisi simgeler güncelleştirir.

![Visual Studio'da metin Gezgini'nde hiyerarşisi görünümü](../ide/media/VSGuide_Testing.png)

## <a name="i-want-to-debug-my-code"></a>Kodum hata ayıklamak istediğiniz.
Visual Studio 2017 bir ton yeni hata ayıklama özelliklerini ekledik. *Çalıştır'ı tıklatın* bir kod satırı yanındaki vurgulu olanak tanır görünür yeşil 'Yürüt' simgesine basın ve bu satırı ulaşana kadar programı çalıştırın. Yeni *özel durum Yardımcısı* en önemli bilgiler, hangi değişkeni gibi üst düzey iletişim kutusunda bir NullReferenceException ' null' geçirir. Ve [geri adım](../debugger/how-to-use-intellitrace-step-back.md) hata ayıklama önceki kesme noktaları veya adımları geri dönün ve geçmişte haliyle uygulama durumunu görüntüleme olanak sağlar.

Azure kaynaklarınız varsa, kullanmak [anlık görüntü hata ayıklama](/azure/application-insights/app-insights-snapshot-debugger) canlı web uygulaması bir özel durum oluşturuldu anda durumunu incelemek için.

![Yeni özel durum Yardımcısı VS2017 içinde](../ide/media/VSGuide_Debugging.png "VSGuide_Debugging")

## <a name="i-want-to-use-version-control-with-my-projects"></a>Sürüm denetimi my projeleri ile kullanmak istediğiniz.
Git veya TFVC'yi depolamak ve Visual Studio kodunuzda güncelleştirmek için kullanabilirsiniz. Düzenleyicisi'ni içinde Takım Gezgini yerel yaptığınız değişikliklerle düzenleyebilir ve durum çubuğu bekleyen işlemeleri ve değişiklikleri izlemek için kullanın. Sürekli tümleştirme ve projelerinizi Visual Studio ile içinde teslime ayarlama bizim [Visual Studio için sürekli teslim Araçları](https://marketplace.visualstudio.com/items?itemName=VSIDEDevOpsMSFT.ContinuousDeliveryToolsforVisualStudio) uzantısı ve Çevik Geliştirici iş akışı benimsemeyi.

![Visual Studio'da kaynak denetimi](../ide/media/VSIDE_Productivity_SourceControl.png)

## <a name="what-other-features-do-i-need-to-know-about"></a>Hakkında bilgi edinmek hangi diğer özellikleri gerekiyor mu?
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
  - **Menü > Düzenle > IntelliSense > tamamlanma modu Değiştir**
- *[CodeLens](../ide/find-code-changes-and-other-history-with-codelens.md)*  kod başvuru bilgileri ve değişiklik geçmişi Düzenleyicisi'nde görüntüler.
  - **Araçlar > Seçenekler > Metin Düzenleyicisi > tüm diller > CodeLens**
- Bizim *kod parçacıkları* ortak Demirbaş (iki kez basın 'Sekmesini') saplama yardımcı olacak. Bkz: [tam listesi](../ide/visual-csharp-code-snippets.md).

![Visual Studio'da kod parçacıkları](../ide/media/VSGuide_SmartEditor.png)

## <a name="missing-a-feature-that-makes-you-productive-or-experiencing-poor-performance"></a>Üretken veya yaşayan düşük performans sağlayan bir özellik eksik mi?
Bize geri bildirim bırakmak için birkaç yolu vardır:
- .NET özellik istekleri Dosyalanan üzerinde bizim [GitHub deposuna](https://github.com/dotnet/roslyn/issues).
- Visual Studio özellik istekleri, hataları ve performans sorunları Dosyalanan kullanarak **geri bildirim gönder** Visual Studio pencerenizin sağ üst simgesine tıklayın.
