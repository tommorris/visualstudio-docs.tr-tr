---
title: "Visual Studio'da C++ kullanmaya başlama | Microsoft Docs"
ms.custom: mvc
ms.date: 12/04/2017
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: get-started-article
author: corob-msft
ms.author: tglee
manager: ghogen
dev_langs:
- CPP
ms.workload:
- cplusplus
ms.openlocfilehash: 2e0e0709b8a1737e3f78268ec324d4481dac285a
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="get-started-with-c-in-visual-studio"></a>Visual Studio'da C++ kullanmaya başlama

Bu hızlı başlangıç araçları ve Visual Studio ile C++ uygulamaları geliştirirken kullanabileceğiniz iletişim kutuları çoğu öğrenmeniz tamamlayın. Bir "Hello, World" oluşturma-stil konsol uygulaması sırasında tümleşik geliştirme ortamı (IDE) çalışma hakkında daha fazla bilgi edinin.

## <a name="prerequisites"></a>Önkoşullar

Bu hızlı başlangıç tamamlamak için C++ ile ilgili bilgi sahibi olmanız gerekmez, ancak bazı genel programlama ve hata ayıklama kavramlarını bilgi sahibi olmanız gerekir. Visual Studio belgelerinde nasıl c++'ta programlanacağı öğretmek değildir. C++ öğrenme kaynakları için iyi bir kılavuzdur [Get Started](https://isocpp.org/get-started) ISO C++ Web sayfasında.

İzlemek için Visual Studio 2017 sürüm kopyasını 15.3 veya sonrasını ihtiyacınız **C++ ile masaüstü geliştirme** yüklü iş yükü. Yükleme için hızlı bir kılavuz için bkz: [Visual Studio yükleme C++ Destek](/cpp/build/vscpp-step-0-installation).

## <a name="create-a-console-app"></a>Bir konsol uygulaması oluşturma

Henüz çalışmıyorsa, Visual Studio'yu başlatın.

