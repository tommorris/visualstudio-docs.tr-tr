---
title: "Visual Studio'da Python kodu düzenleme | Microsoft Docs"
description: "Visual Studio'da düzenleme Python IntelliSense kod parçacıkları ve biçimlendirme, linting ve yeniden düzenleme yanında Gezinti özellikleri sağlar."
ms.custom: 
ms.date: 02/15/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: e1e592d6fdb8fd7deb1e702513a932297a60e6ac
ms.sourcegitcommit: c0a2385a16cc4f47d2e1ff23d35c4da40f5605e0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="editing-python-code"></a>Python kodu düzenleme

Geliştiriciler harcadığı zaman Kod düzenleyicisinde çoğunu şekilde [Python desteği Visual Studio'da](installing-python-support-in-visual-studio.md) daha üretken olmanıza yardımcı olmak için işlevsellik sağlar. IntelliSense sözdizimi vurgulama, otomatik tamamlama, imza Yardım, yöntemi geçersiz kılmalar, arama ve gezinti özellikleri içerir.

Düzenleyici ayrıca kod iki arasında exchange kolaylaşır Visual Studio etkileşimli penceresinde tümleşiktir. Bkz: [Öğreticisi Adım 3: etkileşimli REPL penceresini kullanarak](tutorial-working-with-python-in-visual-studio-step-03-interactive-repl.md) ve [etkileşimli bir pencere - etkileşimli komut gönderme kodu kullanarak](python-interactive-repl-in-visual-studio.md#send-code-to-interactive-command) Ayrıntılar için.

|   |   |
|---|---|
| ![video kamera simgesine film](../install/media/video-icon.png "bir videoyu izleyin") | [(Microsoft Virtual Academy) bir video izlemek](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Editing-Python-Code-r2iQH5LWE_4605918567) Python kodu (2 m 30s) düzenleme tanıtımı için.|

Visual Studio'da kod düzenleme genel belgeler için bkz: [kod ve Metin Düzenleyici'de kod yazma](../ide/writing-code-in-the-code-and-text-editor.md). Ayrıca bkz. [Visual Studio'da anahat oluşturma](../ide/outlining.md), kodunuzu belirli bölümlerini odaklanmış olmanıza yardımcı olur.

Visual Studio nesne tarayıcısı da kullanabilirsiniz (**Görünüm > Diğer Pencereler > Nesne Tarayıcısı** veya Ctrl + W, J) her modülünde tanımlandığı Python sınıfları ve bu sınıfların tanımlanan işlevler İnceleme için.

## <a name="intellisense"></a>IntelliSense

IntelliSense sağlar [tamamlamalar](#completions), [imza Yardım](#signature-help), [hızlı bilgi](#quick-info), ve [kod renklendirme](#code-coloring). Performansı artırmak için IntelliSense projenizdeki her Python ortamı için oluşturulan tamamlama veritabanı bağlıdır. Veritabanları ekleyin, kaldırın veya güncelleştirme paketleri yenileme gerekebilir. Veritabanı durumu görüntülenir **Python ortamları** penceresinde (Çözüm Gezgini eşdüzey) **IntelliSense** sekmesinde (bkz [Python ortamları penceresi başvuru](python-environments-window-tab-reference.md#intellisense-tab)).

### <a name="completions"></a>Tamamlamalar

Deyimler, tanımlayıcılarını ve uygun şekilde Düzenleyicisi'nde geçerli konumda girilebilir diğer sözcükleri olarak tamamlamalar görünür. Listede gösterilen bağlamına dayalı ve hatalı veya dikkat dağıtıcı seçenekleri atlamak için filtrelenir. Tamamlamalar, farklı deyimleri yazarak genellikle tetiklenir (gibi `import`) ve işleçler (bir süre dahil), ancak olabilir bunları istediğiniz zaman Ctrl-J, alan yazarak görünür.

![Üye tamamlama](media/code-editing-completions-simple.png)

Tamamlanma listesi açık olduğunda, fare ok tuşlarını kullanarak istediğiniz tamamlanması için veya yazmaya devam etmek göre arama yapabilirsiniz. Daha fazla harf yazarken, listenin daha büyük bir olasılıkla tamamlamalar göstermek için filtrelenir. Kısayollar gibi de kullanabilirsiniz:

- 'Argparse' bulmak için 'ayrıştırma' gibi adının başında olmayan harf yazarak
- 'As_integer_ratio' bulmak için 'AbstractBaseClass' veya 'hava' bulmak için 'abc' gibi sözcükleri başlangıcında olan harf yazarak
- 'Base64' bulmak için 'b64' gibi harf atlanıyor

Bazı örnekler:

![Filtreleme ile üye tamamlama](media/code-editing-completion-filtering.png)

Bir süre sonra bir değişken veya değer yöntemleri ve öznitelikleri olası türlerinin yanı sıra yazarken üye tamamlamalar otomatik olarak görüntülenir. Bir değişkeni birden fazla tür olabilir, listeyi her tamamlama hangi türlerini destekleyen belirtmek için ek bilgilerle tüm türlerinden tüm olasılıklarını içerir. Bir tamamlanma tüm olası türleri tarafından destekleniyorsa, ek açıklama gösterilir.

![Birden çok tür üye tamamlanma](media/code-editing-completion-types.png)

Varsayılan olarak, "dunder" üyeleri (başlangıç ve bitiş çift çizgiyle üyeleri) gösterilmez. Genel olarak, bu tür üyeler doğrudan erişim. Bir ihtiyacınız varsa, ancak baştaki çift alt çizgi yazarak bu tamamlamalar listeye ekler:

![Özel üye tamamlama](media/code-editing-completion-dunder.png)

`import` Ve `from ... import` ifadeler alınabilir modüllerin listesini görüntüler. İle `from ... import`, belirtilen modülünden içe aktarılması üyeleri listesi içerir.

![İçeri aktarma tamamlama](media/code-editing-completion-import.png)

`raise` Ve `except` ifadeler sınıfları hata türleri büyük olasılıkla listesini görüntüler. Listenin tüm kullanıcı tanımlı özel durumları içermiyor olabilir, ancak uygun yerleşik özel durumları hızlı bir şekilde bulmanıza yardımcı olur:

![Özel durum tamamlama](media/code-editing-completion-exception.png)

Yazma bir oluşturma öğesi başlatır ve olası dekoratörler gösterir. Bu öğeler çoğunu dekoratörler kullanılabilir değil; kullanılacak belirlemek için kitaplık belgelerine bakın.

![Oluşturma öğesi tamamlama](media/code-editing-completion-decorator.png)

> [!Tip]
> Tamamlamalar davranışını yapılandırabilirsiniz **Araçlar > Seçenekler > Metin Düzenleyicisi > Python > Gelişmiş "**. Bunlar arasında **filtresi listesi, arama dizesi esas**: yazarken tamamlama önerileri filtrelerini uygular (varsayılan işaretli), ve **üye tamamlama görüntüler üyeleri kesişimi** yalnızca gösterir (varsayılan olarak işaretli değildir) tüm olası türleri tarafından desteklenen tamamlamalar. Bkz: [seçenekleri - tamamlama sonuçları](python-support-options-and-settings-in-visual-studio.md#completion-results).

### <a name="signature-help"></a>İmza Yardım

Açılış yazdığınızda işlevi çağıran kodu yazarken, imza Yardım görünür `(` ve kullanılabilir belgeleri ve parametre bilgilerini görüntüler. Ctrl + Shift + alanıyla işlev çağrısı içinde görünmesini de yapabilirsiniz. Görüntülenen bilgiler işlevin kaynak kodundaki belge dizelerde bağlıdır, ancak herhangi bir varsayılan değeri içerir.

![İmza Yardım](media/code-editing-signature-help.png)

> [!Tip]
> İmza Yardım devre dışı bırakmak için şu adrese gidin **Araçlar > Seçenekler > Metin Düzenleyicisi > Python > Genel** ve temizleyin **deyim tamamlama > parametre bilgilerini**.

### <a name="quick-info"></a>Hızlı bilgi

Fare işaretçisini tanımlayıcıyı gelerek veya onları hızlı bilgi araç ipucu olarak görüntülenir. Tanımlayıcı, bağlı olarak hızlı bilgi olası değerlerini görüntüleyebilir veya türleri ve tanımı konumlar dönüş türleri, tüm kullanılabilir belgelere:

![Hızlı Bilgi](media/code-editing-quick-info.png)

### <a name="code-coloring"></a>Kod renklendirme

Kod renklendirme renkleri değişkenleri, ifadeler ve kodunuzu diğer bölümleri için Kod Analizi dosyasındaki bilgileri kullanır. Örneğin, modüller ya da sınıfları değişkenleri işlevleri veya diğer değerleri daha farklı bir renkte gösterilebilir ve yerel veya genel değişkenleri daha farklı bir renk parametre adları görüntülenir. (Varsayılan olarak, işlevleri kalın olarak gösterilmez):

![Kod renklendirme](media/code-editing-code-coloring.png)

Renkleri özelleştirmek için şu adrese gidin **Araçlar > Seçenekler > ortamı > yazı tiplerini ve renkleri** ve Python girdileri değiştirme **öğeleri görüntülemek** listesi:

![Yazı tipleri ve renkler seçenekleri](media/code-editing-customize-colors.png)

> [!Tip]
> Kodu renklendirme devre dışı bırakmak için şu adrese gidin **Araçlar > Seçenekler > Metin Düzenleyicisi > Python > Gelişmiş** ve temizleyin **çeşitli seçenekleri > Renk türüne göre adları**. Bkz: [seçenekleri - çeşitli seçenekleri](python-support-options-and-settings-in-visual-studio.md#miscellaneous-options).

## <a name="code-snippets"></a>Kod parçacıkları

Kod parçacıkları olan dosyalarınızı bir kısayol yazarak ve Tab tuşuna basarak veya kullanarak eklenebilir kod parçalarını **Düzenle > IntelliSense > Ekle kod parçacığını** **Surround With** komutları. Örneğin `class` ardından sekmesiyle sınıfı kalan anahtarı oluşturur. Adın üzerine yazın ve sekmesinde vurgulanan alanları arasında taşıma temellerine listesi sonra gövdesi yazmaya başlamak için Enter tuşuna basın.

![Kod Parçacıkları](media/code-editing-code-snippets.png)

Kod parçacıkları Yöneticisi'nde kullanılabilir kod parçacıkları görebilirsiniz (**Araçlar > kod parçacıkları Yöneticisi**), seçme **Python** dili olarak:

![Kod parçacıkları Yöneticisi](media/code-editing-code-snippets-manager.png)

Kendi parçacıkları oluşturmak için bkz: [izlenecek yol: kod parçacığı oluşturma](../ide/walkthrough-creating-a-code-snippet.md). 

Paylaşmak istediğiniz bir harika bir kod parçacığı yazarsanız bir gist sonrası çekinmeyin ve [bize bildirin](https://github.com/Microsoft/PTVS/issues). Visual Studio gelecekteki bir sürümde eklemek mümkün olabilir.

## <a name="navigating-your-code"></a>Kodunuzu gezinme

Visual Studio'da Python desteği sağlar hızlıca kitaplıkları için hangi kaynak kod kullanılabilir dahil olmak üzere kodunuzu içinde gezinmek için birkaç: [gezinti çubuğu](#navigation-bar), [Tanıma Git](#go-to-definition), [Gidin](#navigate-to), ve [tüm başvuruları Bul](#find-all-references). Visual Studio'yu da kullanabilirsiniz [Nesne Tarayıcısı](../ide/viewing-the-structure-of-code.md#BKMK_ObjectBrowser).

### <a name="navigation-bar"></a>Gezinti çubuğu

Gezinti çubuğu her Düzenleyicisi penceresinin üst kısmında görüntülenir ve iki düzeyli listesini tanımları içerir. Aşağı açılan sol üst düzey sınıfı ve geçerli dosyasında işlev tanımları içerir; sağ açılan sol gösterilen kapsam içinde tanımları listesini görüntüler. Düzenleyicide hareket etme gibi geçerli bağlamı göstermek için listeler güncelleştirin ve bu listeleri doğrudan hemen bir giriş öğesini de seçebilirsiniz.

![Gezinti çubuğu](media/code-editing-navigation-bar.png)

> [!Tip]
> Gezinti çubuğu gizlemek için şu adrese gidin **Araçlar > Seçenekler > Metin Düzenleyicisi > Python > Genel** ve temizleyin **Ayarları > gezinti çubuğu**.

### <a name="go-to-definition"></a>Tanıma gitme

**Tanıma Git** hızlı bir şekilde kullanımından doğacak tanımlayıcı (örneğin, bir işlev adı, sınıf veya değişken), kaynak koduna tanımlandığı atlar. Tanımlayıcı sağ tıklayıp seçerek çağırma **Tanıma Git** veya şapka tanımlayıcıda yerleştirip F12 tuşuna basın. Kaynak kodu kullanılabilir olması koşuluyla, kod ve dış kitaplıkları çalışır. Kitaplık kaynak kodu kullanılamıyorsa, **Tanıma Git** atlar ilgili `import` deyimi bir modül başvurusu veya görüntü bir hata oluştu.

![Tanıma gitme](media/code-editing-go-to-definition.png)

### <a name="navigate-to"></a>Gidin

**Düzenle > gidin...**  komutu (Ctrl-virgül), burada herhangi bir dize türü ve olası eşleşmeler işlevi, sınıf veya o dizeyi içeren değişkenini tanımlar, kodunuzda bkz Düzenleyicisi'nde bir arama kutusu görüntüler. Bu özellik olarak benzer bir yetenek sağlar **Tanıma Git** ancak bir tanımlayıcı kullanımını bulmak zorunda kalmadan.

Herhangi bir ad çift veya ok tuşları ve girin, seçerek bu tanıtıcıyı tanımına gider.

![Gidin](media/code-editing-navigate-to.png)

### <a name="find-all-references"></a>Tüm Başvuruları Bul

**Tüm başvuruları Bul** olan herhangi bir belirtilen tanımlayıcı hem olduğu bulmak için kullanışlı bir yol tanımlanır ve içeri aktarmalar ve atamaları dahil olmak üzere kullanılır. Tanımlayıcı sağ tıklayıp seçerek çağırma **tüm başvuruları Bul**, veya şapka tanımlayıcıda yerleştirme Shift + F12 tuşuna basarak. Listesindeki bir öğeyi çift konumuna gider.

![Tüm başvuruları sonuçları Bul](media/code-editing-find-all-references.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Biçimlendirme](formatting-python-code.md)
- [Yeniden Düzenleme](refactoring-python-code.md)
- [Lint uygulama](linting-python-code.md)