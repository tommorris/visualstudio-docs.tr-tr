---
title: C++ ve Python ile çalışma
description: Karışık mod hata ayıklama da dahil olmak üzere Visual Studio'yu kullanarak Python için C++ uzantısı oluşturma için kullanılan bir kılavuz.
ms.date: 06/27/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: fc885df4b85e89c85c366f033113678243fbfe0b
ms.sourcegitcommit: 4ab232758d308bda742434beff8349a80c167890
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37847823"
---
# <a name="creating-a-c-extension-for-python"></a>Python için C++ uzantısı oluşturma

C++ (veya C) yazılmış modüller, alt düzey işletim sistemi özelliklerine erişimi etkinleştirmek için de bir Python yorumlayıcısı yeteneklerini genişletmek için yaygın olarak kullanılır. Üç birincil modül türü vardır:

- Hızlandırıcı modülleri: Python yorumlanan bir dil olduğundan, belirli kod parçaları c++'ta daha yüksek performans için yazılabilir.
- Sarmalayıcı modülleri: Python'dan kullanımı kolay olan daha fazla bir "Pythonic" API'yi kullanıma sunmak veya Python kodu için var olan C/C++ arabirimleri kullanıma sunar.
- Alt düzey sistem erişim modülleri: CPython çalışma zamanı, işletim sistemi ya da temel alınan donanım düşük düzeyli özelliklerine erişmek için oluşturuldu.

Bu makalede, hiperbolik tanjantı hesaplar ve Python kodu çağıran CPython için C++ uzantısı modülü oluşturma sürecinde size yol gösterir. İlk yordam aynı yordamı C++'da uygulama göreli performans kazancı göstermek için Python uygulanır.

