---
title: Visual Studio'da Test birim için uygulamanızın parçalarını yalıtmak üzere saplamalar kullanma
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
dev_langs:
- CSharp
- VB
ms.openlocfilehash: 68ee12b330d6b82307de7d590c09259a559716b7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31978368"
---
# <a name="use-stubs-to-isolate-parts-of-your-application-from-each-other-for-unit-testing"></a>Birim testi için birbirinden uygulamanızın parçalarını yalıtmak üzere saplamalar kullanma

*Saplama türlerini* Microsoft Fakes framework kolayca çağırır başka bir bileşenden test ettiğiniz bir bileşen ayırmanıza olanak sağlayan iki teknolojiyi biridir. Bir saplama test sırasında başka bir bileşenin yer aldığı kodun küçük bir parçasıdır. Bir saplama kullanmanın faydası testi yazmanızı kolaylaştırması, tutarlı sonuçlar döndürmesidir. Ve diğer bileşenleri henüz çalışmıyor olsa bile, testleri çalıştırabilirsiniz.

Genel bir bakış ve Hızlı Başlangıç Kılavuzu Fakes için için bkz: [yalıtma kodu altında Microsoft Fakes ile Test](../test/isolating-code-under-test-with-microsoft-fakes.md).

Saptamalar kullanmak için bileşen yazmalısınız böylece sınıfları değil uygulamanın başka bölümüne başvuran yalnızca arabirimleri kullanır. Diğer bölüme nazaran daha az değişiklik gerektiren bir bölümde değişiklik yaptığından bu iyi bir tasarım uygulamasıdır. Test etmek için gerçek bir bileşen yerine saplama kullanmanıza olanak tanır.

Diyagramda, StockAnalyzer bileşeni test etmek istediğimiz bir bileşendir. Normal olarak, başka bir bileşen, RealStockFeed kullanır. Ancak RealStockFeed her defasında StockAnalyzer test etmeyi zorlaştıran yöntemlerinin çağırdığı farklı sonuçlar döndürür.  Sınama sırasında StubStockFeed gibi farklı bir sınıf ile değiştiririz.

![Gerçek ve saplama sınıfları bir arabirim için uygun.](../test/media/fakesinterfaces.png)

Saplamalar bu yolla kodunuzun yapısına güveneceğinden genellikle saplamaları başka bir uygulamanın bir bölümünü ayırmak için kullanırsınız. System.dll gibi denetiminiz altında olan diğer derlemelerden ayırmak için normal olarak dolgu verileri kullanabilirsiniz. Bkz: [uygulamanızı birim testi için diğer derlemelerden yalıtmak üzere dolgular kullanma](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md).

## <a name="how-to-use-stubs"></a>Saptamalar nasıl kullanılır?

### <a name="design-for-dependency-injection"></a>Tasarım için bağımlılık ekleme

