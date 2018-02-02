---
title: "Visual Studio'da R ile çalışmaya başlama | Microsoft Docs"
description: "Visual Studio projesi oluşturma, etkileşimli pencere dahil R kullanarak bir gözden geçirme kod düzenleme ve hata ayıklama."
ms.custom: 
ms.date: 06/29/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
ms.topic: get-started-article
caps.latest.revision: 
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- data-science
ms.openlocfilehash: cf8df86322e10054dee5dbcee95839506f690306
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2018
---
# <a name="getting-started-with-r-tools-for-visual-studio"></a>Visual Studio için R araçlarını kullanmaya başlama

R araçları Visual Studio (yüklü RTVS için) sahip olduğunda (bkz [yükleme](installing-r-tools-for-visual-studio.md)), bu araçlar sağlayan deneyiminin kısaca hızlı bir şekilde elde edebilirsiniz. 

## <a name="create-an-r-project"></a>Bir R projesi oluşturma

1. Visual Studio'yu başlatın.
1. Seçin **Dosya > Yeni > Proje...** (Ctrl + Shift + N)
1. "R" gelen altında projenizi **şablonları > R**, bir ad ve konum proje verin ve seçin **Tamam**:

   ![R (RTVS VS2017 içinde) Visual Studio'da yeni proje iletişim kutusu](media/getting-started-01-new-project.png)

1. Proje oluşturulduktan sonra aşağıdaki windows bakın:

    - Visual Studio Çözüm Gezgini'nde, projenize içeren bir içinde gördüğünüz sağ tarafta olan *çözüm*. (Çözümler, farklı türlerde projeleri herhangi bir sayıda içerebilir; bkz [projeleri](r-projects-in-visual-studio.md) Ayrıntılar için.
    - Sol üst üzerinde yeni bir R dosyadır (`script.R`), kaynak kodu tüm Visual Studio ile düzenleyebileceğiniz düzenleme özellikleri.
    - Sol alt üzerinde **R etkileşimli** , etkileşimli olarak geliştirme ve test kullanabilirsiniz kod penceresi.

> [!Note]
> Kullanabileceğiniz **R etkileşimli** farklı proje türü yüklendiğinde herhangi bir projeyle açık ve hatta kalmadan penceresi. Yalnızca select **R Araçlar > Windows > R etkileşimli** dilediğiniz zaman.

## <a name="explore-the-interactive-window-and-intellisense"></a>IntelliSense ve etkileşimli penceresini keşfedin

1. Etkileşimli pencere yazarak çalışma test `3 + 4` ve ardından sonuçları görmek için girin:

    ![Visual Studio 2017 (VS2017) R etkileşimli penceresinde](media/getting-started-02-interactive1.png)

1. Biraz daha karmaşık, bir şey girin `ds <- c(1.5, 6.7, 8.9) * 1:12`ve ardından girin `ds` sonuçları görmek için:

    ![Visual Studio'da R için ek etkileşimli örnek](media/getting-started-03-interactive2.png)

1. Yazın `mean(ds)` ancak yazdığınız hemen dikkat `m` veya `me`, Visual Studio IntelliSense otomatik tamamlama seçenekleri sağlar. İstediğiniz tamamlama listede seçildiğinde eklemek için SEKME tuşuna basın; Ok tuşları veya fare seçimle değiştirebilirsiniz.

    ![IntelliSense kod girerken görünmesini](media/getting-started-04-intellisense1.png)

1. Tamamladıktan sonra `mean`, açma parantezi yazın `(` ve nasıl IntelliSense, satır içi Yardım işlevi için sunar not edin:

    ![Bir işlev yardımını gösteren IntelliSense](media/getting-started-05-intellisense2.png)

1. Satır tamamlamak `mean(ds)` ve sonuçları görmek için Enter tuşuna basın (`[1] 39.51667`).

1. Etkileşimli pencere şekilde girme konusunda yardıma ile tümleşik `?mean` görüntüler bu işlev için Yardım **R Yardım** Visual Studio'daki. Ayrıntılar için bkz [R araçları Visual Studio için Yardım](getting-started-help.md).

    ![Visual Studio'da R Help penceresi](media/getting-started-06-help.png)

1. Gibi bazı komutlar `plot(1:100)`, çıktı doğrudan etkileşimli pencerede görüntülendiğinde Visual Studio'da yeni bir pencere aç:

    ![Visual Studio'da bir çizim görüntüleme](media/getting-started-07-plot-window.png)

Etkileşimli penceresi de geçmişinizi gözden geçirin, yükleme ve çalışma alanları kaydedin, bir hata ayıklayıcısını ve kopyala-yapıştır kullanmak yerine kaynak kodu dosyaları ile etkileşim sağlar. Bkz: [R etkileşimli penceresiyle çalışma](interactive-repl-for-r-in-visual-studio.md) Ayrıntılar için.

## <a name="experience-code-editing-features"></a>Özellikleri düzenleme deneyimi kodu

Etkileşimli pencere kısaca çalışmak IntelliSense gibi ayrıca Kod düzenleyicisinde iş temel düzenleme özellikleri gösterir. Önce aynı kodunu girerseniz, aynı otomatik tamamlama ve IntelliSense istemleri, ancak çıktı bakın.

Kod yazma bir `.R` dosya tüm kodunuz aynı anda görmenizi sağlar ve küçük değişiklikler yapmak ve etkileşimli penceresinde kod çalıştırarak sonucu hızlıca görmek kolaylaştırır. Bir proje ile istediğiniz sayıda dosyaları da sahip olabilirsiniz. Kodu bir dosyada olduğunda da (Bu makalenin sonraki bölümlerinde açıklanmıştır) hata ayıklayıcısında adım adım çalıştırabilirsiniz. Bu özellikler, hesaplama algoritmalarına geliştirme ve özellikle tüm ara sonuçların incelemek istediğinizde bir veya daha fazla veri kümeleri, işlemek için kod yazma faydalıdır.

Örnek olarak, aşağıdaki adımları keşfetmek için biraz kod oluşturma [merkezi sınırı Teoremi](https://en.wikipedia.org/wiki/Central_limit_theorem) (Wikipedia). (Bu örnekte gelen uyarlanmış, *R Kılavuzu* Paul Teetor tarafından.)

1. İçinde `script.R` Düzenleyicisi, aşağıdaki kodu girin:

    ```R
    mu <- 50
    stddev <- 1
    N <- 10000
    pop <- rnorm(N, mean = mu, sd = stddev)
    plot(density(pop), main = "Population Density", xlab = "X", ylab = "")
    ```

1. Hızla sonuçları görmek için tüm kod (Ctrl + A) seçin ve Ctrl + Enter tuşuna basın veya sağ tıklatın ve seçin **içinde etkileşimli yürütme**. Doğrudan sonucu gösteren bir çizim penceresinde yazdığınız gibi tüm seçili kod etkileşimli penceresinde çalıştırılır:

    ![Visual Studio'da bir çizim görüntüleme](media/getting-started-08-plot1.png)

1. Tek bir satır için Ctrl + Enter etkileşimli penceresinde bu satırını çalıştırmak için herhangi bir zamanda yalnızca basın.

> [!Tip]
> Düzenlemeleri ve Ctrl + Enter tuşuna basarak (veya Ctrl + A olan her şeyi seçip Ctrl + Enter tuşuna basarak) desenini öğrenin hızlı bir şekilde kod çalıştırabilir. Bunun yapılması, aynı işlemleri için fareyi kullanmaktan çok daha etkilidir.
> 
> Ayrıca, sürükleyin ve çizim penceresi Visual Studio çerçeve dışında bırakma ve ekranınızda başka istediğiniz zaman yerleştirin. Ardından istediğiniz ve ardından bir görüntü veya PDF dosyasını kaydedin boyutlarına çizim penceresini yeniden boyutlandırabilirsiniz.

1. İkinci bir çizim dahil etmek için kod birkaç daha fazla satırı ekleyin:

    ```R
    n <- 30
    samp.means <- rnorm(N, mean = mu, sd = stddev / sqrt(n))
    lines(density(samp.means))
    ```

1. CTRL + A ve Ctrl + Enter yeniden aşağıdaki sonucu oluşturan kodu çalıştırmak için tuşuna basın:

    ![Visual Studio'da güncelleştirilmiş çift çizim](media/getting-started-09-plot2.png)

1. İkinci çizmek için ilk çizim dikey ölçek belirler sorundur (ile `lines`) uygun değil. Bu sorunu düzeltmek için ayarlamak ihtiyacımız `ylim` parametresini `plot` diyebilirsiniz, ama düzgün maksimum dikey değerini hesaplamak üzere kod eklemek ihtiyacımız böylece yapın. Bu satır satır etkileşimli penceresinde yapılması olduğundan kullanışsız kullanmak için kodu yeniden düzenlemek ihtiyacımız `samp.means` çağırmadan önce `plot`. Kod dosyasında, ancak biz kolayca uygun düzenlemeleri yapabilirsiniz:

    ```R
    mu <- 50
    stddev <- 1
    N <- 10000
    pop <- rnorm(N, mean = mu, sd = stddev)

    n <- 30
    samp.means <- rnorm(N, mean = mu, sd = stddev / sqrt(n))
    max.samp.means <- max(density(samp.means)$y)

    plot(density(pop), main = "Population Density",
        ylim = c(0, max.samp.means),
        xlab = "X", ylab = "")
    lines(density(samp.means))
    ```

1. CTRL + A ve Ctrl + Enter yeniden sonuçları görmek için:

    ![Visual Studio'da düzgün ölçeği, güncelleştirilmiş çift çizim](media/getting-started-10-plot3.png)

Daha fazla Düzenleyici'de yapabilirsiniz yoktur. Ayrıntılar için bkz [kod düzenleme](editing-r-code-in-visual-studio.md), [IntelliSense](r-intellisense.md), ve [kod parçacıkları](code-snippets-for-r.md).

## <a name="debugging-your-code"></a>Kodunuzun hatalarını ayıklama

Visual Studio anahtar gücü hata ayıklama kullanıcı Arabiriminde biridir. RTVS bu güçlü bir temel üstünde oluşturur ve yenilikçi UI gibi ekler [değişken Gezgini ve veri tablosu Görüntüleyicisi](variable-explorer.md). Burada, yalnızca hata ayıklama bir ilk bakalım.

1. Başlamak için her şeyi bitti kadarki kullanarak temizlemek için geçerli çalışma alanı sıfırlama **R Araçlar > oturum > sıfırlama** menü komutu. Varsayılan olarak, sonra da hata ayıklayıcı tarafından kullanılan geçerli oturum için etkileşimli pencerede yaptığınız her şey tahakkuk. Oturum sıfırlayarak, hata ayıklama oturumu önceden var olan veri içermeyen başladığından emin olmak. **Sıfırlama** komutu, ancak etkilemez, `script.R` kaynak dosyası, yönetilen ve çalışma dışında kaydedilen olduğundan.

1. İle `script.R` dosyası önceki bölümde oluşturduğunuz, ile başlayan satırında bir kesme noktası belirleyerek `pop <-` bu satırda düzeltme işareti yerleştirme ve F9 tuşuna basarak veya seçerek **hata ayıklama > kesme** menüsü komutu. Alternatif olarak, sol kenar boşluğu (veya cilt payı) kırmızı kesme noktası nokta göründüğü için bu satırı tıklamanız yeterlidir:

    ![Düzenleyicide kesme noktası ayarlama](media/getting-started-11-debug1.png)

1. Hata ayıklayıcı kod ile başlatma `script.R` ya da seçerek **kaynak başlangıç dosya** araç çubuğunda seçme **hata ayıklama > kaynak başlangıç dosya** menü öğelerini veya F5 tuşuna basarak. Visual Studio hata ayıklama moduna girer ve kod çalışmaya başlar. Bu, ancak kesme ayarladığınız satırda durdurur:

    ![Visual Studio hata ayıklayıcısında bir kesme noktası durduruluyor](media/getting-started-12-debug2.png)

1. Hata ayıklama sırasında Visual Studio kodunuzu satır adım olanağı sağlar. Ayrıca, İşlevler, bunları Adımlama adımla veya bunları dışında çağıran bağlamını adım. Bu özellikleri, diğerlerinin yanı sıra bulunabilir **hata ayıklama** menüsü, düzenleyici ve hata ayıklama araç çubuğu sağ bağlam menüsü:

    ![Araç çubuğu Visual Studio'da hata ayıklama](media/getting-started-13-debug3.png)

1. Kesme noktasında durduğunda değişkenlerin değerleri inceleyebilirsiniz. Bulun **otomobiller** Visual Studio ve adlı alt boyunca sekmesini seçin penceresinde **Yereller**. **Yereller** penceresi, geçerli bir noktada programı yerel değişkenleri gösterir. Daha önce kesme üzerinde durdurduysanız, gördüğünüz `pop` değişkeni henüz tanımlanmadı. Şimdi kullanmak **hata ayıklama > Step Over** komutu (F10) ve görmek için değer `pop` görünür:

    ![Visual Studio'da yerel öğeler penceresi](media/getting-started-14-debug4.png)

1. Genel kapsamlı ve paket kapsamları dahil olmak üzere farklı kapsamlar değişkenleri incelemek için [değişken Explorer](variable-explorer.md). Değişken Explorer ayrıca sıralanabilir sütunlarla Tablo görünümüne geçin ve verilerini bir CSV dosyasına verme olanağı sağlar.

    ![Genişletilmiş Görünüm değişken Gezgini](media/variable-explorer-expanded-results.png)

1. Satır veya select programımı adımlarken devam **devam** için tamamlama (veya sonraki kesme) (F5).

Derinlemesine için bkz: [hata ayıklama](debugging-r-in-visual-studio.md) ve [değişken Explorer](variable-explorer.md).

## <a name="next-steps"></a>Sonraki adımlar

Bu kılavuzda R projeleri, etkileşimli penceresini kullanarak öğrendiğinize, düzenleme ve Visual Studio'da hata ayıklamayı kodu. Daha fazla yetenekleri keşfetmeye devam etmek için aşağıdaki makaleler yanı sıra içeriği tabloda gösterilen makaleleri bakın:

- [Örnek Proje](getting-started-samples.md)
- [Kodu düzenleme](editing-r-code-in-visual-studio.md)
- [Hata Ayıklama](debugging-r-in-visual-studio.md)
- [Çalışma Alanları](r-workspaces-in-visual-studio.md)
- [Verileri görselleştirme](visualizing-data-with-r-in-visual-studio.md)
