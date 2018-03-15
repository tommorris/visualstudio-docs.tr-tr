---
title: "Sharepoint 2010 uygulamaları için birim testlerini yalıtmak üzere Öykünücüler kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 356a0efe98a55191757f153a6e228afb1f708312
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="using-emulators-to-isolate-unit-tests-for-sharepoint-2010-applications"></a>Sharepoint 2010 uygulamaları için birim testlerini yalıtmak üzere öykünücüler kullanma
Microsoft.SharePoint.Emulators paketi, Microsoft SharePoint 2010 uygulamaları için yalıtılmış birim testleri oluşturmak için yardımcı olacak bir dizi sağlar. Öykünücüler kullanma [dolgular](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md) gelen [Microsoft Fakes](../test/isolating-code-under-test-with-microsoft-fakes.md) en sık kullanılan nesneleri ve yöntemleri SharePoint API taklit hafif bellek içi nesneler oluşturmak için yalıtım framework. Bir SharePoint yöntem değil benzetilmiş veya bir öykünücü varsayılan davranışını değiştirmek istediğiniz istediğiniz sonuçları sağlamak için Fakes dolgular oluşturabilirsiniz.

 Varolan test yöntemleri ve sınıfları öykünücüsü bağlamında çalışacak şekilde kolayca dönüştürülebilir. Bu özellik, çift kullanımlı testleri oluşturmanızı sağlar. Bir çift kullanımlı test Öykünücüler kullanma yalıtılmış birim testleri ve tümleştirme testleri gerçek SharePoint API'sine karşı arasında geçiş yapabilirsiniz.

##  <a name="BKMK_Requirements"></a> Gereksinimleri

-   Microsoft SharePoint 2010 (SharePoint 2010 Server or SharePoint 2010 Foundation)

-   Microsoft Visual Studio Enterprise

-   Microsoft SharePoint Öykünücüler NuGet paketi

 Da aşina olmalısınız [birim Visual Studio testi Temelleri](../test/unit-test-basics.md) ve bazı bilgisine [Microsoft Fakes](../test/isolating-code-under-test-with-microsoft-fakes.md).

##  <a name="BKMK_The_AppointmentsWebPart_example"></a> AppointmentsWebPart örneği
 AppointmentsWebPart görüntülemek ve bir SharePoint listesi, randevu yönetmenize olanak sağlar.

 ![Randevular Web Bölümü](../test/media/ut_emulators_appointmentswebpart.png "UT_EMULATORS_AppointmentsWebPart")

 Bu örnekte, biz web bölümünün iki yöntem test edeceksiniz:

-   `ScheduleAppointment` Yöntemi yönteme geçirilen liste öğesi değerlerinin doğrular ve listesinde belirtilen SharePoint web üzerinde yeni bir giriş oluşturur.

-   `GetAppointmentsForToday` Yöntemi bugünün randevuları ayrıntılarını döndürür.

##  <a name="BKMK_Converting_an_existing_test"></a> Varolan bir teste dönüştürme
 Bir SharePoint bileşeninde bir yöntem, tipik bir test, test yöntemi SharePoint Foundation geçici bir site oluşturur ve test altındaki kodun gerektiren site için SharePoint bileşenlerini ekler. Test yöntemi oluşturur ve bileşeninin bir örneğini uygular. Test sonunda site kaldırılır.

 `ScheduleAppointment` Yöntemi bizim kodu test altındaki büyük olasılıkla bileşeni için yazılmış ilk yöntemlerden birini:

```
// method under test
public bool ScheduleAppointment(SPWeb web, string listName, string name,
    string phone, string email, string age, DateTime date, out string errorMsg)
{
    errorMsg = string.Empty;
    var badFormat = this.checkInput(name, phone, email, age);
    if (badFormat)
    {
        errorMsg = "Bad Format";
        return false;
    }
    var exists = this.CheckDuplicate(listName, web, name, phone, email, age, date);
    if (exists)
    {
        errorMsg = "Item already exists";
        return false;
    }
    SPListItemCollection items = web.Lists[listName].Items;
    // create item and populate fields
    SPListItem item = items.Add();
    item["Name"] = name;
    item["Phone"] = phone;
    item["Email"] = email;
    item["Age"] = age;
    item["Date"] = date.ToString("D");
    item.Update();
    return true;
}

```

 İşlevselliğinde yapılan ilk testin `ScheduleAppointment` yöntemi şuna benzeyebilir:

