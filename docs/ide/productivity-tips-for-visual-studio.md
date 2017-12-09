---
title: "Visual Studio için üretkenlik ipuçları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: fe42e4d2a61b4166d8a69b7c90cf212c36610bd2
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2017
---
# <a name="productivity-tips-for-visual-studio"></a>Visual Studio için üretkenlik ipuçları

Aşağıdaki ipuçlarını uygulayarak, daha hızlı ve verimli bir şekilde yazma gidin ve kodunuzu Visual Studio'da hata ayıklama.

Ortak klavye kısayolları hakkında daha fazla bilgi için bkz: [ipuçları ve püf noktaları](../ide/tips-and-tricks-for-visual-studio.md). Daha kapsamlı bir liste için bkz: [tanımlama ve özelleştirme klavye kısayolları](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md) ve [varsayılan klavye kısayolları](../ide/default-keyboard-shortcuts-in-visual-studio.md).

## <a name="accessing-visual-studio-tools"></a>Visual Studio Araçları erişme

Başlat menüsü veya görev çubuğunda sabitlerseniz Geliştirici komut istemi veya başka bir Visual Studio aracı, hızlı bir şekilde erişebilir.

1. Windows Gezgini'nde göz `%ProgramData%\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools`.

1. Sağ tıklayın veya bağlam menüsünü açın **Geliştirici komut istemi**ve ardından **Başlangıç ekranına Sabitle** veya **görev çubuğuna Sabitle**.

## <a name="writing-code"></a>Kod yazma

Kod, aşağıdaki özellikleri kullanarak daha hızlı bir şekilde yazın.