Burada uygulanan yaklaşıma için standart CPython uzantıları bölümünde anlatıldığı gibi olan [Python belgeleri](https://docs.python.org/3/c-api/). Bu ve diğer yolları arasında bir karşılaştırma altında açıklanan [alternatif yaklaşımlar](#alternative-approaches) bu makalenin sonunda.

Bu izlenecek yolda tamamlanmış örnekten bulunabilir [python-samples-vs-cpp-extension](https://github.com/Microsoft/python-sample-vs-cpp-extension) (GitHub).

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio 2017 ile her ikisini de **C++ ile masaüstü geliştirme** ve **Python geliştirme** varsayılan seçeneklerle yüklü iş yükleri.
- İçinde **Python geliştirme** iş yükü, aynı zamanda için sağdaki kutusunu işaretlemeniz **Python yerel geliştirme araçları**. Bu makalede açıklanan yapılandırmaların çoğu için bu seçeneği ayarlar. (Bu seçenek ayrıca C++ iş yükünü otomatik olarak içerir.)

    ![Python yerel geliştirme araçları seçeneği](media/cpp-install-native.png)

    > [!Tip]
    > Yükleme **veri bilimi ve analitik uygulamalar** iş yükü, Python de içerir ve **Python yerel geliştirme araçları** varsayılan seçeneği.

Daha fazla bilgi için [Visual Studio için Python desteği yükleme](installing-python-support-in-visual-studio.md), Visual Studio'nun diğer sürümlerinde kullanma dahil olmak üzere. Python ayrı olarak yüklerseniz, seçtiğinizden emin olun **hata ayıklama sembolleri Yükle** ve **indirme hata ayıklama ikililerini** altında **Gelişmiş Seçenekler** yükleyicisi. Bu seçenek, hata ayıklama derlemesi yapmayı tercih ederseniz gerekli hata ayıklama kitaplıklarını kullanılabilir olmasını sağlar.

## <a name="create-the-python-application"></a>Python uygulaması oluşturma

1. Seçerek Visual Studio'da yeni Python projesi oluşturma **Dosya > Yeni > Proje**. Seç "Python" için arama **Python uygulaması** şablonu, uygun bir ad ve konum verin ve seçin **Tamam**.

1. C++ ile çalışmak bir 32 bit Python yorumlayıcısı (önerilen Python 3.6) kullanmanız gerekir. İçinde **Çözüm Gezgini** penceresi Visual Studio'nun proje düğümünü genişletin ve ardından genişletin **Python ortamları** düğümü. Varsayılan (veya kalın veya "genel varsayılan" ile etiketlenmiş) 32-bit ortamından görmüyorsanız, ardından ilgili yönergeleri uygulayın [seçerek bir proje için bir Python ortamı](selecting-a-python-environment-for-a-project.md). Yüklü bir 32-bit yorumlayıcı yoksa bkz [yükleme Python yorumlayıcılarını](installing-python-interpreters.md).

1. Projenin `.py` dosya, hesaplama (matematik kitaplığı için daha kolay karşılaştırma kullanmadan uygulanan) bir hiperbolik tanjant benchmarks aşağıdaki kodu yapıştırın. El ile bazı deneyimi için kodu girin çekinmeyin [düzenleme özellikleri Python](editing-python-code-in-visual-studio.md).

    ```python
    from itertools import islice
    from random import random
    from time import perf_counter

    COUNT = 500000  # Change this value depending on the speed of your computer
    DATA = list(islice(iter(lambda: (random() - 0.5) * 3.0, None), COUNT))

    e = 2.7182818284590452353602874713527

    def sinh(x):
        return (1 - (e ** (-2 * x))) / (2 * (e ** -x))

    def cosh(x):
        return (1 + (e ** (-2 * x))) / (2 * (e ** -x))

    def tanh(x):
        tanh_x = sinh(x) / cosh(x)
        return tanh_x

    def sequence_tanh(data):
        '''Applies the hyperbolic tangent function to map all values in
        the sequence to a value between -1.0 and 1.0.
        '''
        result = []
        for x in data:
            result.append(tanh(x))
        return result

    def test(fn, name):
        start = perf_counter()
        result = fn(DATA)
        duration = perf_counter() - start
        print('{} took {:.3f} seconds\n\n'.format(name, duration))

        for d in result:
            assert -1 <= d <= 1, " incorrect values"

    if __name__ == "__main__":
        print('Running benchmarks with COUNT = {}'.format(COUNT))

        test(sequence_tanh, 'sequence_tanh')

        test(lambda d: [tanh(x) for x in d], '[tanh(x) for x in d]')
    ```

1. Programını kullanarak çalıştırın **hata ayıklama > hata ayıklama olmadan Başlat** sonuçları görmek için (Ctrl + F5). Ayarlayabileceğiniz `COUNT` Kıyaslama noktalarını çalıştırma süresini değiştirmek için değişken. Bu izlenecek yolda amacı doğrultusunda, sayısı her ölçüt yaklaşık iki saniye sürer şekilde ayarlayın.

## <a name="create-the-core-c-project"></a>Çekirdek C++ projesi oluşturma

1. Çözüm Gezgini'nde çözüme sağ tıklayıp **Ekle > Yeni proje...** . Visual Studio çözümü (Visual Studio için Python kullanmanın avantajlarını biridir) hem Python hem de C++ projeleri birlikte içerebilir.

1. Arama seçin "C++" **boş proje**(Bu makalede kullanır "superfastcode") bir ad belirtin ve seçin **Tamam**.

    > [!Tip]
    > İle **Python yerel geliştirme araçları** Visual Studio 2017'de yüklü ile başlayabilirsiniz **Python uzantı Modülü** şablon bunun yerine, sahip olduğu zaten yerinde açıklanana çoğunu. Bu kılavuz için boş bir proje ile başlayarak adım adım uzantı modülü oluşturma gösterir. İşlem anladığınızda, zaman zaman şablon kaydeder kendi uzantılarınızı yazma.

1. Sağ tıklayarak bir C++ dosyası içinde yeni proje oluşturma **kaynak dosyaları** düğümünü seçip **Ekle > Yeni öğe... "** seçin **C++ dosyası**, adlandırın `module.cpp`, ve seçin **Tamam**.

    > [!Important]
    > Bir dosyayla `.cpp` C++ özellik sayfaları'nda aşağıdaki adımları açmak uzantısı gereklidir.

1. Çözüm, select C++ projeye sağ **özellikleri**.

1. Üst kısmındaki **özellik sayfaları** görüntülenen iletişim **yapılandırma** için **yapılandırmalarında** ve **Platform** için**Win32**.

1. Aşağıdaki tabloda açıklandığı gibi belirli özellikleri ayarlayın ve ardından **Tamam**.

    | Tab | Özellik | Değer |
    | --- | --- | --- |
    | Genel | Genel > hedef adı | Python'da bir başvurduğu istediğiniz modül adını `from...import` deyimleri. Bu aynı adı için Python modülü tanımlarken, C++'ta kullanın. Modül adı projenin adı kullanmak istiyorsanız, varsayılan değerini bırakın `$(ProjectName)`. |
    | | Genel > hedef uzantısı | .pyd |
    | | Proje Varsayılanları > yapılandırma türü | Dinamik kitaplık (.dll) |
    | C/C++ > Genel | Ek içeren dizinler | Python'u eklediğinizden `include` klasör, bu gibi bir durumda yükleme için uygun şekilde `c:\Python36\include`.  |
    | C/C++ > önişlemci | Önişlemci tanımları | Ekleme `Py_LIMITED_API;` (noktalı virgül dahil) dize başlangıcına. Bu tanımı bazı işlevlere Python'dan çağırabilir ve kod Python farklı sürümleri arasında daha taşınabilir hale getirir kısıtlar. |
    | C/C++ > kod oluşturma | Çalışma Zamanı Kitaplığı | Çok iş parçacıklı DLL (/ MD) (bkz. aşağıdaki uyarı) |
    | Bağlayıcı > Genel | Ek Kitaplık dizinleri | Python'u eklediğinizden `libs` içeren klasörü `.lib` Örneğin, yükleme için uygun şekilde dosyaları `c:\Python36\libs`. (İşaret edecek şekilde mutlaka `libs` içeren klasörü `.lib` dosyaları ve *değil* `Lib` içeren klasörü `.py` dosyalarını.) |

    > [!Tip]
    > Proje Özellikleri'nde C/C++ sekmesini görmüyorsanız, proje, C/C++ kaynak dosyaları tanımlayan hiçbir dosya içermiyor olmasıdır. Olmayan bir kaynak dosyası oluşturursanız, bu durum ortaya çıkabilir bir `.c` veya `.cpp` uzantısı. Örneğin, yanlışlıkla girdiğiniz `module.coo` yerine `module.cpp` yeni öğe iletişim kutusunda daha önce ardından Visual Studio dosyayı oluşturur ancak dosya türü olarak ayarlayıp ayarlamadığını "C / C + kod," olduğu ne C/C++ Özellikleri sekmesi etkinleştirir. Dosyayı yeniden adlandırın bile durum böyle misidentification kalır `.cpp`. Dosya türü düzgün bir şekilde ayarlamak için Çözüm Gezgini'nde seçin dosyaya sağ tıklayın **özellikleri**, ardından **dosya türü** için **C/C++ kodu**.

    > [!Warning]
    > Her zaman **C/C++ > kod oluşturma > Çalışma Zamanı Kitaplığı** seçeneğini "çok iş parçacıklı DLL (/ MD)" olsa bile bir hata ayıklama yapılandırması için bu ayarı olduğundan hata ayıklama olmayan Python ikili dosyaları ile oluşturulur. Ayarlamak için MSDN aboneliğine "çok iş parçacıklı hata ayıklama DLL'i (/ MDd)" seçeneği, bir hata ayıklama yapılandırma hata üreten *C1189: Py_LIMITED_API Py_DEBUG Py_TRACE_REFS ve Py_REF_DEBUG ile uyumsuz*. Ayrıca, kaldırırsanız `Py_LIMITED_API` derleme hatayı önlemek için Python modülü içe aktarmaya çalışıldığında çöküyor. (Kilitlenme DLL'nin çağrısı içinde olur `PyModule_Create` daha sonra çıktı iletisi ile açıklandığı *önemli Python hata: PyThreadState_Get: geçerli iş parçacığının*.)
    >
    > / MDd seçeneği (örneğin, python_d.exe) Python hata ayıklama ikililerini derlemek için kullanılır, ancak bir uzantı DLL'si seçerek hala neden şu yapı hatasıyla `Py_LIMITED_API`.

1. C++ projesini sağ tıklayıp **derleme** yapılandırmalarınızı (hata ayıklama ve yayın) test etmek için. `.pyd` Dosyaları bulunur *çözüm* klasörü altında **hata ayıklama** ve **yayın**, C++ proje klasörünün kendisi değil.

1. C++ proje için aşağıdaki kodu ekleyin `module.cpp` dosyası:

    ```cpp
    #include <Windows.h>
    #include <cmath>

    const double e = 2.7182818284590452353602874713527;

    double sinh_impl(double x) {
        return (1 - pow(e, (-2 * x))) / (2 * pow(e, -x));
    }

    double cosh_impl(double x) {
        return (1 + pow(e, (-2 * x))) / (2 * pow(e, -x));
    }

    double tanh_impl(double x) {
        return sinh_impl(x) / cosh_impl(x);
    }
    ```

1. Kodunuzun doğru olduğunu onaylamak için yeniden C++ projesi oluşturun.

## <a name="convert-the-c-project-to-an-extension-for-python"></a>C++ projesi için Python uzantısı Dönüştür

C++ DLL için Python uzantısı'na yapmak için önce Python türleri ile etkileşim kurmak için verilen yöntemleri değiştirin. Modülüyle modülün yöntemlerin tanımlarını dışarı aktaran bir işlevi eklersiniz.

Python için bu bölümde gösterilen öğeleri üzerinde arka plan için 3.x başvurmak [Python/C API Reference Manual](https://docs.python.org/3/c-api/index.html) ve özellikle [modülü nesneleri](https://docs.python.org/3/c-api/module.html) python.org üzerinde (Python'dan sürümünüz seçeneğini belirlemeyi unutmayın doğru belgeleri görüntülemek için sağ üst köşedeki aşağı açılan denetim).

Python 2.7 ile çalışıyorsanız, başvuracak [genişletme Python 2.7 C veya C++](https://docs.python.org/2.7/extending/extending.html) ve [taşıma uzantı modüllerini Python 3](https://docs.python.org/2.7/howto/cporting.html) (python.org).

1. C++ dosyasına eklenecek `Python.h` üst:

    ```cpp
    #include <Python.h>
    ```

1. Değiştirme `tanh_impl` kabul edin ve dönüş türleri Python yöntemi (bir `PyOjbect*`, diğer bir deyişle):

    ```cpp
    PyObject* tanh_impl(PyObject *, PyObject* o) {
        double x = PyFloat_AsDouble(o);
        double tanh_x = sinh_impl(x) / cosh_impl(x);
        return PyFloat_FromDouble(tanh_x);
    }
    ```

1. Tanımlayan bir yapı eklemek nasıl C++ `tanh_impl` işlevi için Python sunulur:

    ```cpp
    static PyMethodDef superfastcode_methods[] = {
        // The first property is the name exposed to Python, fast_tanh, the second is the C++
        // function name that contains the implementation.
        { "fast_tanh", (PyCFunction)tanh_impl, METH_O, nullptr },

        // Terminate the array with an object containing nulls.
        { nullptr, nullptr, 0, nullptr }
    };
    ```

1. Python kodunuzun özellikle kullanırken başvurduğu istediğiniz modülü tanımlayan bir yapı eklemek `from...import` deyimi. (Bu proje özelliklerinde değerle aynı **yapılandırma özellikleri > Genel > hedef adı**.) Aşağıdaki örnekte, "superfastcode" modül adı kullanabileceğiniz anlamına gelir `from superfastcode import fast_tanh` Python çünkü `fast_tanh` içinde tanımlanan `superfastcode_methods`. (Dosya adları gibi module.cpp, C++ projesine iç değişimlerle.)

    ```cpp
    static PyModuleDef superfastcode_module = {
        PyModuleDef_HEAD_INIT,
        "superfastcode",                        // Module name to use with Python import statements
        "Provides some functions, but faster",  // Module description
        0,
        superfastcode_methods                   // Structure that defines the methods of the module
    };
    ```

1. Python modülü adlandırılmalıdır yüklediğinde, çağıran bir yöntem ekleyin `PyInit_<module-name>`burada *&lt;module_name&gt;* tam C++ projenin eşleşen **genel >hedefadı** özelliği (diğer bir deyişle, dosya adı ile eşleşen `.pyd` proje tarafından oluşturulan).

    ```cpp
    PyMODINIT_FUNC PyInit_superfastcode() {
        return PyModule_Create(&superfastcode_module);
    }
    ```

1. Hedef yapılandırmasını "Yayın" ayarlama ve kodunuzu yeniden doğrulamak için C++ projesi oluşturun. Hatalarla karşılaşırsanız, aşağıdaki durumlarda denetleyin:
    - Python.h bulunamıyor (*E1696: "Python.h" kaynak dosyası açılamıyor* ve/veya *C1083: açık dosya içeremez: "Python.h": böyle dosya veya dizin*): doğrulayın yolunda **C/C++ > Genel > ek ekleme dizinleri** Python yüklemenizin proje özellikleri işaret `include` klasör. 6. adım altında bkz [core C++ projesi oluşturma](#create-the-core-c-project).
    - Python kitaplıkları bulunamıyor: doğrulayın yolunda **bağlayıcı > Genel > ek kitaplık dizinleri** Python yüklemenizin proje özellikleri işaret `libs` klasör. 6. adım altında bkz [core C++ projesi oluşturma](#create-the-core-c-project).
    - Bağlayıcı hatalarla ilgili için hedef mimari: C++ hedefin proje mimarisi Python yüklemenizi eşleşmesi için değiştirin. Örneğin, C++ proje x64 hedeflediğiniz Python yüklemenizi x86 varsa x86 hedeflemek için C++ projesi değiştirin.

## <a name="test-the-code-and-compare-the-results"></a>Kodu test edin ve sonuçları karşılaştırma

Python uzantı olarak yapılandırılmış DLL olduğuna göre Python projesinden başvurduğu, modülü içeri aktarın ve yöntemlerini kullanın.

### <a name="make-the-dll-available-to-python"></a>DLL Python için kullanılabilir yap

DLL Python için kullanılabilir hale getirmek için iki yolu vardır.

İlk yöntem, aynı çözüm içinde Python projesi ve C++ projesi varsa çalışır. Çözüm Gezgini'ne gidin, sağ **başvuruları** Python projesi ve ardından düğümünde **Başvuru Ekle**. Görüntülenen iletişim kutusunda, seçmek **projeleri** sekmesinde **superfastcode** proje (veya örneğin adı kullandığınızdan) ve ardından **Tamam**.

![Superfastcode projeye bir başvuru ekleme](media/cpp-add-reference.png)

Aşağıdaki adımlarda anlatıldığı alternatif bir yöntem de diğer Python projeleri için kullanılabilir hale getirme global Python ortamı modülünü yükler. (Bu nedenle genellikle yapmak için Visual Studio 2017 sürüm 15.5 ve öncesi ortamında IntelliSense tamamlanma veritabanı yenileme gerektirir. Yenileme ayrıca modülü ortamdan kaldırırken gereklidir.)

1. Visual Studio 2017, Visual Studio Yükleyicisi'ni çalıştırın kullanıyorsanız seçin **Değiştir**seçin **tek tek bileşenler > derleyiciler, derleme araçları ve çalışma zamanları > Visual C++ 2015.3 v140 Araç Seti**. Python (Windows için) kendi Visual Studio 2015 (sürüm 14.0) ile oluşturulmuş ve araçlarda uzantı burada açıklanan yöntemi aracılığıyla oluşturulurken kullanılabilir olduğunu bekliyor olduğundan bu adım gereklidir. (Python'un 32 bit sürümünü yükleyip Win32 ve değil x64 DLL hedef gerekebileceğini unutmayın.)

1. Adlı bir dosya oluşturun `setup.py` projeye sağ tıklayıp seçerek C++ projesinde **Ekle > Yeni öğe...** . "C++ dosyası (.cpp)"'ı seçin, dosyayı adlandırın `setup.py`, seçerek **Tamam** (ile dosya adlandırma `.py` C++ kullanarak rağmen Python şablon dosyası olarak onu tanıyabilmesi Visual Studio extension yapar). Dosya düzenleyicisinde görüntülendiğinde aşağıdaki kodu yapıştırın:

    ```python
    from distutils.core import setup, Extension, DEBUG

    sfc_module = Extension('superfastcode', sources = ['module.cpp'])

    setup(name = 'superfastcode', version = '1.0',
        description = 'Python Package with superfastcode C++ extension',
        ext_modules = [sfc_module]
        )
    ```

    Bkz: [yapı C ve C++ uzantıları](https://docs.python.org/3/extending/building.html) (python.org) bu betik hakkında bilgi için.

1. `setup.py` Uzantısını kullanarak komut satırından kullanıldığında Visual Studio 2015 C++ araç takımı oluşturmak için Python kodu bildirir. Yükseltilmiş bir komut istemi açın, C++ projesi içeren klasöre gidin (diğer bir deyişle, içeren klasörü `setup.py`) ve aşağıdaki komutu girin:

    ```command
    pip install .
    ```

### <a name="call-the-dll-from-python"></a>Python'dan DLL çağırma

Yukarıdaki yöntemlerden birini tamamladıktan sonra artık çağırabilirsiniz `fast_tanh` işlev Python kodu ve Python uygulaması performansını karşılaştırın:

1. Aşağıdaki satırları ekleyin, `.py` çağırmak için dosya `fast_tanh` yöntemi DLL'den dışarı ve çıktısını görüntüler.

    ```python
    from superfastcode import fast_tanh
    test(lambda d: [fast_tanh(x) for x in d], '[fast_tanh(x) for x in d]')
    ```

1. Python programını çalıştırın (**hata ayıklama > hata ayıklama olmadan Başlat** ya da Ctrl + F5) ve C++ yordamı beş ila 20 kat Python uygulamasını daha hızlı çalışır. Normal çıktı aşağıdaki gibi görünür:

    ```output
    Running benchmarks with COUNT = 500000
    sequence_tanh took 1.542 seconds

    [tanh(x) for x in d] took 1.087 seconds

    [fast_tanh(x) for x in d] took 0.158 seconds
    ```

    Varsa **hata ayıklama olmadan Başlat** komutu devre dışı bırakıldı, Çözüm Gezgini'nde Python projeye sağ tıklayıp seçin **başlangıç projesi olarak ayarla**.

1. Artırmayı deneyin `COUNT` daha belirgin farklar için değişken. Hata ayıklama derlemesini daha iyi duruma getirilmiştir ve çeşitli hata denetimleri içeren C++ modülü hata ayıklama yapısını da yayın derlemesi göre daha yavaş çalışır. Karşılaştırma için bu yapılandırmalar arasında geçiş çekinmeyin.

## <a name="debug-the-c-code"></a>C++ kod hatalarını ayıklama

Visual Studio hata ayıklama Python ve C++ kodu birlikte destekler.

1. Python projeyi seçin Çözüm Gezgini'nde sağ **özellikleri**seçin **hata ayıklama** sekmesine tıklayın ve ardından **hata ayıklama > yerel kod hata ayıklamayı** seçeneği.

    > [!Tip]
    > Yerel kodda hata ayıklama etkinleştirdiğinizde, programın normal "to continue... herhangi bir tuşa basın" duraklatma görünürlüğünden vazgeçmeden hemen tamamlandıktan sonra Python çıkış penceresine kaybolabilir. Bir duraklatma zorlamak için ekleme `-i` seçeneğini **çalıştırın > yorumlayıcı bağımsız değişkenleri** alanını **hata ayıklama** sekmesinde yerel kodda hata ayıklama etkinleştirdiğinizde. Bu noktada, Ctrl + Z, çıkmak için Enter tuşuna basın bekler kod tamamlandıktan sonra bu bağımsız değişken Python yorumlayıcısı etkileşimli moduna geçirir. (Alternatif olarak, Python kodunuzu değiştirme sorun değilse ekleyebileceğiniz `import os` ve `os.system("pause")` programınızı sonunda deyimleri. Bu kod özgün duraklatma istemi çoğaltır.)

1. Seçin **Dosya > Kaydet** özellik değişiklikleri kaydedin.

1. Visual Studio araç çubuğunda "Debug" derleme yapılandırmasını ayarlayın.

    ![Derleme yapılandırması hata ayıklama için ayarlama](media/cpp-set-debug.png)

1. Kod genellikle hata ayıklayıcıda çalışması daha uzun sürer çünkü değiştirmek isteyebilirsiniz `COUNT` değişkenini, `.py` yaklaşık beş kat daha küçük bir değer dosyasına (örneğin, ondan değiştirin `500000` için `100000`).

1. C++ kodunuzu ilk satırında bir kesme noktası ayarlayın `tanh_impl` yöntemi, ardından hata ayıklayıcıyı Başlat (F5 veya **hata ayıklama > hata ayıklamayı Başlat**). Bu kod çağırıldığında hata ayıklayıcıyı durdurur. Kesme noktasına isabet değil, yapılandırmanın hata ayıklama için ayarlanır ve (otomatik olarak hata ayıklayıcısı başlatılırken gerçekleşmez) proje kaydettiğiniz denetleyin.

    ![C++ kodunda kesme noktası durduruluyor](media/cpp-debugging.png)

1. Bu noktada C++ kodunuz içinde adım adım, değişkenleri inceleyebilir ve benzeri. Bu özelliklerin ayrıntıları [C++ hata ayıklama ve Python birlikte](debugging-mixed-mode-c-cpp-python-in-visual-studio.md).

## <a name="alternative-approaches"></a>Alternatif yaklaşımlar

Python uzantıları aşağıdaki tabloda açıklandığı gibi oluşturmak için yol çeşitli vardır. CPython ilk girişini ne bu makalede önceden açıklanan ' dir.

| Yaklaşım | Hasat Yılı | Kullanıcı Temsilcisi | Pro(s) | CON(s) |
| --- | --- | --- | --- | --- |
| C/C++ uzantı modüllerini CPython için | 1991 | Standart Kitaplık | [Kapsamlı belgeler ve öğreticiler](https://docs.python.org/3/c-api/). Toplam denetimi. | Derleme, taşınabilirliği, başvuru yönetimi. Yüksek C bilgi. |
| [pybind11](https://github.com/pybind/pybind11) (C++ için önerilir) | 2015 |  | Python bağlamaları var olan C++ kodu oluşturmak için basit, yalnızca üstbilgi kitaplığı. Birkaç bağımlılıkları. PyPy uyumluluğu. | Yeni, daha az olgun. Koyu C ++ 11 özelliklerini kullanın. Desteklenen derleyicileri (Visual Studio dahildir) kısa listesi. |
| Cython (Recommnded c) | 2007 | [gevent](http://www.gevent.org/), [kivy](https://kivy.org/) | Python benzer. Yüksek oranda olgun. Yüksek performans. | Derleme, yeni söz dizimi, yeni bir araç zinciri. |
| [Boost.Python](https://www.boost.org/doc/libs/1_66_0/libs/python/doc/html/index.html) | 2002 | | Neredeyse her C++ derleyicisi ile çalışır. | Kitaplık paketi büyük ve karmaşık; eski derleyicileri için çok sayıda geçici çözümler içerir. |
| ctypes | 2003 | [oscrypto](https://github.com/wbond/oscrypto) | Hiçbir derleme geniş kullanılabilirlik. | Erişim ve C yapıları hantal ve hataya diziyi. |
| SWIG | 1996 | [crfsuite](http://www.chokkan.org/software/crfsuite/) | Tek seferde birçok dil için bağlamaları oluşturur. | Python yalnızca hedef ise aşırı yükü. |
| cffi | 2013 | [şifreleme](https://cryptography.io/en/latest/), [pypy](http://pypy.org/) | Tümleştirme, PyPy uyumluluk kolaylığı. | Yeni, daha az olgun. |

## <a name="see-also"></a>Ayrıca bkz.

Bu izlenecek yolda tamamlanmış örnekten bulunabilir [python-samples-vs-cpp-extension](https://github.com/Microsoft/python-sample-vs-cpp-extension) (GitHub).