---
title: "Genel bakış | Microsoft Intellitest Geliştirici Test aracı | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IntelliTest, Visual Studio IntelliTest developer testing tool
ms.assetid: A7B98509-7ACA-4E25-BD1B-BBC98742F028
caps.latest.revision: "56"
ms.author: douge
manager: douge
ms.openlocfilehash: 454cd11d9e196e7de9775448640a8ee22c434d4c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="overview-of-microsoft-intellitest"></a>Microsoft Intellitest genel bakış

Intellitest hatalar erken bulmanızı sağlar ve test bakım maliyetlerini azaltır. Otomatik ve şeffaf bir sınama yaklaşımı kullanarak, Intellitest .NET kodunuz için testleri adayı dizisi oluşturabilirsiniz. Test paketi oluşturma daha fazla destekli tarafından *doğruluk özellikleri* , belirtin. Test altındaki kodun geliştikçe Intellitest bile test paketi otomatik olarak gelişmesi.

**Belirlemeye testleri**  
Intellitest kod geleneksel birim testleri dizisi açısından davranışını belirlemenizi sağlar. Bu tür bir test paketine eski ya da tanınmayan kodu yeniden düzenleme ile ilişkili karmaşıklık tackling temelini oluşturan bir regresyon paketi olarak kullanılabilir.

**Destekli test giriş oluşturma**  
Açık Kod Analizi Intellitest kullanır ve test giriş değerleri otomatik olarak kesin oluşturmak için kısıtlama çözme yaklaşımı; genellikle gerek kullanıcı müdahalesi. Karmaşık nesne türleri için oluşturucuları otomatik olarak oluşturur. Test giriş nesil genişletme ve gereksinimlerinize uyacak şekilde oluşturucuları yapılandırma yönlendirebilir. Koddaki onaylar olarak belirtilen doğruluk özellikleri de otomatik olarak daha fazla test giriş nesil kılavuzluk etmesi için kullanılır.

**IDE tümleştirme**  
Intellitest Visual Studio IDE içinde tam olarak tümleşiktir. (Otomatik olarak oluşturulan girdi, kodunuzu, oluşturulan test durumları ve bunların geçişi çıktısını veya başarısız durumu gibi) test paketi oluşturma sırasında toplanan tüm bilgiler Visual Studio IDE içinde görüntülenir. Kodunuzu düzeltme ve Intellitest, Visual Studio IDE ayrılmadan yeniden çalıştırmayı arasında kolayca yineleyebilirsiniz. Testleri bir çözüm olarak birim testi projesi içine kaydedilir ve otomatik olarak daha sonra Visual Studio Test Gezgini tarafından algılanır.

**Varolan test yöntemler tamamlar**  
Var olan zaten izleyebilir uygulamaları sınama tamamlamak üzere Intellitest kullanın.

Test etmek isterseniz:

