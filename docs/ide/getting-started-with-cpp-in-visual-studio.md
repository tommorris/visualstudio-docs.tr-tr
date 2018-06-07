---
title: Visual Studio'da C++ kullanmaya başlama
description: ''
ms.custom: mvc
ms.date: 12/04/2017
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: tutorial
author: corob-msft
ms.author: tglee
manager: douge
dev_langs:
- CPP
ms.workload:
- cplusplus
ms.openlocfilehash: b49f83813bc5acd64de74a27a025bc78503902c5
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34747358"
---
# <a name="get-started-with-c-in-visual-studio"></a>Visual Studio'da C++ kullanmaya başlama

Bu hızlı başlangıç araçları ve Visual Studio ile C++ uygulamaları geliştirirken kullanabileceğiniz iletişim kutuları çoğu öğrenmeniz tamamlayın. Bir "Hello, World" oluşturma-stil konsol uygulaması sırasında tümleşik geliştirme ortamı (IDE) çalışma hakkında daha fazla bilgi edinin.

## <a name="prerequisites"></a>Önkoşullar

Bu hızlı başlangıç tamamlamak için C++ ile ilgili bilgi sahibi olmanız gerekmez, ancak bazı genel programlama ve hata ayıklama kavramlarını bilgi sahibi olmanız gerekir. Visual Studio belgelerinde nasıl c++'ta programlanacağı öğretmek değildir. C++ öğrenme kaynakları için iyi bir kılavuzdur [başlama](https://isocpp.org/get-started) ISO C++ Web sayfasında.

İzlemek için Visual Studio 2017 sürüm kopyasını 15.3 veya sonrasını ihtiyacınız **C++ ile masaüstü geliştirme** yüklü iş yükü. Yükleme için hızlı bir kılavuz için bkz: [Visual Studio yükleme C++ Destek](/cpp/build/vscpp-step-0-installation).

## <a name="create-a-console-app"></a>Bir konsol uygulaması oluşturma

Henüz çalışmıyorsa, Visual Studio'yu başlatın.

