---
title: Visual Studio'da kodu gidin
ms.date: 09/26/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code editor, navigation
- code editor, go to
- code editor, go to definition
- code editor, go to line
- code editor, peek definition
- code editor, navigation bar
- go to definition
- peek definition
- go to line
- go to
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 78c983943f7cf99bf9dbe7ee60df06b033404719
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="navigate-code"></a>Kod gidin

Visual Studio düzenleyicisinde kod gitmek için çok çeşitli yollar sağlar. Bu konu, kodunuzu gidebilirsiniz farklı yolları özetler ve daha fazla ayrıntıya konulara bağlantılar sağlar.

## <a name="navigate-backward-and-navigate-forward-commands"></a>Geri ve İleri Git komutları gidin

Kullanabileceğiniz **geriye Git** (**Ctrl**+**-**) ve **ileriye** ( **CTRL**+**Shift**+**-**) ekleme noktasını önceki konumlara taşıyın ya da bir daha geri dönmek için araç çubuğundaki düğmeler bir önceki konumdan son konum. Bu düğme ekleme noktasını son 20 konumlarını korur. Bu komutlar da kullanılabilir **Görünüm** menüsü altında **geriye Git** ve **ileriye**.

![İleri ve geri gezinti düğmeleri](../ide/media/vs2017_nav_buttons.png)

## <a name="navigation-bar"></a>Gezinti çubuğu

Kullanabileceğiniz **gezinti çubuğu** (açılan kutuları kod penceresinin üst) bir codebase kodda gitmek için. Bir tür veya üye doğrudan gitmek için seçebilirsiniz. Bir Visual Basic, C# veya C++ kodu temel kodda düzenlediğinizde gezinti çubuğunda görünür. Kısmi bir sınıfta geçerli kod dosyası dışında tanımlanan üyeleri devre dışı bırakılabilir (bunlar gri görünür).

 ![Kod gezinti çubuğu](../ide/media/vside_navigation_bar.png)

Açılan kutuları gibi gidebilirsiniz:

- Geçerli dosya ait başka bir projeye gitmek için soldaki açılan seçin.

- Bir sınıf ya da türü gitmek için aşağı açılan ortadaki seçin.

- Doğrudan bir yordam veya başka bir sınıf üyesi gitmek için sağ açılan seçin.

- Odak kodu penceresinden gezinti çubuğunun kaydırma için kısayol tuş birleşimine basın **Ctrl**+**F2**.

- Odağı kutusu kutusu gezinti çubuğunda kaydırmak için basın **sekmesini** anahtarı.

- Odak ve dönüş kodu penceresine sahip gezinti çubuğu öğesi seçmek için basın **Enter** anahtarı.

- Odağı Gezinti Çubuğu'ndan için hiçbir şey seçmeden dönüş kodu için basın **Esc** anahtarı.

Gezinti çubuğu gizleme için değiştirme **gezinti çubuğu** seçeneğini **tüm diller metin düzenleyici** ayarları (**Araçları** > **seçenekleri**  >  **Metin düzenleyici** > **tüm diller**), veya bireysel diller için ayarları değiştirebilirsiniz.

## <a name="find-all-references"></a>Tüm başvuruları Bul

Seçilen öğeyi yapılan tüm başvuruları çözümde bulur. Bu, olası yan-büyük bir yeniden düzenleme etkilerini denetleyin veya "ölü" kod doğrulamak için kullanabilirsiniz. Tuşuna **F8** sonuçları arasında atlamak için. Daha fazla bilgi için bkz: [kodunuzda başvuruları Bul](finding-references.md).

Giriş        | İşlev
------------ | ---
**Klavye** | Metin imlecinizi adını yazın ve tuşuna içinde yere yerleştirin **Shift**+**F12**
**Fare**    | Seçin **tüm başvuruları Bul** ve bağlam menüsünden

## <a name="reference-highlighting"></a>Başvuru vurgulama

Kaynak kodda bir simge tıkladığınızda, bu simgeyi tüm örneklerini belgede vurgulanır. Vurgulanan simgeleri bildirimler ve başvurular içerebilir ve diğer birçok, simgeler **tüm başvuruları Bul** döndürür. Bu sınıf, nesneler, değişkenleri, yöntemleri ve özellikleri adlarını içerir. Visual Basic kodunda birçok denetim yapıları için anahtar sözcükleri da vurgulanmıştır. Sonraki veya önceki vurgulanan simgeye gitmek için basın **Ctrl**+**Shift**+**aşağı ok** veya **Ctrl** + **Shift**+**yukarı ok**. Vurgulama rengi değiştirebilirsiniz **Araçları** > **seçenekleri** > **ortam** > **yazı tipleri ve Renkleri** > **vurgulanmış başvuru**.

## <a name="go-to-commands"></a>Git komutları

Gitmek için kullanılabilir olan aşağıdaki komutları sahip **Düzenle** menüsünün altında **gitmek için**:

- **Satıra Git** (**Ctrl**+**G**): Belirtilen satır numarası etkin belgedeki taşıyın.

- **Tüm gidin** (**Ctrl**+**T** veya **Ctrl**+**,**): taşıma türü, belirtilen satırına Dosya, üye veya simge.

- **Dosyaya gidin** (**Ctrl**+**1**, **Ctrl**+**F**): belirtilen dosyaya Taşı çözümü.

- **Türü gidin** (**Ctrl**+**1**, **Ctrl**+**T**): belirtilen türe Taşı çözümü.

