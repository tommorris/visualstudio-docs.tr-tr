---
title: "Test oluşturma | Microsoft Intellitest Geliştirici Test aracı | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IntelliTest, Test generation
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 478dbdd71845d8bc0eb98250318b853ba4b8e5e6
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="test-generation"></a>Test oluşturma

Geleneksel birim testi bir test araya birkaç malzemeleri gerektirir:

```
[Test]
void MyTest() {
    // data
    ArrayList a = new ArrayList();

    // method sequence
    a.Add(5);

    // assertions
    Assert.IsTrue(a.Count==1);
    Assert.AreEqual(a[0], 5);
}
```

Testi farklı yönlerini oluşur:

* Bu düzeltmeler bir [yöntemi çağrısı sırası](test-generation.md#test-generators)
* İle yöntemleri çağırıldığı bağımsız değişkenleri giderir; bağımsız değişkenler [test girişleri](input-generation.md)
* Bir dizi belirterek test edilmiş uygulamanızı hedeflenen davranışını doğrular [onaylar](#assumptions-and-assertions)

Intellitest ilgili bağımsız değişken değerleri için daha fazla genel belirleyebilir genellikle otomatik olarak [parametreli birim testleri](#parameterized-unit-testing), yöntem çağrılarını ve onaylar dizisi sağlar.

<a name="test-generators"></a>
## <a name="test-generators"></a>Test oluşturucuları

Intellitest yürütmek için test altındaki uygulama yöntemlerinin bir dizi seçerek ve ardından türetilmiş verilerinde onaylar denetlenirken yöntemleri için girişleri oluşturmak test çalışmaları üretir.

A [parametreli birim testi](#parameterized-unit-testing) doğrudan bir dizi yöntem çağrıları kendi gövdesinde durumları.

Intellitest nesneleri oluşturmak gerektiğinde oluşturucular ve Fabrika yöntem çağrıları sırası gerektiğinde otomatik olarak eklenir.

<a name="parameterized-unit-testing"></a>
## <a name="parameterized-unit-testing"></a>Parametreli birim testleri

*Parametreli birim testleri* (Yerleştirmelerin) olan bir parametre testleri. Geleneksel birim testleri aksine yöntemleri genellikle olduğu kapalı, herhangi bir parametre kümesi Yerleştirmelerin alın. Bu basit mi? Evet - buradan Intellitest dener [girişleri (en az) kümesini oluşturmak](input-generation.md) , [tam olarak ele](input-generation.md#dynamic-code-coverage) kod testten erişilebilir.

Yerleştirmelerin kullanılarak tanımlanır [PexMethod](attribute-glossary.md#pexmethod) mstest'i (veya NUnit, xUnit) benzer bir şekilde özel öznitelik. Yerleştirmelerin yöntemlerdir ile etiketlenmiş sınıflardaki mantıksal olarak gruplandırılmış örneği [PexClass](attribute-glossary.md#pexclass). Aşağıdaki örnek, depolanan basit PUT gösterir **MyPexTest** sınıfı:

```
[PexMethod]
void ReplaceFirstChar(string target, char c) {

    string result = StringHelper.ReplaceFirstChar(target, c);

    Assert.AreEqual(result[0], c);
}
```

Burada **ReplaceFirstChar** ilk karakteri bir dize olarak değiştiren bir yöntemdir:

```
class StringHelper {
    static string ReplaceFirstChar(string target, char c) {
        if (target == null) throw new ArgumentNullException();
        if (target.Length == 0) throw new ArgumentOutOfRangeException();
        return c + target.Substring(1);
    }
}
```

Bu sınamadan Intellitest otomatik olarak yapabilirsiniz [girişleri oluşturmak](input-generation.md) test edilen kodu birçok yürütme yollarını kapsayan PUT için. Her, bir farklı yürütmesi yolu alır "seri" birim testi kapsayan giriş:

```
[TestMethod, ExpectedException(typeof(ArgumentNullException))]
void ReplaceFirstChar0() {
    this.ReplaceFirstChar(null, 0);
}
...
[TestMethod]
void ReplaceFirstChar10() {
    this.ReplaceFirstChar("a", 'c');
}
```

<a name="generic-parameterized"></a>
## <a name="generic-parameterized-unit-testing"></a>Genel parametreli birim testleri

Parametreli birim testleri genel yöntemler olabilir. Bu durumda, kullanıcı yöntemi kullanarak örneği oluşturmak için kullanılan türleri belirtmelidir [PexGenericArguments](attribute-glossary.md#pexgenericarguments).

```
[PexClass]
public partial class ListTest {
    [PexMethod]
    [PexGenericArguments(typeof(int))]
    [PexGenericArguments(typeof(object))]
    public void AddItem<T>(List<T> list, T value)
    { ... }
}
```

<a name="allowing-exceptions"></a>
## <a name="allowing-exceptions"></a>Özel durumlara izin verme

Intellitest beklenen özel durumlar olarak değerlendirme özel durumlar ve beklenmeyen özel durum yardımcı olmak üzere çok sayıda doğrulama öznitelikleri sağlar.

Özel durumlar oluşturma ile ilgili ek açıklama negatif test çalışmaları gibi beklenen  **ExpectedException (typeof (*xxx*)) **, başarısız olan test çalışmalarını beklenmeyen özel durum oluşturur.

```
[PexMethod, PexAllowedException(typeof(ArgumentNullException))]
void SomeTest() {...}
```

Doğrulayıcıları şunlardır:

* [PexAllowedException](attribute-glossary.md#pexallowedexception): belirli özel durum türü yerden sağlar
* [PexAllowedExceptionFromAssembly](attribute-glossary.md#pexallowedexceptionfromassembly): belirli özel durum türü belirtilen derlemesinden sağlar
* [PexAllowedExceptionFromType](attribute-glossary.md#pexallowedexceptionfromtype): belirli özel durum türü belirtilen türden sağlar
* [PexAllowedExceptionFromTypeUnderTest](attribute-glossary.md#pexallowedexceptionfromtypeundertest): test altındaki türünden belirli özel durum türü sağlar

<a name="internal-types"></a>
## <a name="testing-internal-types"></a>İç türleri test etme

"Bu görebileceği sürece Intellitest iç türleri sınayabilirsiniz". Türlerini görmek Intellitest için aşağıdaki öznitelik ürün veya test projeniz için Visual Studio Intellitest sihirbazları tarafından eklenir:

```
[assembly: InternalsVisibleTo("Microsoft.Pex, PublicKey=002400000480000094000000060200000024000052534131000400000100010007d1fa57c4aed9f0a32e84aa0faefd0de9e8fd6aec8f87fb03766c834c99921eb23be79ad9d5dcc1dd9ad236132102900b723cf980957fc4e177108fc607774f29e8320e92ea05ece4e821c0a5efe8f1645c4c0c93c1ab99285d622caa652c1dfad63d745d6f2de5f17e5eaf0fc4963d261c8a12436518206dc093344d5ad293
```

<a name="assumptions-and-assertions"></a>
## <a name="assumptions-and-assertions"></a>Varsayımlar ve onaylar

Kullanıcıların varsayımlar ve onaylar express için kullanabileceğiniz [önkoşulları](#precondition) (varsayımlar) ve [Sonkoşullar](#postcondition) (onaylar) testlerini hakkında. Intellitest parametre değerleri kümesi oluşturur ve "kodunu inceler", test varsayılır ihlal ediyor. Bu durum oluştuğunda, bu yol için bir sınama oluşturmaz ancak sessizce yoksayar.

Onaylamalardır iyi bilinen bir kavram normal birim test çerçevelerini olarak Intellitest zaten "yerleşik anlar şekilde" **Assert** her desteklenen test çerçevesi tarafından sağlanan sınıfları. Bununla birlikte, çoğu çerçeveleri sağlıyor mu bir **varsay** sınıfı. Bu durumda, Intellitest sağlar [PexAssume](static-helper-classes.md#pexassume) sınıfı. Varolan bir test çerçevesi kullanmak istemiyorsanız, Intellitest de sahip [PexAssert](static-helper-classes.md#pexassert) sınıfı.

```
[PexMethod]
public void Test1(object o) {
    // precondition: o should not be null
    PexAssume.IsNotNull(o);

    ...
}
```

Özellikle, nullness olmayan varsayımına özel öznitelik olarak kodlanmış olmalıdır:

```
[PexMethod]
public void Test2([PexAssumeNotNull] object o)
// precondition: o should not be null
{
   ...
}
```

<a name="precondition"></a>
## <a name="precondition"></a>Önkoşulu

Bir yöntem önkoşulu yöntemi başarılı koşullar ifade eder.

Önkoşul parametreleri ve nesne durumu denetleme ve atma genellikle, zorunlu bir **ArgumentException** veya **InvalidOperationException** , ihlal edilirse.

Intellitest, önkoşulu olarak bir [parametreli birim testi](#parameterized-unit-testing) ile ifade [PexAssume](static-helper-classes.md#pexassume).

<a name="postcondition"></a>
## <a name="postcondition"></a>Sonkoşul

Bir yöntemin Sonkoşul kendi önkoşulları başlangıçta geçerli olduğunu varsayarsak yöntem yürütme sırasında ve sonrasında tutan koşulları ifade eder.

Genellikle, çağrıları tarafından Sonkoşul uygulanan **Assert** yöntemleri.

Intellitest, Sonkoşul biri ile bir [parametreli birim testi](#parameterized-unit-testing) ile ifade [PexAssert](static-helper-classes.md#pexassert).

<a name="test-failures"></a>
## <a name="test-failures"></a>Test başarısızlıklarının
Oluşturulan bir test çalışması başarısız olduğunda?

1. İçinde sona varsa [yol sınırları yapılandırılmış](exploration-bounds.md), sürece hata olarak kabul [TestExcludePathBoundsExceeded](exploration-bounds.md#testexcludepathboundsexceeded) seçeneği

1. Test görüntülerse bir **PexAssumeFailedException**, başarılı. Ancak, bu genellikle sürece filtre [TestEmissionFilter](exploration-bounds.md#testemissionfilter) ayarlanır **tüm**

1. Test bozup bir [onaylama](#assumptions-and-assertions); Örneğin, bir birim testi çerçevesi bir onaylama ihlali özel durum atma tarafından başarısız

Yukarıdakilerin hiçbiri kararı oluşturmak, bir özel durum değil ve yalnızca, bir test başarılı olur. Onaylama işlemi ihlalleri aynı şekilde özel durumlar olarak kabul edilir.

<a name="setup-teardown"></a>
## <a name="setup-and-tear-down"></a>Kurulum ve kesmeden

Parçası olarak test çerçeveleri ile tümleştirme, algılama ve çalışan Intellitest destekler Kurulum ve aşağı kesmeden.

**Örnek**

```
using Microsoft.Pex.Framework;
using NUnit.Framework;

namespace MyTests
{
    [PexClass]
    [TestFixture]
    public partial class MyTestClass
    {
        [SetUp]
        public void Init()
        {
            // monitored
        }

        [PexMethod]
        public void MyTest(int i)
        {
        }

        [TearDown]
        public void Dispose()
        {
            // monitored
        }
    }
}

```

<a name="further-reading"></a>
## <a name="further-reading"></a>Daha fazla bilgi

* [Kod bağlamanın test](https://blogs.msdn.microsoft.com/visualstudioalm/2015/04/18/smart-unit-tests-test-to-code-binding-test-case-management/)
* [Tümünü kural için bir sınama](https://blogs.msdn.microsoft.com/visualstudioalm/2015/07/05/intellitest-one-test-to-rule-them-all/)

## <a name="got-feedback"></a>Geri bildirim var mı?

Fikirlerinizi sonrası ve özellik istekleri  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