* Temel veri ya da dizi ilkel verisi üzerinden algoritmaları:
  * Yazma [parametreli birim testleri](test-generation.md#parameterized-unit-testing)
* Algoritmaları derleyici gibi karmaşık veriler üzerinde:
  * ilk veri soyut bir temsilini oluşturmak ve algoritma akış Intellitest sağlar
  * kullanarak örnekleri derleme Intellitest izin [özel nesne oluşturma](input-generation.md#objects) ve veri invariants ve algoritma çağırma
* Veri kapsayıcıları:
  * Yazma [parametreli birim testleri](test-generation.md#parameterized-unit-testing)
  * kullanarak örnekleri derleme Intellitest izin [özel nesne oluşturma](input-generation.md#objects) ve veri invariants ve kapsayıcı ve yeniden denetleyin ve invariants yöntemi daha sonra çağırma
  * Yazma [parametreli birim testleri](test-generation.md#parameterized-unit-testing) parametrelere bağlı olarak uygulama farklı yöntemlerini çağırın
* Varolan bir kod temel:
  * bir dizi oluşturarak başlamak için Visual Studio'nun Intellitest Sihirbazı'nı kullanın [parametreli birim testleri (Yerleştirmelerin)](test-generation.md#parameterized-unit-testing)

<a name="hello-world"></a>
## <a name="the-hello-world-of-intellitest"></a>Intellitest Merhaba Dünya

Intellitest girişleri, ünlü oluşturmak için kullanabileceğiniz anlamına gelir sınanan program ilgili bulur **Merhaba Dünya!** Dize. Bu bir C# mstest'i dayalı test projesi oluşturulur ve bir başvuru eklenir varsayar **Microsoft.Pex.Framework**. Farklı bir test Framework'te kullanıyorsanız, C# sınıf kitaplığı oluşturun ve projeyi ayarlama konusunda test framework belgelerine bakın.

Aşağıdaki örnek adlı parametre iki kısıtlamalar oluşturur **değeri** böylece Intellitest gerekli dize oluşturur.

```
using System;
using Microsoft.Pex.Framework; 
using Microsoft.VisualStudio.TestTools.UnitTesting; 

[TestClass]
public partial class HelloWorldTest {
    [PexMethod]
    public void HelloWorld([PexAssumeNotNull]string value) {
        if (value.StartsWith("Hello")
            && value.EndsWith("World!")
            && value.Contains(" "))
            throw new Exception("found it!");
    }
}
```

Derlenmiş ve yürütülen sonra Intellitest testleri aşağıdaki gibi bir dizi oluşturur:

1. ""
2. "\0\0\0\0\0"
3. "Hello"
4. "\0\0\0\0\0\0"
5. "Hello\0"
6. "Hello\0\0"
7. "Hello\0World!"
8. "Hello World!"

Git [burada](https://docs.microsoft.com/en-gb/visualstudio/test/generate-unit-tests-for-your-code-with-intellitest#Anchor_0) oluşturulan testleri kaydedildiği anlamak için.
Oluşturulan test kodu aşağıdaki gibi bir test eklemeniz gerekir:

```
[TestMethod]
[PexGeneratedBy(typeof(global::HelloWorldTest))]
[PexRaisedException(typeof(Exception))]
public void HelloWorldThrowsException167()
{
    this.HelloWorld("Hello World!");
}
```

Kolay!

<a name="limitations"></a>
## <a name="limitations"></a>Sınırlamalar

Bu bölümde Intellitest sınırlamaları açıklanmaktadır:

* [Nondeterminism](#nondeterminism)
* [Eşzamanlılık](#concurrency)
* [Yerel .NET kod](#native-code)
* [Platform](#platform)
* [Dil](#language)
* [Simgesel mantığı](#symbolic-reasoning)
* [Yığın izlemeleri](#incorrect-stack)

<a name="nondeterminism"></a>
### <a name="nondeterminism"></a>Nondeterminism

Intellitest çözümlenen program belirleyici olduğunu varsayar. Değilse, bağlı bir araştırması ulaşana kadar Intellitest döngüsü.

Intellitest Intellitest denetleyemezsiniz girişler için dayalıysa determistic olmayan olması için bir program göz önünde bulundurur.

Intellitest denetimleri için sağlanan girişleri [parametreli birim testleri](test-generation.md#parameterized-unit-testing) ve alanından elde edilen [PexChoose](static-helper-classes.md#pexchoose). Bu algılama yönetilmeyen veya uninstrumented kodu çağrıları sonuçlarını da Araçlı programı için "girişler" olarak kabul edilir, ancak Intellitest bunları denetleyemezsiniz. Bu dış kaynaklardan gelen belirli değerleri programının denetim akışı bağlıdır, Intellitest "program daha önce bitişik alanları ilerletebilir olamaz". 

Ayrıca, program değerlerin dış kaynaklardan program yeniden çalıştırırken değiştirirseniz determistic dışı olarak kabul edilir. Bu gibi durumlarda Intellitest programın yürütülmesi denetime kaybeder ve kendi arama çok verimli hale gelir.

Bu gerçekleştiğinde bazen belirgin değildir. Aşağıdaki örnekler göz önünde bulundurun:

* Sonucu **GetHashCode()** yöntemi tarafından yönetilmeyen kodu sağlanır ve tahmin edilebilir değil.
* **System.Random** sınıfı gerçekten rastgele değerler teslim etmek için geçerli sistem saatini kullanır.
* **System.DateTime** sınıfı açıkça Intellitest denetimi altında olmayan geçerli saati sağlar.

<a name="concurrency"></a>
### <a name="concurrency"></a>Eşzamanlılık

Intellitest birden çok iş parçacıklı programlar işlemez.

<a name="native-code"></a>
### <a name="native-code-net-code-that-is-not-instrumented"></a>Yerel kod, değil izlenmiş olan .NET kodu

Intellitest x86 gibi yerel kod anlamak değil yönergeleri adlı aracılığıyla **P/Invoke**. Bu tür çağrılar için geçirilen kısıtlamaları çevirmek nasıl bilmez [kısıtlaması Çözücü](input-generation.md#constraint-solver). .NET kodu için bile, onu Instruments yalnızca kod çözümleyebilirsiniz. Intellitest belirli bölümlerini işaretleme olamaz **mscorlib**, yansıma kitaplığı dahil olmak üzere. **DynamicMethod** izlenmiş olamaz. 

Önerilen çözüm test modu tür yöntem dinamik derlemesindeki türler içinde bulunduğu olmalıdır. Ancak, bazı yöntemler uninstrumented olsa bile Intellitest Araçlı kod mümkün olduğunca çok kapak çalışacaktır.

<a name="platform"></a>
### <a name="platform"></a>Platform

Intellitest yalnızca X86 üzerinde 32-bit desteklenir. NETframework.

<a name="language"></a>
### <a name="language"></a>Dil

Temelde Intellitest herhangi bir .NET dilinde yazılmış rasgele .NET programları analiz edebilirsiniz. Ancak, Visual Studio'da, yalnızca C# destekler.

<a name="symbolic-reasoning"></a>
### <a name="symbolic-reasoning"></a>Simgesel mantığı

Intellitest kullanan otomatik [kısıtlaması Çözücü](input-generation.md#constraint-solver) hangi değerlerin test ve test altındaki program için uygun olduğunu belirlemek için. Ancak, kısıtlama Çözücü yeteneklerini olan, her zaman olacaktır, sınırlı.

<a name="incorrect-stack"></a>
### <a name="slightly-incorrect-stack-traces"></a>(Biraz) yanlış Yığın izlemeleri

Çünkü Intellitest yakalar ve "özel durumlar her Araçlı yönteminde bloğunu" Yığın izlemeleri satır numaralarını doğru olmaz. Bu bir tasarıma göre "yeniden oluşturma" yönerge kısıtlamasıdır.

<a name="further-reading"></a>
## <a name="further-reading"></a>Daha fazla bilgi

* [Giriş blog gönderisi](https://blogs.msdn.microsoft.com/visualstudioalm/2014/11/19/introducing-smart-unit-tests/) konusuna bakın.
* [Intellitest ile kodunuz için birim testleri oluşturma](https://docs.microsoft.com/en-gb/visualstudio/test/generate-unit-tests-for-your-code-with-intellitest)

## <a name="got-feedback"></a>Geri bildirim var mı?

Fikirlerinizi sonrası ve özellik istekleri  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
