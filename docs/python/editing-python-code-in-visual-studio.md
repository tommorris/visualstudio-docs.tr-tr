---
title: Python kodu düzenleme
description: Visual Studio'da düzenleme Python, IntelliSense kod parçacıkları ve biçimlendirme, linting ve yeniden düzenleme ile birlikte Gezinti özellikleri sağlar.
ms.date: 05/07/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 454d8b0294181329c8b1c4414d8f7c70127e661c
ms.sourcegitcommit: f37affbc1b885dfe246d4b2c295a6538b383a0ca
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37175066"
---
# <a name="editing-python-code"></a>Python kodu düzenleme

Geliştiriciler harcama Kod düzenleyicisinde, zamanlarının çoğunu şekilde [Visual Studio'da Python desteği](installing-python-support-in-visual-studio.md) daha üretken olmanıza yardımcı olmak için işlevsellik sağlar. IntelliSense söz dizimi vurgulama, otomatik tamamlama, imza Yardımı, yöntemi geçersiz kılmalar, arama ve gezinti özellikleri içerir.

Düzenleyici, ayrıca Visual Studio, ikisi arasındaki kod exchange kolaylaştıran etkileşimli pencerede ile tümleşiktir. Bkz: [Öğreticisi 3. adım: etkileşimli REPL penceresini kullanma](tutorial-working-with-python-in-visual-studio-step-03-interactive-repl.md) ve [etkileşimli pencereye - gönderme kodu etkileşimli komutunu kullanarak](python-interactive-repl-in-visual-studio.md#send-code-to-interactive-command) Ayrıntılar için.

|   |   |
|---|---|
| ![video kamera simgesini film](../install/media/video-icon.png "bir video izleyin") | [(Microsoft Virtual Academy) videoyu](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Editing-Python-Code-r2iQH5LWE_4605918567) Python kod (2 dk. 30 saniye) düzenleme, tanıtım için.|

Visual Studio'da kod düzenleme genel belgeler için bkz: [Kod Düzenleyicisi özellikleri](../ide/writing-code-in-the-code-and-text-editor.md). Ayrıca bkz: [Visual Studio'daki anahat oluşturma](../ide/outlining.md), kodunuzun belirli bölümleri odaklı kalmanıza yardımcı olur.

Visual Studio nesne tarayıcısı da kullanabilirsiniz (**Görünüm > diğer Windows > Nesne Tarayıcısı** ya da Ctrl + W, J) her modülde tanımlanmış Python sınıfları ve bu sınıfların tanımlanan işlevleri incelemek için.

## <a name="intellisense"></a>IntelliSense

IntelliSense sağlar [tamamlamaları](#completions), [imza Yardımı](#signature-help), [hızlı bilgi](#quick-info), ve [kod renklendirme](#code-coloring). Visual Studio 2017 sürüm 15.7 ve üzeri da destekler [tür ipuçlarını](#type-hints).

IntelliSense, performansı artırmak için **Visual Studio 2017 sürüm 15.5** ve daha önce projenizdeki her Python ortamı için oluşturulan bir tamamlanma veritabanı bağlıdır. Veritabanları eklemek, kaldırmak veya güncelleştirme paketleri yenileme gerekebilir. Veritabanı durumu gösterilir **Python ortamları** penceresinde (Çözüm Gezgini eşdüzey) **IntelliSense** sekme (bkz [ortam penceresi başvurusu](python-environments-window-tab-reference.md#intellisense-tab)).

**Visual Studio 2017 sürüm 15.6** ve daha sonra veritabanına bağımlı olmayan IntelliSense tamamlamaları sağlamak için farklı bir yol kullanır.

### <a name="completions"></a>Tamamlamaları

Tamamlamalar deyimleri, tanımlayıcıların ve düzenleyicide geçerli konumda uygun şekilde girilebilir başka bir deyişle olarak görünür. Listede gösterilen bağlama göre ve hatalı veya dikkat dağıtıcı seçenekleri atlamak için filtrelenir. Tamamlamalar, farklı ifadeler yazarak genellikle tetiklenir (gibi `import`) ve işleçler (nokta dahil), ancak olabilir bunları dilediğiniz zaman Ctrl-J alanı yazarak belirir.

![Üye tamamlama](media/code-editing-completions-simple.png)

Tamamlanma listesi açıkken, fare ok tuşlarını kullanarak istediğiniz tamamlama veya yazmaya devam etmek arama yapabilirsiniz. Daha fazla harf yazarken liste daha büyük olasılıkla tamamlamaları göstermek için filtrelenir. Kısayolları gibi kullanabilirsiniz:

- Başında 'argparse' bulmak için 'parse' gibi bir adı olmayan bir harf yazarak
- 'AbstractBaseClass' veya 'hava' 'as_integer_ratio' bulmak için bulmayı 'abc' gibi bir sözcük başlangıcında olan mektup yazmaya
- Harf, '' base64' bulmak için b64' gibi atlanıyor

Bazı örnekler:

![Filtreleme ile üye tamamlama](media/code-editing-completion-filtering.png)

Bir süre sonra bir değişken veya yöntemleri ve olası türlerinin öznitelikleri ile birlikte bir değer yazdığınızda, üye tamamlamaları otomatik olarak görünür. Bir değişkeni birden fazla tür olabilir, listenin tüm olasılıkları hangi türlerin her tamamlama desteği göstermek için ek bilgilerle, tüm türlerden içerir. Bir tamamlama tüm olası türleri tarafından destekleniyorsa, ek açıklama gösterilmektedir.

![Birden çok türlerinde üye tamamlama](media/code-editing-completion-types.png)

Varsayılan olarak, "dunder" üyeleri (başlayan ve bir çift alt çizgi ile biten üyeler) gösterilmez. Genel olarak, bu tür üyelerin doğrudan erişilmemelidir. Bir tane gerekir, ancak başlarında çift alt çizgi yazarak bu tamamlamaları listeye ekler:

![Özel üye tamamlama](media/code-editing-completion-dunder.png)

`import` Ve `from ... import` ifadeler aktarılabilen modüllerin listesini görüntüler. İle `from ... import`, liste belirtilen modülünden içeri aktarılabilir üyeleri içerir.

![İçeri aktarma tamamlama](media/code-editing-completion-import.png)

`raise` Ve `except` ifadeler sınıfları hata türleri için olası bir listesini görüntüler. Listenin tüm kullanıcı tanımlı özel durumlar içermiyor olabilir, ancak uygun yerleşik özel durumlar hızlı bir şekilde bulmanıza yardımcı olur:

![Özel durum tamamlama](media/code-editing-completion-exception.png)

Yazarak bir dekoratör başlar ve olası dekoratörler gösterir. Bu öğelerin birçoğunu dekoratörler kullanışlı değildir; hangisini kullanacağınızı belirlemek için kitaplık belgelerine bakın.

![Dekoratör tamamlama](media/code-editing-completion-decorator.png)

> [!Tip]
> Tamamlamalar davranışını yapılandırabilirsiniz **Araçlar > Seçenekler > Metin Düzenleyicisi > Python > Gelişmiş "**. Bunlar arasında **filtresi listesi, arama dizesi tabanlı**: yazdığınız sırada tamamlama önerileri ve filtreleme uygular (varsayılan denetlenir) ve **üye tamamlama üyelerini kesişimi görüntüler** yalnızca gösterir (varsayılan olarak işaretli değildir) tüm olası türleri tarafından desteklenen tamamlamalar. Bkz: [seçenekleri - tamamlama sonuçları](python-support-options-and-settings-in-visual-studio.md#completion-results).

### <a name="type-hints"></a>Tür ipuçları

*Visual Studio 2017 sürüm 15.7 ve üzeri.*

"Tür ipuçlarını" Python 3.5 + ([CESARETLENDİRİCİ 484](https://www.python.org/dev/peps/pep-0484/) (python.org) olan işlevler için bir ek açıklama söz dizimi ve bağımsız değişken türlerini belirten sınıflar dönüş değerleri ve sınıf öznitelikleri. İşlev çağrıları, bağımsız değişkenleri ve bu ek açıklamalarına sahip değişkenler geldiğinizde IntelliSense tür ipuçlarını görüntüler.

Aşağıdaki örnekte `Vector` sınıfı olarak bildirilen `List[float]`ve `scale` işlevi, bağımsız değişkenler ve dönüş değeri için tür ipuçları içerir. Bu işleve yapılan bir çağrı geldiğinizde tür ipuçlarını gösterir:

![Tür ipuçlarını görüntülemek için işlev çağrısının üzerinden vurgulama](media/code-editing-type-hints1.png)

Aşağıdaki örnekte, gördüğünüz nasıl özniteliklerini açıklamalı `Employee` sınıfı IntelliSense tamamlanma açılan bir öznitelik için görünür:

![IntelliSense tamamlanma gösteren türü ipuçları](media/code-editing-type-hints2.png)

Hataları çalışma zamanına kadar normal olarak görünmez olduğundan da tür ipuçlarına, proje boyunca doğrulamak yararlıdır. Bu amaç için bağlam menüsü komutu aracılığıyla sektörde standart MyPy aracı Visual Studio'yu tümleştirir **Python > Run Mypy** içinde **Çözüm Gezgini**:

![Çözüm Gezgini'nde MyPy bağlam menüsü komutu Çalıştır](media/code-editing-type-hints-run-mypy.png)

Komut istemlerini çalıştıran, mypy paketini yüklemek için gerekli. Visual Studio projesinde her bir Python dosyasında tür ipuçlarını doğrulamak için mypy sonra çalışır. Visual Studio'da hata görünür **hata listesi** penceresi. Bir öğenin seçilmesi pencerenin kodunuzdaki uygun satırına gider.

Basit bir örnek olarak, aşağıdaki işlev tanımı belirtmek için bir tür ipucu içeren `input` bağımsız değişken türü ise `str`bilgileriyse söz konusu işleve yapılan çağrı, bir tamsayı geçirin dener:

```python
def commas_to_colons(input: str):
    items = input.split(',')
    items = [x.strip() for x in items]
    return ':'.join(items)

commas_to_colons(1)
```

Kullanarak **Run Mypy** komutu bu kodda şu hata oluşturur:

![Tür ipuçlarını doğrulama mypy örnek sonucu](media/code-editing-type-hints-validation-error.png)

> [!Tip]
> Python 3.5 önce sürümleri için Visual Studio aracılığıyla sağladığınız tür ipuçları da görüntüler *saplama dosyalarını* (`.pyi`). Saplama dosyalarını doğrudan kodunuzu tür ipuçları dahil etmek istemediğiniz her ya da bunları doğrudan kullanmayan kitaplığı için tür ipuçlarını oluşturmak istediğinizde kullanabilirsiniz. Daha fazla bilgi için [Python modüllerini için Saplamalar oluşturma](https://github.com/python/mypy/wiki/Creating-Stubs-For-Python-Modules) mypy proje Wiki'de.
>
> Şu anda, Visual Studio açıklamalarda tür ipuçlarını desteklemez.

### <a name="signature-help"></a>İmza Yardımı

Açılış yazdığınızda, bir işlev çağıran kod yazarken, imza Yardımı görünür `(` ve mevcut belgeler ve parametre bilgileri görüntüler. Bu işlev çağrısı içinde Ctrl + Shift + Ara çubuğu ile görünür yapabilirsiniz. Görüntülenen bilgiler, işlevin kaynak kodunu belgeleri dizelerde bağlıdır, ancak varsayılan değerler içerir.

![İmza Yardımı](media/code-editing-signature-help.png)

> [!Tip]
> İmza Yardımı devre dışı bırakmak için Git **Araçlar > Seçenekler > Metin Düzenleyicisi > Python > Genel** temizleyin **deyim tamamlama > parametre bilgileri**.

### <a name="quick-info"></a>Hızlı bilgi

Fare işaretçisi bir tanımlayıcının geldiğinizde, hızlı bilgi araç ipucu görüntülenir. Tanımlayıcı, bağlı olarak hızlı bilgi olası değerlerin görüntüleyebilir veya dönüş türleri, tüm kullanılabilir belgelere türleri ve tanımı konumlar:

![Hızlı Bilgi](media/code-editing-quick-info.png)

### <a name="code-coloring"></a>Kod renklendirme

Kod renklendirme renkleri değişkenler, ifadeler ve kodunuzun diğer bölümlerine Kod Analizi bilgileriyle kullanır. Örneğin, modülleri veya sınıflar için başvuru değişkenleri işlevleri veya diğer değerlere daha farklı bir renkte gösterilebilir ve parametre adları yerel veya genel değişkenleri farklı bir renkte görünür. (Varsayılan olarak, İşlevler kalın olarak gösterilmez):

![Kod renklendirme](media/code-editing-code-coloring.png)

Renkleri özelleştirmek için Git **Araçlar > Seçenekler > ortam > yazı tipleri ve renkler** ve Python girişleri değiştirmek **görüntü öğeleri** listesi:

![Yazı tipleri ve renkler seçenekleri](media/code-editing-customize-colors.png)

> [!Tip]
> Kod renklendirmesini devre dışı bırakmak için Git **araçları > Seçenekler > Metin Düzenleyicisi > Python > Gelişmiş** temizleyin **çeşitli seçenekleri > Renk türüne göre adları**. Bkz: [seçenekleri - çeşitli seçenekleri](python-support-options-and-settings-in-visual-studio.md#miscellaneous-options).

## <a name="code-snippets"></a>Kod parçacıkları

Kod parçacıkları, bir kısayol yazmaya ve SEKME tuşuna basarak veya kullanarak dosyalarınızı eklenebilecek kod parçalarını **Düzenle > IntelliSense > kod parçacığı Ekle** ve **Surround With** komutları seçme **Python**, istenen kod parçacığı seçildikten sonra.

Örneğin, `class` bir sınıf tanımı ekleyen bir kod parçacığı bir kısayol bulunur. Yazarken otomatik tamamlama listede görüntülenen kod parçacığının gördüğünüz `class`:

![Sınıf kısayol için kod parçacığı](media/code-editing-code-snippet-class.png)

Sekme tuşuna basarak rest sınıfı oluşturur. Gövdesi yazmaya başlamak için Enter tuşuna ile sekmesindeki vurgulanan alanları arasında taşıma türü adı ve tabanlar listesi üzerinden sonra kullanabilirsiniz.

![Öne çıkan özellikleri alanlara tamamlayabilmeniz için bir kod parçacığı](media/code-editing-code-snippets.png)

### <a name="menu-commands"></a>Menü komutları

Kullanırken **Düzenle > IntelliSense > kod parçacığı Ekle** menü komutunu ilk "Python" seçin sonra bir parçacığını seçin:

![Kod parçacığı Ekle komutu aracılığıyla kod parçacığı seçme](media/code-editing-code-snippet-insert.png)

**Düzenle > IntelliSense > Surround With** komut, benzer şekilde, yerleştirir geçerli seçim ve metin düzenleyicisindeki seçilen yapısal öğesi içinde. Örneğin, biraz kod aşağıdaki gibi olan varsayalım:

```python
sum = 0
for x in range(1, 100):
    sum = sum + x
```

Bu kod ve seçerek **Surround With** komutu kullanılabilir kod parçacıkları bir listesini görüntüler. Seçme `def` listesi yerlerde seçili kod içinde bir işlev tanımı ve vurgulanan işlev adı ve bağımsız değişkenleri arasında gezinmek için Tab tuşunu kullanabilirsiniz:

![Surround With komutu için kod parçacıkları kullanma](media/code-editing-code-snippet-surround-with.png)

### <a name="examine-available-snippets"></a>Kullanılabilir kod parçacıkları inceleyin

Kullanılabilir kod parçacıkları kullanılarak açılan kod parçacıkları Yöneticisi'nde gördüğünüz **Araçlar > kod parçacıkları Yöneticisi** menü komutu ve seçerek **Python** dili olarak:

![Kod parçacıkları Yöneticisi](media/code-editing-code-snippets-manager.png)

Kendi parçacıklarınızı oluşturmak için bkz [izlenecek yol: kod parçacığı oluşturma](../ide/walkthrough-creating-a-code-snippet.md).

Paylaşmak istediğiniz bir harika bir kod parçacığı yazarsanız, içinde bir gist göndermekten çekinmeyin ve [bize bildirin](https://github.com/Microsoft/PTVS/issues). Visual Studio'nun gelecekteki bir sürümde eklemek mümkün olabilir.

## <a name="navigating-your-code"></a>Kodunuzda gezinme

Visual Studio'da Python desteği için hangi kaynak kodu kullanılabilir kitaplıklar gibi kodunuzu içinde hızlıca gezinmek için birkaç yol sağlar: [gezinti çubuğu](#navigation-bar), [tanıma](#go-to-definition), [Gidin](#navigate-to), ve [tüm başvuruları Bul](#find-all-references). Visual Studio ayrıca kullanabileceğiniz [Nesne Tarayıcısı](../ide/viewing-the-structure-of-code.md#BKMK_ObjectBrowser).

### <a name="navigation-bar"></a>Gezinti çubuğu

Gezinti çubuğunda, her Düzenleyicisi penceresinin üst kısmında görüntülenir ve iki düzeyli listesini tanımları içerir. Soldaki aşağı açılan, üst düzey bir sınıf ve işlev tanımları geçerli dosyadaki içerir. doğru açılan sola gösterilen kapsamındaki tanımlarını listesini görüntüler. Düzenleyicide yerleri gibi geçerli Bağlamınızı gösterilecek listelerini güncelleştirmek ve bir giriş, doğrudan atlamak için bu listeleri de seçebilirsiniz.

![Gezinti çubuğu](media/code-editing-navigation-bar.png)

> [!Tip]
> Gezinti çubuğunu gizlemek için şuraya gidin: **Araçlar > Seçenekler > Metin Düzenleyicisi > Python > Genel** temizleyin **Ayarları > gezinti çubuğu**.

### <a name="go-to-definition"></a>Tanıma Git

**Tanıma Git** hızlı bir şekilde (örneğin, bir işlev adı, sınıf veya değişken), bir tanımlayıcının kullanıma karşı kaynak koduna tanımlandığı atlar. Bir tanımlayıcı sağ tıklatıp seçerek çağırma **tanıma** veya giriş işaretini bir tanımlayıcıda yerleştirip F12 tuşuna basın. Kaynak kodu kullanılabilir olması koşuluyla, kod ve dış kitaplıkları çalışır. Kitaplığı kaynak kodunu kullanılamıyorsa **tanıma** atlar ilgili `import` deyimi bir modül başvurusu veya görünen bir hata oluştu.

![Tanıma Git](media/code-editing-go-to-definition.png)

### <a name="navigate-to"></a>Gidin

**Düzenle > gidin...**  komut (Ctrl-ayrılmış), burada herhangi bir dizesini yazın ve kodunuzda bir işlev, sınıf veya o dizeyi içeren bir değişkeni tanımlar olası eşleşmeleri görmek Düzenleyicisi'nde bir arama kutusu görüntüler. Bu özellik, benzer bir özellik olarak sağlar. **tanıma** ancak tanımlayıcının kullanımını bulmak zorunda kalmadan.

Herhangi bir ad çift veya ok tuşlarını ve Enter tuşuna ile seçerek bu tanımlayıcının tanımına gider.

![Gidin](media/code-editing-navigate-to.png)

### <a name="find-all-references"></a>Tüm Başvuruları Bul

**Tüm başvuruları Bul** herhangi bir tanımlayıcı hem olduğu bulmak için kullanışlı bir yol tanımlanır ve içeri aktarmalar ve atamaları dahil olmak üzere kullanılır. Bir tanımlayıcı sağ tıklatıp seçerek çağırma **tüm başvuruları Bul**, ya da giriş işaretini bir tanımlayıcıda yerleştirme ve Shift + F12 tuşuna basın. Listedeki bir öğeye çift tıklatarak konumuna gider.

![Tüm başvuruları sonuçları bulma](media/code-editing-find-all-references.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Biçimlendirme](formatting-python-code.md)
- [Yeniden Düzenleme](refactoring-python-code.md)
- [Bir lint kullanın](linting-python-code.md)