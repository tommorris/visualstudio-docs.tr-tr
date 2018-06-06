---
title: Visual Studio'da birim testi temelleri
ms.date: 2016-01-07
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
f1_keywords:
- vs.UnitTest.CreateUnitTest
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8a69f644fecd74328eb3fa007e4589ff194c8e11
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751523"
---
# <a name="unit-test-basics"></a>Birim testi temel bilgileri

Kod oluşturma ve birim testleri çalıştırma beklendiği gibi çalışıp çalışmadığını denetleyin. Birim, programınızı işlevselliğini test edebilirsiniz ayrık sınanabilir davranışları içine olarak tek tek ayırmanız çünkü testi adlı *birimleri*. Visual Studio Test Gezgini birim testleri çalıştırma ve sonuçları Visual Studio'da görüntülemek için esnek ve verimli bir yol sağlar. Visual Studio Microsoft Birim yönetilen ve yerel kodu çerçeveyi testi yükler. Kullanım bir *birim testi çerçevesi* birim testleri oluşturmak için bunları çalıştırmak ve bu test sonuçlarını rapor. Kodunuzun doğru şekilde çalışıp çalışmadığını sınamak için değişiklik yaptığınız zaman yeniden çalıştır birim testleri. Visual Studio Enterprise ile otomatik olarak yapabilirsiniz [Canlı birim testi](live-unit-testing-intro.md), hangi kodunuz tarafından etkilenen testleri algılar değiştirir ve yazarken arka planda çalışır.

Yazılım geliştirme akışınızın ayrılmaz bir parçası olduğunda birim testi kodunuzun kalitesini üzerinde en yüksek etkisi yoktur. Birim testleri standart, sınır ve giriş verileri hatalı örneklerini yanıt kodunu davranışını doğrulayın ve kodu tarafından yapılan açık veya örtülü varsayımlar denetleyin bir işlev veya diğer uygulama kod bloğunu yazma hemen oluşturun. İle *test güdümlü geliştirme*, birim testleri tasarım belgeleri ve işlevsel belirtimleri kullanmak için kod yazmadan önce birim testleri oluşturma.

