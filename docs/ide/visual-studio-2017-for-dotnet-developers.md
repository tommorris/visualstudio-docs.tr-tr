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
ms.openlocfilehash: 2dac5f48f69ce00ae914929638f08cf35f5a96ac
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2018
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
Kodlama kuralları kod oluşturma ve bunları kaynağınız ile seyahat sağlamak için bir .editorconfig dosyasını kullanabilirsiniz.
- Yüklemenizi öneririz [EditorConfig dil Hizmetleri Uzantısı](https://aka.ms/editorconfig) eklemek ve Visual Studio .editorconfig dosyasında düzenlemek için. 
- Kullanıma [belgelerine](https://aka.ms/editorconfigDocs) kodlama kuralı seçenekleri tüm .NET için.
- Bkz: [bu gist](https://gist.github.com/kuhlenh/5471666a7a2c57fea427e81cf0a41da8) bir örnek .editorconfig için.

![Visual Studio'da kod stili zorlama](../ide/media/VSGuide_CodeStyle.png)

## <a name="i-need-more-refactorings-and-code-fixes"></a>Daha fazla yapan yeniden düzenlemeler ve kod düzeltmeleri ihtiyacım.
Visual Studio 2017 nesil Eylemler ile çok sayıda yapan yeniden düzenlemeler, kod ve düzeltmeleri kod gelir. Kırmızı dalgalı çizgiler hataları temsil eder, yeşil dalgalı çizgiler uyarıları temsil eder ve üç gri nokta kodu önerileri temsil eder. Ampul/tornavida simgesine tıklayarak veya tuşlarına basarak erişim kodu düzeltmeler yapabilirsiniz **Ctrl +.** veya **Alt + girin**. Her Düzelt bir Canlı kod fark düzeltme nasıl çalıştığını gösteren bir önizleme penceresi ile birlikte gelir.

- Popüler hızlı düzeltmeler ve yapan yeniden düzenlemeler şunları içerir: 
  - *Yeniden Adlandır*
  - *Ayıklama Yöntemi*
  - *Metot İmzasını Değiştirme* 
  - *Oluşturucu Oluşturma*
  - *Üretme Metodu*
  - *Dosyaya taşıma türü*
  - *Null denetimi ekleme*
  - *Add Parameter*
  - *Gereksiz kullanımları kaldırma*
  - Daha fazla bilgi için bkz: bizim [belgeleri](https://aka.ms/refactorings)
- Kendi yeniden düzenleme veya kod düzeltme yazma [Roslyn çözümleyiciler](https://github.com/dotnet/roslyn/wiki/Getting-Started-Writing-a-Custom-Analyzer-&-Code-Fix). 
- Birkaç topluluk üyeleri yazmıştır *ücretsiz* kod incelemeleri ek eklenmesi uzantıları: 
  - [Roslynator](https://marketplace.visualstudio.com/items?itemName=josefpihrt.Roslynator2017)
  - [Visual Studio için SonarLint](https://marketplace.visualstudio.com/items?itemName=SonarSource.SonarLintforVisualStudio2017)
  - [StyleCopAnalyzers](https://www.nuget.org/packages/stylecop.analyzers/)

![Visual Studio'da yapan yeniden düzenlemeler](../ide/media/VSGuide_CodeAnalysis.png "VSGuide_CodeAnalysis")

## <a name="i-need-find-usages-go-to-implementation-navigate-to-decompiled-assemblies"></a>Bul kullanımları, uygulama gidin, Decompiled derlemeler gidin almam gerekiyor
Visual Studio 2017 temelinizde gezinti ve arama size yardımcı olmak için çok sayıda özelliğe sahiptir. Daha fazla bilgi edinin [Gezinti özellikleri kod](../ide/navigating-code.md)

| Özellik | Kısayol | Ayrıntılar/geliştirmeleri |
|- | - | -| 
| Tüm Başvuruları Bul | **Shift+F12**| Sonuçları renklendirilmiştir ve gruplandırılabilir proje, tanımı, vb. tarafından. Ayrıca 'sonuçları kilitleyebilir'. |
| Uygulamasına gidin | **Ctrl+F12** | Tanıma Git kullanabileceğiniz `override` geçersiz kılınan üye gitmek için anahtar sözcüğü |
| Tanıma gitme | **F12** veya **Ctrl + tıklatın**| Basılı tutabilirsiniz **Ctrl** navgiate tanımına tıklarken | 
| Özet tanımı | **Alt+F12** | Satır içi görünüm tanımı |
| Yapı Görselleştirici | Gri, noktalı satırları ayraçlar arasında | Kod yapısını görmek için getirin |
| Decompiled derlemeler gezinme | **F12** veya **Ctrl + tıklatın** | Özelliği etkinleştirerek dış kaynak (ILSpy ile decompiled) gidin: **Araçlar > Seçenekler > Metin Düzenleyicisi > C# > Gelişmiş > etkinleştirmek Gezinti decompiled kaynaklarına**. |

![Tüm gidin ve tüm başvuruları Bul](../ide/media/VSIDE_Productivity_Navigation.png)

## <a name="i-want-to-run-and-see-my-unit-tests"></a>Çalıştırın ve my birim testleri görmek istiyorum.
Biz Visual Studio 2017 test deneyimi geliştirmeleri çok yapılan. Kullanım bizim birim testi deneyimleri mstest'i v1, v2 mstest'i, NUnit veya XUnit birini çerçeveleri sınayın.
- *Explorer test* test saptama, hızlı sürümünde 15,6 (en iyi sonuçlar için test bağdaştırıcınızı en son sürümüne yükseltme).
- Test Gezgini testlerinizde bizim yeni ile düzenleme *hiyerarşik sıralama* sürümünde 15,6.
- [Birim testi canlı](../test/live-unit-testing.md) sürekli, kod değişikliklerinden etkilenen testleri çalıştırır ve testlerinizi durumunu size bildirmek için satır içi Düzenleyicisi simgeler güncelleştirir. Eklemek veya belirli sınamalar hariç tutma veya test projelerden, *Canlı Test kümesi*.

![Visual Studio'da metin Gezgini'nde hiyerarşisi görünümü](../ide/media/VSGuide_Testing.png)

## <a name="i-want-to-debug-my-code"></a>Kodum hata ayıklamak istediğiniz.
Visual Studio 2017 bir ton yeni hata ayıklama özelliklerini ekledik. 
- *Çalıştır'ı tıklatın* bir kod satırı yanındaki vurgulu olanak tanır görünür yeşil 'Yürüt' simgesine basın ve bu satırı ulaşana kadar programı çalıştırın. 
- Yeni *özel durum Yardımcısı* en önemli bilgiler, hangi değişkeni gibi üst düzey iletişim kutusunda bir NullReferenceException ' null' geçirir.
- [Adım arka](../debugger/how-to-use-intellitrace-step-back.md) hata ayıklama önceki kesme noktaları veya adımları geri dönün ve geçmişte haliyle uygulama durumunu görüntüleme olanak sağlar.
- [Hata ayıklama anlık görüntü](/azure/application-insights/app-insights-snapshot-debugger) canlı web uygulamasının bir özel durum oluşturuldu anda durumu araştırmanıza olanak tanır (Azure üzerinde olmalıdır).

![Yeni özel durum Yardımcısı VS2017 içinde](../ide/media/VSGuide_Debugging.png "VSGuide_Debugging")

## <a name="i-want-to-use-version-control-with-my-projects"></a>Sürüm denetimi my projeleri ile kullanmak istediğiniz.
Git veya TFVC'yi depolamak ve Visual Studio kodunuzda güncelleştirmek için kullanabilirsiniz. 
- Yerel yaptığınız değişikliklerle düzenlemek *Takım Gezgini* ve durum çubuğu bekleyen işlemeleri ve değişiklikleri izlemek için kullanın. 
- Sürekli tümleştirme ve projelerinizi Visual Studio ile içinde teslime ayarlama bizim [Visual Studio için sürekli teslim Araçları](https://marketplace.visualstudio.com/items?itemName=VSIDEDevOpsMSFT.ContinuousDeliveryToolsforVisualStudio) uzantısı ve Çevik Geliştirici iş akışı benimsemeyi.

![Visual Studio'da kaynak denetimi](../ide/media/VSIDE_Productivity_SourceControl.png)

## <a name="what-other-features-do-i-need-to-know-about"></a>Hakkında bilgi edinmek hangi diğer özellikleri gerekiyor mu?
Kod yazma daha verimli hale getirmek için Düzenleyicisi ve üretkenlik özelliklerin bir listesi aşağıda verilmiştir. Bazı özellikler-(bunlar makinenizde şeyler dizin, tartışmalı veya şu anda Deneysel) varsayılan olarak kapalı olduğundan etkinleştirilmesi gerekebilir.

| Özellik | Ayrıntılar | Etkinleştirme |
|-|-|-|
| Çözüm Gezgini'nde dosyasını bulun | Çözüm Gezgini'nde etkin dosya vurgular | **Araçlar > Seçenekler > Projeler ve çözümler > izlemek Çözüm Gezgini'nde etkin öğesi** |
| Kullanımları türleri başvuru derlemeleri ve NuGet paketleri ekleme | Ampul başvurulmayan türü için NuGet paketini yüklemek için bir kod düzeltmeyle gösterir | **Araçları > Seçenekler > Metin Düzenleyicisi > C# > Gelişmiş > başvuru derlemeleri türlerinde kullanımları önermek** ve **NuGet paketlerini türlerinde kullanımları öneririz** |
| Tam çözüm analizini etkinleştir | Hata listesi çözümünüzdeki tüm hatalar görebilirsiniz | **Araçlar > Seçenekler > Metin Düzenleyicisi > C# > Gelişmiş > tam çözüm analizini etkinleştir** |
| Gezinti decompiled kaynaklarına etkinleştir | Tanıma Git türleri üyesi dış kaynaklardan ver ve yöntem gövdeleri göstermek için ILSpy decompiler kullanın | **Araçlar > Seçenekler > Metin Düzenleyicisi > C# > Gelişmiş > decompiled kaynaklarına Gezinti etkinleştir** |
| Tamamlama/öneri modu | IntelliSense--Intellij arka planlar geliştiricilere tamamlama davranış eğilimindedir ayarını değiştirmek için değişiklikleri varsayılan burada | **Menü > Düzenle > IntelliSense > tamamlanma modu Değiştir** |
| [CodeLens](../ide/find-code-changes-and-other-history-with-codelens.md) | Başvuru bilgileri kod ve değişiklik geçmişi düzenleyicisinde görüntüler | **Araçlar > Seçenekler > Metin Düzenleyicisi > tüm diller > CodeLens** |
| [Kod parçacıkları](../ide/visual-csharp-code-snippets.md) | Genel Demirbaş saplama Yardım |  Kod parçacığında adını yazın ve 'Sekme' iki kez basın. |

![Visual Studio'da kod parçacıkları](../ide/media/VSGuide_SmartEditor.png)

## <a name="missing-a-feature-that-makes-you-productive-or-experiencing-poor-performance"></a>Üretken veya yaşayan düşük performans sağlayan bir özellik eksik mi?
Bize geri bildirim bırakmak için birkaç yolu vardır:
- .NET özellik istekleri Dosyalanan üzerinde bizim [GitHub deposuna](https://github.com/dotnet/roslyn/issues).
- Visual Studio özellik istekleri, hataları ve performans sorunları Dosyalanan kullanarak **geri bildirim gönder** Visual Studio pencerenizin sağ üst simgesine tıklayın.
