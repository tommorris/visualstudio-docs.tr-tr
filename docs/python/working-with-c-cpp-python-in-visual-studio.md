---
title: C++ ve Python ile çalışma
description: Visual Studio'da Python için C++ uzantısı veya modülü yazmak için işlem amd adımları
ms.custom: ''
ms.date: 04/03/2018
ms.technology:
- devlang-python
dev_langs:
- python
- C++
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: d7545f22f7fd19d37cfdbe90839ff83bd9d0ec38
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="creating-a-c-extension-for-python"></a>Python için C++ uzantısı oluşturma

C++ (veya C) ile yazılmış modüller, alt düzey işletim sistemi özellikleri erişimi etkinleştirmek için de bir Python yorumlayıcısı yeteneklerini artırmak için yaygın olarak kullanılır. Üç birincil tür modülü vardır:

- Hızlandırıcı modülleri: Python yorumlanan dil olduğu için bazı kod parçalarını C++'da daha yüksek performans için yazılabilir.
- Sarmalayıcı modülleri: Python kodu için varolan C/C++ arabirimleri kullanıma sunar veya Python kullanımı kolay bir daha fazla "Pythonic" API kullanıma sunma.
- Alt düzey sistem erişim modülleri: CPython çalışma zamanı, işletim sistemi veya temel alınan donanım düşük düzeyli özelliklerine erişmek için oluşturulmuş.

Bu makalede, hiperbolik tanjantı hesaplar ve Python kodundan çağıran CPython için C++ uzantısı modülü oluşturma sürecinde anlatılmaktadır. Yordam ilk Python C++'da aynı yordamını uygulama göreli performans kazancı göstermek için uygulanır.

