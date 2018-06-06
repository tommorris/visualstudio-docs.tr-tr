---
title: Visual Studio'da Özet tanımı kullanma
ms.date: 01/10/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c64f271f041c28dc621ed85a8cd9d79c36caa3dd
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34746721"
---
# <a name="how-to-view-and-edit-code-by-using-peek-definition-altf12"></a>Nasıl yapılır: Gözat tanımı (Alt + F12) kullanarak görüntüleme ve düzenleme kod

Kullanabileceğiniz **Peek tanımı** görüntülemek ve kodu yazdığınız kodu çıktığınızda geçmeden düzenlemek için komutu. **Tanım Ara** ve **Tanıma Git** aynı bilgileri gösterir, ancak **Peek tanımı** açılır pencerede, gösterir ve **Tanıma Git** gösterir ayrı kod penceresinde kod. **Tanıma Git** tanımı kod penceresine geçiş yapmak, içerik (diğer bir deyişle, etkin kod penceresi, geçerli satır ve imleç konumu) neden olur. Kullanarak **Peek tanımı**, görüntüleyebilir ve tanımını düzenlemek ve özgün kod dosyasında yerinizi tutarken tanım dosyası içinde hareket etme.

Kullanabileceğiniz **Peek tanımı** C#, Visual Basic ve C++ kodu ile. Visual Basic'te **Peek tanımı** bağlantısını gösterir **Nesne Tarayıcısı** tanımı meta veriler (yerleşik olan Örneğin, .NET Framework türleri) yoksa sembolleri.

## <a name="working-with-peek-definition"></a>Özet Tanım ile Çalışma

### <a name="to-open-a-peek-definition-window"></a>Bir Özet Tanım penceresi açmak için

1. Seçerek bir tanımı iletiye göz atabilirsiniz **Özet tanımı** türü ya da keşfetmek istediğiniz üye bağlam menüsünden. Seçeneği etkinleştirilirse, Visual Studio 2017 içinde 15.4 ve sonraki sürümleri, siz de tuşlarına basarak Fare kullanarak bir tanımını iletiye göz atabilirsiniz **Ctrl** (veya başka bir değiştiricisi) ve üye adı'nı tıklatın. Veya klavyeden basın **Alt**+**F12**.

     Bu gösterimde **Peek tanımı** adlı bir yöntem için pencere `Print()`:

     ![Peek penceresi](../ide/media/peekwindow.png)

     Aşağıda tanım penceresi görüntülenir `printer.Print("Hello World!")` özgün dosyasındaki satır. Pencerede, özgün dosyanızdaki kodlardan hiçbiri gizlenmez. İzleyen satırlarını `printer.Print("Hello World!")` altında tanımı penceresi görünür.

1. İmleci, gözlem tanımı penceresinde farklı konumlara taşıyın. Özgün kod penceresinde yine de taşıyabilirsiniz.

1. Dizeyi tanım penceresinden kopyalayıp özgün koda yapıştırabilirsiniz. Dizeyi tanım penceresinden sürükleyip özgün koda da bırakabilirsiniz (tanım penceresinden silinmeden).

1. Seçerek tanımı pencerenizi kapatabilir **Esc** anahtar veya **kapatmak** tanımı penceresi sekmesindeki düğmesi.

### <a name="open-a-peek-definition-window-from-within-a-peek-definition-window"></a>Peek tanımı penceresi içinde bir gözatma tanımı penceresi açın

Zaten varsa bir **Peek tanımı** penceresi açık, çağırabilir **Peek tanımı** yeniden bu pencereyi kodunda üzerinde. Başka bir tanım penceresi açılır. Tanım penceresi sekmesinin yanında, tanım pencereleri arasında gezinmek için kullanabileceğiniz bir dizi içerik haritası noktası görünür. Her bir noktadaki araç ipucu, noktanın temsil ettiği tanım dosyasının dosya adını ve yolunu gösterir.

   ![Peek penceresi pencereye Gözat](../ide/media/peekwithinpeek.png)

### <a name="peek-definition-with-multiple-results"></a>Birden çok sonuçlarla Özet tanımı

Kullanırsanız **Peek tanımı** birden fazla tanımı (örneğin, bir parçalı sınıf) kodu, bir sonuç listesi kod tanım görünümü sağında görünür. Listede istediğiniz sonucu seçerek tanımını görüntüleyebilirsiniz.

   ![Birden çok sonuç penceresinden Gözat](../ide/media/peekmultiple.png)

### <a name="edit-inside-the-peek-definition-window"></a>Peek tanımı penceresinin içine Düzenle

İçinde düzenlemek başlattığınızda bir **Peek tanımı** penceresinde, otomatik olarak değişiklik yaptığınız dosya olarak kod düzenleyicisinde ayrı bir sekmesinde açar ve yaptığınız değişiklikleri yansıtır. Yapmak, Geri Al ve değişiklikleri kaydetmek devam edebilirsiniz **Peek tanımı** penceresi ve sekmesinde bu değişiklikleri yansıtacak şekilde sürdürür. Bile kapatırsanız **Peek tanımı** Değişikliklerinizi kaydetmeden penceresinde, yapabilir, Geri Al ve bırakabilirsiniz tam olarak kaldığınız yerden yukarı çekme sekmesinde, daha fazla değişiklikleri kaydetmek **Peek tanımı** penceresi.

   ![Peek penceresi içinde düzenleme](../ide/media/peekedit.png)

### <a name="to-change-options-for-peek-definition"></a>Peek tanımı seçeneklerini değiştirmek için

1. Git **Araçları** > **seçenekleri** > **metin düzenleyici** > **genel**.

1. Seçeneğini **tanımı gözlem görünümünde açmak**.

1. Tıklatın **Tamam** kapatmak için **seçenekleri** iletişim kutusu.

   ![Fare tıklatma gözlem tanımı seçeneği ayarlama](../ide/media/editor_options_peek_view.png)

### <a name="keyboard-shortcuts-for-peek-definition"></a>Peek tanımı için klavye kısayolları

Bu klavye kısayollarını kullanabilirsiniz **Peek tanımı** penceresi:

|İşlevi|Klavye kısayolu|
|-------------------|:-----------------------:|
|Tanım penceresini açma|**Alt**+**F12**|
|Tanım penceresini kapatma|**ESC**|
|Tanım penceresini bir normal belge sekmesine yükseltme|**Shift**+**Alt**+**giriş**|
|Tanım pencereleri arasında gezinme|**CTRL**+**Alt** + **-** ve **Ctrl**+**Alt**+**=**|
|Birden fazla sonuç arasında gezinme|**F8** ve **Shift**+**F8**|
|Kod düzenleyicisi penceresi ile tanım penceresi arasında geçiş yapma|**Shift**+**Esc**|

> [!NOTE]
> Kodda düzenlemek için aynı klavye kısayollarını kullanabilirsiniz bir **Peek tanımı** yazarken penceresini kullanma başka bir yerde Visual Studio'da.

## <a name="see-also"></a>Ayrıca bkz.

- [Kod gidin](../ide/navigating-code.md)
- [Tanıma ve Özet Tanıma Gitme](../ide/go-to-and-peek-definition.md)
- [Üretkenlik ipuçları](../ide/productivity-tips-for-visual-studio.md)