```csharp

[TestMethod]
public void ScheduleAppointmentReturnsTrueWhenNewAppointmentIsCreated()
{
    using( var site = new SPSite("http://localhost"))
    using (var webPart = new BookAnAppointmentWebPart())
    {
        // Arrange
        string errorMsg = string.Empty;
        DateTime date = DateTime.Now;
        SPList list = AddListToSiteHelper(site);

        // Act
        bool success = webPart.ScheduleAppointment(site.RootWeb, list.Title,
            "Raisa Pokrovskaya", "425-555-0163", "raisa@outlook.com", "55", date,
            out errorMsg);
        list.Delete();

        // Assert
        Assert.IsTrue(success);
    }
}
```

 Bu test yöntemi doğrulayın rağmen `ScheduleAppointment` yöntemi doğru yeni bir giriş listesine ekler, daha fazla bir tümleştirme testte web bölümünün belirli davranışlarını kodunuzun bir test. SharePoint ve SharePoint API için dış bağımlılıklar testin kullanıcı kodunda dışında nedenlerle başarısız olmasına neden olabilir `ScheduleAppointment` yöntemi. Oluşturma ve SharePoint sitesi yok etme yükü de normal bir kodlama işleminin parçası olarak çalıştırmak için yavaş test yapabilirsiniz. Kurulum ve site yok etme için her test yönteminin gerçekleştirdiği yalnızca verimli Geliştirici birim testleri oluşturma sorunu compounds.

 Microsoft SharePoint Öykünücüler bir dizi nesnesi ve "en yaygın SharePoint API'ları davranışını taklit eden çiftleri" yöntemi sağlar. Benzetilmiş yöntemleri çalıştırmak SharePoint gerektirmeyen basit SharePoint API uygulamalarıdır. Microsoft Fakes SharePoint Öykünücüler, yöntemi çiftleri için SharePoint API çağrıları saptıran için kullanarak, testlerinizi yalıtmak ve istediğiniz kod test ettiğinizden emin olun. Değil Öykünülen SharePoint yöntemlerini çağırdığınızda, Fakes doğrudan istenen davranışı oluşturmak için kullanabilirsiniz.

###  <a name="BKMK_Adding_the_Emulators_package_to_a_test_project"></a> Bir test projesi için Öykünücüler paketi ekleme
 SharePoint Öykünücüler test projesine eklemek için:

1.  Çözüm Gezgini'nde test projesini seçin.

2.  Seçin **NuGet paketlerini Yönet...**  kısayol menüsünde.

3.  Arama **çevrimiçi** kategorisi için `Microsoft.SharePoint.Emulators`ve ardından **yükleme**.

 ![SharePoint Öykünücüler NuGet paketi](../test/media/ut_emulators_nuget.png "UT_EMULATORS_Nuget")

###  <a name="BKMK__Running_a_test_method_in_the_emulation_context"></a> Test yöntemi öykünme ile çalıştırma
 Paket yükleme gerekli kitaplıkları başvurularını projelerinize ekler. Varolan bir test sınıfı kullanımı kolay Öykünücüler yapmak için ad alanları Ekle `Microsoft.SharePoint.Emulators` ve `Microsoft.QualityTools.Testing.Emulators`.

 Test yöntemlerinizi öykünmelerine etkinleştirmek için yöntemi gövdesinde sarmalamak bir `using` oluşturur deyimi bir `SharePointEmulationScope` nesnesi. Örneğin:

```csharp

[TestMethod]
public void ScheduleAppointmentReturnsTrueWhenNewAppointmentIsCreated()
{
    // create the emulation scope with a using statement
    using (new SharePointEmulationScope())
    using( var site = new SPSite("http://localhost"))
    using (var webPart = new BookAnAppointmentWebPart())
    {
        // Arrange
        string errorMsg = string.Empty;
        DateTime date = DateTime.Now;
        SPList list = AddListToSiteHelper(site);

        // Act
        bool success = webPart.ScheduleAppointment(site.RootWeb, list.Title,
            "Raisa Pokrovskaya", "425-555-0163", "raisa@outlook.com", "55", date,
            out errorMsg);
        list.Delete();

        // Assert
        Assert.IsTrue(success);
    }
}

```

 Test yöntemi yürütüldüğünde öykünücüsü çalışma zamanı dinamik olarak kod Microsoft.SharePoint.Fakes.dll içinde bildirilen Temsilciler bu yönteme çağrıları yönlendir SharePoint yöntemlerde eklemesine Microsoft Fakes çağırır. Microsoft.SharePoint.Emulators.dll yakın gerçek SharePoint davranışını mimicking temsilcileri benzetilmiş yöntemleri için uygular. Test yöntemi veya test altındaki bileşen SharePoint yöntemi çağırdığında sonucu, öykünme davranıştır.

 ![Öykünücü yürütme akış](../test/media/ut_emulators_flowchart.png "UT_EMULATORS_FlowChart")