![Visual C# 43; &#43;IDE; uygulanan ayarları](../ide/media/get-started-cpp-ide-layout.png "IDE Visual C# 43; &#43; ile uygulanan ayarları")

Visual Studio açtıktan sonra IDE üç temel bölümlerini görebilirsiniz: aracı windows, menüleri ve araç çubukları ve ana penceresi alanı. Araç pencereleri ve uygulama penceresinin sol tarafında üzerinde sabitlenir. **Hızlı başlatma** kutusu, menü çubuğundaki ve standart araç en üstünde bulundu. Pencerenin merkezi içerir **başlangıç sayfası**. Bir çözüm ya da projeyi açtığınızda, düzenleyiciler ve tasarımcıları bu alanında görünür. Bir uygulama geliştirirken, çoğu zaman, bu merkezi alanında harcanır.

Visual Studio kullanan *projeleri* bir uygulama kodunu düzenlemenizi ve *çözümleri* projelerinizi düzenlemek için. Bir proje tüm seçenekleri, yapılandırmaları ve uygulamalarınızı oluşturmak için kullanılan kuralları içerir. Ayrıca, projenin tüm dosyaları ve dış dosyaları arasındaki ilişkiyi yönetir. Uygulamanızı oluşturmak için ilk olarak, yeni proje ve çözüm oluşturun.

### <a name="to-create-a-console-app-project"></a>Bir konsol uygulama projesi oluşturmak için

1. Menü çubuğunda seçin **Dosya > Yeni > Proje** açmak için **yeni proje** iletişim kutusu.

   ![Menü çubuğunda, Dosya > Yeni > Proje](../ide/media/get-started-cpp-file-new-project-menu.png "menü çubuğunda, Dosya > Yeni > Proje")

1. İçinde **yeni proje** iletişim kutusunda **yüklü > Visual C++** zaten seçili değilse. Orta bölmede seçin **Windows konsol uygulaması** şablonu. İçinde **adı** düzenleme kutusu, girin *HelloApp*.

   ![Yeni Proje iletişim kutusu, uygulama projesi oluşturmak için kullanın](../ide/media/get-started-cpp-new-project-dialog.png "yeni proje iletişim kutusu, uygulama projesi oluşturmak için kullanın")

   İletişim kutusu bileşenleri yükledikten ve Visual Studio iş yükleri bağlı olarak farklı seçenekleriniz olabilir. Visual C++ proje şablonları görmüyorsanız Visual Studio yükleyiciyi yeniden çalıştırın ve yüklemek gereken **C++ ile masaüstü geliştirme** iş yükü. Bunu doğrudan yapabilirsiniz **yeni proje** iletişim. Yükleyici başlatmak için tercih **açık Visual Studio yükleyicisi** iletişim kutusundaki bağlantı.

1. Seçin **Tamam** uygulama proje ve çözüm oluşturmak için düğmesi.

   HelloApp proje ve çözüm, bir Windows konsol uygulaması için temel dosyalarla oluşturulur ve otomatik olarak yüklenen **Çözüm Gezgini**. Kod Düzenleyicisi'nde HelloApp.cpp dosya açılır. Bu öğe görünür **Çözüm Gezgini**:

   ![Çözüm Gezgini'ndeki çözüme dosyaları](../ide/media/get-started-cpp-solution-explorer.png "Çözüm Gezgini'ndeki çözüme dosyaları")

## <a name="add-code-to-the-app"></a>Uygulama için kod ekleme

Ardından, word görüntülemek için kod konsol penceresinde "Hello ifadesini" ekleyin.

### <a name="to-edit-code-in-the-editor"></a>Kod Düzenleyicisi'nde düzenlemek için

1. HelloApp.cpp dosyasında satırdan önce boş bir satır girin `return 0;` ve ardından bu kodu girin:

   ```cpp
   cout << "Hello\n";
   ```

   Kırmızı kırık çizgi altında görünür `cout`. İşaretçinin üzerine getirirseniz, hata iletisi görüntülenir.

   ![Cout hata metni](../ide/media/get-started-cpp-intellisense-error.png "cout hata metni")

   Hata iletisi de görünür **hata listesi** penceresi. Bu pencere seçerek görüntüleyebilirsiniz **Görünüm > hata listesi** menü çubuğunda.

   ![Hata Listesi penceresini hata](../ide/media/get-started-cpp-error-list.png "hata listesi penceresini hatası")

   Kodunuz için bir bildirim eksik [std::cout](/cpp/standard-library/iostream), içinde bulunan \<iostream > Üstbilgi dosyası.

1. İostream üstbilgisi eklemek için sonra bu kodu girin `#include "stdafx.h"`:

   ```cpp
   #include <iostream>
   using namespace std;
   ```

   Büyük olasılıkla kodu girdiğiniz gibi görünen bir kutusu fark. Bu kutu otomatik tamamlama önerileri girdiğiniz karakterler içerir. Sınıfta veya arabirimde üye ve parametre bilgileri de dahil olmak üzere kodlama istemleri sağlayan C++ IntelliSense parçası kullanıcının. Kodu önceden tanımlanmış taşlarıdır kod parçacıkları de kullanabilirsiniz. Daha fazla bilgi için bkz: [kullanarak IntelliSense](../ide/using-intellisense.md) ve [kod parçacıkları](../ide/code-snippets.md).

   ![Sabit Kod düzenleyicisinde](../ide/media/get-started-cpp-cout-fix.png "sabit Kod Düzenleyicisi")

   Altında kırmızı kırık çizgi `cout` hata düzelttiğinizde kaybolur.

1. Değişiklikleri dosyaya kaydetmek için basın **Ctrl + S**.

## <a name="build-the-app"></a>Uygulaması oluşturma

Kodunuzu oluşturmak kolaydır. Menü çubuğunda seçin **Yapı > Yapı çözümü**. Visual Studio HelloApp çözüm oluşturur ve raporları ilerleme **çıkış** penceresi.

   ![HelloApp çözümü derleme](../ide/media/get-started-cpp-build-solution.gif "HelloApp çözümü oluşturun")

## <a name="debug-and-test-the-app"></a>Hata ayıklama ve uygulamayı test etme

"Hello" sözcüğü konsol penceresinde görünür olup olmadığını görmek için HelloApp ayıklayabilirsiniz.

### <a name="to-debug-the-app"></a>Uygulama hata ayıklamak için

1. Hata ayıklayıcı başlatmayı seçin **hata ayıklama > hata ayıklamayı Başlat** menü çubuğunda.

   ![Hata ayıklama menüsündeki komutu hata ayıklamayı Başlat](../ide/media/get-started-cpp-start-debugging-menu.png "hata ayıklamayı Başlat menüsündeki hata ayıklama")

   Hata ayıklayıcı başlar ve kodu çalıştırır. Konsol penceresi (bir komut istemi gibi görünüyor ayrı bir pencerede) birkaç saniye görünür ancak hata ayıklayıcı çalışmayı durdurduğunda hızlı bir şekilde kapatır. Metin görmek için program yürütme durdurmak için kesme noktası ayarlamanız gerekir.

### <a name="to-add-a-breakpoint"></a>Bir kesme noktası eklemek için

1. Düzenleyicisi'nde imleci satıra yerleştirin `return 0;`. Menü çubuğunda seçin **hata ayıklama > kesme**. Bir kesme noktası ayarlamak için sol kenar boşluğunda de tıklayabilirsiniz.

     ![Hata Ayıklama menüsünde kesme komutu geçiş](../ide/media/get-started-cpp-toggle-breakpoint-menu.png "Debug menüsünden kesme komutu")

     Düzenleyici penceresinin en sol kenar boşluğunda, kod satırının yanında kırmızı bir daire görünür.

     ![Kesme noktası belirtilen pencere kenar boşluğunda](../ide/media/get-started-cpp-breakpoint-set.png "kesme noktası belirtilen pencere kenar boşluğunda")

1. Hata ayıklama başlatmak için basın **F5**.

   Hata ayıklayıcıyı başlatır, ve word gösteren bir konsol penceresi görünür **Hello**.

   ![Metin konsol penceresinde Hello](../ide/media/get-started-cpp-helloapp-window.png "Hello konsol penceresinde metin")

1. Hata ayıklamayı durdurmak için basın **Shift + F5**.

Konsol projesi hata ayıklama hakkında daha fazla bilgi için bkz: [konsol projeleri](../debugger/debugging-preparation-console-projects.md).

## <a name="build-a-release-version-of-the-app"></a>Uygulama sürümü oluşturma

Her şeyi çalıştığını doğruladıktan, uygulamanın yayın derlemesi hazırlayabilirsiniz. Yayın hata ayıklama bilgilerini ve daha küçük, daha hızlı kodu oluşturmak için kullanım derleyici en iyi duruma getirme seçenekleri bırakın oluşturur.

### <a name="to-clean-the-solution-files-and-build-a-release-version"></a>Çözüm dosyalarını temizlemek ve yayın sürümünü oluşturmak için

1. Menü çubuğunda seçin **Yapı > temiz çözüm** Ara dosyaları ve önceki yapıları sırasında oluşturulan çıkış dosyaları silmek için.

   ![Yapı menüsünde çözümü Temizle komutunu](../ide/media/get-started-cpp-clean-solution-menu.png "ExploreIDE CleanSolution")

1. HelloApp çözüm yapılandırmasını değiştirmek için **hata ayıklama** için **sürüm**, araç çubuğunda, çözüm yapılandırmaları denetimindeki açılır seçin ve ardından **sürüm**.

   ![Uygulama sürümü yapı](../ide/media/get-started-cpp-set-release-configuration.png "C ++ IDE_ChangingBuildtoRelease")

1. Çözümü oluşturun. Menü çubuğunda seçin **Yapı > Yapı çözümü**.

Bu yapı tamamlandığında kopyalayın ve herhangi bir komut istemi penceresinde çalıştırın bir uygulama oluşturduğunuzu düşünün. Bunu çok yapmanız, ancak büyük işlemleri için geçididir.

Bu hızlı başlangıç Tamamlanıyor Tebrikler! Daha fazla örnek keşfetmek, bkz: [Visual Studio örnekleri](../ide/visual-studio-samples.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ Masaüstü Geliştirmesi için Visual Studio IDE Kullanma](/cpp/ide/using-the-visual-studio-ide-for-cpp-desktop-development)  
[İzlenecek yol: C# veya Visual Basic ile basit uygulama oluşturma](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md)  
[Visual Studio için Üretkenlik İpuçları](../ide/productivity-tips-for-visual-studio.md)  
[Visual Studio Örnekleri](../ide/visual-studio-samples.md)  
[Visual Studio ile Geliştirmeye Başlama](../ide/get-started-developing-with-visual-studio.md)
