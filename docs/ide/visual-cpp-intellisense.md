---
title: Visual C++ IntelliSense
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 6fabaa7b1df2522abd9e76a8e4772a2f8111cfe9
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34748091"
---
# <a name="visual-c-intellisense"></a>Visual C++ IntelliSense

C++ için IntelliSense de tek başına dosyaları, C++ projesinin bir parçası olan dosyalar için kullanılabilir. Platformlar arası projelerinde IntelliSense özelliklerinden bazıları kullanılabilir olan *.cpp* ve *.c* paylaşılan kod projesinde bir Android veya iOS bağlamında olduğunda bile dosya.

## <a name="intellisense-features-in-c"></a>C++'ta IntelliSense özellikleri

IntelliSense kodlama daha kullanışlı hale özellikler kümesi için verilen bir addır. Farklı kişilerin ne kullanışlı olduğu konusunda farklı fikirleri sahip olduğundan, neredeyse tüm IntelliSense özellikleri etkinleştirilebilir veya devre dışı **seçenekleri** iletişim kutusunda **metin düzenleyici**  >  **C/C++** > **Gelişmiş**. **Seçenekleri** iletişim kutusu edinilebilir **Araçları** menü çubuğundaki menüsü.

![Aracı Seçenekleri iletişim kutusu](../ide/media/sintellisensecpptoolsoptions.PNG)

IntelliSense erişmek için menü öğeleri ve aşağıdaki görüntüde gösterilen klavye kısayollarını kullanabilirsiniz.

![IntelliSense menüsü](../ide/media/vs2015_cpp_intellisense_menu.png)

### <a name="statement-completion-and-member-list"></a>Deyim tamamlama ve üye listesi

Bir anahtar sözcük, türü, işlev, değişken adı veya derleyicisi tanır başka bir program öğesi yazmaya başladığınızda, word tamamlamanız Düzenleyici sunar.

Simgeler ve anlamlarını listesi için bkz: [sınıf görünümü ve Nesne Tarayıcısı simgeleri](../ide/class-view-and-object-browser-icons.md).

