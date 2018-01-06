---
title: "Visual Studio'da Python için karışık mod hata ayıklaması | Microsoft Docs"
ms.custom: 
ms.date: 07/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload: python
ms.openlocfilehash: 762829628e4f52c797bf98acf83a48eec0cbce6c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-python-and-c-together"></a>Python ve C++ birlikte hata ayıklama

Çoğu normal Python hata ayıklayıcıları yalnızca Python kodu hata ayıklama desteği. Uygulamada, ancak Python C veya C++ ile birlikte yüksek performans veya platform API'lerini doğrudan çağırma yeteneği gerekli olduğu kullanılır (bkz [Python için C++ uzantısı oluşturma](cpp-and-python.md) bir örnek. Python proje yüklendiğinde, Visual Studio tümleşik, eşzamanlı karma Python ve yerel ile C/C++, birleştirilmiş çağrı yığınları adım Python ve yerel kodu, her iki tür kod bir kesme noktaları arasındaki olanağı ve yeteneği hata ayıklama modu sağlar. Yerel çerçeveler ve tersi nesneleri Python gösterimlerini bakın:

![Karışık mod hata ayıklaması](media/mixed-mode-debugging.png) 

Test ve yerel C modülleri Visual Studio ile hata ayıklama yapı giriş için bkz: [derinlemesine: yerel modülleri oluşturma](https://youtu.be/D9RlT06a1EI) (youtube.com, 9m9s). Video için Visual Studio 2015 ve 2017 için geçerlidir.

> [!VIDEO https://www.youtube.com/embed/D9RlT06a1EI]

> [!Note]
> Karışık mod hata ayıklaması Visual Studio için Python araçları ile kullanılabilir değil 1.x.

## <a name="enabling-mixed-mode-debugging"></a>Karışık mod hata ayıklamayı etkinleştirme

1. Select Çözüm Gezgini'nde projeye sağ tıklayın **özellikleri**seçin **hata ayıklama** sekmesini tıklatın ve ardından seçeneğini Aç **yerel kod hata ayıklamayı etkinleştir**. Bu seçenek, tüm hata ayıklama oturumları için karışık mod sağlar.

    ![Yerel kod hata ayıklamasını etkinleştirme](media/mixed-mode-debugging-enable-native.png)

    > [!Tip]    
    > Yerel kodda hata ayıklama etkinleştirdiğinizde, hemen program, normal "devam etmek için... herhangi bir tuşa basın" Duraklat vermeden tamamlandığında Python çıktı penceresi kaybolabilir. Bir duraklama zorlamak için add `-i` için seçenek **çalıştırmak > yorumlayıcı bağımsız değişkenleri** alanını **hata ayıklama** sekmesinde yerel kodda hata ayıklama etkinleştirdiğinizde. Bu noktada, Ctrl + Z, çıkmak için Enter tuşuna basın bekler kodu tamamlandıktan sonra bu bağımsız değişken Python yorumlayıcı etkileşimli moduna geçirir.

1. Karışık mod hata ayıklayıcı varolan bir işlemi eklerken (**hata ayıklama > ekleme işlemi için...** ), select **seçin...**  açmak için düğmeye **kod türünü seç** iletişim, kümesi **bu kodu türleri hata ayıklama** seçeneği ve her ikisini de seçin **yerel** ve  **Python** listesinde:

    ![Yerel ve Python kodu türü seçme](media/mixed-mode-debugging-code-type.png)

    Kod türü ayarlarını kalıcı, böylece daha sonra farklı bir işlem eklerken karışık mod hata ayıklaması devre dışı bırakmak istiyorsanız, bu adımları yineleyin ve Python kodu türü temizleyin.

    Ek olarak, veya bunun yerine, diğer kod türlerini seçmek mümkündür **yerel**. Örneğin, bir yönetilen uygulamayı CPython barındırıyorsa, hangi içinde Aç yerel uzantısı modülleri kullanır ve tüm üç kontrol edebilirsiniz hata ayıklamak istediğiniz **Python**, **yerel**ve yönetilen ** bir araya toplamak için bir birleşik hata ayıklama deneyimini dahil çağrı yığınları ve tüm üç çalışma zamanları arasında adımlama birleşik.

1. Karışık modda hata ayıklama ilk kez başlattığınızda, görebileceğiniz bir **simgeleri Python gerekli** iletişim. Bkz: [karışık mod hata ayıklama simgeleri](debugging-symbols-for-mixed-mode.md) Ayrıntılar için. Verilen tüm Python ortamı için yalnızca bir kez simgeleri yüklemeniz gerekir. Visual Studio 2017 yükleyici Python desteğini yüklerseniz, simge otomatik olarak dahil olduğunu unutmayın.

1. Python kaynak kodu kendisini taraftan olmasını isteyebilirsiniz. Standart Python için kaynak kodu alanından elde edilen [https://www.python.org/downloads/source/](https://www.python.org/downloads/source/). Sürümünüz için uygun arşiv karşıdan yükleyip bir klasöre ayıklayın. Ardından belirli dosyaları noktası ne olursa olsun, o klasördeki için Visual Studio ister noktası.

> [!Note]
> Visual Studio'ya yüklenen bir Python proje olduğunda karma-burada açıklandığı gibi hata ayıklama modu etkindir. Bu proje karma mod seçeneği kullanılabilir kılan olan Visual Studio'nun hata ayıklama modunu belirler. Ancak, yüklenen C++ projesi varsa (yaptığınız gibi [python.org üzerinde açıklandığı gibi başka bir uygulamada Python katıştırma](https://docs.python.org/3/extending/embedding.html), Visual Studio karışık mod hata ayıklaması desteklemiyor yerel C++ hata ayıklayıcı kullanıyorsa.
>
> Bu durumda, hata ayıklama olmadan C++ projesi Başlat (**hata ayıklama > hata ayıklama olmadan Başlat** veya Ctrl + F5) ve ardından **hata ayıklama > ekleme işlemi için...** . Görüntülenen iletişim kutusunda, uygun işlem seçin, ardından kullanmak **seçin...**  açmak için düğmeye **kod türünü seç** , seçebileceğiniz Python aşağıda gösterildiği gibi iletişim. Seçin **Tamam** sonra bu iletişim kutusunu kapatmak için **Attach** hata ayıklayıcısını başlatın. Uygun duraklama veya gecikme hata ayıklayıcı eklemeden önce hata ayıklamak istediğiniz Python çağrı değil emin olmak için C++ uygulamasında tanıtmak gerekebileceğini unutmayın.
>
> ![Bir hata ayıklayıcısı eklerken Python hata ayıklama türünü seçme](media/mixed-mode-debugging-attach-type.png)

## <a name="mixed-mode-specific-features"></a>Karışık mod belirli özellikler

- [Birleşik çağrı yığını](#combined-call-stack)
- [Python ve yerel kodu arasında adımlama](#stepping-between-python-and-native-code)
- [Yerel kod görünümünde PyObject değerleri](#pyobject-values-view-in-native-code)
- [Python kodu yerel değerleri görünümde](#native-values-view-in-python-code)

### <a name="combined-call-stack"></a>Birleşik çağrı yığını

Çağrı yığını penceresi, hem yerel hem de ikisi arasında işaretlenmiş geçişleri ile araya eklemeli Python yığın çerçeveleri gösterir:

![Birleşik çağrı yığını](media/mixed-mode-debugging-call-stack.png)

> [!Note]
> Geçişler, geçiş, yönünü belirtmeden "[dış kod olarak]" görünür **Araçlar > Seçenekler > hata ayıklama > Genel > sadece kendi kodumu etkinleştir** seçeneği ayarlanmış.

Herhangi bir çağrı kareyi çift etkin hale getirir ve uygun kaynak kodu mümkünse açar. Kaynak kodu kullanılabilir durumda değilse, çerçeve hala etkin oluşturulur ve yerel değişkenler Denetlenmekte.

### <a name="stepping-between-python-and-native-code"></a>Python ve yerel kodu arasında adımlama

Step Into (F11) veya Step Out (Shift + F11) komutlarını kullanarak, karışık mod hata ayıklayıcı kod türleri arasındaki değişiklikleri doğru şekilde işler. Python C'de uygulanan bir türde bir yöntem aradığında, örneğin, bir çağrıda yöntemi yerel işlevi yöntemi uygulama başlangıcında durdurur atlama. Benzer şekilde, ne zaman yerel kod çağrılan Python kodu sonuçları bazı Python API işlevi çağırır. Örneğin, içine Adımlama bir `PyObject_CallObject` Python içinde tanımlanmış bir işlev değeri Python işlevi başında durur. Yerel Python atlama de desteklenir python'dan çağrılan yerel işlevler için [ctypes](http://docs.python.org/3/library/ctypes.html).

### <a name="pyobject-values-view-in-native-code"></a>Yerel kod görünümünde PyObject değerleri

Yerel (C veya C++) çerçeve etkin olduğunda, kendi yerel değişkenler hata ayıklayıcı Yereller penceresinde görünür. Yerel Python uzantısı modüller, bu değişkenleri çoğunu türlerinin `PyObject` (için typedef olduğu `_object`), ya da (bkz. Aşağıdaki liste) diğer birkaç temel Python türleri. Karışık mod hata ayıklama, bu değerleri "Python Görünüm" etiketli bir ek alt düğüm sunma Genişletildiğinde, bu düğüm değişkenin Python gösterimi gösterir, ne yerel bir değişken varsa görür aynı aynı nesneye başvuran bir Python çerçevede yoktu. Bu düğümün alt düzenlenebilir.

![Python görünümü](media/mixed-mode-debugging-python-view.png)

Bu özellik devre dışı bırakmak için herhangi bir yere yerel öğeler penceresi iki durumlu içinde sağ tıklayın ve **Python > Göster Python görünüm düğümleri** menü seçeneği:

![Python görünüm etkinleştirme](media/mixed-mode-debugging-enable-python-view.png)

C (etkinse) bu düğümleri Göster "[Python Görünüm]" türleri:

- `PyObject `
- `PyVarObject`
- `PyTypeObject`
- `PyByteArrayObject`
- `PyBytesObject`
- `PyTupleObject`
- `PyListObject`
- `PyDictObject`
- `PySetObject`
- `PyIntObject`
- `PyLongObject`
- `PyFloatObject`
- `PyStringObject`
- `PyUnicodeObject`

"[Python Görünüm]" kendiniz yazın türleri için otomatik olarak görüntülenmez. Uzantıları için Python yazarken 3.x, bu eksiklik değil genellikle bir sorun herhangi bir nesne sonuçta sahip olduğu bir `ob_base` alan türlerinden birinin yukarıdaki "[görünmesi Python Görünüm]" neden olur. 

Python için 2.x, Bununla birlikte, her nesne türü satır içi alanlar koleksiyonu olarak genellikle üstbilgisinde bildirir ve özel yazılan türler arasında bir ilişkilendirme yok ve `PyObject` C/C++ kod türü sistem düzeyinde. "[Python Görünüm]" düğümleri gibi özel türler için etkinleştirmek için düzenleme `PythonDkm.natvis` içinde [Python araçları yükleme dizini](installation.md#install-locations)ve XML Yapısı C veya C++ sınıfı için başka bir öğe ekleyin.

Bir alternatif (ve daha iyi) seçenek izlemektir [CESARETLENDİRİCİ 3123](http://www.python.org/dev/peps/pep-3123/) ve açık bir `PyObject ob_base;` alan yerine `PyObject_HEAD`, her zaman geriye doğru uyumluluk nedenleriyle mümkün olmayabilir ancak.


### <a name="native-values-view-in-python-code"></a>Python kodu yerel değerleri görünümde

Python çerçeve etkin olduğunda önceki bölümde benzer, "[C++]"için Görünüm yerel öğeler penceresi yerel değerleri etkinleştirebilirsiniz. Bu özellik varsayılan olarak etkindir, bu, yerel öğeler penceresi sağ tıklayarak ve geçiş açmak için değil **Python > Göster C++ görünüm düğümleri** menü seçeneği.

![C++ görünüm etkinleştirme](media/mixed-mode-debugging-enable-cpp-view.png)

"[C++ Görünüm]" düğümü için bir değer, yerel bir çerçevede ne görür için aynı temel C/C++ yapısı bir gösterimini sağlar. Örneğin, bir örneği gösterir `_longobject` (kendisi için `PyLongObject` bir typedef olduğu) bir Python uzun tamsayı ve bunun için yerel sınıfları için türlerini anlamak için çalışır kendiniz yazmış. Bu düğümün alt düzenlenebilir.

![C++ görünümü](media/mixed-mode-debugging-cpp-view.png)

Bir nesnenin alt alan türü olup olmadığını `PyObject`, veya diğer birini desteklenen türleri, burada bağlantılar doğrudan gösterilmez için nesne grafiklerinin gitmek olası hale getirerek (Bu Beyanları etkinse) "[Python Görünüm]" gösterimi düğümüne sahipse Python.

Nesne türünü belirlemek için Python nesne meta verilerini kullanın, "[Python Görünüm]" düğümleri, "[C++ Görünüm]" için benzer şekilde güvenilir hiçbir mekanizması yoktur. Genel olarak bakıldığında, Python değeri verildiğinde (diğer bir deyişle, bir `PyObject` başvuru) güvenilir bir şekilde hangi C/C++ yapısı yedekleme belirlemek mümkün değil. Karışık mod hata ayıklayıcı nesnenin türü çeşitli alanlarını bakarak bu tür tahmin etmeye çalışır (gibi `PyTypeObject` tarafından başvuruda bulunulan kendi `ob_type` alan) işlevi işaretçi türlerine sahip. Bu işlev işaretçileri birini başvuran çözümlenebilir bir işlev ve bu işlev varsa bir `self` daha fazla belirli türüne sahip parametre `PyObject*`, sonra da bu tür yedekleme türü olduğu varsayılır. Örneğin, varsa `ob_type->tp_init` aşağıdaki işlevi, belirtilen nesne noktalarının:

```c
static int FobObject_init(FobObject* self, PyObject* args, PyObject* kwds) {
    return 0;
}
```

hata ayıklayıcı nesnesinin C türü olduğunu doğru şekilde türetme sonra `FobObject`. Daha kesin bir türden belirlenemiyor ise `tp_init`, bunu diğer alanlara taşır. Bu alanlarının tümünden türünü türetme kaydedemediği "[C++ Görünüm]" düğüm nesnesi olarak gösterir. bir `PyObject` örneği.

Her zaman özel yazılan türleri için kullanışlı bir temsilini almak için en az bir özel işlevi türü kaydedilirken kaydetmek ve kesin türü belirtilmiş bir kullanmak en iyisidir `self` parametresi. Çoğu türleri doğal olarak bu gereksinimi karşılamak; Bu durumda, ardından değilse `tp_init` genellikle bu amaçla kullanmak için en uygun girişidir. Bir kukla uygulaması `tp_init` yalnızca var olan bir türü için hata ayıklayıcı türü etkinleştirmek çıkarım yalnızca sıfır hemen Yukarıdaki kod örneği olduğu gibi geri dönebilirsiniz.

## <a name="differences-from-standard-python-debugging"></a>Python standart hata ayıklama gelen farklar

Karışık mod hata ayıklayıcı farklıdır [standart Python hata ayıklayıcı](debugging.md) içeren bazı ek özellikler sunar ancak Python ile ilgili bazı özellikler eksik:

- Desteklenmeyen özellikler: koşullu kesme noktaları, hata ayıklama etkileşimli pencere ve platformlar arası uzaktan hata ayıklama.
- Komut penceresi: tüm sınırlamalar da dahil olmak üzere işlevselliği, sınırlı bir alt kümesinde kullanılabilir ancak burada listelenir.
- Python sürümleri desteklenir: CPython 2.7 ve 3.3 + yalnızca.
- Visual Studio Kabuğu: Python ile Visual Studio Kabuğu kullanırken (örneğin, tümleşik yükleyici kullanarak yüklediyseniz), Visual Studio C++ projeleri açamıyor ve yalnızca bir temel metin düzenleyici, C++ dosyaları düzenleme deneyimini olmasıdır. Ancak, C/C++ hata ayıklama ve karışık mod hata ayıklaması tam olarak Kabuğu'nda yerel kod ve C++ ifade değerlendirme hata ayıklayıcı Windows içine Adımlama kaynak koduyla desteklenir.
- Görüntüleme ve nesneleri genişletme: Python görüntüleme, izleme ve yerel hata ayıklayıcısı aracı windows nesneleri, yalnızca nesnelerin yapısı karışık mod hata ayıklayıcı gösterir. Bu otomatik olarak özellikleri değerlendirmek veya hesaplanan öznitelikleri gösterir. İsteğe bağlı olarak koleksiyonlar için yalnızca yerleşik koleksiyon türleri için öğeleri gösterir (`tuple`, `list`, `dict`, `set`). Bazı yerleşik koleksiyonu türünden devralınan sürece özel koleksiyon türlerini koleksiyon olarak görselleştirilen değil.
- İfade değerlendirme: aşağıya bakın.

### <a name="expression-evaluation"></a>İfade değerlendirme

Hata ayıklaması işlem kodda, herhangi bir noktada duraklatıldığında, bir g/ç işlemi veya diğer benzer sistem çağrısı engellenmez sürece standart Python hata ayıklayıcı izleme ve anında windows rasgele Python ifadeler sağlar. Karışık mod hata ayıklaması içinde rastgele ifadeleri yalnızca Python kodu bir kesme noktası sonra durduğunda veya koda adımlarken değerlendirilebilir. Deyimler kesme veya sürüm işleminin gerçekleştiği parçacığında değerlendirilebilir.

İfade değerlendirme yerel kod veya Python kodu nereye Yukarıdaki koşullar (örneğin, bir adım kullanıma işleminden sonra veya farklı bir iş parçacığı üzerinde) uygulamayın durduğunda, yerel ve genel değişkenler şu anda seçili kapsamdaki erişimle sınırlı Çerçeve, onların alanları erişme ve yerleşik koleksiyon türleri değişmez değerler ile dizin oluşturma. Örneğin, (mevcut değişkenler ve uygun türlerini alanlarının tüm tanımlayıcılar bakın olması koşuluyla) aşağıdaki deyim her bağlamda değerlendirilebilir:

```python
foo.bar[0].baz['key']
```

Karışık mod hata ayıklayıcısı olsa da gibi ifadeler farklı çözümleniyor. Tüm üye erişimi işlemleri doğrudan nesnesinin bir parçası olan alanları bakın (bir girişe gibi kendi `__dict__` veya `__slots__`, veya Python maruz yerel bir yapı alanı `tp_members`) ve Yoksay `__getattr__`, `__getattribute__`veya tanımlayıcısı mantığı. Benzer şekilde, tüm dizin oluşturma işlemlerini Yoksay `__getitem__`ve koleksiyonların iç veri yapılarını doğrudan erişebilirsiniz.

Tutarlılık sağlamak, bu ad çözümleme düzeni rastgele ifadeleri geçerli Dur noktada izin verilip verilmediğini bağımsız olarak, sınırlı ifade değerlendirme kısıtlamalarla eşleşen tüm ifadeler için kullanılır. Uygun Python semantiği tam özellikli bir değerlendirici zaman zorlamak için kullanılabilir, ifadesi parantez içine alın:

```python
(foo.bar[0].baz['key'])
```