Burada uygulanan yaklaşıma standart CPython uzantıları için açıklandığı gibi olan [Python belgelerine](https://docs.python.org/3/c-api/). Bu ve diğer yolları arasında bir karşılaştırma altında açıklanan [alternatif yaklaşımlar](#alternative-approaches) bu makalenin sonunda.

Bu kılavuzda tamamlanmış örnekten bulunabilir [python-samples-vs-cpp-uzantısı](https://github.com/Microsoft/python-sample-vs-cpp-extension) (GitHub).

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio 2017 hem **C++ ile masaüstü geliştirme** ve **Python geliştirme** varsayılan seçeneklerle yüklü iş yükleri.
- İçinde **Python geliştirme** iş yükü, aynı zamanda için sağ taraftaki kutusunu işaretlemeniz **Python yerel geliştirme araçları**. Bu makalede açıklanan yapılandırma çoğu bu seçeneği ayarlar. (Bu seçenek ayrıca C++ iş yükünü otomatik olarak içerir.)

    ![Python yerel geliştirme araçları seçeneği](media/cpp-install-native.png)

    > [!Tip]
    > Yükleme **veri bilimi ve analitik uygulamaları** iş yükü de Python içerir ve **Python yerel geliştirme araçları** varsayılan seçeneği.

Daha fazla bilgi için bkz: [Visual Studio için Python desteği yükleme](installing-python-support-in-visual-studio.md), diğer Visual Studio sürümlerini kullanan dahil olmak üzere. Python ayrı olarak yüklerseniz, seçtiğinizden emin olun **hata ayıklama simgeleri karşıdan** ve **indirme hata ayıklama ikili** altında **Gelişmiş Seçenekler** yükleyicisinde. Bu seçenek, hata ayıklama derlemesi yapmayı seçerseniz kullanılabilir gerekli hata ayıklama kitaplıkları sahip olmasını sağlar.

## <a name="create-the-python-application"></a>Python uygulaması oluşturma

1. Seçerek Visual Studio'da yeni bir Python projesi oluşturma **Dosya > Yeni > Proje**. Seçin "Python" için arama **Python uygulama** şablonu, bir uygun bir ad ve konum girin ve seçin **Tamam**.

1. C++ birlikte çalışma 32 bit Python Yorumlayıcı (Python önerilen 3.6) kullanmanızı gerektirir. İçinde **Çözüm Gezgini** penceresi Visual Studio'nun proje düğümünü genişletin, sonra genişletin **Python ortamları** düğümü. Varsayılan (ya da kalın ya da "genel varsayılan" ile etiketlenmiş) olarak 32 bit bir ortamın görmüyorsanız, ardından yönergeleri izleyin [bir proje için bir Python ortamı seçme](selecting-a-python-environment-for-a-project.md). Yüklü bir 32 bit yorumlayıcı sahip değilseniz, bkz: [yükleme Python yorumlayıcılar](installing-python-interpreters.md).

1. Projenin `.py` dosya, (daha kolay karşılaştırma için math kitaplığı kullanmadan uygulanan) hiperbolik tanjantını hesaplama benchmarks aşağıdaki kodu yapıştırın. El ile bazı deneyimi için kodu girmek çekinmeyin [düzenleme özellikleri Python](editing-python-code-in-visual-studio.md).

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

1. Programını kullanarak çalıştırmak **hata ayıklama > hata ayıklama olmadan Başlat** sonuçları görmek için (Ctrl + F5). Ayarlayabileceğiniz `COUNT` değerlendirmeler çalıştırma süresini değiştirmek için değişken. Bu kılavuzda amaçları doğrultusunda sayısı her ölçüt yaklaşık iki saniye sürer şekilde ayarlayın.

## <a name="create-the-core-c-project"></a>Çekirdek C++ projesi oluşturma

1. Çözüm Gezgini'ndeki çözüme sağ tıklayın ve **Ekle > Yeni proje...** . Visual Studio çözümü (Visual Studio için Python kullanmanın yararları biridir) Python ve C++ projeleri birlikte içerebilir.

1. "C++", select Search'te **boş proje**(Bu makalede kullanır "superfastcode") bir ad belirtin ve seçin **Tamam**.

    > [!Tip]
    > İle **Python yerel geliştirme araçları** Visual Studio 2017 yüklü olan başlatabilirsiniz **Python Uzantısı Modülü** şablonu bunun yerine, sahip olduğu çoğunu ne aşağıda zaten yerinde açıklanmıştır. Bu kılavuz için boş bir proje ile başlayarak adım adım uzantı modülü oluşturma gösterir. İşlem anladığınızda, zaman zaman şablonu kaydeder kendi uzantıları yazma.

1. C++ dosyasına sağ tıklayarak yeni projede oluşturmak **kaynak dosyaları** düğümü, ardından **Ekle >... yeni öğe "**seçin **C++ dosya**, adlandırın `module.cpp`, ve seçin **Tamam**.

    > [!Important]
    > Bir dosyayla `.cpp` adımları C++ özellik sayfalarında etkinleştirmek uzantısı gereklidir.

1. Çözümde seçin C++ projeye sağ **özellikleri**.

1. Üstündeki **özellik sayfaları** görünür, iletişim ayarlayın **yapılandırma** için **tüm yapılandırmaları** ve **Platform** için**Win32**.

1. Aşağıdaki tabloda açıklandığı gibi belirli özellikleri ayarlayın ve ardından **Tamam**.

    | Tab | Özellik | Değer |
    | --- | --- | --- |
    | Genel | Genel > hedef adı | Python içinde bir başvurduğu istediğiniz şekilde modülünün adını belirtin `from...import` deyimleri. Bu aynı adı için Python modülü tanımlarken, C++'da kullanın. Proje adı Modül adı olarak kullanmak istiyorsanız, varsayılan değerini bırakın `$(ProjectName)`. |
    | | Genel > hedef uzantısı | .pyd |
    | | Proje Varsayılanları > yapılandırma türü | Dinamik kitaplığı (.dll) |
    | C/C++ > Genel | Ek içeren dizinler | Python eklemek `include` klasörü, yükleme, örneğin, uygun şekilde `c:\Python36\include`.  |
    | C/C++ > ön işlemci | Önişlemci tanımları | Ekleme `Py_LIMITED_API;` (noktalı virgül dahil) dize başlangıcına. Bu tanım bazı Python çağırabilir ve kod Python farklı sürümleri arasında daha taşınabilir yapar işlevleri kısıtlar. |
    | C/C++ > kod oluşturma | Çalışma Zamanı Kitaplığı | Çok iş parçacıklı DLL (/ MD) (uyarı aşağıya bakın) |
    | Bağlayıcı > Genel | Ek Kitaplık dizinleri | Python eklemek `libs` içeren klasör `.lib` Örneğin, yükleme için uygun şekilde dosya `c:\Python36\libs`. (İşaret edecek şekilde unutmayın `libs` içeren klasörü `.lib` dosyaları ve *değil* `Lib` içeren klasörü `.py` dosyaları.) |

    > [!Tip]
    > Proje Özellikleri'nde C/C++ sekmesini görmüyorsanız, C/C++ kaynak dosyaları tanımlayan herhangi bir dosya içermiyor. proje nedeni. Bir kaynak dosyası olmadan oluşturursanız, bu durum ortaya çıkabilir bir `.c` veya `.cpp` uzantısı. Örneğin, yanlışlıkla girdiğiniz `module.coo` yerine `module.cpp` yeni öğe iletişim kutusunda daha önce ardından Visual Studio dosyası oluşturur ama dosya türü ayarlamaz "C / C + kodu," olduğu ne C/C++ Özellikleri sekmesi etkinleştirir. Dosyayı yeniden adlandırın bile bu tür misidentification durumda kalır `.cpp`. Dosya türü düzgün bir şekilde ayarlamak için Çözüm Gezgini'nde, select dosyasını sağ tıklatın **özellikleri**, ardından **dosya türü** için **C/C++ kod**.

    > [!Warning]
    > Her zaman **C/C++ > kod oluşturma > Çalışma Zamanı Kitaplığı** için seçenek "çok iş parçacıklı DLL (/ MD)" hata ayıklama yapılandırması için bile bu ayarı olmayan hata ayıklama Python ikili ile oluşturulan olduğundan. Ayarlanacak görülüyorsa "çok iş parçacıklı hata ayıklama DLL (/ MDd)" seçeneği, bir hata ayıklama yapılandırma hata üretir *C1189: Py_LIMITED_API Py_DEBUG, Py_TRACE_REFS ve Py_REF_DEBUG uyumlu*. Ayrıca, kaldırırsanız `Py_LIMITED_API` yapı hatayı önlemek için Python modülü almaya çalışırken çöküyor. (DLL çağrı içinde kilitlenme olur `PyModule_Create` daha sonra çıktı iletisiyle açıklandığı gibi *önemli Python hata: PyThreadState_Get: hiçbir geçerli iş parçacığının*.)
    >
    > /MDd seçeneği Python hata ayıklama ikili dosyalarının (örneğin, python_d.exe) oluşturmak için kullanılır, ancak uzantı DLL için seçme hala neden derleme hatası ile `Py_LIMITED_API`.

1. C++ projesine sağ tıklatın ve **yapı** yapılandırmalarınızı (hata ayıklama ve yayın) test etmek için. `.pyd` Dosyaları içinde bulunur *çözüm* klasörü altında **hata ayıklama** ve **sürüm**, C++ projesi klasörünün kendisi değil.

1. C++ projenin için aşağıdaki kodu ekleyin `module.cpp` dosyası:

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

## <a name="convert-the-c-project-to-an-extension-for-python"></a>C++ projesi uzantısı Python için Dönüştür

C++ DLL Python için uzantı yapmak için ilk Python türleri ile etkileşim kurmak için dışarı aktarılan yöntemleri değiştirin. Sonra modülün yöntemleri tanımlarını birlikte modülü aktaran işlevi ekleyin.

Python için bu bölümde gösterilen öğeleri üzerinde arka planının 3.x başvurmak [Python/C API başvuru el ile](https://docs.python.org/3/c-api/index.html) ve özellikle [modülü nesneleri](https://docs.python.org/3/c-api/module.html) python.org üzerinde (Python sürümünüz seçmeyi unutmayın aşağı açılan denetiminde doğru belgeleri görüntülemek için sağ üst).

Python 2.7 ile çalışıyorsanız, başvuracak [genişletme Python 2.7 C veya C++ ile](https://docs.python.org/2.7/extending/extending.html) ve [uzantısı modüllerle taşıma Python 3](https://docs.python.org/2.7/howto/cporting.html) (python.org).

1. C++ dosyasına eklenecek `Python.h` üst:

    ```cpp
    #include <Python.h>
    ```

1. Değiştirme `tanh_impl` kabul etmek ve dönüş Python türleri için yöntemi (bir `PyOjbect*`, yani):

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

1. Modül için özellikle kullanırken Python kodunuzu başvurmak istediğinizde olarak tanımlayan bir yapı eklemek `from...import` deyimi. (Bu değerin altında Proje Özellikleri'nde eşleşmesi hale **yapılandırma özellikleri > Genel > hedef adı**.) Aşağıdaki örnekte, "superfastcode" modül adı kullanabileceğiniz anlamına gelir `from superfastcode import fast_tanh` python'da, çünkü `fast_tanh` içinde tanımlanan `superfastcode_methods`. (Dosya adları gibi module.cpp, C++ projesi iç göz önüne alınmaz.)

    ```cpp
    static PyModuleDef superfastcode_module = {
        PyModuleDef_HEAD_INIT,
        "superfastcode",                        // Module name to use with Python import statements
        "Provides some functions, but faster",  // Module description
        0,
        superfastcode_methods                   // Structure that defines the methods of the module
    };
    ```

1. Adlandırılmalıdır modülü yüklediğinde, Python çağıran bir yöntem ekleyin `PyInit_<module-name>`, burada *&lt;module_name&gt;* C++ projenin tam olarak eşleşen **genel >hedefadı** özelliği (diğer bir deyişle, dosya adı ile eşleşen `.pyd` projenin oluşturduğu).

    ```cpp
    PyMODINIT_FUNC PyInit_superfastcode() {
        return PyModule_Create(&superfastcode_module);
    }
    ```

1. Hedef yapılandırmasını "Yayın" olarak ayarlayın ve yeniden kodunuzu doğrulamak için C++ projesi oluşturun. Hatalarla karşılaşırsanız, aşağıdaki durumlarda denetleyin:
    - Python.h bulunamadı (*E1696: kaynak dosyası "Python.h" açılamıyor* ve/veya *C1083: açık dosya içeremez: "Python.h": böyle dosya veya dizin*): doğrulayın yolunda **C/C++ > Genel > ek içeren dizinler** Python yüklemenin proje özelliklerini işaret `include` klasör. 6. adım altında bkz [çekirdek C++ projesi oluşturma](#create-the-core-c-project).
    - Python Kitaplığı bulunamıyor: doğrulayın yolunda **bağlayıcı > Genel > ek kitaplık dizinleri** Python yüklemenin proje özelliklerini işaret `libs` klasör. 6. adım altında bkz [çekirdek C++ projesi oluşturma](#create-the-core-c-project).
    - Bağlayıcı hatalarını ilgili hedef mimari: C++ hedefin proje mimarisi, Python yüklemenizin eşleşecek şekilde değiştirin. Örneğin, C++ projesi ile x64 hedefleme Python yüklemenizi x86 varsa x86 hedeflemek için C++ projesi değiştirin.

## <a name="test-the-code-and-compare-the-results"></a>Kodu test etmek ve sonuçları karşılaştırma

Python uzantısı olarak yapılandırılmış DLL sahip olduğunuza göre Python projeden başvurduğu modülü içe aktarın ve yöntemlerini kullanın.

### <a name="make-the-dll-available-to-python"></a>DLL Python için kullanılabilir hale

DLL Python için kullanılabilir hale getirmek iki yolu vardır.

İlk yöntem, Python proje ve C++ projesi aynı çözüm içinde olduğunda çalışır. Çözüm Gezgini'ne gidin, sağ **başvuruları** Python proje ve ardından düğümünde **Başvuru Ekle**. Görüntülenen iletişim kutusunda, seçin **projeleri** sekmesine **superfastcode** proje (veya, ad kullanmakta olduğunuz) ve ardından **Tamam**.

![Superfastcode projesine bir başvuru ekleme](media/cpp-add-reference.png)

Aşağıdaki adımlarda açıklandığı Alternatif yöntem de diğer Python projeleri için kullanılabilir hale getirme Genel Python ortamında modülünü yükler. (Bu nedenle genellikle yapılması, ortamda Visual Studio 2017 15,5 ve önceki sürümü için IntelliSense tamamlanma veritabanını yenileme gerektirir. Yenileme ayrıca modülün ortamından kaldırırken gereklidir.)

1. Visual Studio yükleyiciyi çalıştırın, Visual Studio 2017 kullanıyorsanız seçin **Değiştir**seçin **bileşenleri tek tek > derleyicileri, yapı araçları ve çalışma zamanları > Visual C++ 2015.3 v140 araç takımı**. Python (Windows için) kendisini (sürüm 14.0) Visual Studio 2015 ile oluşturulan ve bu araçlara uzantı burada açıklanan yöntemle oluşturulurken kullanılabilir olmasını bekliyor olduğundan bu adım gereklidir. (Python 32-bit sürümünü yükleyin ve Win32 ve değil x64 DLL'e hedeflemek gerekebileceğini unutmayın.)

1. Adlı bir dosya oluşturun `setup.py` projeye sağ tıklatıp seçerek C++ projesinde **Ekle > Yeni öğe...** . "C++ dosyası (.cpp)" seçin, dosya adı `setup.py`, seçerek **Tamam** (ile dosya adlandırma `.py` uzantısı Visual C++ kullanarak rağmen Python şablon dosyası olarak tanımak Studio yapar). Dosya düzenleyicisinde görüntülendiğinde aşağıdaki kodu yapıştırın:

    ```python
    from distutils.core import setup, Extension, DEBUG

    sfc_module = Extension('superfastcode', sources = ['module.cpp'])

    setup(name = 'superfastcode', version = '1.0',
        description = 'Python Package with superfastcode C++ extension',
        ext_modules = [sfc_module]
        )
    ```

    Bkz: [yapı C ve C++ uzantıları](https://docs.python.org/3/extending/building.html) (python.org) bu betik belgeleri için.

1. `setup.py` Kod uzantısını kullanarak komut satırından kullanıldığında Visual Studio 2015 C++ araç takımını oluşturmak için Python bildirir. Yükseltilmiş bir komut istemi açın, C++ projeyi içeren klasöre gidin (diğer bir deyişle, içeren klasörü `setup.py`) ve aşağıdaki komutu girin:

    ```command
    pip install .
    ```

### <a name="call-the-dll-from-python"></a>Python DLL çağrı

Yukarıdaki yöntemlerden birini tamamladıktan sonra artık çağırabilirsiniz `fast_tanh` işlev Python koddan ve Python uygulama performansını karşılaştırır:

1. Aşağıdaki satırları ekleyin, `.py` çağırmak için dosya `fast_tanh` yöntemi DLL'den dışarı ve çıktısını görüntüleyin.

    ```python
    from superfastcode import fast_tanh
    test(lambda d: [fast_tanh(x) for x in d], '[fast_tanh(x) for x in d]')
    ```

1. Python programı çalıştırın (**hata ayıklama > hata ayıklama olmadan Başlat** veya Ctrl + F5) ve C++ yordamı 20 kez beş Python uygulaması daha hızlı çalışır uyun. Tipik çıkış aşağıdaki gibi görünür:

    ```output
    Running benchmarks with COUNT = 500000
    sequence_tanh took 1.542 seconds

    [tanh(x) for x in d] took 1.087 seconds

    [fast_tanh(x) for x in d] took 0.158 seconds
    ```

1. Artırmayı deneyin `COUNT` farklar daha belirgin böylece değişken. Hata ayıklama derlemesi daha iyi duruma getirilmiştir ve çeşitli hata denetimleri içeren için C++ modülü hata ayıklama derlemesi de yayın derlemesi daha yavaş çalışır. Karşılaştırma için bu yapılandırmalar arasında geçiş yapmak çekinmeyin.

## <a name="debug-the-c-code"></a>C++ kod hatalarını ayıklama

Visual Studio hata ayıklama Python ve C++ kodu birlikte destekler.

1. Çözüm Gezgini'nde, select Python projeye sağ **özellikleri**seçin **hata ayıklama** sekmesini tıklatın ve ardından **hata ayıklama > yerel kod hata ayıklamayı etkinleştir** seçeneği.

    > [!Tip]
    > Yerel kodda hata ayıklama etkinleştirdiğinizde, hemen program, normal "devam etmek için... herhangi bir tuşa basın" Duraklat vermeden tamamlandığında Python çıktı penceresi kaybolabilir. Bir duraklama zorlamak için add `-i` için seçenek **çalıştırmak > yorumlayıcı bağımsız değişkenleri** alanını **hata ayıklama** sekmesinde yerel kodda hata ayıklama etkinleştirdiğinizde. Bu noktada, Ctrl + Z, çıkmak için Enter tuşuna basın bekler kodu tamamlandıktan sonra bu bağımsız değişken Python yorumlayıcı etkileşimli moduna geçirir. (Alternatif olarak, Python kodunuzu değiştirme sizin için sorun değilse ekleyebileceğiniz `import os` ve `os.system("pause")` deyimleri programınızı sonunda. Bu kod özgün Duraklat istemi çoğaltır.)

1. Seçin **Dosya > Kaydet** özelliği değişiklikler kaydedilemiyor.

1. Derleme yapılandırmasını "Hata ayıklama" Visual Studio araç çubuğunda ayarlayın.

    ![Derleme yapılandırması hata ayıklama için ayarlama](media/cpp-set-debug.png)

1. Kod genellikle hata ayıklayıcısı'ndaki çalışması daha uzun sürdüğü için değiştirmek isteyebilirsiniz `COUNT` değişkeni, `.py` yaklaşık beş kez daha küçük olan bir değer dosyaya (örneğin, ondan değiştirme `500000` için `100000`).

1. C++ kodunuzda ilk satırında bir kesme noktası belirleyerek `tanh_impl` yöntemi sonra Başlangıç hata ayıklayıcısı (F5 veya **hata ayıklama > hata ayıklamayı Başlat**). Bu kodu çağrıldığında hata ayıklayıcı durdurur. Kesme noktası isabet değil, hata ayıklama yapılandırmasını ayarlanır ve (otomatik olarak hata ayıklayıcı başlatırken gerçekleştirilmez) projesi kaydettiğiniz denetleyin.

    ![C++ kodu bir kesme noktasında durdurma](media/cpp-debugging.png)

1. Bu noktada C++ kod boyunca adım, değişkenleri inceleyin ve benzeri. Bu özelliklerin ayrıntıları [C++ hata ayıklama ve Python birlikte](debugging-mixed-mode-c-cpp-python-in-visual-studio.md).

## <a name="alternative-approaches"></a>Alternatif yaklaşımlar

Aşağıdaki tabloda açıklandığı gibi Python uzantıları oluşturulacağı anlamına gelir, çeşitli vardır. İlk CPython için ne bu makalede önceden açıklanan giriştir.

| Yaklaşım | Mahsul | Temsilcisi kullanıcıları | Pro(s) | CON(s) |
| --- | --- | --- | --- | --- |
| C/C++ uzantısı modülleri CPython için | 1991 | Standart Kitaplık | [Kapsamlı belgeler ve öğreticiler](https://docs.python.org/3/c-api/). Toplam denetim. | Derleme, taşınabilirlik, başvuru yönetimi. Yüksek C bilgi. |
| [pybind11](https://github.com/pybind/pybind11) (C++ için önerilir) | 2015 |  | Mevcut C++ kodunu Python bağlamalarını oluşturmak için basit, yalnızca üstbilgi kitaplığı. Birkaç bağımlılıkları. PyPy uyumluluk. | Yeni, daha az olgun. Koyu C ++ 11 özelliklerini kullanın. Desteklenen derleyicileri (Visual Studio bulunur) kısa listesi. |
| Cython (Recommnded c) | 2007 | [gevent](http://www.gevent.org/), [kivy](https://kivy.org/) | Python benzeri. Yüksek oranda olgun. Yüksek performans. | Derleme, yeni sözdizimi, yeni araç zinciri. |
| [Boost.Python](https://www.boost.org/doc/libs/1_66_0/libs/python/doc/html/index.html) | 2002 | | Neredeyse her C++ derleyicisi ile çalışır. | Büyük ve karmaşık suite kitaplıkların; eski derleyicileri için birçok geçici çözümler içerir. |
| ctypes | 2003 | [oscrypto](https://github.com/wbond/oscrypto) | Hiçbir derleme uluslararası kullanılabilirlik. | Verilere erişme ve C yapıları zahmetli ve hataya diziyi. |
| SWIG | 1996 | [crfsuite](http://www.chokkan.org/software/crfsuite/) | Aynı anda birçok diller için bağlamaları oluşturur. | Python yalnızca hedef ise aşırı yükü. |
| cffi | 2013 | [şifreleme](https://cryptography.io/en/latest/), [pypy](http://pypy.org/) | Tümleştirme, PyPy uyumluluk kolaylığı. | Yeni, daha az olgun. |

## <a name="see-also"></a>Ayrıca bkz.

Bu kılavuzda tamamlanmış örnekten bulunabilir [python-samples-vs-cpp-uzantısı](https://github.com/Microsoft/python-sample-vs-cpp-extension) (GitHub).