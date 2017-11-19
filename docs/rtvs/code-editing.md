---
title: "Visual Studio için R araçları ile kod düzenleme | Microsoft Docs"
ms.custom: 
ms.date: 06/29/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a198ccc3-5506-48e7-b3b2-9399661b80d5
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 5c856bb02ca33f999273fd6da782226be5f0f2d2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="editing-r-code-in-visual-studio"></a>Visual Studio'da R kodu düzenleme
 
R araçları için Visual Studio (RTVS) düzenleme deneyimi tüm özellikleri ve uzantıları kullanabilme korurken özellikle r için Visual Studio uyarlar. (VIM anahtar bağlama tercih ederseniz, örneğin, ücretsiz yükleyebilirsiniz [VsVim uzantısı](https://visualstudiogallery.msdn.microsoft.com/59ca71b3-a4a3-46ca-8fe1-0e90e3f79329) Visual Studio Galerisi'nden.)

Bu konuda:

- [Söz dizimi vurgulama](#syntax-highlighting)
- [Düzenleme ve kod düzenleme](#editing-and-organizing-code)
- [Kod gezinme](#code-navigation)
- [Etkileşimli penceresine kod gönderme](#sending-code-to-the-interactive-window)
- [Kod biçimlendirme](#formatting-code)
- [Roxygen açıklamaları ekleme](#inserting-roxygen-comments)
- [Düzenleyici Seçenekleri](#editor-options)

Ayrıca üzerinde konulara bakın [IntelliSense](code-intellisense.md), [kod parçacıkları](code-snippets.md), ve [R Markdown](rmarkdown.md).


## <a name="syntax-highlighting"></a>söz dizimi vurgulama 

Dizeleri, açıklamalar ve anahtar sözcükler gibi kodunuzu farklı kısımlarını renklendirme yanı sıra RTVS da vurgular ve açıklamalarındaki bağlantılar sağlar:

![R kodu renklendirme sözdizimi](media/editing-syntax-colors.png)

Yazı tipleri ve belirli vurgu renkleri özelleştirmek için seçin **Araçlar > Seçenekler** komutu, gidin **ortam > yazı tiplerini ve renkleri**, R ile ilişkili öğeleri ayarlarını değiştirme  **Öğeleri görüntüleme:** kutusunda:

![Yazı tipleri ve renk seçeneklerini R kodu](media/editing-syntax-colors-options.png)

Visual Studio düzenleyicisinde sözdizimi hataları da altını çizer:

![Sözdizimi hatası R kodda vurgulama](media/editing-syntax-error.png)

Bu davranışı değiştirmek için bkz: **Gelişmiş > sözdizimi denetimi** altında ayarı [Düzenleyici Seçenekleri](#editor-options).

## <a name="editing-and-organizing-code"></a>Düzenleme ve kod düzenleme

Kod yazarken RTVS otomatik tamamlama açıklandığı gibi sağlar [IntelliSense](code-intellisense.md) sayfası. Ayrıca, otomatik biçimlendirme küme parantezleri ve parantez tamamlanmasından gibi yapar: 

![Satır içi biçimlendirme animasyon](media/editing-inline-formatting.gif)

Görmemeleri birçok parametrelerine sahip işlev çağrıları yazarken kodu okunmasını kolaylaştırmak için parametreleri satır istiyorsunuz. RTVS kümenizi parametreler için girinti hatırlıyor ve otomatik olarak o girintileme sonraki satırların için geçerlidir:

![Otomatik Girinti animasyonu](media/editing-auto-indentation.gif)

Bu davranışı değiştirmek için bkz: [Düzenleyici Seçenekleri](#editor-options) için **sekmeleri** grubu.

Daraltılabilir kod bölgeler, geçici olarak kod düzenleyicisinde parçası Gizle olanak tanır. Visual Studio oluşturur çeşitli bölgelere sizin için otomatik olarak, çok satırlı deyimleri için olduğu gibi sürece **Gelişmiş > Anahat > anahat oluşturma kodu** seçeneği kapalı olarak ayarlanır.

Kendi saran bir bölge ile biter yorumlarla istediğiniz kodu oluşturmak için `---`. Küçük denetimleri kodun soluna +/-ardından genişletme ve bölgeler daraltma olanak tanır:

![Yorumlarla daraltılabilir bir bölge oluşturma](media/editing-collapsible-regions.gif)
 
Sekme tuşuna bastığınızda, varsayılan olarak, Visual Studio boşluk ekler. Yeniden açıklandığı gibi bu davranışı değiştirebilirsiniz [seçenekler, metin düzenleyici, sekmeler](../ide/reference/options-text-editor-all-languages.md).

## <a name="code-navigation"></a>Kod gezinme

Kod Gezinti R programınızı ve başlatılamadığından kaynak koduna hızlı erişim sağlar. Bu özellikleri el ile kodunuzu arama gerek kalmadan yerine iş akışında tutun.

**Tanıma Git** hızla atlayan bir işlev tanımı ya da kitaplığı işlevi kaynak kodunu okumak için bir satır içi kısa bir Düzenleyicisi açılır. Yalnızca işlevi faiz seçin ve sağ **Tanıma Git**, veya işleve imleci yerleştirin ve F12 tuşuna basın.

Bu komut işlevi için kaynak kodunu içeren yeni bir Düzenleyicisi penceresini açar. İmleç işlev tanımının başlangıcında rahat konumlandırıldı.

**Tanım Ara**, sağ tıklatma menüsünden veya Alt + F12 çağrılan, işlev çağrısı aşağıda işlevinin kaynak kodunu içeren bir salt okunur, kaydırılabilir bölge ekler:

![Animasyon Özet tanımı için](media/editing-peek-definition.gif)

## <a name="sending-code-to-the-interactive-window"></a>Etkileşimli penceresine kod gönderme

Çoğu geliştiricinin Düzenleyicisi'nde biraz kod yazın ve ardından bu kodu göndermek ister [etkileşimli pencere](interactive-repl.md) sınama hemen (okuma değerlendirmek yazdırma döngü veya REPL olarak da bilinir). R Düzenleyicisi'nde Ctrl + Enter tuşuna basarak geçerli kod satırı ile etkileşimli penceresine gönderir ve ardından sonraki satırında imleci yerleştirir. Ctrl + Enter ile daha sonra etkili bir şekilde kodunuzu Düzenleyicisi'nden geçebilirsiniz.

Ayrıca, kodu seçip, tüm seçimi uygulamak için Ctrl + Enter tuşuna basın. Alternatif olarak, seçime sağ tıklayın ve **etkileşimli Execute**.

## <a name="formatting-code"></a>Kod biçimlendirme

Visual Studio'nun otomatik biçimlendirme yanı sıra küme olarak tercihlerinize göre biçimlendirilmiş düzenleyicisine yapıştırın kodu yazma kodu tutar. Ayrıca bir seçim yapabileceğiniz sağ tıklayın ve ardından seçin **Biçim Seçimi** (Ctrl + K, F) Bu tercihler uygulanır. Örneğin, tümü tek bir satıra bir işlev tanımı varsa:

```R
f<-function  (a){  return(a + 1) }
```

Biçimlendirme uygulayarak bunu olacak şekilde temizler:

```R
f <- function(a) { return(a + 1) }
```

Tüm kod dosyasını yeniden biçimlendirmek için seçin **Düzenle > Gelişmiş > biçimi belge** (Ctrl + E, D).

Otomatik biçimlendirme alınabilecek ayrı bir işlemdir. Örneğin, düzenleyici ve geçerli biçimlendirme kod yapıştırırsanız seçme **Düzenle > Geri** veya Ctrl + Z kez basarak tersine çevirir biçimlendirme; ikinci bir geri alma Yapıştır tersine çevirir.
 
Biçimlendirme seçenekleri (biçimlendirmeyi devre dışı bırakma dahil) aracılığıyla ayarlanır **Araçlar > Seçenekler** üzerinde **metin düzenleyicisi > R > Gelişmiş** sekmesi. Doğrudan kullanarak bu sayfaya geçebilir **R Araçlar > Düzenleyici Seçenekleri...**  komutunu veya göre Düzenleyicisi'nde sağ tıklayıp seçerek **biçimlendirme seçeneklerini...** . Bkz: [Düzenleyici Seçenekleri](#editor-options) ayrıntıları bölümü.
 
## <a name="inserting-roxygen-comments"></a>Roxygen açıklamaları ekleme

RTVS oluşturmak için bir kısayol sunar [Roxygen](http://roxygen.org/) işlevinin parametre adları kullanarak açıklamalar. Yalnızca yazın `###` işlev tanımı üzerinde boş bir satıra:

![Animasyon Roxygen açıklama ekleme](media/editing-roxygen-comments.gif)

## <a name="editor-options"></a>Düzenleyici Seçenekleri

Düzenleyicisi özgü seçenekleri aracılığıyla ayarlanır **Araçlar > Seçenekler** giderek komutu, **metin düzenleyicisi > R**, veya kısayol komutunu kullanın **R Araçlar > Düzenleyici Seçenekleri...** .

Seçeneklerinden **genel**, **kaydırma çubukları**, ve **sekmeleri** sekmeleri R belirli değildir, ancak bunun yerine genel Visual Studio ayarları tüm diller için kullanılabilir, ancak üzerinde uygulanan bir Dil başına temel. Ayrıntılar için aşağıdaki konulara bakın:

- [Seçenekler, metin düzenleyici, tüm diller](../ide/reference/options-text-editor-all-languages.md)
- [Kaydırma çubuğu özelleştirerek, kod izleme](../ide/how-to-track-your-code-by-customizing-the-scrollbar.md)
- [Seçenekler, metin düzenleyici, sekmeler](../ide/reference/options-text-editor-all-languages-tabs.md)

Seçeneklerinden **R > Gelişmiş** sekmesini RTVS için özeldir:

| Grup | Seçenek | Varsayılan | Açıklama |
| --- | --- | --- | --- |
| Biçimlendirme | Otomatik biçimlendirme | Açık | Yazarken kodu yeniden biçimlendirir. Etkilemez **Biçim Seçimi** veya **belgeyi Biçimlendir** komutları. |
| | Genişletilmiş küme ayraçları | Kapalı | {Yeni bir satıra. açık yerleştirir |
| | Üzerinde Yapıştır biçimlendirme | Açık | Üzerinde Yapıştır biçimlendirme uygular. |
| | Biçim kapsamına} | Açık | Kapsamı bir kapanış yazdıktan sonra biçimlendirir}. |
| | Virgül sonra boşluk | Açık | Boşluk, virgül sonra yerleştirir. |
| | Anahtar sözcüğü sonra boşluk | Açık | Anahtar sözcükler ister sonra bir alanı yerleştirir `if`, `while`, ve `repeat`. |
| | {Önce boşluk | Açık | Önce bir boşluk yerleştirir ve açma {. |
| | Alanları geçici = | Açık | Eşittir işareti boşluk yerleştirir. |
| IntelliSense | ENTER tuşuna Yürüt | Kapalı | ENTER tuşuna bastığınızda, otomatik tamamlama seçim kaydeder. |
| | Alan anahtarı Yürüt | Kapalı | Otomatik Tamamlama seçim alanı basıldığında kaydeder.|
| | İlk karakter üzerinde tamamlanma listesi | Açık | Tamamlanma listesi ilk karakter türleri üzerinde gösterir. Tamamlanma listesi görüntülenir ne zaman devre dışı **Düzenle > IntelliSense > listesi üyeleri** (Ctrl + J). |
| | SEKME tuşu üzerinde tamamlanma listesi | Kapalı | Tamamlanma listesi bir veya daha fazla karakter girip SEKME tuşuna basarak çağırır. |
| | Bağımsız değişken adları kısmen eşleşme türleri | Kapalı | Bağımsız değişken adları bir işlev çağrısında yazarken imza Yardım en iyi eşleşme olan bağımsız değişkeni için bir açıklama gösterir. |
| Etkileşimli penceresi | R konsolunda sözdizimi denetimi | Kapalı | Söz dizimi etkileşimli pencerede denetimi uygular. Sözdizimi denetimi, çok satırlı deyimleri ile düzgün çalışmayabilir. | 
| Anahat Oluşturma | Anahat oluşturma kodu | Açık | Çok satırlı deyimleri gibi alanlar için daraltılabilir bölgeler otomatik olarak oluşturur. | 
| Sözdizimi denetimi | Sözdizimi hataları göster | Açık | Otomatik söz dizimi kodu denetimi sağlar. |