##  <a name="BKMK_Creating_dual_use_classes_and_methods"></a> Çift kullanımlı sınıflar ve yöntemler oluşturma
 Her iki tümleştirme testleri gerçek SharePoint API'sine karşı ve Öykünücüler kullanma yalıtılmış birim testleri için kullanılan yöntemleri oluşturmak için aşırı yüklü Oluşturucu kullanın `SharePointEmulationScope(EmulationMode)` test yöntemi kodunuzu sarmalamak için. İki değerlerini `EmulationMode` enum belirtin kapsamı Öykünücüler kullanıp kullanmadığını (`EmulationMode.Enabled`) veya kapsamı SharePoint API kullanıp kullanmadığını (`EmulationMode.Passthrough`).

 Örneğin, işte çift kullanımı olacak şekilde önceki testi nasıl düzenleyebilirsiniz:

```csharp

// class level field specifies emulation mode
private const EmulationMode emulatorMode = EmulationMode.Enabled;

[TestMethod]
public void ScheduleAppointmentReturnsTrueWhenNewAppointmentIsCreated()
{
    // emulation scope determined by emulatorMode
    using( SharePointEmulationScope(emulatorMode))
    using( var site = new SPSite("http://localhost"))
    using (var webPart = new BookAnAppointmentWebPart())
    {
        // Arrange
        string errorMsg = string.Empty;
        DateTime date = DateTime.Now;
        SPList list = AddListToSiteHelper(site);

        // Act
        bool success = webPart.ScheduleAppointment(site.RootWeb, list.Title,
            "Raisa Pokrovskaya", "425-555-0163", "raisa@outlook.com", "55", date,
            out errorMsg);
        list.Delete();

        // Assert
        Assert.IsTrue(success);
    }
}
```

## <a name="using-testinitialize-and-testcleanup-attributes-to-create-a-dual-use-test-class"></a>Çift kullanımı oluşturmak için öznitelikleri sınıfı test TestInitialize ve TestCleanup kullanma

Kullanarak bir sınıfın tüm veya çoğu testleri çalıştırırsanız `SharePointEmulationScope`, öykünme modu ayarlamak için sınıf düzeyi teknikleri yararlanabilir.

-   Test ile öznitelikli sınıfı yöntemleri <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestInitializeAttribute> ve <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCleanupAttribute> oluşturabilir ve kapsamı yok.

-   Ayarı `EmulationMode` sınıfta arasında modu değişikliği otomatikleştirmenize düzeyi izin `EmulationMode.Enabled` ve `EmulationMode.Passthrough`.

 İle öznitelikli bir sınıf yöntemi `[TestInitialize]` her test yöntemi ile birlikte öznitelikli bir yöntem başlangıcında Çalıştır `[TestCleanup]` her test yönteminin sonunda çalıştırır. Özel bir alan için bildirebilir `SharePointEmulationScope` nesne sınıf düzeyinde, bunu başlatmak `TestInitialize` yöntemi öznitelikli ve nesnenin dispose `TestCleanup` yöntemi öznitelikli.

 Seçimi otomatikleştirmek için seçtiğiniz herhangi bir yöntemi kullanabilirsiniz `EmulationMode`. Önişlemci yönergeleri kullanarak bir simge varlığını denetlemek bir yoludur. Örneğin, test yöntemleri Öykünücüler kullanma bir sınıfta çalıştırmak için bir simge gibi tanımlayabilirsiniz `USE_EMULATION` test proje dosyasında veya yapı komut satırında. Simgenin tanımlanırsa, bir sınıf düzeyinde `EmulationMode` sabiti bildirilir ve kümesine `Enabled`. Sabit kümesine Aksi halde, `Passthrough`.

 Önişlemci yönergeleri kullanımı gösterilmiştir test sınıfının örneği ve `TestInitialize` ve `TestCleanup` öykünme modu ayarlamak için yöntemler öznitelikli.