![Visual C&#43; &#43; tam sözcüğü penceresi](../ide/media/vs2015_cpp_complete_word.png)

Üye listesi çağrılan ilk kez geçerli bağlam için erişilebilir üyeleri yalnızca gösterir. Basarsanız **Ctrl**+**J** bundan sonra erişilebilirlik bağımsız olarak tüm üyeleri gösterir. Üçüncü bir kez çağırma durumunda bile daha geniş bir program öğeleri listesi gösterilir. Üye listesinde kapatabilirsiniz **seçenekleri** iletişim kutusunda **metin düzenleyici** > **C/C++** > **genel**  >  **Otomatik listesi üyeleri**.

![Visual C&#43; &#43; üye listesi](../ide/media/vs2015_cpp_list_members.png)

### <a name="parameter-help"></a>Parametre Yardım

Bir sınıf şablonu değişken bildirimi bir işlev çağrısı veya açılı ayraç açılan parantez yazdığınızda, düzenleyici küçük bir pencere işlevi veya oluşturucusu her yüklemesini parametre türleri ile gösterir. "Geçerli" parametre&mdash;imleç konumu temel&mdash;kalın değil. Parametre bilgileri kapatabilirsiniz **seçenekleri** iletişim kutusunda **metin düzenleyici** > **C/C++** > **genel**  >  **Parametre bilgilerini**.

![Visual C&#43; &#43; parametresi Yardım](../ide/media/vs_2015_cpp_param_help.png)

### <a name="quick-info"></a>Hızlı Bilgi

Fare imlecini bir değişken geldiğinizde türü bilgilerini gösteren satır içi ve türünün tanımlandığı üstbilgi küçük bir pencere görüntülenir. İşlev imzası görmek için işlev çağrısı gelin. Hızlı bilgisini kapatabilirsiniz **seçenekleri** iletişim kutusunda **metin düzenleyici** > **C/C++** > **Gelişmiş**  >  **Otomatik hızlı bilgi**.

![Visual C&#43; &#43; Quıckınfo](../ide/media/vs2015_cpp_quickinfo.png)

### <a name="error-squiggles"></a>Hata dalgalı çizgiler

Bir program öğesi (değişkeni, anahtar sözcüğü, kuşak, tür adı ve benzeri) altında dalgalı çizgiler dikkatinizi bir hata veya olası hata kodu çağırın. Hala uygulama yazmak ihtiyacınız olduğunu anımsatmak için bir iletme bildirimi yazdığınızda yeşil dalgalı görüntülenir. Olduğunda mor dalgalı paylaşılan bir proje Android bağlamında bir hata olacaktır Windows bağlamında çalışan, ancak bir şey girin, örneğin şu anda etkin değil, kodda bir hata görüntülenir. Derleyici hatası veya uyarısı uğraşmanız gereken active kodda kırmızı dalgalı gösterir.

![Visual C&#43; &#43; hata dalgalı çizgiler](../ide/media/vs2015_cpp_error_quiggles.png)

### <a name="code-colorization-and-fonts"></a>Kod renklendirme ve yazı tipleri

Varsayılan renk ve yazı tipleri değiştirilebilir **seçenekleri** iletişim kutusunda **ortam** > **yazı tiplerini ve renkleri**. Yazı tipleri birçok UI burada yalnızca Düzenleyicisi windows için değiştirebilirsiniz. C++'ye özgü ayarları "C++ ile"; başlayın diğer tüm diller için ayarlardır.

### <a name="cross-platform-intellisense"></a>Platformlar arası IntelliSense

Paylaşılan kod projesinde bile bir Android bağlamında çalışırken dalgalı çizgiler gibi bazı IntelliSense özellikleri kullanılamaz. Etkin olmayan projesinde bir hata ile sonuçlandı bazı kodlar yazmak, IntelliSense dalgalı çizgiler görüntülenmeye devam eder, ancak geçerli bağlamda hatalara dalgalı çizgiler daha farklı bir renk bulundukları.

Burada, Android ve iOS için oluşturmak için yapılandırılmış bir OpenGLES uygulama verilmiştir. Çizimde düzenlenmekte olan paylaşılan kod gösterir. İlk görüntüde etkin projeyi Android şöyledir:

![Etkin projeyi Android projesidir.](../ide/media/intellisensecppcrossplatform.png)

Aşağıdakilere dikkat edin:

- `#else` Satır 8 dalda gri çıkışı etkin olmayan bölge belirtmek için çünkü `__ANDROID__` Android projesi için tanımlanmış.

- Satırı 11 Tebrik değişkeni tanımlayıcısıyla başlatılır `HELLO`, mor dalgalı sahiptir. Bunun nedeni, hiçbir tanımlayıcı `HELLO` şu anda etkin iOS projesinde tanımlanır. Android projesi satır 11 derleme, ancak iOS olmaz. Bu, bir şeyin paylaşılan kod olduğundan şu anda etkin yapılandırmasında derler olsa da değiştirmeniz gerekir.

- Çizgi 12 bulunan kırmızı dalgalı tanımlayıcısı `BYE`; bu tanımlayıcı şu anda seçili etkin projedeki tanımlı değil.

Şimdi, etkin projeye değiştirmek **iOS.StaticLibrary** ve dalgalı çizgiler nasıl değiştiğini dikkat edin.

![iOS etkin projesi olarak seçilir.](../ide/media/intellisensecppcrossplatform2.png)

Aşağıdakilere dikkat edin:

- `#ifdef` Satır 6 dalda gri çıkışı etkin olmayan bölge belirtmek için çünkü `__ANDROID__` iOS projesi için tanımlı değil.

- Satırı 11 Tebrik değişkeni tanımlayıcısıyla başlatılır `HELLO`, şimdi kırmızı dalgalı sahiptir. Bunun nedeni, hiçbir tanımlayıcı `HELLO` şu anda etkin iOS projesinde tanımlanır.

- Satır 12 sahip mor dalgalı tanımlayıcısı `BYE`; bu tanımlayıcı tanımlı değil şu anda etkin **Android.NativeActivity** projesi.

### <a name="intellisense-for-stand-alone-files"></a>Tek başına dosyaları için IntelliSense

Herhangi bir projenin dışında tek bir dosyayı açtığınızda, IntelliSense hala alın. Etkinleştirmek veya belirli IntelliSense özelliklerini devre dışı **seçenekleri** iletişim kutusunda **metin düzenleyici** > **C/C++**  >  **Gelişmiş**. IntelliSense, projesinin bir parçası olmayan tek dosyaları için yapılandırmak için Ara **IntelliSense ve proje olmayan dosyaları için gözatma** bölümü.

![Visual C&#43; &#43; tek dosya IntelliSense](../ide/media/vs2015_cpp_single_file_intellisense.png)

Varsayılan olarak, tek dosyalı IntelliSense yalnızca kullanan standart üstbilgi dosyaları bulmak için içeren dizinler. Ek dizinler eklemek için kısayol menüsünü açmak **çözüm** düğümünü ve dizininize eklemek **hata ayıklama kaynak kodu** listesinde, aşağıdaki çizimde gösterildiği gibi:

![Bir yol için bir üstbilgi dosyası ekleme.](../ide/media/intellisensedebugyourcode.jpg)

## <a name="see-also"></a>Ayrıca bkz.

- [IntelliSense kullanma](../ide/using-intellisense.md)