![Visual C ile IDE&#43; &#43; uygulanan ayarları](../ide/media/get-started-cpp-ide-layout.png)

Visual Studio açtıktan sonra IDE üç temel bölümlerini görebilirsiniz: aracı windows, menüleri ve araç çubukları ve ana penceresi alanı. Araç pencereleri ve uygulama penceresinin sol tarafında üzerinde sabitlenir. **Hızlı başlatma** kutusu, menü çubuğundaki ve standart araç en üstünde bulundu. Pencerenin merkezi içerir **başlangıç sayfası**. Bir çözüm ya da projeyi açtığınızda, düzenleyiciler ve tasarımcıları bu alanında görünür. Bir uygulama geliştirirken, çoğu zaman, bu merkezi alanında harcanır.

Visual Studio kullanan *projeleri* bir uygulama kodunu düzenlemenizi ve *çözümleri* projelerinizi düzenlemek için. Bir proje tüm seçenekleri, yapılandırmaları ve uygulamalarınızı oluşturmak için kullanılan kuralları içerir. Ayrıca, projenin tüm dosyaları ve dış dosyaları arasındaki ilişkiyi yönetir. Uygulamanızı oluşturmak için ilk olarak, yeni proje ve çözüm oluşturun.

### <a name="to-create-a-console-app-project"></a>Bir konsol uygulama projesi oluşturmak için

1. Menü çubuğunda seçin **Dosya > Yeni > Proje** açmak için **yeni proje** iletişim kutusu.

   ![Menü çubuğunda, Dosya > Yeni > Proje](../ide/media/get-started-cpp-file-new-project-menu.png)

1. İçinde **yeni proje** iletişim kutusunda **yüklü > Visual C++** zaten seçili değilse. Orta bölmede seçin **Windows konsol uygulaması** şablonu. İçinde **adı** düzenleme kutusu, girin *HelloApp*.

   ![Yeni Proje iletişim kutusu, uygulama projesi oluşturmak için kullanın](../ide/media/get-started-cpp-new-project-dialog.png)

   İletişim kutusu bileşenleri yükledikten ve Visual Studio iş yükleri bağlı olarak farklı seçenekleriniz olabilir. Visual C++ proje şablonları görmüyorsanız Visual Studio yükleyiciyi yeniden çalıştırın ve yüklemek gereken **C++ ile masaüstü geliştirme** iş yükü. Bunu doğrudan yapabilirsiniz **yeni proje** iletişim. Yükleyici başlatmak için tercih **açık Visual Studio yükleyicisi** iletişim kutusundaki bağlantı.

1. Seçin **Tamam** uygulama proje ve çözüm oluşturmak için düğmesi.

   HelloApp proje ve çözüm, bir Windows konsol uygulaması için temel dosyalarla oluşturulur ve otomatik olarak yüklenen **Çözüm Gezgini**. *HelloApp.cpp* dosya Kod Düzenleyicisi'nde açılır. Bu öğe görünür **Çözüm Gezgini**:

   ![Çözüm Gezgini'ndeki çözüme dosyaları](../ide/media/get-started-cpp-solution-explorer.png)

## <a name="add-code-to-the-app"></a>Uygulama için kod ekleme

Ardından, word görüntülemek için kod konsol penceresinde "Hello ifadesini" ekleyin.

### <a name="to-edit-code-in-the-editor"></a>Kod Düzenleyicisi'nde düzenlemek için

1. İçinde *HelloApp.cpp* dosya, satırından önce boş bir satıra girin `return 0;` ve ardından bu kodu girin:

   ```cpp
   cout << "Hello\n";
   ```

   Kırmızı kırık çizgi altında görünür `cout`. İşaretçinin üzerine getirirseniz, hata iletisi görüntülenir.

   ![Cout hata metni](../ide/media/get-started-cpp-intellisense-error.png)

   Hata iletisi de görünür **hata listesi** penceresi. Bu pencere seçerek görüntüleyebilirsiniz **Görünüm > hata listesi** menü çubuğunda.

   ![Hata Listesi penceresini hatası](../ide/media/get-started-cpp-error-list.png)

   Kodunuz için bir bildirim eksik [std::cout](/cpp/standard-library/iostream), içinde bulunan  *\<iostream >* üstbilgi dosyası.

1. Eklenecek *iostream* başlığı, sonra bu kodu girin `#include "stdafx.h"`:

   ```cpp
   #include <iostream>
   using namespace std;
   ```

   Büyük olasılıkla kodu girdiğiniz gibi görünen bir kutusu fark. Bu kutu otomatik tamamlama önerileri girdiğiniz karakterler içerir. Sınıfta veya arabirimde üye ve parametre bilgileri de dahil olmak üzere kodlama istemleri sağlayan C++ IntelliSense parçası kullanıcının. Kodu önceden tanımlanmış taşlarıdır kod parçacıkları de kullanabilirsiniz. Daha fazla bilgi için bkz: [kullanarak IntelliSense](../ide/using-intellisense.md) ve [kod parçacıkları](../ide/code-snippets.md).

   ![Sabit Kod Düzenleyicisi](../ide/media/get-started-cpp-cout-fix.png)

   Altında kırmızı kırık çizgi `cout` hata düzelttiğinizde kaybolur.

1. Değişiklikleri dosyaya kaydetmek için basın **Ctrl + S**.

## <a name="build-the-app"></a>Uygulaması oluşturma

Kodunuzu oluşturmak kolaydır. Menü çubuğunda seçin **Yapı > Yapı çözümü**. Visual Studio HelloApp çözüm oluşturur ve raporları ilerleme **çıkış** penceresi.

   ![HelloApp çözümü oluşturun](../ide/media/get-started-cpp-build-solution.gif)

## <a name="debug-and-test-the-app"></a>Hata ayıklama ve uygulamayı test etme

"Hello" sözcüğü konsol penceresinde görünür olup olmadığını görmek için HelloApp ayıklayabilirsiniz.

### <a name="to-debug-the-app"></a>Uygulama hata ayıklamak için

Hata ayıklayıcı başlatmayı seçin **hata ayıklama > hata ayıklamayı Başlat** menü çubuğunda.

![Hata ayıklama komutu Debug menüsünden Başlat](../ide/media/get-started-cpp-start-debugging-menu.png)

Hata ayıklayıcı başlar ve kodu çalıştırır. Konsol penceresi (bir komut istemi gibi görünüyor ayrı bir pencerede) birkaç saniye görünür ancak hata ayıklayıcı çalışmayı durdurduğunda hızlı bir şekilde kapatır. Metin görmek için program yürütme durdurmak için kesme noktası ayarlamanız gerekir.

### <a name="to-add-a-breakpoint"></a>Bir kesme noktası eklemek için

1. Düzenleyicisi'nde imleci satıra yerleştirin `return 0;`. Menü çubuğunda seçin **hata ayıklama > kesme**. Bir kesme noktası ayarlamak için sol kenar boşluğunda de tıklayabilirsiniz.

     ![Hata Ayıklama menüsünde kesim noktasını Değiştir komutu](../ide/media/get-started-cpp-toggle-breakpoint-menu.png)

     Düzenleyici penceresinin en sol kenar boşluğunda, kod satırının yanında kırmızı bir daire görünür.

     ![Pencere kenar boşluğunda belirtilen kesme noktası](../ide/media/get-started-cpp-breakpoint-set.png)

1. Hata ayıklama başlatmak için basın **F5**.

   Hata ayıklayıcıyı başlatır, ve word gösteren bir konsol penceresi görünür **Hello**.

   ![Konsol penceresinde Hello metin](../ide/media/get-started-cpp-helloapp-window.png)

1. Hata ayıklamayı durdurmak için basın **Shift + F5**.

Konsol projesi hata ayıklama hakkında daha fazla bilgi için bkz: [konsol projeleri](../debugger/debugging-preparation-console-projects.md).

## <a name="build-a-release-version-of-the-app"></a>Uygulama sürümü oluşturma

Her şeyi çalıştığını doğruladıktan, uygulamanın yayın derlemesi hazırlayabilirsiniz. Yayın hata ayıklama bilgilerini ve daha küçük, daha hızlı kodu oluşturmak için kullanım derleyici en iyi duruma getirme seçenekleri bırakın oluşturur.

### <a name="to-clean-the-solution-files-and-build-a-release-version"></a>Çözüm dosyalarını temizlemek ve yayın sürümünü oluşturmak için

1. Menü çubuğunda seçin **Yapı > temiz çözüm** Ara dosyaları ve önceki yapıları sırasında oluşturulan çıkış dosyaları silmek için.

   ![Build menüsünden temiz çözümü komutu](../ide/media/get-started-cpp-clean-solution-menu.png)

1. HelloApp çözüm yapılandırmasını değiştirmek için **hata ayıklama** için **sürüm**, araç çubuğunda, çözüm yapılandırmaları denetimindeki açılır seçin ve ardından **sürüm**.

   ![Uygulamanın yayın sürümünü oluşturma](../ide/media/get-started-cpp-set-release-configuration.png)

1. Çözümü oluşturun. Menü çubuğunda seçin **Yapı > Yapı çözümü**.

Bu yapı tamamlandığında kopyalayın ve herhangi bir komut istemi penceresinde çalıştırın bir uygulama oluşturduğunuzu düşünün. Bunu çok yapmanız, ancak büyük işlemleri için geçididir.

Bu hızlı başlangıç Tamamlanıyor Tebrikler! Daha fazla örnek keşfetmek, bkz: [Visual Studio örnekleri](../ide/visual-studio-samples.md).

## <a name="see-also"></a>Ayrıca bkz.

- [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanma](/cpp/ide/using-the-visual-studio-ide-for-cpp-desktop-development)
- [İzlenecek yol: C# veya Visual Basic ile basit uygulama oluşturma](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md)
- [Visual Studio için üretkenlik ipuçları](../ide/productivity-tips-for-visual-studio.md)
