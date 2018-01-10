---
title: "Dinamik simgesel yürütme | Microsoft Intellitest Geliştirici Test aracı | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IntelliTest, Dynamic symbolic execution
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: c8d72ad4e5b84802f3c8f2eba426f98ed5477468
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="input-generatation-using-dynamic-symbolic-execution"></a>Giriş generatation kullanılarak dinamik simgesel yürütme

Intellitest oluşturur girdileri [parametreli birim testleri](test-generation.md#parameterized-unit-testing) programda dal koşulları çözümleme tarafından. Test girişleri olup olmadığını programının yeni dallanma davranışları tetikleyebilir göre seçilir. Analiz artımlı bir işlemdir. Bir koşul iyileştirir **t -> {true, false} s:** giriş parametreleri resmi test **ı**. **q** Intellitest zaten gözlemleri davranışları kümesini temsil eder. Başlangıçta, **q: = false**, bu yana hiçbir şey henüz gözlenmiştir.

Döngü adımlardır:

1. Intellitest belirler girişleri **ı** şekilde **q (i) = false** kullanarak bir [kısıtlaması Çözücü](#constraint-solver). 
   Yapı, giriş tarafından **ı** önce görülen olmayan bir yürütme yolu sürer. Başlangıçta, bunun anlamı **ı** yürütme yol henüz saptanmamış olduğundan herhangi bir giriş olabilir.

1. Intellitest giriş seçilen ile test yürütür **ı**, test ve test altındaki program yürütülmesi izler.

1. Yürütme sırasında programın tüm koşullu dalları program tarafından belirlenen belirli bir yolunu alır. Yürütme belirlemek tüm koşullar kümesi adlı *yol koşulu*koşulu olarak yazılmış **t -> {true, false} p:** resmi giriş parametreleri üzerinden. Bu koşul gösterimini Intellitest hesaplar.

1. Intellitest kümeleri **q: (q ya da p) =**. Diğer bir deyişle, tarafından temsil edilen yolu görüldüğü olgu kayıtları **p**.

1. 1. adıma gidin.

Intellitest'ın [kısıtlaması Çözücü](#constraint-solver) .NET programlarda görünebilir tüm türlerin değerleri uğraşmanız:

* [Tamsayıları](#integers-and-floats) ve [gezinen](#integers-and-floats)
* [Nesneler](#objects)
* [Yapılar](#structs)
* [Diziler](#arrays-and-strings) ve [dizeleri](#arrays-and-strings)

Intellitest belirtilen varsayımlar ihlal girişleri filtreler.

Hemen girişleri yanı sıra (bağımsız değişkenleri [parametreli birim testleri](test-generation.md#parameterized-unit-testing)), bir test daha fazla giriş değerleri çizebilirsiniz [PexChoose](static-helper-classes.md#pexchoose) statik sınıf. Seçenekler ayrıca davranışını belirlemek [mocks parametreli](#parameterized-mocks).

<a name="constraint-solver"></a>
## <a name="constraint-solver"></a>Kısıtlama Çözücü

Intellitest kısıtlaması Çözücü bir test ve test altındaki program ilgili giriş değerlerini belirlemek için kullanır.

Intellitest kullanan [Z3](https://github.com/Z3Prover/z3/wiki) kısıtlaması Çözücü.

<a name="dynamic-code-coverage"></a>
## <a name="dynamic-code-coverage"></a>Dinamik kod kapsamı

Yan-etkisi olarak izleme çalışma zamanı, Intellitest dinamik kod kapsamı verilerini toplar. Bu adlı *dinamik* Intellitest yürütüldüğü kod hakkında bildiği için diğer kapsamı aracı genellikle yaptığınız gibi bu nedenle, mutlak değerler kapsam için aynı şekilde veremez. 

Intellitest 5/10 temel taşı olarak dinamik kapsamı bildirdiğinde, örneğin, bu beş blok on dışında burada kapsanan olduğunu anlamına gelir göre Analiz kadarki ulaştınız tüm yöntemleri bloklarında toplam sayısı (mevcut tüm yöntemleri aksine bir test altındaki ssembly) on ' dir.
Daha fazla erişilebilir yöntemi olarak analiz, ileride bulunan, her iki pay (Bu eaxmple 5) ve (10) payda artırabilir.

<a name="integers-and-floats"></a>
## <a name="integers-and-floats"></a>Tamsayılar ve float

Intellitest'ın [kısıtlaması Çözücü](#constraint-solver) test giriş değerlerini ilkel türleri gibi belirler **bayt**, **int**, **float**ve diğerleri test ve test altındaki program için farklı bir yürütme yollarını tetiklemek için sırası.

<a name="objects"></a>
## <a name="objects"></a>Nesneler

Intellitest olabilir ya da [varolan .NET sınıfların örnekleri oluşturmak](#existing-classes), veya Intellitest için otomatik olarak kullanabileceğiniz [sahte nesneler oluşturmak](#parameterized-mocks) , belirli bir arabirim uygulamak ve farklı şekilde davranır kullanımınıza bağlı olarak.

<a name="existing-classes"></a>
## <a name="instantiating-existing-classes"></a>Varolan sınıflarını örnekleme

**Sorun nedir?**

Bir test ve test altındaki program çalıştırıldığında Intellitest yürütülen yönergeleri izler. Özellikle, tüm alanları erişimi izler. Ardından kullanan bir [kısıtlaması Çözücü](#constraint-solver) test ve test altındaki program diğer ilginç şekillerde davranacak şekilde nesneleri ve alan değerlerine dahil olmak üzere yeni test girişleri belirlemek için.

Bu, Intellitest belirli türdeki nesneleri oluşturmak ve alan değerlerini ayarlamak için gerektiği anlamına gelir. Sınıf ise [görünür](#visibility) ve bir [görünür](#visibility) varsayılan oluşturucu, Intellitest sınıfının bir örneğini oluşturabilirsiniz.
Sınıfın tüm alanları ise [görünür](#visibility), Intellitest ayarlayabileceğiniz alanları otomatik olarak.

Tür görünür değil veya alanlar değildir [görünür](#visibility), Intellitest nesneleri oluşturmak ve bunları ilginç durumlara düzeyde kod kapsamı elde etmek için hale getirmek için Yardım gerekiyor. Intellitest yansıma oluşturmak ve örnekleri rasgele şekilde başlatmak için kullanabilirsiniz, ancak bu genelde değil  
Nesne hiçbir zaman normal program yürütülmesi sırasında oluşabilecek bir duruma getirmeniz çünkü önerilir. Bunun yerine, kullanıcıdan ipuçları Intellitest kullanır.

<a name="visibility"></a>
## <a name="visibility"></a>Görünürlük

.NET Framework bir karmaşık görünürlük modeli vardır: türleri, yöntemleri, alanları ve diğer üyeleri olabilir **özel**, **ortak**, **iç**ve daha fazlası.

Intellitest testleri oluşturduğunda, .NET görünürlük kurallardan oluşturulan testleri bağlamında ilgili yasal (örneğin, Oluşturucular, yöntemleri çağırma ve alanlarını ayarlama) yalnızca eylemleri gerçekleştirmek deneyecek.

Kurallar aşağıdaki gibidir:

* **İç üye görünürlüğü**
  * Intellitest varsayar oluşturulan testleri kapsayan görünür iç üyeleri erişimi olmasını [PexClass](attribute-glossary.md#pexclass).
  .NET sahip **Internalsvisibletoattribute** iç üyeleri görünürlüğünü diğer derlemelerden genişletmek için.<p />

* **Özel görünürlüğünü ve ailesi (korumalı, C#) üyeleri [PexClass](attribute-glossary.md#pexclass)**
  * Intellitest her zaman yerleştirir oluşturulan testleri doğrudan [PexClass](attribute-glossary.md#pexclass) ya da bir alt sınıfı. Bu nedenle, tüm görünür aile üyelerine kullanabilir Intellitest varsayar (**korumalı** C#).
  * Oluşturulan testleri doğrudan yerleştirilmişse [PexClass](attribute-glossary.md#pexclass) (genellikle kısmi sınıflar kullanarak), tüm özel üyeleri de kullanabilir Intellitest varsayar [PexClass](attribute-glossary.md#pexclass).<p />

* **Genel üyeler görünürlüğünü**
  * Intellitest varsayar dışarı aktarılan tüm üyeleri bağlamında görünür kullanabilir [PexClass](attribute-glossary.md#pexclass).

<a name="parameterized-mocks"></a>
## <a name="parameterized-mocks"></a>Parametreli mocks

Bir arabirim türünde bir parametre içeren bir yöntem test etme? Veya korumalı olmayan bir sınıfın? Bu yöntem çağrıldığında hangi uygulamaları daha sonra kullanılacak Intellitest bilmez. Ve belki de hiç bile gerçek bir uygulama kullanılabilir test zaman.

Geleneksel yanıt kullanmaktır *mock nesneleri* açık davranışına sahip. 

Sahte bir nesne bir arabirimini uygulayan (veya korumalı olmayan sınıfını genişleten). Gerçek bir uygulama, ancak yalnızca sahte nesnesini kullanarak testlerin yürütmesini sağlayan kısayol temsil etmiyor. Buna ait davranışı el ile kullanıldığı her test çalışmasının bir parçası olarak tanımlanır. Sahte nesneler ve onların beklenen bir davranış tanımlamanızı kolaylaştıran birçok aracı var, ancak bu davranış hala el ile tanımlanmış olmalıdır.

Sabit kodlanmış değerler yerine sahte nesneler, Intellitest değerleri oluşturabilir. Etkinleştirir gibi [parametreli birim testi](test-generation.md#parameterized-unit-testing), Intellitest ayrıca parametreli mMocks sağlar.

Parametreli mocks iki farklı bir yürütme modu vardır:

* **seçme**: kod keşfetme, parametreli mocks bir ek sınama girdi kaynaktır ve Intellitest denemesini ilginç değerleri seçin
* **yeniden yürütme**: daha önce oluşturulan test yürütülürken parametreli mocks saplamalar davranışı (diğer bir deyişle, önceden tanımlanmış davranış) gibi davranırlar.

Kullanım [PexChoose](static-helper-classes.md#pexchoose) parametreli mocks değerlerini elde edilir.

<a name="structs"></a>
## <a name="structs"></a>Yapılar

Intellitest akıl hakkında **yapısı** ilgilenir ile şekilde değerleri benzer [nesneleri](#objects).

<a name="arrays-and-strings"></a>
## <a name="arrays-and-strings"></a>Diziler ve dizeler

Bir test ve test altındaki program çalışırken Intellitest yürütülen yönergeleri izler. Özellikle, ne zaman program uzunluğuna bir dize veya dizi (ve alt sınırlarını ve çok boyutlu bir dizi uzunluğu) bağlıdır görür. Program bir dize veya dizi farklı öğelerinin nasıl kullandığını görür. Ardından kullanan bir [kısıtlaması Çözücü](#constraint-solver) hangi uzunlukları ve öğe değerleri test ve ilginç şekillerde davranmasına test altındaki program neden olabilir belirlemek için.

Diziler ve ilginç program davranışları tetiklemek için gereken dizeleri boyutunu en aza indirmek Intellitest çalışır.

<a name="additional-inputs"></a>
## <a name="obtaining-additional-inputs"></a>Ek girişlerini alma

[PexChoose](static-helper-classes.md#pexchoose) statik sınıf testine ek girişleri elde etmek için kullanılabilir ve uygulamak için kullanılan [mocks parametreli](#parameterized-mocks).

<a name="further-reading"></a>
## <a name="further-reading"></a>Daha fazla bilgi

* [Nasıl çalışır?](https://blogs.msdn.microsoft.com/visualstudioalm/2014/12/11/smart-unit-tests-a-mental-model/)

## <a name="got-feedback"></a>Geri bildirim var mı?

Fikirlerinizi sonrası ve özellik istekleri  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