Hızlı bir şekilde test projeleri oluşturmak ve kodunuzdan test yöntemleri veya gereksinim duyduğunuzda el ile testleri oluşturma. .NET kodu keşfetmek için Intellitest kullandığınızda, test verileri ve birim testleri dizisi oluşturabilirsiniz. Koddaki her deyim için bir test giriş oluşturulan bu deyim yürütülecek. Nasıl yapılır öğrenmek [kodunuz için birim testleri oluşturma](http://msdn.microsoft.com/library/dn823749.aspx).

Test Gezgini, Test Gezgini eklentisi arabirimleri uyguladık birim test çerçevelerini üçüncü taraf ve açık kaynak de çalıştırabilirsiniz. Visual Studio Uzantı Yöneticisi'ni ve Visual Studio Galerisi aracılığıyla bu çerçeveleri çoğunu ekleyebilirsiniz. Bkz: [üçüncü taraf birim test çerçevelerini yükleme](../test/install-third-party-unit-test-frameworks.md)

## <a name="getting-started"></a>Başlarken

Doğrudan kodlama içine alır birim testi giriş için aşağıdaki konulardan birine bakın:

- [İzlenecek yol: Yönetilen Kod için Birim Testleri Oluşturma ve Çalıştırma](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)

- [Hızlı Başlangıç: Test Gezgini ile güdümlü geliştirme test etme](../test/quick-start-test-driven-development-with-test-explorer.md)

- [Visual Studio'da C/C++ için birim testleri yazma](../test/writing-unit-tests-for-c-cpp.md)

## <a name="the-mybank-solution-example"></a>MyBank çözümü örneği

Bu konuda, kullandığımız adlı kurgusal bir uygulamanın geliştirilmesi `MyBank` bir örnek olarak. Bu konudaki Açıklamalar izlemeniz gereken gerçek bir kod gerekmez. Test yöntemleri C# ile yazılmış ve yönetilen kod için Microsoft birim testi çerçevesi kullanarak sunulan, ancak kavramları kolayca diğer dilleri ve çerçeveleri aktarılır.

 ![MyBank çözümü](../test/media/ute_mybanksolution.png)

 Bizim için tasarım ilk teşebbüs `MyBank` uygulama, tek bir hesap ve hareketlerini banka ile temsil eden bir hesapları bileşeni ve toplama ve yönetmek için işlevleri temsil eden bir veritabanı bileşeni içerir Bireysel hesaplar.

 Oluşturuyoruz bir `MyBank` iki proje içeren çözüm:

-   `Accounts`

-   `BankDb`

 Bizim ilk teşebbüs tasarlama `Accounts` proje içeren bir hesap, ortak işlevsellik ürünü ve hesap ve bir sınıf varlıklar geri alınmasının gibi hesabının herhangi bir türde belirten bir arabirim hakkındaki temel bilgileri tutmak için bir sınıf bir denetimi hesabını temsil eder arabiriminden türetilmiş. Biz, hesapları projeleri aşağıdaki kaynak dosyalarını oluşturarak başlayın:

-   `AccountInfo.cs` bir hesap için temel bilgileri tanımlar.

-   `IAccount.cs` Standart bir tanımlar `IAccount` Yatırma ve varlıklar bir hesaptan çekme ve hesap bakiyesini almak için yöntemleri de dahil olmak üzere, hesap için arabirim.

-   `CheckingAccount.cs` içeren `CheckingAccount` uygulayan sınıf `IAccounts` denetleme hesabı için arabirim.

Geri miktar Bakiye daha az olduğundan emin olmak için denetleme hesabından mevzuatı yapmanız gerekir, bir şey olduğunu deneyimlerden biliyoruz. Biz geçersiz kılmak için `IAccount.Withdaw` yönteminde `CheckingAccount` denetler bu koşul için bir yöntem ile. Yöntem şuna benzeyebilir:

```csharp
public void Withdraw(double amount)
{
    if(m_balance >= amount)
    {
        m_balance -= amount;
    }
    else
    {
        throw new ArgumentException(amount, "Withdrawal exceeds balance!")
    }
}
```

Biz bazı koda sahip olduğunuza göre test zamanı geldi.

## <a name="create-unit-test-projects-and-test-methods"></a>Birim testi projelerini oluşturmak ve test yöntemleri

Genellikle birim testi projesi ve birim testi saplamalar kodunuzdan oluşturmak daha hızlı olur. Veya, gereksinimlerinize bağlı olarak el ile testleri ve birim testi projesi oluşturmayı seçebilirsiniz.

 **Birim testi projesi oluşturun ve birim testi saplamalar**

1.  Kod Düzenleyicisi penceresinde, sağ tıklatın ve seçin **birim testleri oluşturma** ve bağlam menüsünden.

     ![Düzenleyicisi penceresinde, bağlam menüsü görüntüleme](../test/media/createunittestsrightclick.png)

2.  Birim testleri oluşturma veya oluşturmak için kullanılan değerleri değiştirmek için Varsayılanları kabul etmek için Tamam'a tıklayın ve ad birim testi projesi ve birim testleri. Varsayılan olarak birim testi yöntemlerine eklenen kodu seçebilirsiniz.

     ![Sağ&#45;Düzenleyicisi'nde tıklatın ve birim testleri oluşturmak seçin](../test/media/createunittestsdialog.png)

3.  Birim testi saplamalar sınıfındaki tüm yöntemler için yeni bir birim testi projesi oluşturulur.

     ![Birim testleri oluşturulur](../test/media/createunittestsstubs.png)

4.  Bilgi edinmek için şimdi İleri atlamayın nasıl [kod için birim test yöntemleri eklemek](#BKMK_Writing_your_tests) anlamlı, birim testi ve baştan sona kodunuzu test etmek için eklemek isteyebilirsiniz herhangi bir ek birim testi yapmak için.

 **Birim testi projesi ve birim testleri el ile oluşturma**

 Birim testi projesi genellikle tek bir kod projenin yapısını yansıtır. Adlı iki birim testi projelerini eklediğiniz MyBank örnekte `AccountsTests` ve `BankDbTests` için `MyBanks` çözümü. Test proje adları rasgele, ancak standart bir adlandırma kuralına benimsenmesi iyi bir fikirdir.

 **Birim testi projesi bir çözüme eklemek için:**

1.  Üzerinde **dosya** menüsünde seçin **yeni** ve ardından **proje** (klavye Ctrl + Shift + N).

2.  Yeni Proje iletişim kutusunda genişletin **yüklü** düğümü, test projeniz için kullanın ve ardından istediğiniz dili seçin **Test**.

3.  Microsoft birim test çerçevelerini birini kullanmayı da tercih **birim testi projesi** proje şablonları listesinden. Aksi takdirde, kullanmak istediğiniz test çerçevesi biriminin proje şablonu seçin. Test etmek için `Accounts` proje bizim örnek, proje adı `AccountsTests`.

    > [!WARNING]
    > Tüm üçüncü taraf ve açık kaynak birim test çerçevelerini Visual Studio Proje şablonu sağlar. Proje oluşturma hakkında daha fazla bilgi için framework belge başvurun.

4.  Birim testi projesi içinde örneğimizde hesapları projeye test altındaki kod projesine bir başvuru ekleyin.

     Başvuru kodunu projeyi oluşturmak için:

    1.  Çözüm Gezgini'nde proje seçin.

    2.  Üzerinde **proje** menüsünde seçin **Başvuru Ekle**.

    3.  Başvuru Yöneticisi iletişim kutusunu açın **çözüm** düğümü seçin **projeleri**. Kod proje adını seçin ve iletişim kutusunu kapatın.

 Her birim testi projesi kodunu projeyi sınıflarda adlarını yansıtma sınıfları içerir. Örneğimizde `AccountsTests` proje aşağıdaki sınıflar içerebilir:

-   `AccountInfoTests` sınıfı için birim test yöntemleri içeren `AccountInfo` sınıfını `BankAccount` proje

-   `CheckingAccountTests` sınıfı için birim test yöntemleri içeren `CheckingAccount` sınıfı.

## <a name="write-your-tests"></a>Testleri yazma

Birim testi kullandığınız framework ve Visual Studio IntelliSense kod projesi için birim testleri için kod yazma aracılığıyla rehberlik sağlar. Test Gezgini içinde çalıştırmak için birim test yöntemleri tanımlamak için özel öznitelikler eklemek çoğu çerçeveleri gerektirir. Çerçeveleri de bir yöntem sunar — genellikle aracılığıyla deyimleri veya yöntem öznitelikleri assert — test yöntemine geçirilen veya başarısız olana belirtmek için. Diğer öznitelikleri sınıfı başlatma sırasında ve her bir test yöntemi ve her test yönteminin sonra ve sınıf yok önce çalışmak erdirme yöntemleri önce isteğe bağlı kurulum yöntemlerini tanımlayın.

AAA (Düzenle, Act, Assert) deseni, test altındaki bir yöntem için birim testleri yazma genel bir yoludur.

- **Yerleştir** birim test yöntemi bölümünü nesneleri başlatır ve test altındaki yöntemine geçirilen verileri değerini ayarlar.

- **Act** bölüm düzenlenen parametreleri ile test yöntemi çağırır.

- **Assert** bölüm doğrular eylem yönteminin test altındaki beklendiği gibi davranır.

Test etmek için `CheckingAccount.Withdraw` yöntemi Bizim örneğimizde, biz sınamalarının yazabilirsiniz: yöntemi Standart davranışını doğrular ve birden çok Bakiye, mevzuatı başarısız olur doğrular. İçinde `CheckingAccountTests` sınıfı, biz aşağıdaki yöntemleri ekleyin:

```csharp
[TestMethod]
public void Withdraw_ValidAmount_ChangesBalance()
{
    // arrange
    double currentBalance = 10.0;
    double withdrawal = 1.0;
    double expected = 9.0;
    var account = new CheckingAccount("JohnDoe", currentBalance);
    // act
    account.Withdraw(withdrawal);
    double actual = account.Balance;
    // assert
    Assert.AreEqual(expected, actual);
}

[TestMethod]
[ExpectedException(typeof(ArgumentException))]
public void Withdraw_AmountMoreThanBalance_Throws()
{
    // arrange
    var account = new CheckingAccount("John Doe", 10.0);
    // act
    account.Withdraw(20.0);
    // assert is handled by the ExpectedException
}
```

Unutmayın `Withdraw_ValidAmount_ChangesBalance` açık bir kullanır `Assert` test yöntemi başarılı veya başarısız olup olmadığını belirlemek için ifade ederken `Withdraw_AmountMoreThanBalance_Throws` kullanır `ExpectedException` test yöntemi başarısını belirlemek için öznitelik. Perde arkasında birim test çerçevesi test yöntemleri try/catch deyimleri sarmalar. Çoğu durumda, bir özel durum yakalandı, test yöntem başarısız olur ve özel durum göz ardı edilir. `ExpectedException` Özniteliği test yöntemi belirtilen özel durum oluşursa geçmesine neden olur.

Microsoft birim test çerçevelerini hakkında daha fazla bilgi için aşağıdaki konulardan birine bakın:

-   [Yönetilen Kod için Microsoft Birim Testi Çerçevesi ile .NET Framework için Birim Testleri Yazma](../test/writing-unit-tests-for-the-dotnet-framework-with-the-microsoft-unit-test-framework-for-managed-code.md)

-   [C/C++ için birim testleri yazma](writing-unit-tests-for-c-cpp.md)

## <a name="set-timeouts-for-unit-tests"></a>Birim testleri için zaman aşımını ayarla

Zaman aşımı üzerinde bir teste yöntemini ayarlamak için:

```csharp
[TestMethod]
[Timeout(2000)]  // Milliseconds
public void My_Test()
{ ...
}
```

İzin verilen en büyük zaman aşımı ayarlamak için:

```csharp
[TestMethod]
[Timeout(TestTimeout.Infinite)]  // Milliseconds
public void My_Test ()
{ ...
}
```

## <a name="run-tests-in-test-explorer"></a>Test Gezgini testleri çalıştırma

Test projesi derlerken, testleri Test Gezgini'nde görünür. Test Gezgini görünür durumda değilse, seçin **Test** Visual Studio menüsünde, **Windows**ve ardından **Test Gezgini**.

 ![Birim Test Gezgini](../test/media/ute_failedpassednotrunsummary.png)

 Çalıştırmak, yazma ve testleri yeniden gibi Test Gezgini varsayılan görünümü sonuçları gruplar halinde görüntülenir. **başarısız testler**, **testleri geçti**, **atlandı testleri** ve  **Testler değil**. Tüm testler o grupta görüntüler görünümünü açmak için bir Grup başlığını seçebilirsiniz.

 Ayrıca, arama kutusuna genel düzeyde eşleşen metin veya önceden tanımlanmış filtrelerden birini seçerek herhangi bir görünüm testlerinde filtre uygulayabilirsiniz. Herhangi bir zamanda herhangi bir seçimi testleri çalıştırabilirsiniz. Testi sonuçlarını Gezgini penceresinin üst geçişi/başarısız çubuğundaki hemen görünür. Test yöntemi sonucu ayrıntılarını test seçtiğinizde görüntülenir.

### <a name="run-and-view-tests"></a>Çalıştırın ve testlerin görüntüleyin

Test Gezgini araç bulmak, düzenlemenize ve ilgilendiğiniz testler yardımcı olur.

 ![Test Gezgini araç çubuğundan testleri çalıştırma](../test/media/ute_toolbar.png)

 Seçebileceğiniz **tümünü Çalıştır** tüm testleri çalıştırma veya seçmek için **çalıştırmak** Çalıştırılacak testleri kümesini seçin. Sonra testleri kümesi çalıştırmak, test çalışması özetini Test Gezgini penceresinin alt kısmında görüntülenir. Bir test alt bölmesinde test ayrıntılarını görüntülemek için seçin. Seçin **açık Test** ve bağlam menüsünden (klavye: F12) seçili test için kaynak kodunu görüntüleyin.

 Tek tek testlerin herhangi bir sırayla çalıştırmak engelleyen bağımlılık varsa, paralel test yürütmesi ile Aç ![UTE&#95;parallelicon&#45;küçük](../test/media/ute_parallelicon-small.png) iki durumlu düğme araç çubuğunda. Bu, tüm testleri çalıştırmak için geçen süre önemli ölçüde azaltabilir.

### <a name="run-tests-after-every-build"></a>Her yapıdan sonra testleri çalıştırma

> [!WARNING]
> Her derleme yalnızca Visual Studio kuruluş içinde desteklenen sonra çalışan birim testleri.

|||
|-|-|
|![Derleme sonrası çalıştırın](../test/media/ute_runafterbuild_btn.png)|Her yerel yapıdan sonra birim testleri çalıştırmak için tercih **Test** standart menüsünde, **çalıştırmak sonra yapı testleri** Test Gezgini araç çubuğunda.|

### <a name="filter-and-group-the-test-list"></a>Filtre ve grup test listesi

Çok sayıda testleri sahip olduğunuzda, Test Gezgini tarafından belirtilen dize listesini filtrelemek için arama kutusuna yazabilirsiniz. Filtre olayınızın filtre listeden seçerek daha fazla kısıtlayabilirsiniz.

 ![Arama filtresi kategorileri](../test/media/ute_searchfilter.png)

|||
|-|-|
|![Test Gezgini Grup düğmesi](../test/media/ute_groupby_btn.png)|Kategoriye göre testlerinizi gruplamak için seçin **Group By** düğmesi.|

 Daha fazla bilgi için bkz: [Test Gezgini ile birim testleri çalıştırma](../test/run-unit-tests-with-test-explorer.md)

## <a name="qa"></a>SORU- CEVAP

**S: birim testleri nasıl hata?**

**Y:** testleriniz için hata ayıklama oturumu başlatmak için kullanım Test Gezgini. Kodunuz Visual Studio hata ayıklayıcısı ile sorunsuz bir şekilde Adımlama, İleri ve geri birim testleri ve test altındaki proje arasında alır. Hata ayıklama başlatmak için:

1.  Visual Studio Düzenleyicisi'nde hata ayıklamak istediğiniz bir veya daha fazla test yöntemler bir kesme noktası ayarlayın.

    > [!NOTE]
    > Test yöntemleri herhangi bir sırada çalıştığından hata ayıklamak istediğiniz tüm test yöntemler kesme noktalarını ayarlayın.

2.  Test Gezgini test yöntemleri seçin ve ardından **seçili Testlerde Hata Ayıkla** kısayol menüsünden.

Daha fazla ayrıntı öğrenin [birim testleri hata ayıklama](../debugger/debugging-in-visual-studio.md).

 **S: TDD kullanıyorum olursa, nasıl ı kod my testlerden oluştur?**

 **Y:** IntelliSense sınıflar ve yöntemler proje kodunuzda oluşturmak için kullanın. Sınıf çağıran bir test yöntemi veya oluşturmak istediğiniz yöntemi bir ifadesi yazın, ardından çağrının altında IntelliSense menüsünü açın. Çağrı yeni sınıfın bir oluşturucuya ise seçmeniz **yeni türü** sınıfı kod projenize eklemek için sihirbazı izleyin ve menüden. Arama için bir yöntem ise seçmeniz **üretme yeni yöntemi** IntelliSense menüsünde.

 ![Yöntem saplama IntelliSense menü oluşturma](../test/media/ute_generatemethodstubintellisense.png)

 **S: birden çok veri kümesi testi çalıştırmak için giriş olarak ele birim testleri oluşturma?**

 **Y:** Evet. *Veri temelli test yöntemleri* , tek bir birim testi yöntemiyle değerleri aralığı test olanak tanır. Kullanım bir `DataSource` özniteliğinin test etmek istediğiniz değişken değerleri veri kaynağı ve, tablo belirtir test yöntemi içerir.  Yöntem gövdesinde kullanarak değişkenlere satır değerleri atamak `TestContext.DataRow[` *ColumnName* `]` dizin oluşturucu.

> [!NOTE]
> Yönetilen kod için Microsoft birim test çerçevesi kullanarak yazma yöntemleri yalnızca test etmek için bu yordamları uygulayın. Farklı bir Framework'te kullanıyorsanız, eşdeğer işlevselliği için framework belgelerine bakın.

 Örneğin, gereksiz bir yönteme eklediğimiz varsayın `CheckingAccount` adlı sınıfı `AddIntegerHelper`. `AddIntegerHelper` iki tamsayının ekler.

 Veri temelli bir test için oluşturmak için `AddIntegerHelper` yöntemi, önce oluşturduğumuz adında bir Access veritabanı `AccountsTest.accdb` ve adlı bir tablo `AddIntegerHelperData`. `AddIntegerHelperData` Tabloyu tanımlayan eklenmesi birinci ve ikinci işlenenleri belirtmek için sütunlar ve beklenen sonucu belirtmek için bir sütun. Biz satır sayısını uygun değerlerle doldurun.

```csharp
[DataSource(
    @"Provider=Microsoft.ACE.OLEDB.12.0;Data Source=C:\Projects\MyBank\TestData\AccountsTest.accdb",
    "AddIntegerHelperData"
)]
[TestMethod()]
public void AddIntegerHelper_DataDrivenValues_AllShouldPass()
{
    var target = new CheckingAccount();
    int x = Convert.ToInt32(TestContext.DataRow["FirstNumber"]);
    int y = Convert.ToInt32(TestContext.DataRow["SecondNumber"]);
    int expected = Convert.ToInt32(TestContext.DataRow["Sum"]);
    int actual = target.AddIntegerHelper(x, y);
    Assert.AreEqual(expected, actual);
}
```

Öznitelikli yöntemi, tablodaki her satır için bir kez çalışır. Herhangi bir yineleme başarısız olursa test Gezgini yöntemi için bir test hata bildirir. Test sonuçları ayrıntılar bölmesine yöntemi her veri satırının geçişi/başarısız durumu yöntemi gösterir.

 Daha fazla bilgi edinmek [veri temelli birim testleri](../test/how-to-create-a-data-driven-unit-test.md).

 **S: ne kadar kodumu tarafından my birim testleri test görüntülemek?**

 **Y:** Evet. Visual Studio kod kapsamı aracını kullanarak, birim testleri tarafından gerçekten sınanan kodunuzu miktarını belirleyebilir. Yerel ve yönetilen dilleri ve Birim Test çerçevesi tarafından çalıştırılabilir tüm birim test çerçevelerini desteklenir.

 Kod kapsamı seçili testleri ya da bir çözümde tüm testleri çalıştırabilirsiniz. Kod Kapsamı Sonuçları penceresi satır, işlev, sınıf, ad alanı ve modülü tarafından kullanılabilecek ürün kod bloklarını yüzdesini görüntüler.

 Bir çözümde test yöntemleri için kod kapsamı çalıştırmak için tercih **testleri** Visual Studio menüsünde ve ardından **kod kapsamını çözümleme**.

 Kapsamı sonuçları kod kapsamı Sonuçları penceresinde görünür.

 ![Kod kapsamı sonuçları](../test/media/ute_codecoverageresults.png)

 Daha fazla bilgi edinmek [kod kapsamı](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md) .

 **S: nasıl ı yöntemleri dış bağımlılıkları olan kodumda test edebilirim?**

 **Y:** Evet. Visual Studio Enterprise varsa, Microsoft Fakes ile yönetilen kod için birim test çerçevelerini kullanarak yazma test yöntemleri kullanılabilir.

 Microsoft Fakes dış bağımlılıkları için alternatif sınıfları oluşturmak için iki yaklaşım kullanır:

1.  *Saplamalar* hedef bağımlılık sınıf üst arabiriminden türetilmiş ikame sınıfları oluşturur. Saplama yöntemleri için hedef sınıf ortak sanal yöntemleri yerine.

2.  *Dolgular* sanal olmayan yöntemler için bir yedek dolgusu yöntemi hedef yönteme çağrıları yönlendir için çalışma zamanı Araçları'nı kullanın.

Her iki yaklaşım, bağımlılık yöntemine yönelik çağrılar oluşturulan temsilcileri test yönteminde istediğiniz davranışı belirtmek için kullanın.

Daha fazla bilgi edinmek [birim test yöntemleri Microsoft Fakes ile yalıtma](../test/isolating-code-under-test-with-microsoft-fakes.md).

 **S: diğer birim test çerçevelerini birim testleri oluşturmak için kullanabilir miyim?**

 **Y:** Evet, şu adımları izleyin [bulma ve diğer çerçeveler yükleme](../test/install-third-party-unit-test-frameworks.md). Visual Studio yeniden başlattıktan sonra birim testleri oluşturmak için çözümü kapatıp yeniden açın ve yüklü çerçeveleri aşağıda seçin:

 ![Diğer yüklü birim test çerçevesi seçin](../test/media/createunittestsdialogextensions.png)

 Birim testi saplamalar seçili framework kullanılarak oluşturulur.