- **Örnek uygulamalar kullanmak**. Örnek uygulamalarından indirip uygulama geliştirme hızlandırabilir [Microsoft Developer Network](https://code.msdn.microsoft.com/). Karşıdan yükleme ve bu alan için bir örnek paketi keşfetme tarafından belirli teknoloji veya programlama kavramı öğrenebilirsiniz.

- **IntelliSense kullanma**. Kod Düzenleyicisi'nde girerken, listesi üyeleri, parametre bilgisi, hızlı bilgi, imza yardımcı olmak ve tam sözcüğü gibi IntelliSense bilgiler görüntülenir. Bu özellikler, metnin benzer eşleştirme destekler; Örneğin, sonuçları listeler listesi üyeleri için değil yalnızca, girdiğiniz karakterlerle Başlat girişleri aynı zamanda adlarını başka bir yerindeki karakter bileşimi içeren girdileri içerir. Daha fazla bilgi için bkz: [kullanarak IntelliSense](../ide/using-intellisense.md).

- **Kod girerken otomatik ekleme IntelliSense seçenekleri değiştirme**. Öneri modu için IntelliSense geçerek, yalnızca açıkça bunları seçerseniz, IntelliSense seçenekleri eklenen belirtebilirsiniz.

     Öneri Modu etkinleştirmeyi seçerseniz **Ctrl** + **Alt** + **boşluk** anahtarları veya menü çubuğunda seçin **Düzenle**, **IntelliSense**, **geçiş tamamlama modu**.

- **Kod parçacıklarını kullanma**. Yerleşik parçacıkları kullanabilir veya kendi parçacıkları oluşturabilirsiniz.

     Menü çubuğunda, kod parçacığında eklemek için seçin **Düzenle**, **IntelliSense**, **Ekle parçacığı** veya bir dosyada kısayol menüsünü açın ve seçin **parçacığı Ekle** . Daha fazla bilgi için bkz: [kod parçacıkları](../ide/code-snippets.md).

- **Kod hataları satır içi düzeltme**. Hızlı Eylemler kolayca düzenleme olanak tanır, oluşturmak veya aksi halde tek bir eylemle kodunu değiştirin. Ampul simgesini kullanarak bu eylemleri uygulanabilir ![küçük ampul simge](media/vs2015_lightbulbsmall.png "VS2017_LightBulbSmall"), basarak veya **Alt + Enter** veya **Ctrl +.** İmleci kod uygun satırında olduğunda. Bkz: [hızlı Eylemler](quick-actions.md) daha fazla bilgi için.

- **Gösterme ve code öğesi tanımını Düzenle**. Hızlı bir şekilde göstermek ve üye, değişken veya bir yerel gibi bir kod öğesi tanımlandığı modülü düzenleyin.

    Bir tanımı açılır pencerede açmak için öğe vurgulayın ve ardından **Alt + F12** anahtarları veya öğe için kısayol menüsünü açın ve ardından **Peek tanımı**. Bir tanım ayrı kod penceresinde açmak için öğe için kısayol menüsünü açın ve ardından **Tanıma Git**.

## <a name="navigating-within-your-code"></a>Kodunuzu içinde gezinme

 Bul ve belirli konumlara daha hızlı bir şekilde kodunuzda taşımak için çeşitli teknikleri kullanabilirsiniz.

- **Kod satırlarını yer işareti**. Yer işaretleri, hızlı bir şekilde kod bir dosyada belirli satırları gitmek için kullanabilirsiniz.

    Menü çubuğunda bir yer işareti ayarlamak için seçin **Düzenle**, **yer işaretleri**, **geçiş yer işareti**. Yer işaretleri bir çözüm için tüm görüntüleyebilirsiniz **yer işaretleri** penceresi. Daha fazla bilgi için bkz: [kodu ayarı işaretlerinde](../ide/setting-bookmarks-in-code.md).

- **Sembol tanımlarını bir dosyada arayın**. Sembol tanımlarını ve dosya adlarını bulmak için bir çözüm içinde arama yapabilirsiniz ancak arama sonuçları ad alanları veya yerel değişkenler eklemeyin.

   Menü çubuğunda, bu özelliğe erişmek için seçin **Düzenle**, **gitmek için**.

- **Genel yapısı, kodunuzun Gözat**. İçinde **Çözüm Gezgini**, arama ve sınıfları ve türleri ve üyeleri projelerinizde göz atın. Ayrıca simgelerini arama, bir yöntemin çağrı hiyerarşisi görüntülemek simge başvurularını bulun ve başka görevler gerçekleştirebilirsiniz. Bir kod öğesinde seçerseniz **Çözüm Gezgini**, ilişkili dosya açılır bir **Önizleme** sekmesi ve dosyayı öğedeki imlecin taşır. Daha fazla bilgi için bkz: [kodunu yapısı görüntüleme](../ide/viewing-the-structure-of-code.md).

## <a name="finding-items-faster"></a>Daha hızlı öğeleri bulma

IDE komutları, dosyalar ve yalnızca ilgili bilgiler, geçerli görev göstermek için aracı windows içeriğini filtreleme ek seçenekleri arasında arama yapabilirsiniz.

- **Araç pencereleri içeriğini filtre**. Gibi birçok aracı windows içeriğini içinde arama **araç**, **özellikleri** penceresinde ve **Çözüm Gezgini**, ancak görünen adları yalnızca öğeler Belirttiğiniz karakterler içeriyor.

- **Yalnızca hataları adresine görüntülemek**. Seçerseniz **filtre** düğmesini **hata listesi** araç çubuğunda görünür hatalarının sayısını azaltabilir **hata listesi** penceresi. Yalnızca hataları düzenleyicide açık olan dosyaları yalnızca geçerli dosyasındaki hataları ya da yalnızca geçerli projede hataları görüntüleyebilirsiniz. Ayrıca belirli hataları bulmak için Hata Listesi penceresi içinde arama yapabilirsiniz.

- **İletişim kutuları, menü komutları ve seçenekleri bulmak**. İçinde [hızlı başlatma](../ide/reference/quick-launch-environment-options-dialog-box.md) kutusuna, anahtar sözcükleri veya tümcecikleri bulmaya çalıştığınız öğeleri için girin. Girerseniz, örneğin, aşağıdaki seçenekler görünür `new project`:

    !['Yeni Proje' için hızlı başlatma sonuçları](../ide/media/productivity_quicklaunch.png "Productivity_QuickLaunch")

    **Hızlı başlatma** bağlantılar görüntüler **yeni proje** iletişim kutusu, **Yeni Öğe Ekle** iletişim kutusu ve projeler ve çözümler sayfasında **seçenekleri** iletişim kutusu, diğerlerinin yanı sıra. Hızlı Başlatma sonuçları proje dosyalarını ve aracı windows de içerir.

## <a name="debugging-code"></a>Kodda hata ayıklama

Hata ayıklama çok zaman kullanabileceğinden, ancak aşağıdaki ipuçları yardımıyla işlemi hızlandırmak.

- **Sayfa, uygulama veya site farklı tarayıcılarda test**. Kodunuzdaki hataları ayıklamanıza gibi dahil olmak üzere yüklü web tarayıcıları arasında kolayca geçiş yapabilirsiniz [sayfa denetçisi (Visual Studio)](http://msdn.microsoft.com/Library/65880969-1ad2-47be-85b9-bb12c81bf209), açmak zorunda kalmadan **Gözat ile** iletişim kutusu. Kullanabilirsiniz **hata ayıklama hedefi** açıktır listesi **standart** yanındaki araç **hata ayıklamayı Başlat** hata ayıklama gibi kullanmakta olduğunuz tarayıcı hızlı bir şekilde doğrulamak için düğmesini veya sayfalarını görüntüleyin.

    ![Web tarayıcısı hata ayıklama seçeneklerini](../ide/media/webbrowserdropdowntoolbar.png "WebBrowserDropDownToolbar")

- **Kesme geçici**. Kodu geçerli satırda geçici bir kesme noktası oluşturun ve hata ayıklayıcı eşzamanlı olarak başlatılır. Bu kod satırı isabet olduğunda hata ayıklayıcı kesme moduna girer. Daha fazla bilgi için bkz: [hata ayıklayıcısı ile kodlarda gezinme](../debugger/navigating-through-code-with-the-debugger.md).

    Bu özelliği kullanmayı tercih **Ctrl** + **F10** anahtarları veya bölün ve ardından istediğiniz kod satırı için kısayol menüsünü açın **çalıştırmak için imleç** .

- **Hata ayıklama sırasında yürütme noktasını taşıyın**. Geçerli yürütme noktası kodunun farklı bir bölüme taşıyın ve sonra o noktadan itibaren hata ayıklamayı yeniden başlatın. Bu yöntem, tüm bu bölümün erişmek için gerekli adımlar tekrar oluşturmak zorunda kalmadan bir bölüm kod hatalarını ayıklamak istediğiniz yararlıdır. Daha fazla bilgi için bkz: [hata ayıklayıcısı ile kodlarda gezinme](../debugger/navigating-through-code-with-the-debugger.md).

     Sarı Ok ucunu yürütme noktasını taşımak için aynı kaynak dosyasına next deyimi ayarlayın ve ardından istediğiniz bir konuma sürükleyin **F5** hata ayıklama devam etmek için anahtarı.

- **Değişkenleri için değer bilgilerini yakalama**. Bir DataTip kodunuzda bir değişkeni eklemek ve hata ayıklama tamamlandıktan sonra değişken için son bilinen değeri erişebilmesi için sabitleyin. Daha fazla bilgi için bkz: [veri İpuçlarında veri değerlerini görüntüleme](../debugger/view-data-values-in-data-tips-in-the-code-editor.md).

     Bir DataTip eklemek için hata ayıklayıcı kesme modunda olması gerekir. İmleç değişkeni üzerine yerleştirin ve görünür DataTip PIN düğmesini seçin. Hata ayıklama durduğunda değişkenini içeren kod satırı yanındaki kaynak dosyasında bir mavi PIN simgesi görünür. Mavi PIN noktası ise, en son hata ayıklama oturumunda değişkenin değeri olarak görünür.

- **Komut penceresi temizleyin**. İçeriğini silme [komut penceresi](../ide/reference/immediate-window.md) girerek tasarım zamanında `>cls` veya`>Edit.ClearAll`

     Ek komutlar hakkında daha fazla bilgi için bkz: [Visual Studio komut diğer adları](../ide/reference/visual-studio-command-aliases.md).

## <a name="managing-files-toolbars-and-windows"></a>Dosyaları, araç çubukları ve Windows yönetme

 Herhangi bir zamanda, birden çok kod dosyalarında çalışma ve uygulama geliştirme gibi birkaç araç pencereleri arasında taşıma. Aşağıdaki ipuçlarını kullanarak düzenlenmiş kullanmaya devam edebilir.

- **Sık kullandığınız dosyaları Düzenleyicisi'nde görünsün**. Böylece iyi kaç dosya düzenleyicide açık bağımsız olarak görünür kalmasını sekmesinin sol tarafındaki dosyalara sabitleyebilirsiniz.

     Bir dosya sabitlemek için dosyanın sekmesini seçin ve ardından **geçiş Pin durumu** düğmesi.

- **Belgeler ve windows için diğer izleyicilerin taşıma**. Uygulamaları geliştirirken birden fazla İzleyicisi'ni kullanırsanız, başka bir izleme düzenleyicide açık olan dosyaları taşıyarak, uygulamanızın bölümlerini üzerinde daha kolay çalışabilir. Belge ve aracı windows birlikte "rafts." oluşturmak için başka bir izleme ve sekmesinde hata ayıklayıcı windows gibi araç pencereleri yerleştirme taşıyabilirsiniz Daha fazla bilgi için bkz: [Visual Studio'da pencere düzenlerini özelleştirme](../ide/customizing-window-layouts-in-visual-studio.md).

     Ayrıca dosyaları daha kolay başka bir örneğini oluşturarak yönetebilirsiniz **Çözüm Gezgini** ve başka bir izleme taşıma. Başka bir örneğini oluşturmak için **Çözüm Gezgini**, bir kısayol menüsünü açın **Çözüm Gezgini**ve ardından **yeni Solution Explorer görünümü**.

- **Visual Studio'da yazı tiplerini özelleştirme**. Yazı tipi, boyut ve IDE içinde metni için kullanılan renk değiştirebilirsiniz. Örneğin, belirli bir kod öğeleri Düzenleyicisi ve aracı Windows veya IDE içinde yazı tipi rengini özelleştirebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: değişiklik yazı tiplerini ve renkleri](../ide/how-to-change-fonts-and-colors-in-visual-studio.md) ve [nasıl yapılır: değişiklik yazı tiplerini ve renkleri Düzenleyicisi'nde](../ide/reference/how-to-change-fonts-and-colors-in-the-editor.md).

## <a name="see-also"></a>Ayrıca bkz.

[Sık kullanılan komutlar için varsayılan klavye kısayolları](../ide/default-keyboard-shortcuts-for-frequently-used-commands-in-visual-studio.md)  
[Nasıl yapılır: menüleri ve araç çubuklarını özelleştirme](../ide/how-to-customize-menus-and-toolbars-in-visual-studio.md)  
[İzlenecek yol: basit bir uygulama oluşturma](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md)  
[Erişilebilirlik İpuçları ve Püf Noktaları](../ide/reference/accessibility-tips-and-tricks.md)