Saptamaları kullanmak için uygulamanızın farklı bileşenlerini değil birbirlerine bağımlı ancak arabirim tanımlarının yalnızca bağımlı olmasını sağlamak için tasarlanır. Derleme zamanında bağlanmak yerine, bileşenler çalışma zamanında bağlıdır. Bu model yazılımın güncellemesinin güçlü ve kolay yapılmasına yardımcı olur çünkü değişiklikler bileşen sınırları boyunca yayılmaz. Saplamalar kullanmasanız bile kullanmanızı öneririz. Yeni kod yazıyorsanız izleyin daha kolaydır [bağımlılık ekleme](http://en.wikipedia.org/wiki/Dependency_injection) düzeni. Varolan yazılım için testler yazıyorsanız, yeniden düzenlemeniz gerekebilir. Pratik olursa, yerine dolgu verileri kullanmayı düşünebilirsiniz.

Bu tartışma diyagramdaki bir seçimini artıran bir örnekle başlayalım. Sınıf StockAnalyzer fiyatları paylaşmayı okur ve bazı ilginç sonuçlar üretir. Test etmek istediğimiz bazı ortak yöntemler vardır. Örneği basit tutmak için yalnızca, belirli bir paylaşımın geçerli fiyat raporları çok basit bir tane olmak üzere bu yöntemlerden birini bakalım. Bu yöntemin bir birim testini yazmak istiyoruz. Bir test ilk taslağını şöyledir:

```csharp
[TestMethod]
public void TestMethod1()
{
    // Arrange:
    var analyzer = new StockAnalyzer();
    // Act:
    var result = analyzer.GetContosoPrice();
    // Assert:
    Assert.AreEqual(123, result); // Why 123?
}
```

```vb
<TestMethod()> Public Sub TestMethod1()
    ' Arrange:
    Dim analyzer = New StockAnalyzer()
    ' Act:
    Dim result = analyzer.GetContosoPrice()
    ' Assert:
    Assert.AreEqual(123, result) ' Why 123?
End Sub
```

Bu test ile ilgili hemen açık bir sorun: paylaşım fiyatları farklılık gösterir ve bu nedenle onaylama işlemi genellikle başarısız olur.

StockAnalyzer tarafından kullanılan hala geliştirilmekte olan StockFeed bileşeninde başka bir sorun olabilir. Kodun test altındaki yönteminin ilk taslak şöyledir:

```csharp
public int GetContosoPrice()
{
    var stockFeed = new StockFeed(); // NOT RECOMMENDED
    return stockFeed.GetSharePrice("COOO");
}
```

```vb
Public Function GetContosoPrice()
    Dim stockFeed = New StockFeed() ' NOT RECOMMENDED
    Return stockFeed.GetSharePrice("COOO")
End Function
```

Anlaşıldığı gibi bu yöntem, derleme veya StockFeed sınıf çalışmaları henüz tam olmadığı için özel bir durum fırlatabilir. Arabirim ekleme her iki sorunu giderir. Arabirim eklemeye aşağıdaki kural uygulanır:

Bir sınıfta bir bildirimi veya başka bir bileşen için uygulamanızın herhangi bir bileşenin kod asla açıkça başvurmalıdır bir `new` deyimi. Bunun yerine, değişkenler ve parametreler arabirimleriyle bildirilmesi gerekir. Bileşen örnekleri yalnızca bileşenin kapsayıcı tarafından oluşturulması gerekir.

- "Bileşeni tarafından", bir sınıf veya grup geliştirip birlikte güncelleştirme sınıfların anlama. Genellikle, bir bileşen Visual Studio projesindeki koddur. Aynı anda güncelleştirilmediğinden bir bileşen sınıfları ayırırsınız daha az önemlidir.

- Ayrıca bileşenlerinizi göreceli olarak tutarlı bir platformu sınıflardan gibi aynı şekilde çok önemli değil *System.dll*. Bu sınıfların arabirimlerini yazmak kodunuzu dağıtabilir.

Böyle bir arabirim kullanılarak StockFeed StockAnalyzer koddan ayırırsınız:

```csharp
public interface IStockFeed
{
    int GetSharePrice(string company);
}

public class StockAnalyzer
{
    private IStockFeed stockFeed;
    public StockAnalyzer(IStockFeed feed)
    {
        stockFeed = feed;
    }
    public int GetContosoPrice()
    {
        return stockFeed.GetSharePrice("COOO");
    }
}
```

```vb
Public Interface IStockFeed
    Function GetSharePrice(company As String) As Integer
End Interface

Public Class StockAnalyzer
    ' StockAnalyzer can be connected to any IStockFeed:
    Private stockFeed As IStockFeed
    Public Sub New(feed As IStockFeed)
        stockFeed = feed
    End Sub
    Public Function GetContosoPrice()
        Return stockFeed.GetSharePrice("COOO")
    End Function
End Class
```

Bu örnekte, yeniden oluşturulduğunda StockAnalyzer bir IStockFeed uygulamasına geçirilir. Tamamlanan uygulamada, başlatma kodu bağlantı yerine getirilir:

```csharp
analyzer = new StockAnalyzer(new StockFeed());
```

Bu bağlantıyı gerçekleştirmede daha esnek bir yol vardır. Örneğin, StockAnalyzer, IStockFeed, farklı koşullarda farklı uygulamaları oluşturabileceğiniz factory nesnesi kabul edemedi.

### <a name="generate-stubs"></a>Saptamalar oluştur

Bunu kullanan başka bir bileşenden test etmek istediğiniz sınıfı ayrılmış. Uygulama yapmanın yanı sıra güçlü ve esnek, bağlantıyı kesmenize izin veren bileşen arayüzlerinin test amaçlı uygulamalarını saptama testteki bağlanmanıza olanak sağlar.

Her zamanki şekilde sınıflar gibi saptamaları basitçe yazabilirsiniz. Ancak Microsoft Fakes her test için en uygun saptama oluşturmak için daha dinamik bir yol sağlar.

Saptamalar kullanmak için saptama türleri arabirimi tanımlarından oluşturmanız gerekir.

#### <a name="add-a-fakes-assembly"></a>Fakes derleme ekleyin

1. Çözüm Gezgini'nde, birim testi projenizin genişletin **başvurular**.

   Visual Basic'te çalışıyorsanız, seçmelisiniz **tüm dosyaları göster** başvuruları listesini görmek için Çözüm Gezgini araç çubuğunda.

2. Saptamaları oluşturmak istediğiniz arabirim tanımlarını içeren derlemeyi seçin.

3. Kısayol menüsünden seçin **Fakes derleme Ekle**.

### <a name="write-your-test-with-stubs"></a>Saptamalarla test yazma

```csharp
[TestClass]
class TestStockAnalyzer
{
    [TestMethod]
    public void TestContosoStockPrice()
    {
      // Arrange:

        // Create the fake stockFeed:
        IStockFeed stockFeed =
             new StockAnalysis.Fakes.StubIStockFeed() // Generated by Fakes.
                 {
                     // Define each method:
                     // Name is original name + parameter types:
                     GetSharePriceString = (company) => { return 1234; }
                 };

        // In the completed application, stockFeed would be a real one:
        var componentUnderTest = new StockAnalyzer(stockFeed);

        // Act:
        int actualValue = componentUnderTest.GetContosoPrice();

        // Assert:
        Assert.AreEqual(1234, actualValue);
    }
    ...
}
```

```vb
<TestClass()> _
Class TestStockAnalyzer

    <TestMethod()> _
    Public Sub TestContosoStockPrice()
        ' Arrange:
        ' Create the fake stockFeed:
        Dim stockFeed As New StockAnalysis.Fakes.StubIStockFeed
        With stockFeed
            .GetSharePriceString = Function(company)
                                       Return 1234
                                   End Function
        End With
        ' In the completed application, stockFeed would be a real one:
        Dim componentUnderTest As New StockAnalyzer(stockFeed)
        ' Act:
        Dim actualValue As Integer = componentUnderTest.GetContosoPrice
        ' Assert:
        Assert.AreEqual(1234, actualValue)
    End Sub
End Class
```

Özel burada Sihirli sınıfı parçasıdır `StubIStockFeed`. Başvurulan derlemedeki her genel tür için Microsoft Fakes mekanizması saptama sınıfı oluşturur. Saplama sınıfın adını türetilmiş arabirimi adı olan "`Fakes.Stub`" öneki ve eklenmiş parametre türü adları olarak.

Saptamalar ayrıca olaylar ve genel yöntemlerle ilgili olarak özellik okuyucu ve ayarlayıcılar için oluşturulur.

### <a name="verify-parameter-values"></a>Parametre değerleri doğrulayın

Bileşeniniz başka bir bileşen için çağrı yaptığında, doğrulayabilirsiniz, doğru değerleri geçirir. Bir onaylama işlemini saptamaya yerleştirebilirsiniz veya değer depolayabilir ve testin ana gövdesini de doğrulayabilirsiniz. Örneğin:

```csharp
[TestClass]
class TestMyComponent
{
    [TestMethod]
    public void TestVariableContosoPrice()
    {
        // Arrange:
        int priceToReturn;
        string companyCodeUsed;
        var componentUnderTest = new StockAnalyzer(new StubIStockFeed()
            {
               GetSharePriceString = (company) =>
                  {
                     // Store the parameter value:
                     companyCodeUsed = company;
                     // Return the value prescribed by this test:
                     return priceToReturn;
                  };
            };
        // Set the value that will be returned by the stub:
        priceToReturn = 345;

        // Act:
        int actualResult = componentUnderTest.GetContosoPrice();

        // Assert:
        // Verify the correct result in the usual way:
        Assert.AreEqual(priceToReturn, actualResult);

        // Verify that the component made the correct call:
        Assert.AreEqual("COOO", companyCodeUsed);
    }
...
}
```

```vb
<TestClass()> _
Class TestMyComponent
    <TestMethod()> _
    Public Sub TestVariableContosoPrice()
        ' Arrange:
        Dim priceToReturn As Integer
        Dim companyCodeUsed As String = ""
        Dim stockFeed As New StockAnalysis.Fakes.StubIStockFeed()
        With stockFeed
            ' Implement the interface's method:
            .GetSharePriceString = _
                Function(company)
                    ' Store the parameter value:
                    companyCodeUsed = company
                    ' Return a fixed result:
                    Return priceToReturn
                End Function
        End With
        ' Create an object to test:
        Dim componentUnderTest As New StockAnalyzer(stockFeed)
        ' Set the value that will be returned by the stub:
        priceToReturn = 345

        ' Act:
        Dim actualResult As Integer = componentUnderTest.GetContosoPrice()

        ' Assert:
        ' Verify the correct result in the usual way:
        Assert.AreEqual(priceToReturn, actualResult)
        ' Verify that the component made the correct call:
        Assert.AreEqual("COOO", companyCodeUsed)
    End Sub
...
End Class
```

## <a name="stubs-for-different-kinds-of-type-members"></a>Tür üyelerinin farklı türleri için saptamalar

### <a name="methods"></a>Yöntemler

Örnekte açıklandığı gibi yöntemler saptama sınıfının bir örneği için temsilci ekleyerek tamamlanmamış. Saptama türünün adı yöntemi ve parametreleri adlarından türetilir. Örneğin, aşağıdaki verilen `IMyInterface` arabirim ve yöntem `MyMethod`:

```csharp
// application under test
interface IMyInterface
{
    int MyMethod(string value);
}
```

Biz bir saplama ekleme `MyMethod` , her zaman 1 döndürür:

```csharp
// unit test code
var stub = new StubIMyInterface ();
stub.MyMethodString = (value) => 1;
```

Bir işlev için saptama belirtmezseniz, Fakes dönüş türünün varsayılan değerini döndüren bir işlev oluşturur. Numaraları için varsayılan değer 0'dır ve sınıf türleri için bu `null` (C#) veya `Nothing` (Visual Basic).

### <a name="properties"></a>Özellikler

Özellik alıcılar ve ayarlayıcılar, ayrı temsilciler olarak sunulur ve ayrı ayrı saptanmış olabilirler. Örneğin, göz önünde bulundurun `Value` özelliği `IMyInterface`:

```csharp
// code under test
interface IMyInterface
{
    int Value { get; set; }
}
```

Set'yordamı, temsilcileri ekleme `Value` otomatik özelliği benzetimini yapmak için:

```csharp
// unit test code
int i = 5;
var stub = new StubIMyInterface();
stub.ValueGet = () => i;
stub.ValueSet = (value) => i = value;
```

Ayarlayıcı veya özellik alıcısı için saptama yöntemleri belirtmezseniz, saptama özelliği gibi basit bir değişken çalışmasını Fakes değerleri saklayan bir saptama oluşturacaktır.

### <a name="events"></a>Olaylar

Olaylar, temsilci alanları olarak sunulur. Sonuç olarak herhangi bir saptama olayı, olay yedekleme alanını çağırarak basitçe yükseltilebilir. Şimdi saplama için aşağıdaki arabirimi göz önünde bulundurun:

```csharp
// code under test
interface IWithEvents
{
    event EventHandler Changed;
}
```

Yükseltmek için `Changed` olay, biz yalnızca yedekleme temsilci Çağır:

```csharp
// unit test code
  var withEvents = new StubIWithEvents();
  // raising Changed
  withEvents.ChangedEvent(withEvents, EventArgs.Empty);
```

### <a name="generic-methods"></a>Genel yöntemler

Genel yöntemler her istenen yöntemi örnek oluşturma için temsilci sağlayarak saplama mümkündür. Örneğin, aşağıda verilen arayüz genel yöntem içerir:

```csharp
// code under test
interface IGenericMethod
{
    T GetValue<T>();
}
```

yerleştirir bir test yazabilirsiniz `GetValue<int>` örnek oluşturma:

```csharp
// unit test code
[TestMethod]
public void TestGetValue()
{
    var stub = new StubIGenericMethod();
    stub.GetValueOf1<int>(() => 5);

    IGenericMethod target = stub;
    Assert.AreEqual(5, target.GetValue<int>());
}
```

Kod çağırmak için olsaydı `GetValue<T>` diğer örneklemesi ile saplama yalnızca davranışı çağırırdı.

### <a name="stubs-of-virtual-classes"></a>Sanal sınıf saptamaları

Önceki örneklerde saptamalar arabirimlerden üretilmedi. Sanal veya özet üyeler bir sınıftan saptamalar da oluşturabilir. Örneğin:

```csharp
// Base class in application under test
    public abstract class MyClass
    {
        public abstract void DoAbstract(string x);
        public virtual int DoVirtual(int n)
        { return n + 42; }
        public int DoConcrete()
        { return 1; }
    }
```

Bu sınıftan üretilen yer DoAbstract() ve DoVirtual(), ancak değil DoConcrete() temsilci yöntemleri ayarlayabilirsiniz.

```csharp
// unit test
  var stub = new Fakes.MyClass();
  stub.DoAbstractString = (x) => { Assert.IsTrue(x>0); };
  stub.DoVirtualInt32 = (n) => 10 ;
```

Sanal bir yöntem için temsilci belirtmezseniz, Fakes ya da varsayılan davranışı sağlayabilir veya temel sınıf yöntemi çağırabilirsiniz. Adlı temel yöntem olacak şekilde ayarlanmış `CallBase` özelliği:

```csharp
// unit test code
var stub = new Fakes.MyClass();
stub.CallBase = false;
// No delegate set - default delegate:
Assert.AreEqual(0, stub.DoVirtual(1));

stub.CallBase = true;
// No delegate set - calls the base:
Assert.AreEqual(43,stub.DoVirtual(1));
```

## <a name="debug-stubs"></a>Saplamalar hata ayıklama

Saptama türleri, yumuşak bir hata ayıklama deneyimini sağlamak üzere tasarlanmıştır. Varsayılan olarak, hata ayıklayıcı herhangi oluşturulan bir kod üzerinde adım adım ilerler, bu nedenle saptamaya eklenmiş olan özel üye uygulamalarının içine doğrudan atlar.

## <a name="stub-limitations"></a>Saptama sınırlamaları

1. Yöntem imzaları işaretçilerle desteklenmez.

2. Saplama türlerini üzerinde sanal yöntemi gönderme dayandığından sealed sınıfları veya statik yöntemler tamamlanmamış olamaz. Böyle durumlarda, açıklandığı gibi dolgusu türlerini kullanan [uygulamanızı birim testi için diğer derlemelerden yalıtmak üzere dolgular kullanma](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md)

## <a name="change-the-default-behavior-of-stubs"></a>Saplamalar varsayılan davranışını değiştirme

Her oluşturulan saplama türünün bir örneğini tutan `IStubBehavior` arabirimi (aracılığıyla `IStub.InstanceBehavior` özelliği). Hiç eklenmemiş özel temsilci ile üye istemci çağrıları olarak adlandırılır. Davranış ayarlı değil, tarafından döndürülen örnek kullanacak `StubsBehaviors.Current` özelliği. Varsayılan olarak, bu özellik oluşturur bir davranış döndürür bir `NotImplementedException` özel durum.

Davranışı ayarlayarak herhangi bir zamanda değiştirilebilir `InstanceBehavior` herhangi bir saplama örneği özelliği. Örneğin, aşağıdaki kod parçacığında, hiçbir şey yapmaz veya dönüş türü varsayılan değerini döndürür bir davranışını değiştiren: `default(T)`:

```csharp
// unit test code
var stub = new StubIFileSystem();
// return default(T) or do nothing
stub.InstanceBehavior = StubsBehaviors.DefaultValue;
```

Tüm nesneler için davranış ayarlanmamış ayarlayarak saplama davranış da genel değiştirilebilir `StubsBehaviors.Current` özelliği:

```csharp
// Change default behavior for all stub instances
// where the behavior has not been set.
StubBehaviors.Current = BehavedBehaviors.DefaultValue;
```

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft Fakes ile Test Edilen Kodu Yalıtma](../test/isolating-code-under-test-with-microsoft-fakes.md)