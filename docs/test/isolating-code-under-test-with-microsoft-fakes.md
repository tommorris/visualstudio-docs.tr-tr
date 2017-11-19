---
title: "Microsoft Fakes ile Test edilen kodu yalıtma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a03c2e83-a41f-4854-bcf2-fcaa277a819d
caps.latest.revision: "16"
ms.author: douge
manager: douge
ms.openlocfilehash: 1802f211002585a2f23e82b8e0b097c118bd1ff5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="isolating-code-under-test-with-microsoft-fakes"></a>Microsoft Fakes ile Test Edilen Kodu Yalıtma
Microsoft Fakes Yardım diğer bölümleri uygulama ile değiştirerek test kodu yalıtmak *saplamalar* veya *dolgular*. Bunlar, testlerinizin denetimi altında olan küçük kod parçalarıdır. Kodunuzu sınama için yalıttığınız zaman, sınama başarısız olduğunda nedeninin başka bir yerde değil, tam da orada olduğunu bileceksiniz. Uygulamanın diğer parçaları çalışmıyor olsa bile, saptamalar ve dolgular kodunuzu test etmenize olanak sağlar.  
  
 Fakes iki türde olabilir:  
  
-   A [saplama](#stubs) bir sınıf aynı arabirimini uygulayan küçük bir yedek ile değiştirir.  Saptamalar kullanmak için uygulamanızı her bir bileşenin diğer bileşenlere değil yalnızca arabirimlere bağlı olacak şekilde tasarlamanız gerekir. ("Bileşen" ifadesiyle, birlikte tasarlanan ve güncelleştirilen ve tipik olarak bir derlemede yer alan sınıf veya sınıflardan oluşan grup kastedilmektedir.)  
  
-   A [dolgusu](#shims) uygulamanızın çalışma zamanında derlenen kodunu belirtilen yöntem çağrısı yapmak yerine testinizi sağlar dolgusu kodu çalıştırır şekilde değiştirir. Dolgular gibi .NET derlemelerini değiştirilemiyor derlemeleri çağrıları değiştirmek için kullanılabilir.  
  
 ![Fakes diğer bileşenleri yerine](../test/media/fakes-2.png "Fakes 2")  
  
 **Gereksinimler**  
  
-   Visual Studio Enterprise  
  
## <a name="choosing-between-stub-and-shim-types"></a>Saptama ve dolgu türü arasında seçim yapma  
 Genelde bu sınıfları aynı anda geliştirip güncelleştirdiğinizden bir Visual Studio projesini bileşen olarak kabul edebilirsiniz. Projenin çözümünüzdeki diğer projelere veya diğer derlemelere yaptığı çağrılar için saptama ve dolgu kullanmayı deneyebilirsiniz.  
  
 Genel bir kılavuzluk sağlaması için, Visual Studio çözümünüzdeki çağrılar için saptamaları ve diğer başvurulan derlemelerde çağrılar için dolgu verilerini kullanın. Bunun nedeni kendi çözümünüzde bileşenleri, saptamaların gerektirdiği şekilde arabirimleri tanımlayarak ayırmanızın iyi bir uygulama olmasıdır. Ancak System.dll gibi dış derlemeler genellikle ayrı arabirim tanımlarıyla sağlanmaz, dolayısıyla onun yerine dolguları kullanmalısınız.  
  
 Diğer değerlendirmeler şunlardır:  
  
 **Performans.** Çalışma zamanında kodunuzu yeniden yazdıkları için dolgular daha yavaş çalışır. Saptamalarda bu performans düşüklüğü yoktur ve sanal yöntemler kadar hızlı ilerleyebilirler.  
  
 **Türleri korumalı statik yöntemler.** Arayüzleri uygulamak için yalnızca saptamalar kullanabilirsiniz. Bu nedenle saptama türleri statik yöntemler, sanal olmayan yöntemler, korumalı sanal yöntemler, korumalı türlerdeki yöntemler gibi yöntemlerle kullanılamaz.  
  
 **İç türleri.** Derleme özniteliği kullanılarak erişilebilir yapılan iç türleriyle saplamalar ve dolgular kullanılabilir <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.  
  
 **Özel yöntemler.** Dolgular, bir yöntem imzasındaki tüm türler görünür durumdaysa çağrıları özel yöntemlerle değiştirebilir. Saptamalar yalnızca görünür yöntemlerle değiştirilebilir.  
  
 **Arabirimleri ve soyut yöntemler.** Saptamalar, test sırasında kullanılabilecek arayüzlerin ve özet yöntemlerin uygulanmalarını sağlar. Yöntem gövdeleri olmadığından dolgular arabirimleri ve soyut yöntemler izleme olamaz.  
  
 Genel olarak saptama türlerini kod temelindeki bağımlılıkları ayırmak için kullanmanızı öneririz. Bunu bileşenleri arayüzlerin arkasına gizleyerek yapabilirsiniz. Dolgu türleri, test edilebilir API sağlamayan üçüncü taraf bileşenlerden ayırmak için kullanılabilir.  
  
##  <a name="stubs"></a>Saplamalar ile çalışmaya başlama  
 Daha ayrıntılı bir açıklaması için bkz: [birim testi için birbirinden uygulamanızın parçalarını yalıtmak üzere saplamalar kullanma](../test/using-stubs-to-isolate-parts-of-your-application-from-each-other-for-unit-testing.md).  
  
1.  **Arabirimleri Ekle**  
  
     Saptamalar kullanmak için test etmek istediğiniz kodu, uygulamanızın içindeki diğer bileşende yer alan sınıflara açıkça başvurmayacak şekilde yazmanız gerekir. "Bileşen" ifadesiyle, birlikte geliştirilen ve güncellenen ve tipik olarak tek Visual Studio projesinde yer alan sınıf veya sınıflar kastedilmektedir. Değişkenler ve parametreler, arabirimler kullanılarak bildirilmelidir ve diğer bileşenlerin örnekleri iletilmeli veya fabrika kullanılarak oluşturulmalıdır. Örneğin, StockFeed uygulamadaki farklı bir bileşende bulunan bir sınıfsa bu hatalı olarak değerlendirilir:  
  
     `return (new StockFeed()).GetSharePrice("COOO"); // Bad`  
  
     Bunun yerine, başka bir bileşen tarafından uygulanabilecek ve bir saptama tarafından test amaçlarıyla uygulanabilecek bir arabirim tanımlayın:  
  
    ```csharp  
    public int GetContosoPrice(IStockFeed feed)  
    { return feed.GetSharePrice("COOO"); }  
  
    ```  
  
    ```vb  
    Public Function GetContosoPrice(feed As IStockFeed) As Integer  
     Return feed.GetSharePrice("COOO")  
    End Function  
  
    ```  
  
2.  **Fakes derleme ekleyin**  
  
    1.  Çözüm Gezgini'nde, test projesinin başvuru listeyi genişletin. Visual Basic'te çalışıyorsanız, seçmelisiniz **tüm dosyaları göster** başvuru listesini görmek için.  
  
    2.  Arabirimin (örneğin IStockFeed) tanımlandığı derleme başvurusunu seçin. Bu başvuru kısayol menüsünden seçin **Fakes derleme Ekle**.  
  
    3.  Çözümü yeniden derleyin.  
  
3.  Testlerinizde saptama örnekleri oluşturun ve yöntemleri için kod sağlayın:  
  
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
  
     Özel burada Sihirli sınıfı parçasıdır `StubIStockFeed`. Başvurulan derlemedeki her arabirim için saptama sınıfı Microsoft Fakes mekanizması oluşturur. Saplama sınıfın adını türetilmiş arabirimi adı olan "`Fakes.Stub`" öneki ve eklenmiş parametre türü adları olarak.  
  
     Saptamalar ayrıca olaylar ve genel yöntemlerle ilgili olarak özellik okuyucu ve ayarlayıcılar için oluşturulur. Daha fazla bilgi için bkz: [birim testi için birbirinden uygulamanızın parçalarını yalıtmak üzere saplamalar kullanma](../test/using-stubs-to-isolate-parts-of-your-application-from-each-other-for-unit-testing.md).  
  
##  <a name="shims"></a>Dolgular ile çalışmaya başlama  
 (Daha ayrıntılı bir açıklaması için bkz: [uygulamanızı birim testi için diğer derlemelerden yalıtmak üzere dolgular kullanma](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md).)  
  
 Bileşeniniz çağrıları içeren varsayalım `DateTime.Now`:  
  
```csharp  
// Code under test:  
    public int GetTheCurrentYear()  
    {  
       return DateTime.Now.Year;  
    }  
  
```  
  
 Test sırasında dolguya istediğiniz `Now` özelliği, çünkü gerçek sürüm inconveniently yapılan her çağrı sırasında farklı bir değer döndürür.  
  
 Dolgular kullanmak için uygulama kodu değiştirin veya belirli bir şekilde yazma gerekmez.  
  
1.  **Fakes derleme ekleyin**  
  
     Çözüm Gezgini'nde, birim testi projenin başvurular açın ve taklit etmek istediğiniz yöntemini içeren derlemenin referansı seçin. Bu örnekte, `DateTime` sınıfı olan **System.dll**.  Visual Basic projesinde başvuruları görmek için seçin **tüm dosyaları göster**.  
  
     Seçin **Fakes derleme ekleyin**.  
  
2.  **Bir ShimsContext bir dolgu Ekle**  
  
    ```csharp  
    [TestClass]  
    public class TestClass1  
    {   
            [TestMethod]  
            public void TestCurrentYear()  
            {  
                int fixedYear = 2000;  
  
                // Shims can be used only in a ShimsContext:  
                using (ShimsContext.Create())  
                {  
                  // Arrange:  
                    // Shim DateTime.Now to return a fixed date:  
                    System.Fakes.ShimDateTime.NowGet =   
                    () =>  
                    { return new DateTime(fixedYear, 1, 1); };  
  
                    // Instantiate the component under test:  
                    var componentUnderTest = new MyComponent();  
  
                  // Act:  
                    int year = componentUnderTest.GetTheCurrentYear();  
  
                  // Assert:   
                    // This will always be true if the component is working:  
                    Assert.AreEqual(fixedYear, year);  
                }  
            }  
    }  
  
    ```  
  
    ```vb  
    <TestClass()> _  
    Public Class TestClass1  
        <TestMethod()> _  
        Public Sub TestCurrentYear()  
            Using s = Microsoft.QualityTools.Testing.Fakes.ShimsContext.Create()  
                Dim fixedYear As Integer = 2000  
                ' Arrange:  
                ' Detour DateTime.Now to return a fixed date:  
                System.Fakes.ShimDateTime.NowGet = _  
                    Function() As DateTime  
                        Return New DateTime(fixedYear, 1, 1)  
                    End Function  
  
                ' Instantiate the component under test:  
                Dim componentUnderTest = New MyComponent()  
                ' Act:  
                Dim year As Integer = componentUnderTest.GetTheCurrentYear  
                ' Assert:   
                ' This will always be true if the component is working:  
                Assert.AreEqual(fixedYear, year)  
            End Using  
        End Sub  
    End Class  
    ```  
  
     Dolgu sınıf adları yapılma ekleyerek `Fakes.Shim` özgün türü adı. Parametre adları yöntem adına eklenir. (System.Fakes için herhangi bir derleme başvurusu eklemek gerekmez.)  
  
 Önceki örnek statik yöntem olarak bir dolgu kullanır. Bir dolgu için örnek yöntemi kullanmak için yazma `AllInstances` tür adı ve yöntem adını arasında:  
  
```  
System.IO.Fakes.ShimFile.AllInstances.ReadToEnd = ...  
```  
  
 (Başvurmak için 'System.IO.Fakes' derlemesi bulunmuyor. Ad alanı dolgusu oluşturma işlemi tarafından oluşturulur. Ancak, 'kullanılarak' veya 'Alma' her zamanki gibi kullanabilirsiniz.)  
  
 Ayrıca belirli örnekler, oluşturucular ve özellikler için dolgular oluşturabilirsiniz. Daha fazla bilgi için bkz: [uygulamanızı birim testi için diğer derlemelerden yalıtmak üzere dolgular kullanma](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md).  
  
## <a name="in-this-section"></a>Bu bölümde  
 [Birim testi için birbirinden uygulamanızın parçalarını yalıtmak üzere saplamalar kullanma](../test/using-stubs-to-isolate-parts-of-your-application-from-each-other-for-unit-testing.md)  
  
 [Uygulamanızı birim testi için diğer derlemelerden yalıtmak üzere dolgular kullanma](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md)  
  
 [Kod oluşturma, derleme ve Microsoft Fakes adlandırma kuralları](../test/code-generation-compilation-and-naming-conventions-in-microsoft-fakes.md)