```csharp
//namespace declarations
...

namspace MySPAppTests
{
    [TestClass]
    public class BookAnAppointmentWebPartTests
    {

        // emulationScope is a class level field
        private SharePointEmulationScope emulationScope;

        // preprocessor directives determine the value of emulatorMode
        #if USE_EMULATIONprivate const EmulationMode emulatorMode = EmulationMode.Enabled;#elseprivate const EmulationMode emulatorMode = EmulationMode.Passthrough;#endif

        // InitializeTest sets the emulation scope at the beginning of each test method
        [TestInitialize]public void InitializeTest(){this.emulationScope = new SharePointEmulationScope(emulatorMode);}

        // CleanupTest disposes the emulation scope at the end of each test method
        [TestCleanup]public void CleanupTest(){this.emulationScope.Dispose();}

        [TestMethod]
        public void ScheduleAppointmentReturnsTrueWhenNewAppointmentIsCreated()
        {
            // remove the SharePointEmulationScope using statement from the method
            using( var site = new SPSite("http://localhost"))
            using (var webPart = new BookAnAppointmentWebPart())
            {
                // Arrange
                string errorMsg = string.Empty;
                DateTime date = DateTime.Now;
                SPList list = AddListToSiteHelper(site);

                // Act
                bool success = webPart.ScheduleAppointment(site.RootWeb, list.Title,
                    "Raisa Pokrovskaya", "425-555-0163", "raisa@outlook.com", "55", date,
                    out errorMsg);
                list.Delete()

                // Assert
                Assert.IsTrue(success);
            }
        }

        ...// More tests

    }
}
```

##  <a name="BKMK_Handling_non_emulated_SharePoint_methods"></a> İşleme benzetilmiş SharePoint yöntemleri
 Tüm SharePoint türleri Öykünülen ve bazı benzetilmiş türleri tüm yöntemleri benzetilmiş. Test altındaki kodun değil benzetilmiş bir SharePoint yöntemini çağırırsa, yöntem oluşturulur bir `NotSupportedException` özel durum. Özel durum oluştuğunda Fakes dolgusu SharePoint yöntemi ekleyin.

 **Sharepoint Fakes ayarlama**

 Microsoft Fakes dolgular açıkça çağırmak için:

1.  Değil benzetilmiş bir SharePoint sınıf dolguya istiyorsanız, Microsoft.SharePoint.fakes dosyasını düzenleyin ve sınıf shimmed sınıfları listesine ekleyin. Bkz: [saplamalar ve dolgular kod oluşturma yapılandırma](http://msdn.microsoft.com/library/hh708916.aspx#bkmk_configuring_code_generation_of_stubs) bölümünü [kod oluşturma, derleme ve adlandırma kuralları Microsoft Fakes içinde](../test/code-generation-compilation-and-naming-conventions-in-microsoft-fakes.md).

     ![Çözüm Gezgininde klasör fakes](../test/media/ut_emulators_fakesfilefolder.png "UT_EMULATORS_FakesFileFolder")

2.  Oluşturduğunuz test projesinin en az bir kez Microsoft SharePoint Öykünücüler paketini yükledikten sonra ve Microsoft.SharePoint.Fakes dosyayı düzenlerseniz yeniden oluşturun. Proje derleme oluşturur ve dolduran bir **FakesAssembly** , disk üzerindeki proje kök klasöründe.

     ![FakesAssembly klasörü](../test/media/ut_emulators_fakesassemblyfolder.png "UT_EMULATORS_FakesAssemblyFolder")

3.  Bir başvuru ekleyin **Microsoft.SharePoint.14.0.0.0.Fakes.dll** bulunan derleme **FakesAssembly** klasör.

4.  (İsteğe bağlı) İçin test sınıf için bir ad alanı yönergesi eklemek `Microsoft.QualityTools.Testing.Fakes`, `Microsoft.SharePoint.Fakes` ve tüm iç içe geçmiş ad alanı `Microsoft.SharePoint.Fakes`kullanmak istediğiniz.

 **Bir SharePoint yöntem dolgusu temsilcisi uygulama**

 Bizim örnek projesinde `GetAppointmentsForToday` yöntem çağrılarını [SPList.GetItems(SPQuery)](http://msdn.microsoft.com/library/ms457534.aspx) SharePoint API yöntemi.

```csharp
// method under test
public string GetAppointmentsForToday(string listName, SPWeb web)
{
    SPList list = web.Lists[listName];
    DateTime today = DateTime.Now;
    var listQuery = new SPQuery{Query = String.Format("<Where><Eq><FieldRef Name='Date'/>" +"<Value Type='Text'>{0}</Value>" +"</Eq></Where>", today.ToString("D"))};
    var result = new System.Text.StringBuilder();
    foreach (SPListItem item in list.GetItems(listQuery))
    {
        result.AppendFormat("Name: {0}, Phone: {1}, Email: {2}, Age: {3}, Date: {4}\n",
            item["Name"], item["Phone"], item["Email"], item["Age"], item["Date"]);
    }
    return result.ToString();
}

```

 `SPList.GetItems(SPQuery)` Aşırı yüklenmiş sürümü `GetItems` yöntemi benzetilmiş değil. Bu nedenle, yalnızca var olan bir test için kaydırma `GetAppointmentsForToday` içinde `SharePoint.Emulation.Scope` başarısız olmasına neden olabilir. Fakes temsilci uygulaması yazmak zorunda çalışma test oluşturmak için `ShimSPList.GetItemsSPQuery` karşı test etmek istediğiniz sonuçları döndürür.

 Varolan bir test yöntemi değiştirilmesini işte `GetAppointmentsForTodayReturnsOnlyTodaysAppointments`, Fakes temsilci uygular. Gerekli değişiklikleri açıklamaları çağrılır:

> [!IMPORTANT]
>  Test açıkça dolgular throw Fakes oluşturma yöntemleri bir `ShimNotSupported` testi çalıştırdığınızda, özel durum `EmulationMode.Passthrough` bağlamı. Bu sorunu önlemek için ayarlamak için bir değişken kullanın `EmulationMode` değerini ve tüm Fakes kodda sarmalayın bir `if` değeri test deyimi.

```csharp
// class level field to set emulation mode
private const EmulationMode emulatorMode = EmulationMode.Enabled

[TestMethod]
public void GetAppointmentsForTodayReturnsOnlyTodaysAppointments()
{

    // create the emulation scope with a using statement
    using (var emulationScope = new SharePointEmulationScope(emulatorMode))
    using( var site = new SPSite("http://localhost"))
    using (var webPart = new BookAnAppointmentWebPart())
    {
        // Arrange
        DateTime date = DateTime.Now;
        SPList list = AddListToSiteHelper(site);
        // insert 2 items into list
        AddItemsToListHelper(list, new string[] {"Raisa Pokrovskaya", "425-555-0163",
            "raisa@outlook.com", "55", date.ToString("D") });
        AddItemsToListHelper(list, new string[] {"Francis Totten", "313-555-0100",
            "francis@contoso.com", "42", date.AddDays(1).ToString("D") });

        // use Fakes shims only if emulation is enabled
        if (emulatorMode == EmulationMode.Enabled){var sList = new ShimSPList(list);sList.GetItemsSPQuery = (query) =>{var shim = new ShimSPListItemCollection();shim.Bind(new[] { list.Items[0] });return shim.Instance;}}

        // Act
        string result = webPart.GetAppointmentsForToday(list.Title, site.RootWeb);
        list.Delete();

        // Assert
        Assert.IsTrue(result.Contains(String.Format(
            "Name: Raisa Pokrovskaya, Phone: 425-555-0163, Email: raisa@outlook.com," +
            "Age: 55, Date: {0}", date.ToString("D"))));
        Assert.IsFalse(result.Contains("Name: Francis Totten"));
    }
}

```

 Bu yöntemde, biz öncelikle öykünme etkin olduğunu sınayın. İse, Fakes dolgusu nesne için oluşturuyoruz bizim `SPList` listesinde oluşturmak ve atamak için bir yöntem kendi `GetItemsSPQuery` temsilci. Temsilci Fakes kullanan `Bind` yöntemi için doğru liste öğesi eklemek için `ShimSPListItemCollection` çağırana döndürülen.

##  <a name="BKMK_Writing_emulation_tests_from_scratch__and_a_summary"></a> Karalama ve bir Özet yazma öykünme testleri
 Var olan testleri dönüştürüyorsunuz öykünme ve önceki bölümlerde açıklanan çift kullanımlı testleri oluşturmak için kullanılan teknikleri varsayar ancak sıfırdan testleri yazmak için teknikler de kullanabilirsiniz. Aşağıdaki listede bu teknikler özetlenmektedir:

-   Bir test projesinde Öykünücüler kullanmak için Microsoft.SharePoint.Emulators NuGet paketini projeye ekleyin.

-   Bir test yöntemine Öykünücüler kullanmak için oluşturun bir `SharePointEmulationScope` yöntemi başındaki nesnesi. Kapsam bırakılana kadar tüm desteklenen SharePoint API'leri benzetilmiş.

-   Test kodunuzu karşı gerçek SharePoint API yazıyordunuz gibi yazın. Öykünme içeriği otomatik olarak kendi Öykünücüler SharePoint yöntemlere çağrıları saptıran.

-   Tüm SharePoint nesneleri Öykünülen ve bazı benzetilmiş nesnelerin tüm yöntemleri benzetilmiş. A `NotSupportedException` benzetilmiş olmayan nesne veya yöntemi kullandığınızda, özel durum. Bu durumda, açıkça gerekli davranışı döndürülecek Fakes dolgusu temsilci yöntemi için oluşturun.

-   Çift kullanımlı testler oluşturmak için kullanmak `SharePointEmulationScope(EmulationMode)` Oluşturucusu öykünme kapsam nesnesi oluşturur. `EmulationMode` SharePoint çağrıları benzetilmiş veya gerçek bir SharePoint sitesi karşı yürütülen değerini belirtir.

-   Tümünü veya bir test yöntemlerinizi test sınıfındaki çoğunu öykünme bağlamda yürütüyorsa sınıf düzeyi kullanabilirsiniz `TestInitialize` oluşturmak için yöntemi öznitelikli `SharePointEmulationScope` nesne ve öykünme modu ayarlamak için bir sınıf düzeyi alanı. Bu, öykünme modunu değiştirme otomatikleştirmek için yardımcı olur. Ardından bir `TestCleanup` kapsam nesnesinin dispose yöntemini öznitelikli.

##  <a name="BKMK_Example"></a> Örnek
 Yukarıda açıklanan SharePoint öykünücüsü teknikleri içerir son bir örnek aşağıda verilmiştir:

```csharp
using System;
//other namespace declarations
...
// code under test
using MySPApps;
using Microsoft.SharePoint;
// unit testing and emulators
using Microsoft.VisualStudio.TestTools.UnitTesting;
using Microsoft.QualityTools.Testing.Emulators;
using Microsoft.SharePoint.Emulators;
// explicit Fakes shims
using Microsoft.QualityTools.Testing.Fakes;
using Microsoft.SharePoint.Fakes

namspace MySPAppTests
{
    [TestClass]
    public class BookAnAppointmentWebPartTests
    {

        // emulationScope is a class level field
        private SharePointEmulationScope emulationScope;

        // preprocessor directives determine the value of emulatorMode
        #if USE_EMULATION
            private const EmulationMode emulatorMode = EmulationMode.Enabled;
        #else
            private const EmulationMode emulatorMode = EmulationMode.Passthrough;
        #endif

        // InitializeTest sets the emulation scope at the beginning of each test method
        [TestInitialize]
        public void InitializeTest()
        {
            this.emulationScope = new SharePointEmulationScope(emulatorMode);
        }

        // CleanupTest disposes the emulation scope at the end of each test method
        [TestCleanup]
        public void Cleanup()
        {
            this.emulationScope.Dispose();
        }

        [TestMethod]
        public void ScheduleAppointmentReturnsTrueWhenNewAppointmentIsCreated()
        {
            // remove the SharePointEmulationScope using statement from the method
            using( var site = new SPSite("http://localhost"))
            using (var webPart = new BookAnAppointmentWebPart())
            {
                // Arrange
                string errorMsg = string.Empty;
                DateTime date = DateTime.Now;
                SPList list = AddListToSiteHelper(site);

                // Act
                bool success = webPart.ScheduleAppointment(site.RootWeb, list.Title,
                    "Raisa Pokrovskaya", "425-555-0163", "raisa@outlook.com", "55", date,
                    out errorMsg);
                list.Delete()

                // Assert
                Assert.IsTrue(success);
            }
        }

        [TestMethod]
        public void GetAppointmentsForTodayReturnsOnlyTodaysAppointments()
        {

            // remove the SharePointEmulationScope using statement from the method
            using( var site = new SPSite("http://localhost"))
            using (var webPart = new BookAnAppointmentWebPart())
            {
                // Arrange
                DateTime date = DateTime.Now;
                SPList list = AddListToSiteHelper(site);
                // insert 2 items into list
                AddItemsToListHelper(list, new string[] {"Raisa Pokrovskaya", "425-555-0163",
                    "raisa@outlook.com", "55", date.ToString("D") });
                AddItemsToListHelper(list, new string[] {"Francis Totten", "313-555-0100",
                    "francis@contoso.com", "42", date.AddDays(1).ToString("D") });

                // use Fakes shims only if emulation is enabled
                if (emulatorMode == EmulationMode.Enabled)
                {
                    var sList = new ShimSPList(list);

                    sList.GetItemsSPQuery = (query) =>
                    {
                        var shim = new ShimSPListItemCollection();
                        shim.Bind(new[] { list.Items[0] });
                        return shim.Instance;
                    }
                }

                // Act
                string result = webPart.GetAppointmentsForToday(list.Title, site.RootWeb);
                list.Delete();

                // Assert
                Assert.IsTrue(result.Contains(String.Format(
                    "Name: Raisa Pokrovskaya, Phone: 425-555-0163, Email: raisa@outlook.com," +
                    "Age: 55, Date: {0}", date.ToString("D"))));
                Assert.IsFalse(result.Contains("Name: Francis Totten"));
            }
        }

        ...// More tests

    }
}

```

##  <a name="BKMK_Emulated_SharePoint_types"></a> Benzetilmiş SharePoint türleri
 [Microsoft.SharePoint.SPField](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPField)

 [Microsoft.SharePoint.SPFieldIndex](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPFieldIndex)

 [Microsoft.SharePoint.SPFieldIndexCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPFieldIndexCollection)

 [Microsoft.SharePoint.SPFieldLink](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPFieldLink)

 [Microsoft.SharePoint.SPFieldLinkCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPFieldLinkCollection)

 [Microsoft.SharePoint.SPFieldUrlValue](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPFieldUrlValue)

 [Microsoft.SharePoint.SPFile](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPFile)

 [Microsoft.SharePoint.SPFileCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPFileCollection)

 [Microsoft.SharePoint.SPFolder](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPFolder)

 [Microsoft.SharePoint.SPFolderCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPFolderCollection)

 [Microsoft.SharePoint.SPItem](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPItem)

 [Microsoft.SharePoint.SPItemEventDataCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPItemEventDataCollection)

 [Microsoft.SharePoint.SPItemEventProperties](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPItemEventProperties)

 [Microsoft.SharePoint.SPList](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPList)

 [Microsoft.SharePoint.SPListCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPListCollection)

 [Microsoft.SharePoint.SPListEventProperties](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPListEventProperties)

 [Microsoft.SharePoint.SPListItem](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPListItem)

 [Microsoft.SharePoint.SPListItemCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPListItemCollection)

 [Microsoft.SharePoint.SPQuery](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPQuery)

 [Microsoft.SharePoint.SPRoleAssignment](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPRoleAssignment)

 [Microsoft.SharePoint.SPRoleAssignmentCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPRoleAssignmentCollection)

 [Microsoft.SharePoint.SPSecurableObject](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPSecurableObject)

 [Microsoft.SharePoint.SPSecurity](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPSecurity)

 [Microsoft.SharePoint.SPSite](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPSite)

 [Microsoft.SharePoint.SPUser](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPUser)

 [Microsoft.SharePoint.SPUserCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPUserCollection)

 [Microsoft.SharePoint.SPView](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPView)

 [Microsoft.SharePoint.SPViewCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPViewCollection)

 [Microsoft.SharePoint.SPViewContext](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPViewContext)

 [Microsoft.SharePoint.SPWeb](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPWeb)

 [Microsoft.SharePoint.SPWebCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPWebCollection)

## <a name="see-also"></a>Ayrıca bkz.

- [Kodunuza Birim Testi Uygulama](../test/unit-test-your-code.md)
- [Kodlanmış UI Testleriyle SharePoint 2010 Uygulamalarını Test Etme](../test/testing-sharepoint-2010-applications-with-coded-ui-tests.md)
- [SharePoint Çözümleri Geliştirme](/office-dev/office-dev/developing-sharepoint-solutions)
