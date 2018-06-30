---
title: "Nasıl yapılır: Visual Studio'da veri temelli birim testi oluşturma"
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
f1_keywords:
- vs.test.testresults.unittest.datadriven
- vs.test.testresults.unittest.datadriven.failure
helpviewer_keywords:
- unit tests, running
- unit tests, data-driven
- data-driven unit tests
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: f8811d2c9b1d27a2a436004da29711a7a4e34f55
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37117607"
---
# <a name="how-to-create-a-data-driven-unit-test"></a>Nasıl Yapılır: Veri Temelli Birim Testi Oluşturma

Yönetilen kod için Microsoft birim test çerçevesi kullanarak bir veri kaynağından test yönteminde kullanılan değerleri almak için bir birim testi yöntemi ayarlayabilirsiniz. Yöntemi, tek bir yöntem kullanarak giriş çeşitli test kolaylaştırır veri kaynağındaki her satır için sırayla çalışır.

Veri temelli birim testi oluşturma, aşağıdaki adımları içerir:

1.  Test yönteminde kullanmanız değerleri içeren bir veri kaynağı oluşturun. Veri kaynağı test çalışmaları makinede kayıtlı herhangi bir türü olabilir.

2.  Özel eklemek <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext> alan ve ortak bir `TestContext` test sınıf özelliğine.

3.  Bir birim test yöntemi oluşturma ve ekleme bir <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute> kendisine özniteliği.

4.  Kullanmak <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext.DataRow%2A> bir testinde kullanmak değerleri almak için dizin oluşturucu özelliği.

##  <a name="BKMK_The_method_under_test"></a> Test yöntemi

Örnek olarak, kimliğin şöyle olduğunu varsayalım:

1.  Bir çözüm olarak adlandırılan `MyBank` kabul eder ve işlemleri farklı türler için işler.

2.  Bir proje ile `MyBank` adlı `BankDb` hesapları için işlemleri yönetir.

3.  Bir sınıfa `Maths` içinde `DbBank` herhangi bir işlem bankasına avantajlı olduğundan emin olmak için matematik işlevleri gerçekleştirir projesi.

4.  Bir birim testi adlı proje `BankDbTests` davranışını test etmek için `BankDb` bileşeni.

5.  Bir birim testi adlı bir sınıf `MathsTests` davranışını doğrulamak için `Maths` sınıfı.

Bir yöntemin test edecek `Maths` bir döngü kullanarak iki tamsayı ekler:

```csharp
public int AddIntegers(int first, int second)
{
    int sum = first;
    for( int i = 0; i < second; i++)
    {
        sum += 1;
    }
    return sum;
}
```

##  <a name="BKMK_Creating_a_data_source"></a> Veri kaynağı oluşturma
 Test etmek için `AddIntegers` yöntemi, bir dizi parametreler için değerler ve döndürülecek beklediğiniz toplamı belirten bir veri kaynağı oluşturun. Bu örnekte, adlandırılmış bir Sql Compact veritabanı oluşturacağız `MathsData` ve adlı bir tablo `AddIntegersData` aşağıdaki sütun adları ve değerleri içerir

|İlksayı|İkincisayı|TOPLA|
|-----------------|------------------|---------|
|0|1.|1.|
|1.|1.|2|
|2|-3|-1|

##  <a name="BKMK_Adding_a_TestContext_to_the_test_class"></a> Bir testiyse test sınıfına ekleme
 Birim testi çerçevesi oluşturur bir `TestContext` veri temelli bir test veri kaynağı bilgilerini depolamak için nesne. Çerçeve, ardından bu nesne değeri olarak ayarlar `TestContext` oluşturduğunuz özelliği.

```csharp
private TestContext testContextInstance;
public TestContext TestContext
{
    get { return testContextInstance; }
    set { testContextInstance = value; }
}
```

 Test yönteminize aracılığıyla verilere `DataRow` dizin oluşturucu özelliği `TestContext`.

##  <a name="BKMK_Writing_the_test_method"></a> Test yöntemi yazma
 İçin test yöntemini `AddIntegers` oldukça basittir. Veri kaynağındaki her satır için çağrı `AddIntegers` ile **İlksayı** ve **İkincisayı** sütun değerleri olarak parametreler ve dönüş değeri ile karşılaştırarak doğrulayın **toplam** Sütun değeri:

```csharp
[DataSource(@"Provider=Microsoft.SqlServerCe.Client.4.0; Data Source=C:\Data\MathsData.sdf;", "Numbers")]
[TestMethod()]
public void AddIntegers_FromDataSourceTest()
{
    var target = new Maths();

    // Access the data
    int x = Convert.ToInt32(TestContext.DataRow["FirstNumber"]);
    int y = Convert.ToInt32(TestContext.DataRow["SecondNumber"]);
    int expected = Convert.ToInt32(TestContext.DataRow["Sum"]);
    int actual = target.IntegerMethod(x, y);
    Assert.AreEqual(expected, actual,
        "x:<{0}> y:<{1}>",
        new object[] {x, y});
}
```

`Assert` Yöntemi görüntüleyen bir ileti içerir `x` ve `y` başarısız yineleme değerleri. Varsayılan olarak, onaylanan değerler `expected` ve `actual`, başarısız bir test ayrıntılarında önceden eklendi.