- **Üye gidin** (**Ctrl**+**1**, **Ctrl**+**M**): Belirtilen üye taşıyın çözümü.

- **Sembol gidin** (**Ctrl**+**1**, **Ctrl**+**S**): Belirtilen sembolü taşıyın çözümü.

Bu komutlar hakkında daha fazla [Git komutları kullanarak kod Bul](../ide/go-to.md) konu.

## <a name="go-to-definition"></a>Tanıma gitme

Tanıma Git seçilen öğeyi tanımını alır. Daha fazla bilgi için bkz: [Tanıma Git ve Peek tanımı](../ide/go-to-and-peek-definition.md).

Giriş        | İşlev
------------ | ---
**Klavye** | Metin imlecinizi adını yazın ve tuşuna içinde yere yerleştirin **F12**
**Fare**    | Tür adına sağ tıklayıp **Tanıma Git** veya basın **Ctrl** (Visual Studio 2017 15.4 sürüm için yeni) tür adı'e tıklayın

## <a name="peek-definition"></a>Özet tanımı

Tanımı görüntüler konumunuzu Kod düzenleyicisinde çıktığınızda gitmeden penceresinde seçili öğesinin tanımı Gözat. Daha fazla bilgi için bkz: [nasıl yapılır: Peek tanımı kullanarak görüntüleme ve düzenleme kod](../ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md) ve [Tanıma Git ve Peek tanımı](../ide/go-to-and-peek-definition.md).

Giriş        | İşlev
------------ | ---
**Klavye** | Metin imlecinizi adını yazın ve tuşuna içinde yere yerleştirin **Alt**+**F12**
**Fare**    | Türü adını sağ tıklatın ve seçin **Özet tanımı** veya basın **Ctrl** ve tür adına tıklayın (varsa **tanımı gözlem görünümünde açmak** teslim seçeneği)

## <a name="go-to-implementation"></a>Uygulamasına gidin

Uygulamayı Git kullanarak bir taban sınıftan gidin veya bunun uygulamalarını yazın. Birden çok uygulamaları varsa bunları listelenen görürsünüz **Bul simgesi sonuçlarınızı** penceresi:

Giriş        | İşlev
------------ | ---
**Klavye** | Metin imlecinizi adını yazın ve tuşuna içinde yere yerleştirin **Ctrl**+**F12**
**Fare**    | Tür adına sağ tıklayıp **uygulaması Git**

## <a name="call-hierarchy"></a>Çağrı Hiyerarşisi

Bir yöntemin gelen ve giden çağrıları görüntüleyebilirsiniz [çağrı hiyerarşisi penceresi](../ide/reference/call-hierarchy.md):

Giriş        | İşlev
------------ | ---
**Klavye** | Metin imlecinizi adını yazın ve tuşuna içinde yere yerleştirin **Ctrl**+**K**, **Ctrl**+**T**
**Fare**    | Üye adını sağ tıklatın ve seçin **görünüm çağrı hiyerarşisi**

## <a name="next-method-and-previous-method-commands-visual-basic"></a>Sonraki yöntem ve önceki yöntem komutları (Visual Basic)

Visual Basic kod dosyalarında için farklı yöntemler ekleme noktasını taşımak için bu komutları kullanın. Seçin **Düzenle** > **sonraki yöntemi** veya **Düzenle** > **önceki yöntemi**.

## <a name="structure-visualizer"></a>Yapı Görselleştirici

Kod Düzenleyicisi gösterir yapısı Görselleştirici özelliğinde *yapısı kılavuz çizgileri* -dikey temelinizde kaşlı ayraç eşleştirme belirtmek satırları kesik. Bu mantıksal blokları nerede başlaması görmeyi kolaylaştırır ve son kolaylaştırır.

![Yapı Görselleştirici](../ide/media/vside_structure_visualizer.png)

Yapı kılavuz çizgileri devre dışı bırakmak için Git **Araçları** > **seçenekleri** > **metin düzenleyici** > **genel** ve temizleyin **yapısı kılavuz çizgileri göster** kutusu.

## <a name="enhanced-scroll-bar"></a>Gelişmiş kaydırma çubuğu

Bakışı bir görünüm kodunuzu almak için bir kod penceresinde Gelişmiş kaydırma çubuğu kullanabilirsiniz. Harita modunda imleç kaydırma çubuğu yukarı ve aşağı taşıdığınızda kodu önizlemesini görebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: kaydırma çubuğu özelleştirerek kodunuzu izlemek](../ide/how-to-track-your-code-by-customizing-the-scrollbar.md).

## <a name="codelens-information"></a>CodeLens bilgileri

Değişiklikleri ve bu değişiklikler, başvurular, hatalar, iş öğeleri, kod gözden geçirme ve kod düzenleyicisinde CodeLens kullandığınızda test durumu birim kimin yaptığını gibi belirli kodu hakkında bilgi bulabilirsiniz. Team Foundation Server ile Visual Studio Enterprise kullandığınızda CodeLens ekran göstergesi görüntü gibi çalışır. Bkz: [kod değişikliklerini ve diğer geçmişi bulma](../ide/find-code-changes-and-other-history-with-codelens.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Kod ve Metin Düzenleyici'de kod yazma](../ide/writing-code-in-the-code-and-text-editor.md)
- [Çağrı hiyerarşisini görüntüleme](../ide/reference/call-hierarchy.md)
