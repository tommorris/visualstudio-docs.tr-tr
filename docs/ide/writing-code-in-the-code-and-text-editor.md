---
title: Visual Studio Düzenleyicisi özellikleri kod | Microsoft Docs
ms.custom: ''
ms.date: 02/23/2018
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code, editing [Visual Studio]
- code editor [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a7aacedac2045dcf069ea2d8a0f406d6322d7ca6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="features-of-the-code-editor"></a>Kod Düzenleyicisi özellikleri

Visual Studio düzenleyicisinde yazma ve kod ve metin yönetmek kolaylaştıran birçok özellik sağlar. Genişletebilir ve farklı kod bloklarını anahat oluşturma kullanarak daraltabilirsiniz. IntelliSense, kullanarak kodu hakkında daha fazla bilgiyi **Nesne Tarayıcısı**ve çağrı hiyerarşisi. Kod gibi özellikleri kullanarak bulabileceğiniz **gitmek için**, **Tanıma Git**, ve **tüm başvuruları Bul**. Kod parçacıkları ile kod bloklarını ekleyebilir ve kod gibi özellikleri kullanarak oluşturabileceğiniz **kullanımından Oluştur**. Visual Studio düzenleyicisinde önce hiç kullanmadıysanız bkz [kodunuzu düzenleme](https://www.visualstudio.com/features/ide-vs) hızlı bir genel bakış için.

Kodunuzu çeşitli farklı şekillerde görüntüleyebilirsiniz. Varsayılan olarak, **Çözüm Gezgini** dosyaları tarafından düzenlenen kodunuzu gösterir. Tıklatabilirsiniz **sınıf görünümü** sekmesini kodunuzu görüntülemek için pencerenin altındaki sınıfları tarafından düzenlenir.

Arama ve tek veya birden çok dosya metni değiştirin. Daha fazla bilgi için bkz: [bulma ve değiştirme metnini](../ide/finding-and-replacing-text.md). Metin bulma ve değiştirme için normal ifadeleri kullanma. Daha fazla bilgi için bkz: [Visual Studio'da normal ifadeler kullanarak](../ide/using-regular-expressions-in-visual-studio.md).

Farklı Visual Studio dilleri farklı özellik kümesi sunar ve bazı durumlarda özellikleri farklı dillerde farklı şekilde davranır. Bu farklılıklar çoğunu özelliklerin açıklamaları içinde belirtildi ancak daha fazla bilgi için belirli Visual Studio dillerden bölümleri görebilirsiniz.

## <a name="editor-features"></a>Düzenleyicisi özellikleri

|||
|-|-|
|Sözdizimi renklendirmesi|Kod ve biçimlendirme dosyaların bazı sözdizimi öğeleri, bunları ayırt etmek için farklı renkte görünür. Örneğin, anahtar sözcükler (gibi `using` C# ve `Imports` Visual Basic'te) bir renk ancak türleri (gibi `Console` ve `Uri`) başka bir renk şunlardır. Dize değişmez değerleri ve açıklamaları gibi diğer söz dizimi öğeleri de renklendirilmiştir. C++ renk türleri, numaralandırmalar ve diğer belirteçleri arasında makrolar arasında ayırt etmek için kullanır.<br /><br /> Her tür için varsayılan renk görebilir ve herhangi bir özel sözdizimi öğe rengini değiştirmek [yazı tipleri ve renkler, ortam, Seçenekler iletişim kutusu](../ide/reference/fonts-and-colors-environment-options-dialog-box.md), hangi açabileceğiniz **Araçları** menüsü.|
|Hata ve uyarı işaretleri|Kodu ekleyin ve çözümünüzü gibi (a) farklı renkli dalgalı çizgiler (dalgalı çizgiler da bilinir) veya (b) kodunuzda görünmesini ampuller görebilirsiniz. Sözdizimi hataları kırmızı dalgalı çizgiler belirtmek, mavi derleyici hataları gösterir, uyarıları yeşil gösterir ve başka tür hataları mor gösterir. [Ampuller](../ide/perform-quick-actions-with-light-bulbs.md) sorunlara yönelik düzeltmelerin önermek ve düzeltmeyi uygulamak kolaylaştırır.<br /><br /> Her hata ve uyarı dalgalı varsayılan rengini görebilirsiniz **Araçları** > **seçenekleri** > **ortam**  >   **Yazı tipleri ve renkler** iletişim kutusu. Ara **sözdizimi hatası**, **derleyici hatası**, **uyarı**, ve **diğer hata**.|
|Ayraç eşleştirme|Ekleme noktasını, açık bir kod dosyası ayraç yerleştirildiğinde, onu ve kapanış ayracı vurgulanır. Bu özellik eksik veya yanlış yerleştirilmiş köşeli parantez anında geri bildirim sağlar. Açmak veya kapatmak ile eşleşen ayraç kapatabilirsiniz **otomatik sınırlayıcı vurgulama** ayarı (**Araçları** > **seçenekleri**  >   **Metin düzenleyici**). Vurgu rengi değiştirebilirsiniz **yazı tiplerini ve renkleri** ayarı (**Araçları** > **seçenekleri** > **ortam**). Ara **ayracı (Vurgu) eşleşen** veya **ayracı (dikdörtgen) eşleşen**.|
|Yapı Görselleştirici|Noktalı çizgiler eşleşen ayraç kod dosyaları açma ve kapama parantezi çiftleri görmeyi kolaylaştırır bağlayın. Bu kodda bulmanıza yardımcı olabilir, daha hızlı codebase. Bu satırları açmak veya kapatmak ile kapatabilirsiniz **Göster yapısı yönergeleri** içinde **görüntü** bölümünü **Araçları** > **seçenekleri**  >  **Metin düzenleyici** > **genel** sayfası.|
|Satır numaraları|Satır numaraları kod penceresinin sol kenar boşluğunda görüntülenebilir. Varsayılan olarak görüntülenmez. Bu seçenek de açabilirsiniz **tüm diller metin düzenleyici** ayarları (**Araçları** > **seçenekleri** > **Metin Düzenleyicisi**  >  **Tüm diller**). Bu diller için ayarlarını değiştirerek tek tek programlama dilleri için satır numaralarını görüntüleyebilirsiniz (**Araçları** > **seçenekleri** > **metin düzenleyicisi**   >   **\<dil >**). Satır numaraları yazdırmak, seçmelisiniz **satır numaralarını dahil** içinde **yazdırma** iletişim kutusu.|
|Değişiklik izleme|Sol kenar boşluğu rengi, bir dosyada yapılan değişiklikleri izlemek sağlar. Dosya açıldığında ama kaydedilmedi beri yaptığınız değişiklikleri (Seçim kenar boşluğu da bilinir) sol kenar boşluğu sarı bir çubuğunda gösterilir. Değişiklikleri kaydettikten sonra (ancak dosyayı kapatmadan önce), çubuk yeşil etkinleştirir. Dosyayı kaydettikten sonra bir değişikliği geri almak, çubuğu turuncu etkinleştirir. Bu özellik kapatıp açmak için değiştirme **Değişiklikleri İzle** seçeneğini **metin düzenleyici** ayarları (**Araçları** > **seçenekleri**  >  **Metin düzenleyici**).|
|Kodu ve metni seçme|Standart Sürekli akış modu veya satırlar yerine metin dikdörtgen bir kısmını seçmeniz kutusunu modda metni seçebilirsiniz. Fare seçimi sürükleyin kutusunu modunda seçim yapmak için ALT tuşuna basın (veya ALT + SHIFT tuşlarına basın + \<ok tuşu >). Seçim ilk karakter ve son karakter seçimdeki tarafından tanımlanan dikdörtgenin içindeki karakterleri içerir. Yazılan veya seçili alanına yapıştırılan her şey, her satırda bir aynı noktada eklenir.|
|Yakınlaştır|Tuşuna basarak ve CTRL tuşunu basılı tutarak ve fare kaydırma tekerleği taşıma herhangi bir kod pencerede giriş veya çıkış yakınlaştırabilirsiniz (veya CTRL + SHIFT +. artırma ve CTRL + SHIFT +, azaltmak için). Kod penceresinin sol alt köşesinde yakınlaştırma kutusuna, belirli yakınlaştırma oranını ayarlamak için de kullanabilirsiniz. Yakınlaştırma özelliği, aracı windows çalışmaz.|
|Sanal alan|Böylece bir satır sonunda sağ ok tuşu imleci sonraki satırın başlangıcına taşır. varsayılan olarak, Visual Studio düzenleyicileri satırlarında son karakter sonra sonlandırın. Diğer bazı düzenleyicilerde sonra son karakter bir satır bitmez ve imleci satırında herhangi bir yere yerleştirebilirsiniz. Düzenleyicide sanal alanda etkinleştirebilirsiniz **Araçları** > **seçenekleri** > **metin düzenleyici** > **tüm Dilleri** ayarlar. Ya da etkinleştirebilirsiniz Not **sanal adres alanı** veya **Kaydır**, ancak ikisini birden değil.|
|Yazdırma|Seçeneklerinde kullanabilirsiniz **yazdırma** satır numaralarını dahil etmek veya gizlemek için iletişim kutusu daraltılmış bölge kodu bir dosya yazdırma. İçinde **sayfa yapısı** iletişim kutusu, ayrıca seçebilirsiniz tam yolunu ve dosya adını seçerek yazdırmak **sayfa üstbilgisi**.<br /><br /> Renk yazdırma seçeneklerini ayarlayabilirsiniz **Araçları** > **seçenekleri** > **ortam** > **yazı tipleri ve Renkleri** iletişim kutusu. Seçin **yazıcı** içinde **ayarlarını göster** renk yazdırma özelleştirmek için liste. Bir dosyayı düzenlemek için bir dosyadan daha yazdırma için farklı renkleri belirtebilirsiniz.|
|Genel Geri Al ve Yinele|**Geri son genel eylemi** ve **son genel eylemi yinele** komutlarını **Düzenle** menü geri veya birden çok dosya etkileyen genel eylemi yinele. Bir sınıf veya ad alanı, bir veritabanı ya da birden çok dosya değişiklikleri herhangi bir eylemde yeniden düzenleme bir çözüm bulma ve değiştirme işlemi gerçekleştirilirken yeniden adlandırma genel Eylemler içerir. Genel Geri Al uygulamak ve bir eylem uygulanan çözüm kapatsanız bile geçerli Visual Studio oturumunda, komutları eylemler için yineleyebilirsiniz.|

## <a name="advanced-editing-features"></a>Gelişmiş düzenleme özellikleri

Gelişmiş Özellikler sayısı bulabilirsiniz **Düzenle** > **Gelişmiş** araç çubuğundaki menüsü. Bu özelliklerin tümü tüm kod dosyaları türleri için kullanılabilir.

|||
|-|-|
|Belgeyi Biçimlendir|Kod satırlarını uygun girinti ayarlar ve belgedeki satırlarını ayırmak için süslü ayraçlar taşır.|
|Biçim Seçimi|Kod satırlarını uygun girinti ayarlar ve seçimdeki satırlarını ayırmak için süslü ayraçlar taşır.|
|Seçili satırları Sekmelere ayırma|Uygun olan yerlerde sekmelere öndeki boşlukları değiştirir.|
|Seçili satırları untabify|Sekmeleri öndeki boşlukları değiştirir. Sekme (veya alanları için tüm sekmeler) dosyanızdaki tüm alanları dönüştürmek istiyorsanız, kullanabileceğiniz `Edit.ConvertSpacesToTabs` ve `Edit.ConvertTabsToSpaces` komutları. Bu komutlar, Visual Studio menülerde görünmez, ancak bunları hızlı erişim penceresinden veya komut penceresinden çağırabilirsiniz.|
|Büyük Harf Yap|Tüm karakterleri büyük harfe için seçimdeki değiştirir veya herhangi bir seçim ise, büyük harfe ekleme noktasını karakterinde değiştirir.|
|Küçük Harf Yap|Tüm karakterleri küçük harfe için seçimdeki değiştirir veya herhangi bir seçim varsa, ekleme noktasını karakteri küçük harfe dönüştürür.|
|Seçili satırları Yukarı Taşı|Seçilen satırın bir satır yukarı taşır. Kısayol: ALT + YUKARI OK.|
|Seçili satırları Aşağı Taşı|Seçili satır bir satır aşağı taşır. Kısayol: ALT + AŞAĞI OK.|
|Yatay boşluk Sil|Sekme veya boşluk geçerli satırın sonundaki siler.|
|Görünüm beyaz alan|Yükseltilmiş noktalar ve sekmelerle oklarla alanları görüntüler. Dosya sonuna bir dikdörtgen karakteri görüntülenir. Varsa **Araçları** > **seçenekleri** > **metin düzenleyici** > **tüm diller**  >  **Kaydır** > **Göster sözcük kaydırma için görünür karakterlerinin** olduğunu belirlenirse, bu karakter de görüntülenir.|
|Sözcük kaydırma|Tüm satırları kodu pencerede görünmesi için bir belge neden olur. Sözcük kaydırma metin düzenleyici tüm diller ayarlarında kapatıp kapatabilirsiniz (**Araçları** > **seçenekleri** > **metin düzenleyici**  >  **Tüm diller**).|
|Açıklama Seçimi|Açıklama karakterleri seçimi veya geçerli satır ekler.|
|Seçim açıklamadan çıkarın|Seçim ya da geçerli satır yorum karakterleri kaldırır.|
|Satır Girintisini Artır|Sekme (veya eşdeğer alanları) seçili satırları veya geçerli satır ekler.|
|Satır Girintiyi|Sekme (veya eşdeğer alanları) seçili satırları veya geçerli satırı kaldırır.|
|Etiket seçin|Etiketler (örneğin, XML veya HTML) içeren bir belgede etiket seçer.|
|Etiket içeriğini seçin|Etiketler (örneğin, XML veya HTML) içeren bir belgedeki içeriği seçer.|

## <a name="navigate-and-find-code"></a>Gidin ve kod Bul

Kod düzenleyicisinde birkaç geriye doğru gezinme dahil olmak üzere, farklı şekillerde ve ileten önceki ekleme noktaları için bir tür veya üye tanımını görüntüleme ve gezinti çubuğunu kullanarak belirli bir yönteme atlama taşıyabilirsiniz. Daha fazla bilgi için bkz: [kodda gezinme](navigating-code.md).

## <a name="finding-references-in-your-code-base"></a>Kod temeliniz içinde başvurular bulma

Belirli kod öğeleri temelinizde Burada başvurulan bulmak için kullanabileceğiniz **tüm başvuruları Bul** komutu. Ayrıca, tıkladığınızda bir tür veya üye, **başvuru vurgulama** özelliği otomatik olarak bu tür veya üye yapılan tüm başvuruları vurgular. Daha fazla bilgi için bkz: [başvuruları kodunuzda bulma](finding-references.md).

## <a name="customize-the-editor"></a>Düzenleyiciyi özelleştirme

Visual Studio ayarlarınızı ile başka bir geliştirici paylaşmak, ayarlarınız bir standardına uygun ya da kullanarak Visual Studio varsayılan ayarlara dönmek **içeri ve dışarı aktarım ayarları Sihirbazı** komutunu  **Araçlar** menüsü. İçinde **içeri ve dışarı aktarım ayarları Sihirbazı**, seçilen genel veya dil ve projeye özgü ayarlarını değiştirebilirsiniz.

Yeni kısayollarıyla tanımlamak ya da varolan kısayollarıyla yeniden tanımlamak için şu adrese gidin **Araçları** > **seçenekleri** > **ortam**  >  **Klavye**. Kısayol tuşları hakkında daha fazla bilgi için bkz: [varsayılan klavye kısayolları](../ide/default-keyboard-shortcuts-in-visual-studio.md).

Düzenleyiciyi özelleştirme hakkında daha fazla bilgi için bkz: [düzenleyiciyi özelleştirme](../ide/customizing-the-editor.md). JavaScript özgü Düzenleyici seçenekleri için bkz: [JavaScript Düzenleyicisi Seçenekleri](../ide/reference/options-text-editor-javascript-formatting.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio IDE](../ide/visual-studio-ide.md)
- [Visual Studio'da C++ kullanmaya başlama](../ide/quickstart-cpp.md)
- [C# ve Visual Studio'da ASP.NET kullanmaya başlama](../ide/tutorial-csharp-aspnet-core.md)
- [Visual Studio'da Python kullanmaya başlama](../ide/quickstart-python.md)