###  <a name="BKMK_Specifying_the_DataSourceAttribute"></a> DataSourceAttribute belirtme
 `DataSource` Özniteliği test yönteminde veri kaynağı ve kullandığınız tablo adı için bağlantı dizesini belirtir. Tam bilgileri bağlantı dizesinde, kullandığınız veri kaynağı türüne bağlı olarak farklılık gösterir. Bu örnekte, bir SqlServerCe veritabanı kullandık.

```csharp
[DataSource(@"Provider=Microsoft.SqlServerCe.Client.4.0;Data Source=C:\Data\MathsData.sdf", "AddIntegersData")]
```

Veri kaynağı özniteliği üç Oluşturucusu vardır.

```csharp
[DataSource(dataSourceSettingName)]
```

 Bir parametre ile bir oluşturucu çözüm için app.config dosyasında depolanan bağlantı bilgilerini kullanır. *DataSourceSettingsName* bağlantı bilgilerini belirleyen yapılandırma dosyasındaki Xml öğesi adı.

 App.config dosyasını kullanarak birim testi kendisini değişiklik yapmadan veri kaynağının konumunu değiştirmenize izin verir. Bir app.config dosyası oluşturma ve kullanma hakkında daha fazla bilgi için bkz: [izlenecek yol: bir veri kaynağı tanımlamak için bir yapılandırma dosyası kullanma](../test/walkthrough-using-a-configuration-file-to-define-a-data-source.md)

```csharp
[DataSource(connectionString, tableName)]
```

 `DataSource` Oluşturucusu iki parametre ile veri kaynağı ve test yöntemi için veri içeren bir tablo adı için bağlantı dizesini belirtir.

 Bağlantı dizeleri veri kaynağı türü türüne bağlıdır, ancak veri sağlayıcı değişmez adını belirten bir sağlayıcısı öğesi içermelidir.

```csharp
[DataSource(
    dataProvider,
    connectionString,
    tableName,
    dataAccessMethod
    )]
```

###  <a name="BKMK_Using_TestContext_DataRow_to_access_the_data"></a> Veri erişim için TestContext.DataRow kullanma
 Verilerine erişmek için `AddIntegersData` tablo, kullanın `TestContext.DataRow` dizin oluşturucu. `DataRow` olan bir <xref:System.Data.DataRow> nesne, bu nedenle dizin veya sütun adlarına göre sütun değerlerini almak. Değerleri nesneler olarak döndürdüğünden, bunları uygun türe Dönüştür:

```csharp
int x = Convert.ToInt32(TestContext.DataRow["FirstNumber"]);
```

##  <a name="BKMK_Running_the_test_and_viewing_results"></a> Testi Çalıştırma ve sonuçları görüntüleme
 Test yöntemi yazmayı bitirdiğinizde test projesi oluşturun. Test yöntemi Test Gezgini penceresinde görünür **testleri değil Çalıştır** grubu. Test Gezgini çalıştırmak, yazma ve testleri yeniden çalıştırmak gibi sonuçları gruplar halinde görüntülenir. **başarısız testler**, **testleri geçti**, ve **testleri değil Çalıştır**. Seçebileceğiniz **tümünü Çalıştır** tüm testleri çalıştırma veya seçmek için **çalıştırmak** Çalıştırılacak testleri kümesini seçin.

 Test çalışırken test sonuçları çubuğu Explorer üstündeki animasyon eklenir. Herhangi bir test başarısız olursa test çalıştırması sonunda çubuğu tüm testleri geçmişse yeşil veya kırmızı olur. Test Gezgini penceresinin altındaki ayrıntılar bölmesinde test çalışması özeti görüntülenir. Bir test alt bölmesinde test ayrıntılarını görüntülemek için seçin.

 Çalıştırdıysanız `AddIntegers_FromDataSourceTest` yöntemi örneğimizde sonuçlar çubuğu kırmızı kapatır ve test yöntemi taşınır **başarısız testler** verilerden tekrarlayan yöntemlerin herhangi biriyle başarısız kaynak veri güdümlü bir sınama başarısız olur. Test Gezgini penceresinde başarısız bir veri güdümlü test seçtiğinizde, Ayrıntılar bölmesinde verileri satır dizini tarafından tanımlanan her bir yineleme sonuçlarını görüntüler. Bizim örneğimizde, göründüğü `AddIntegers` algoritması negatif değerler düzgün işlemez.

 Ne zaman yöntemi test altında düzeltilinceye yeniden test sonuçları çubuk yeşil kapatır ve test yöntemi taşınır **geçirilen Test** grubu.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute?displayProperty=fullName>
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext?displayProperty=fullName>
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext.DataRow%2A?displayProperty=fullName>
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert?displayProperty=fullName>
- [Kodunuza Birim Testi Uygulama](../test/unit-test-your-code.md)
- [Test Gezgini ile birim testleri çalıştırma](../test/run-unit-tests-with-test-explorer.md)
- [Yönetilen Kod için Microsoft Birim Testi Çerçevesi ile .NET Framework için Birim Testleri Yazma](../test/writing-unit-tests-for-the-dotnet-framework-with-the-microsoft-unit-test-framework-for-managed-code.md)